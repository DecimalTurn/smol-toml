# Changes from upstream smol-toml bench

This fork (`toml-patch-bench2`) modifies the smol-toml benchmark suite to focus on comparing **toml-patch versions** rather than competing TOML libraries.

## Summary of changes

### 1. Replaced competitor libraries with toml-patch versions

**Upstream** benchmarks smol-toml against `@iarna/toml`, `@ltd/j-toml`, `@std/toml`, `js-toml`, and a single `@decimalturn/toml-patch`.

**Fork** benchmarks smol-toml against 4 toml-patch variants:

| Package alias | Resolves to | Purpose |
|---|---|---|
| `@decimalturn/toml-patch-local` | `file:../../` | Current dev build |
| `@decimalturn/toml-patch-v3.0.2` | `npm:@decimalturn/toml-patch@3.0.2` | Latest release |
| `@decimalturn/toml-patch-v2.1.0` | `npm:@decimalturn/toml-patch@2.1.0` | Previous release |
| `@decimalturn/toml-patch-v2.0.0` | `npm:@decimalturn/toml-patch@2.0.0` | Baseline (matches README numbers) |

The original competitor imports (`@iarna/toml`, etc.) remain in `package.json` but are no longer imported in the bench files.

### 2. JIT warmup

Added a warmup phase before benchmarks that calls each function 50× on the spec document:

```ts
const stringifiers = [smolTomlStringify, localTomlPatchStringify, ...]
for (const fn of stringifiers) {
  for (let i = 0; i < 50; i++) {
    try { fn(tomlSpec) } catch { /* ignore */ }
  }
}
await new Promise(r => setTimeout(r, 50))
```

This reduces (but doesn't eliminate) JIT warmup artifacts. Applied to both `parse.bench.ts` and `stringify.bench.ts`.

### 3. `BENCH_SPEC_ONLY` flag

Environment variable to skip the 5MB document and only benchmark the spec document:

```powershell
$env:BENCH_SPEC_ONLY=1; pnpm bench
```

The 5MB file takes ~2-4 seconds per toml-patch version vs microseconds for the spec doc. This flag makes quick iteration practical.

### 4. Vitest config

Added `vitest.config.ts` at the smol-toml root to run bench files:

```ts
export default defineConfig({
  test: { include: ['bench/**/*.bench.ts'] },
})
```

Added `"bench"` and `"bench:spec"` scripts to smol-toml's `package.json`. This replaces the upstream approach of running `tsx bench/*.bench.ts` directly.

### 5. Local package junction

On Windows, `pnpm install` creates a junction for `file:../../` that points to pnpm's virtual store (without `dist/`). After each install, the junction must be recreated to point directly at the toml-patch project root:

```powershell
New-Item -ItemType Junction -Path bench\node_modules\@decimalturn\toml-patch-local `
  -Target C:\Users\...\toml-patch
```

### 6. Order sensitivity note

Benchmark order matters significantly due to V8 JIT inline cache sensitivity. The current order is smol-toml-first (matching upstream convention). Reversing the order (v2.x first) can show v2.x ~2.3× faster than when smol-toml runs first.

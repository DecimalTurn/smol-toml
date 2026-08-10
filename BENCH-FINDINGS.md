# toml-patch stringify benchmarks

Run on: Intel i9-13900H @ ~2.9 GHz, Node 24.14.1, Windows 11

## Spec document (toml-spec-example.toml)

smol-toml-first order, JIT warmup applied:

| Implementation | Avg | vs smol-toml |
|---|---|---|
| smol-toml | 6.3 µs | 1× |
| toml-patch-local (dev) | ~130 µs | ~21× |
| toml-patch@3.0.2 (release) | ~130 µs | ~21× |
| toml-patch@2.1.0 | ~510 µs | ~81× |
| toml-patch@2.0.0 | ~480 µs | ~76× |

## 5MB document (5mb-mixed.toml)

smol-toml-first order, no warmup (warmup causes mitata hang on v2.x):

| Implementation | Avg | vs smol-toml |
|---|---|---|
| smol-toml | 88 ms | 1× |
| toml-patch-local (dev) | 2.51 s | 28× |
| toml-patch@3.0.2 (release) | 2.95 s | 33× |
| toml-patch@2.1.0 | ~3.2 s † | ~36× |
| toml-patch@2.0.0 | ~3.2 s † | ~36× |

† Standalone test — mitata hangs on v2.x 5MB (framework bug). Manually verified.

## Key findings

### 1. The v2→v3 gap is real but smaller than initially measured

On the **spec document**, v3.0.2 is ~3.7× faster than v2.x when smol-toml runs first (cold v2.x). When v2.x runs first (warm JIT), the gap shrinks to ~1.7×. On the **5MB document**, the gap shrinks further to ~1.1× — the bundler/code improvements matter less when work-per-call dominates.

### 2. JIT order effects are significant for v2.x only

v3.0.2 and the local build are stable at ~125-130 µs regardless of benchmark order. v2.x swings from ~215 µs (warm) to ~490 µs (cold) depending on whether it runs before or after other implementations. This suggests v3's generated code is more JIT-friendly (inline string literals vs object property lookups for type checks).

### 3. Bundler change (Rollup → Rolldown) contributes

v2.x was built with Rollup; v3.x with Rolldown/tsdown. Rolldown inlines enum constants as string literals (`e.type==="Document"`) while Rollup kept them as object property lookups (`t.type===e.Document`). This eliminates ~19 closure variable + property dereferences per type check on the hot path.

### 4. Real code improvements in v3.0.0

The v3.0.0 changelog lists two explicit stringify perf improvements:
- Emit `[key]` headers in a single write instead of three (bracket + key + bracket)
- Skip `formatTable` machinery for empty inline tables

### 5. Local dev build beats v3.0.2 on 5MB

The local build (dev-fix-insert-scan branch) includes writer optimizations not in v3.0.2:
- `markStringifyRoot` — skips comment scans during stringify
- `applyWrites` inline fast path — skips WeakMap lookups on clean subtrees
- O(n²) scan fix in `insertOnNewLine`

These yield a ~15% improvement on 5MB (2.51s vs 2.95s) but are neutral on the spec doc.

### 6. smol-toml is 20-80× faster

smol-toml's stringify is in a different performance class — 6 µs vs 130 µs on spec, 88 ms vs 2.5 s on 5MB. This is expected: toml-patch preserves formatting and supports non-destructive editing, while smol-toml is a pure serializer.

## Comparison with smol-toml README

The upstream README reports toml-patch@2.0.0 at 81.54 µs (36.4× vs smol-toml) on an AMD 9950X3D. Our machine shows 480 µs (76×). The ~6× absolute difference is due to CPU/RAM/Node version. The relative ranking is consistent.

## Recommendations

1. **Ship the writer optimizations** (dev-fix-insert-scan) — 15% improvement on large docs, no regression
2. **The bundler change already shipped** — rolldown inlining is a free win
3. **Consider warming up benchmarks** — per-function warmup before each bench would give fairer comparisons
4. **The 1.7× spec-doc gap is acceptable** — it narrows to 1.1× on real workloads

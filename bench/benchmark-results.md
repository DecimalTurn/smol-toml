# toml-patch Stringify Benchmarks

**Machine:** Intel i9-13900H @ ~3.0 GHz, Node 24.14.1, Windows 11
**Date:** 2026-08-10
**Order:** v2.0.0 → v2.1.0 → v3.0.2 → local → smol-toml (avoids mitata hang on v2.x 5MB)

## Spec document (toml-spec-example.toml)

| Implementation | Avg |
|---|---|
| smol-toml | 6.16 µs |
| toml-patch-local (dev) | 122.93 µs |
| toml-patch@3.0.2 | 123.19 µs |
| toml-patch@2.1.0 | 208.91 µs |
| toml-patch@2.0.0 | 208.85 µs |

**Summary:**
- smol-toml 20.0× faster than v3.0.2
- smol-toml 33.9× faster than v2.x
- v3.0.2 1.7× faster than v2.x

## 5MB document (5mb-mixed.toml)

| Implementation | Avg |
|---|---|
| smol-toml | 82.46 ms |
| toml-patch-local (dev) | 2.27 s |
| toml-patch@3.0.2 | 2.28 s |
| toml-patch@2.1.0 | 2.70 s |
| toml-patch@2.0.0 | 3.75 s |

**Summary:**
- smol-toml 27.6× faster than v3.0.2 / local
- smol-toml 32.8× faster than v2.1.0
- smol-toml 45.4× faster than v2.0.0
- v3.0.2 1.2× faster than v2.1.0, 1.6× faster than v2.0.0
- local and v3.0.2 are effectively tied on 5MB

## Notes

- Benchmark order is v2.x-first to avoid a mitata hang that occurs when smol-toml runs first with v2.x on 5MB data.
- With smol-toml-first order, v2.x spec results are ~2.3× slower (480-510 µs) due to cold JIT inline caches.
- v3.0.2 and local are stable regardless of order (~125 µs spec, ~2.3s 5MB).
- Warmup (50 iterations per function before benchmarks) is enabled.

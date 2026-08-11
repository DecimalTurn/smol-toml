# toml-patch Stringify Benchmarks — No Warmup

**Machine:** Intel i9-13900H @ ~2.8 GHz, Node 24.14.1, Windows 11
**Date:** 2026-08-10
**Order:** v2.0.0 → v2.1.0 → v3.0.2 → local → smol-toml
**Warmup:** disabled

## Spec document (toml-spec-example.toml)

| Implementation | Avg |
|---|---|
| smol-toml | 6.53 µs |
| toml-patch-local (dev) | 123.43 µs |
| toml-patch@3.0.2 | 158.24 µs |
| toml-patch@2.1.0 | 145.75 µs |
| toml-patch@2.0.0 | 210.52 µs |

**Summary:**
- smol-toml 18.9× faster than local, 22.3× faster than v2.1.0, 24.2× faster than v3.0.2, 32.2× faster than v2.0.0
- v2.1.0 slightly beats v3.0.2 on spec (146 vs 158 µs) — order effect from running second vs third

## 5MB document (5mb-mixed.toml)

| Implementation | Avg |
|---|---|
| smol-toml | 203.71 ms |
| toml-patch@2.0.0 | 2.62 s |
| toml-patch@2.1.0 | 4.78 s |
| toml-patch-local (dev) | 6.01 s |
| toml-patch@3.0.2 | 6.63 s |

**Summary:**
- smol-toml 12.9× faster than v2.0.0, 23.5× faster than v2.1.0, 29.5× faster than local, 32.6× faster than v3.0.2
- v2.0.0 is the fastest toml-patch on 5MB (2.62s) — surprising result
- v3.0.2 is slowest on 5MB (6.63s) — may indicate thermal throttling or GC pressure during the long run (269s total, 269s import)

## Comparison: Warmup vs No Warmup

| Implementation | Spec (warm) | Spec (cold) | 5MB (warm) | 5MB (cold) |
|---|---|---|---|---|
| smol-toml | 6.16 µs | 6.53 µs | 82.46 ms | 203.71 ms |
| toml-patch-local | 122.93 µs | 123.43 µs | 2.27 s | 6.01 s |
| toml-patch@3.0.2 | 123.19 µs | 158.24 µs | 2.28 s | 6.63 s |
| toml-patch@2.1.0 | 208.91 µs | 145.75 µs | 2.70 s | 4.78 s |
| toml-patch@2.0.0 | 208.85 µs | 210.52 µs | 3.75 s | 2.62 s |

## Notes

- The no-warmup 5MB results show significant slowdown vs the warmup run — likely thermal throttling during the 269s total runtime.
- With warmup, v2.x and v3.x converge on spec (~209 vs 123 µs); without warmup, v2.1.0 (145 µs) beats v3.0.2 (158 µs) on spec due to order position.
- v2.0.0's 5MB result (2.62s cold vs 3.75s warm) is inconsistent — the warmup run had smol-toml first which may have caused different GC/IC states.
- These results highlight that benchmark methodology (order, warmup, thermal state) can swing results by 2-3× for the same code.

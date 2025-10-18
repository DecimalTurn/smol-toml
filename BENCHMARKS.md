# Benchmarks - 2025-10-18T17:26:50+00:00

```text

> smol-toml@1.4.2 bench
> vitest bench

Benchmarking is an experimental feature.
Breaking changes might not follow SemVer, please pin Vitest's version when using it.

 DEV  v3.2.4 /workspaces/smol-toml


 ✓ bench/stringifyLargeMixed.bench.ts 159148ms
     name                          hz       min       max      mean       p75       p99      p995      p999      rme  samples
   · smol-toml                10.0224   85.4651    138.28   99.7768    118.12    138.28    138.28    138.28  ±15.25%       10
   · @iarna/toml               2.9355    294.26    377.30    340.66    365.99    377.30    377.30    377.30   ±5.59%       10
   · @ltd/j-toml               0.6481  1,435.72  1,671.58  1,542.90  1,574.73  1,671.58  1,671.58  1,671.58   ±3.17%       10
   · @decimalturn/toml-patch   0.1354  7,169.56  7,572.23  7,385.88  7,496.75  7,572.23  7,572.23  7,572.23   ±1.31%       10

 ✓ bench/stringifyLargeMixed.bench.ts 159148ms
     name                          hz       min       max      mean       p75       p99      p995      p999      rme  samples
   · smol-toml                10.0224   85.4651    138.28   99.7768    118.12    138.28    138.28    138.28  ±15.25%       10
   · @iarna/toml               2.9355    294.26    377.30    340.66    365.99    377.30    377.30    377.30   ±5.59%       10
   · @ltd/j-toml               0.6481  1,435.72  1,671.58  1,542.90  1,574.73  1,671.58  1,671.58  1,671.58   ±3.17%       10
   · @decimalturn/toml-patch   0.1354  7,169.56  7,572.23  7,385.88  7,496.75  7,572.23  7,572.23  7,572.23   ±1.31%       10

 ✓ bench/parseSpecExample.bench.ts 3097ms
     name                            hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml                64,055.67  0.0145  0.3111  0.0156  0.0149  0.0304  0.0337  0.1322  ±0.44%    32028
   · @iarna/toml              31,794.37  0.0265  0.5115  0.0315  0.0278  0.0827  0.0999  0.1984  ±0.76%    15898
   · @ltd/j-toml              15,667.64  0.0546  2.4470  0.0638  0.0604  0.1360  0.1694  0.8347  ±1.98%     7834
   · @decimalturn/toml-patch  11,993.33  0.0620  2.5471  0.0834  0.0733  0.2595  0.2908  0.9955  ±2.18%     5997
   · fast-toml                43,677.40  0.0204  0.3813  0.0229  0.0208  0.0484  0.0527  0.1441  ±0.50%    21839

 ✓ bench/parseSpecExample.bench.ts 3097ms
     name                            hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml                64,055.67  0.0145  0.3111  0.0156  0.0149  0.0304  0.0337  0.1322  ±0.44%    32028
   · @iarna/toml              31,794.37  0.0265  0.5115  0.0315  0.0278  0.0827  0.0999  0.1984  ±0.76%    15898
   · @ltd/j-toml              15,667.64  0.0546  2.4470  0.0638  0.0604  0.1360  0.1694  0.8347  ±1.98%     7834
   · @decimalturn/toml-patch  11,993.33  0.0620  2.5471  0.0834  0.0733  0.2595  0.2908  0.9955  ±2.18%     5997
   · fast-toml                43,677.40  0.0204  0.3813  0.0229  0.0208  0.0484  0.0527  0.1441  ±0.50%    21839

 ✓ bench/stringifySpecExample.bench.ts 2531ms
     name                             hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml                150,348.78  0.0060  0.3046  0.0067  0.0062  0.0132  0.0164  0.0517  ±0.46%    75176
   · @iarna/toml               33,999.73  0.0199  2.5972  0.0294  0.0391  0.0691  0.0845  0.3174  ±2.16%    17001
   · @ltd/j-toml                4,675.29  0.1790  2.0599  0.2139  0.2029  0.4663  0.4839  0.6922  ±1.46%     2338
   · @decimalturn/toml-patch    4,337.78  0.1692  4.6254  0.2305  0.2087  0.4996  0.5905  2.2308  ±2.83%     2169

 ✓ bench/stringifySpecExample.bench.ts 2531ms
     name                             hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml                150,348.78  0.0060  0.3046  0.0067  0.0062  0.0132  0.0164  0.0517  ±0.46%    75176
   · @iarna/toml               33,999.73  0.0199  2.5972  0.0294  0.0391  0.0691  0.0845  0.3174  ±2.16%    17001
   · @ltd/j-toml                4,675.29  0.1790  2.0599  0.2139  0.2029  0.4663  0.4839  0.6922  ±1.46%     2338
   · @decimalturn/toml-patch    4,337.78  0.1692  4.6254  0.2305  0.2087  0.4996  0.5905  2.2308  ±2.83%     2169

 BENCH  Summary

  smol-toml - bench/parseLargeMixed.bench.ts
    1.45x faster than @ltd/j-toml
    NaNx faster than @decimalturn/toml-patch
    1.06x faster than fast-toml

  smol-toml - bench/parseSpecExample.bench.ts
    1.47x faster than fast-toml
    2.01x faster than @iarna/toml
    4.09x faster than @ltd/j-toml
    5.34x faster than @decimalturn/toml-patch

  smol-toml - bench/stringifyLargeMixed.bench.ts
    3.41x faster than @iarna/toml
    15.46x faster than @ltd/j-toml
    74.02x faster than @decimalturn/toml-patch

  smol-toml - bench/stringifySpecExample.bench.ts
    4.42x faster than @iarna/toml
    32.16x faster than @ltd/j-toml
    34.66x faster than @decimalturn/toml-patch

 PASS  Waiting for file changes...
       press h to show help, press q to quit

```

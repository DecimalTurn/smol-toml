# Benchmarks - 2025-10-18T18:32:59+00:00

```text

> smol-toml@1.4.2 bench
> vitest bench

Benchmarking is an experimental feature.
Breaking changes might not follow SemVer, please pin Vitest's version when using it.

 DEV  v3.2.4 /workspaces/smol-toml


 ✓ bench/stringifyLargeMixed.bench.ts 174348ms
     name             hz       min       max      mean       p75       p99      p995      p999      rme  samples
   · smol-toml    9.9930   88.7490    146.27    100.07    103.11    146.27    146.27    146.27  ±12.92%       10
   · @iarna/toml  2.8203    292.11    471.19    354.57    404.69    471.19    471.19    471.19  ±11.38%       10
   · @ltd/j-toml  0.6874  1,352.68  1,599.39  1,454.79  1,552.14  1,599.39  1,599.39  1,599.39   ±4.46%       10
   · toml-patch1  0.2726  3,508.58  3,827.69  3,668.00  3,736.90  3,827.69  3,827.69  3,827.69   ±1.86%       10
   · toml-patch2  0.2985  3,108.11  3,655.23  3,349.94  3,417.85  3,655.23  3,655.23  3,655.23   ±3.44%       10

 ✓ bench/stringifyLargeMixed.bench.ts 174348ms
     name             hz       min       max      mean       p75       p99      p995      p999      rme  samples
   · smol-toml    9.9930   88.7490    146.27    100.07    103.11    146.27    146.27    146.27  ±12.92%       10
   · @iarna/toml  2.8203    292.11    471.19    354.57    404.69    471.19    471.19    471.19  ±11.38%       10
   · @ltd/j-toml  0.6874  1,352.68  1,599.39  1,454.79  1,552.14  1,599.39  1,599.39  1,599.39   ±4.46%       10
   · toml-patch1  0.2726  3,508.58  3,827.69  3,668.00  3,736.90  3,827.69  3,827.69  3,827.69   ±1.86%       10
   · toml-patch2  0.2985  3,108.11  3,655.23  3,349.94  3,417.85  3,655.23  3,655.23  3,655.23   ±3.44%       10

 ✓ bench/parseSpecExample.bench.ts 3715ms
     name                hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml    62,594.22  0.0146  0.3711  0.0160  0.0151  0.0316  0.0366  0.1484  ±0.54%    31298
   · @iarna/toml  33,798.46  0.0264  2.1466  0.0296  0.0274  0.0669  0.0817  0.1979  ±1.31%    16900
   · @ltd/j-toml  14,664.81  0.0549  2.6407  0.0682  0.0612  0.1587  0.2184  0.8877  ±2.38%     7333
   · toml-patch1  12,978.89  0.0588  2.7721  0.0770  0.0684  0.2498  0.2759  0.4205  ±2.17%     6490
   · toml-patch2  10,018.48  0.0662  5.3418  0.0998  0.1287  0.2675  0.3347  0.5623  ±3.07%     5010
   · fast-toml    38,533.75  0.0204  3.5757  0.0260  0.0211  0.0564  0.0677  0.2202  ±2.56%    19267

 ✓ bench/parseSpecExample.bench.ts 3715ms
     name                hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml    62,594.22  0.0146  0.3711  0.0160  0.0151  0.0316  0.0366  0.1484  ±0.54%    31298
   · @iarna/toml  33,798.46  0.0264  2.1466  0.0296  0.0274  0.0669  0.0817  0.1979  ±1.31%    16900
   · @ltd/j-toml  14,664.81  0.0549  2.6407  0.0682  0.0612  0.1587  0.2184  0.8877  ±2.38%     7333
   · toml-patch1  12,978.89  0.0588  2.7721  0.0770  0.0684  0.2498  0.2759  0.4205  ±2.17%     6490
   · toml-patch2  10,018.48  0.0662  5.3418  0.0998  0.1287  0.2675  0.3347  0.5623  ±3.07%     5010
   · fast-toml    38,533.75  0.0204  3.5757  0.0260  0.0211  0.0564  0.0677  0.2202  ±2.56%    19267

 ✓ bench/stringifySpecExample.bench.ts 3125ms
     name                 hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml    149,918.63  0.0059  0.9059  0.0067  0.0061  0.0135  0.0164  0.0459  ±0.59%    74961
   · @iarna/toml   37,677.02  0.0201  3.8878  0.0265  0.0210  0.0632  0.0848  0.2892  ±3.13%    18843
   · @ltd/j-toml    3,519.01  0.1789  2.7397  0.2842  0.3560  0.7727  1.2068  2.1930  ±2.69%     1760
   · toml-patch1    4,471.38  0.1635  2.5681  0.2236  0.2022  0.5338  0.6763  2.5301  ±2.49%     2236
   · toml-patch2    4,106.66  0.1697  2.5521  0.2435  0.2802  0.6478  0.6867  1.1367  ±2.19%     2054

 ✓ bench/stringifySpecExample.bench.ts 3125ms
     name                 hz     min     max    mean     p75     p99    p995    p999     rme  samples
   · smol-toml    149,918.63  0.0059  0.9059  0.0067  0.0061  0.0135  0.0164  0.0459  ±0.59%    74961
   · @iarna/toml   37,677.02  0.0201  3.8878  0.0265  0.0210  0.0632  0.0848  0.2892  ±3.13%    18843
   · @ltd/j-toml    3,519.01  0.1789  2.7397  0.2842  0.3560  0.7727  1.2068  2.1930  ±2.69%     1760
   · toml-patch1    4,471.38  0.1635  2.5681  0.2236  0.2022  0.5338  0.6763  2.5301  ±2.49%     2236
   · toml-patch2    4,106.66  0.1697  2.5521  0.2435  0.2802  0.6478  0.6867  1.1367  ±2.19%     2054

 BENCH  Summary

  smol-toml - bench/parseLargeMixed.bench.ts
    1.41x faster than @ltd/j-toml
    NaNx faster than toml-patch1
    NaNx faster than toml-patch2
    0.99x faster than fast-toml

  smol-toml - bench/parseSpecExample.bench.ts
    1.62x faster than fast-toml
    1.85x faster than @iarna/toml
    4.27x faster than @ltd/j-toml
    4.82x faster than toml-patch1
    6.25x faster than toml-patch2

  smol-toml - bench/stringifyLargeMixed.bench.ts
    3.54x faster than @iarna/toml
    14.54x faster than @ltd/j-toml
    33.48x faster than toml-patch2
    36.65x faster than toml-patch1

  smol-toml - bench/stringifySpecExample.bench.ts
    3.98x faster than @iarna/toml
    33.53x faster than toml-patch1
    36.51x faster than toml-patch2
    42.60x faster than @ltd/j-toml

 PASS  Waiting for file changes...
       press h to show help, press q to quit

```

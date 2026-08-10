# Benchmark Results

## Parse Benchmark

[90mclk: ~2.96 GHz[0m
[90mcpu: AMD EPYC 7763 64-Core Processor[0m
[90mruntime: node 24.14.0 (x64-linux)[0m

benchmark                   avg (min … max) p75 / p99    (min … top 1%)
------------------------------------------- -------------------------------
• spec document
[90m------------------------------------------- -------------------------------[0m
smol-toml                    [1m[33m 18.16 µs[0m[1m/iter[0m [90m 16.07 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                       [90m([0m[36m13.54 µs[0m[90m … [0m[35m3.14 ms[0m[90m)[0m [90m 49.20 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m  1.51 kb[0m[90m … [0m[33m522.03 kb[0m[90m) [0m[33m 16.30 kb[0m [36m█▅▂[0m[33m▁[0m[35m▃▂▁▂▂▂▂▂▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@iarna/toml                  [1m[33m 45.71 µs[0m[1m/iter[0m [90m 49.96 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                       [90m([0m[36m29.45 µs[0m[90m … [0m[35m2.57 ms[0m[90m)[0m [90m140.03 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m696.00  b[0m[90m … [0m[33m597.40 kb[0m[90m) [0m[33m 28.16 kb[0m [36m█▅▂[0m[33m▂[0m[35m▃▂▂▂▃▂▂▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@ltd/j-toml                  [1m[33m 87.42 µs[0m[1m/iter[0m [90m 81.44 µs[0m [36m ▆█ [0m[33m [0m[35m                [0m
                      [90m([0m[36m59.52 µs[0m[90m … [0m[35m10.94 ms[0m[90m)[0m [90m188.26 µs[0m [36m ██ [0m[33m [0m[35m                [0m
                    [90m([0m[33m688.00  b[0m[90m … [0m[33m  1.03 mb[0m[90m) [0m[33m 32.20 kb[0m [36m▃██▃[0m[33m▂[0m[35m▃▂▂▃▃▃▃▂▂▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

fast-toml                    [1m[33m 29.37 µs[0m[1m/iter[0m [90m 23.50 µs[0m [36m█ [0m[33m [0m[35m                  [0m
                       [90m([0m[36m21.70 µs[0m[90m … [0m[35m4.15 ms[0m[90m)[0m [90m 87.10 µs[0m [36m█ [0m[33m [0m[35m                  [0m
                    [90m([0m[33m368.00  b[0m[90m … [0m[33m  2.87 mb[0m[90m) [0m[33m 15.92 kb[0m [36m█▄[0m[33m▁[0m[35m▁▁▁▂▂▂▂▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

deno's @std/toml             [1m[33m 96.84 µs[0m[1m/iter[0m [90m120.47 µs[0m [36m█   [0m[33m [0m[35m                [0m
                       [90m([0m[36m56.06 µs[0m[90m … [0m[35m4.18 ms[0m[90m)[0m [90m241.82 µs[0m [36m█   [0m[33m [0m[35m                [0m
                    [90m([0m[33m  2.51 kb[0m[90m … [0m[33m  1.22 mb[0m[90m) [0m[33m 75.54 kb[0m [36m█▅▂▂[0m[33m▂[0m[35m▃▅▆▅▃▂▂▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

node-toml                    [1m[33m152.28 µs[0m[1m/iter[0m [90m173.24 µs[0m [36m█ [0m[33m [0m[35m                  [0m
                       [90m([0m[36m84.13 µs[0m[90m … [0m[35m4.15 ms[0m[90m)[0m [90m816.07 µs[0m [36m█ [0m[33m▂[0m[35m                  [0m
                    [90m([0m[33m  2.54 kb[0m[90m … [0m[33m  2.09 mb[0m[90m) [0m[33m121.81 kb[0m [36m█▆[0m[33m█[0m[35m█▃▂▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

js-toml                      [1m[33m144.68 µs[0m[1m/iter[0m [90m148.54 µs[0m [36m█[0m[33m [0m[35m                   [0m
                       [90m([0m[36m69.71 µs[0m[90m … [0m[35m5.44 ms[0m[90m)[0m [90m  1.27 ms[0m [36m█[0m[33m▆[0m[35m                   [0m
                    [90m([0m[33m728.00  b[0m[90m … [0m[33m  1.46 mb[0m[90m) [0m[33m106.45 kb[0m [36m█[0m[33m█[0m[35m▆▂▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@decimalturn/toml-patch      [1m[33m 78.14 µs[0m[1m/iter[0m [90m 83.78 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                       [90m([0m[36m48.18 µs[0m[90m … [0m[35m4.20 ms[0m[90m)[0m [90m254.17 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m744.00  b[0m[90m … [0m[33m  1.71 mb[0m[90m) [0m[33m 64.22 kb[0m [36m█▆▂[0m[33m▃[0m[35m▂▃▃▂▂▁▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

[1msummary[0m
  [1m[36msmol-toml[0m
   [32m1.62[0mx faster than [1m[36mfast-toml[0m
   [32m2.52[0mx faster than [1m[36m@iarna/toml[0m
   [32m4.3[0mx faster than [1m[36m@decimalturn/toml-patch[0m
   [32m4.81[0mx faster than [1m[36m@ltd/j-toml[0m
   [32m5.33[0mx faster than [1m[36mdeno's @std/toml[0m
   [32m7.97[0mx faster than [1m[36mjs-toml[0m
   [32m8.39[0mx faster than [1m[36mnode-toml[0m

• 5MB document
[90m------------------------------------------- -------------------------------[0m
smol-toml                    [1m[33m347.77 ms[0m[1m/iter[0m [90m376.52 ms[0m [36m         █ [0m[33m [0m[35m         [0m
                    [90m([0m[36m266.84 ms[0m[90m … [0m[35m428.62 ms[0m[90m)[0m [90m411.34 ms[0m [36m▅  ▅  ▅▅ █ [0m[33m [0m[35m▅▅ ▅▅   ▅[0m
                    [90m([0m[33m 24.35 mb[0m[90m … [0m[33m 65.27 mb[0m[90m) [0m[33m 43.63 mb[0m [36m█▁▁█▁▁██▁█▁[0m[33m▁[0m[35m██▁██▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@iarna/toml                  [31merror:[0m Unexpected character in datetime, expected period (.), minus (-), plus (+) or Z at row 5, col 45, pos 569:
4: NfF6LuAerfn5mDPI7Cp 2qsrB4vGmJTyb5jNubOIBYYWrWlAsrw PX93S57gjb5GEhR8qOU5blDQmwfVJTA YvmJ9cE3cUZU NAJQgAbIdpZLhc4lOs4ZhMEWehhZqXCsVD1YP1vN2GEoM2WX''', 1986-05-27T18:36:13Z, -5460, "2ZAV3fYlb23hf7r7QoftVlicWE2iuwp", 4790.2253 ]
5> SzeC4Me8T = [ 5928.9340, 1991-04-28 19:24:24, 7807, -782.4516, 0b1000011111, "YvXRZKBGle9d51sqE90t8hP" ]
                                               ^
6: SLMvBirT.pmpX1D.9PivpfFBo = 2010-09-29



@ltd/j-toml                  [1m[33m639.45 ms[0m[1m/iter[0m [90m638.95 ms[0m [36m  █     [0m[33m█[0m[35m            [0m
                    [90m([0m[36m510.07 ms[0m[90m … [0m[35m841.70 ms[0m[90m)[0m [90m834.84 ms[0m [36m▅▅█▅  ▅▅[0m[33m█[0m[35m         ▅ ▅[0m
                    [90m([0m[33m  5.29 mb[0m[90m … [0m[33m 63.10 mb[0m[90m) [0m[33m 35.76 mb[0m [36m████▁▁██[0m[33m█[0m[35m▁▁▁▁▁▁▁▁▁█▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

fast-toml                    [1m[33m337.37 ms[0m[1m/iter[0m [90m334.55 ms[0m [36m         ██[0m[33m [0m[35m         [0m
                    [90m([0m[36m302.59 ms[0m[90m … [0m[35m410.33 ms[0m[90m)[0m [90m367.90 ms[0m [36m▅▅   ▅ ▅▅██[0m[33m [0m[35m    ▅   ▅[0m
                    [90m([0m[33m 12.20 mb[0m[90m … [0m[33m 56.21 mb[0m[90m) [0m[33m 26.55 mb[0m [36m██▁▁▁█▁████[0m[33m▁[0m[35m▁▁▁▁█▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

deno's @std/toml             [1m[33m   1.19 s[0m[1m/iter[0m [90m   1.27 s[0m [36m██  █   [0m[33m [0m[35m            [0m
                          [90m([0m[36m1.11 s[0m[90m … [0m[35m1.33 s[0m[90m)[0m [90m   1.32 s[0m [36m██▅ █▅  [0m[33m [0m[35m      ▅   ▅▅[0m
                    [90m([0m[33m150.93 mb[0m[90m … [0m[33m194.89 mb[0m[90m) [0m[33m186.15 mb[0m [36m███▁██▁▁[0m[33m▁[0m[35m▁▁▁▁▁▁█▁▁▁██[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

node-toml                    [1m[33m   1.35 s[0m[1m/iter[0m [90m   1.53 s[0m [36m           [0m[33m [0m[35m       █ [0m
                          [90m([0m[36m1.11 s[0m[90m … [0m[35m1.56 s[0m[90m)[0m [90m   1.56 s[0m [36m▅▅ ▅▅ ▅ ▅  [0m[33m [0m[35m▅   ▅  █▅[0m
                    [90m([0m[33m 27.62 mb[0m[90m … [0m[33m 85.54 mb[0m[90m) [0m[33m 47.91 mb[0m [36m██▁██▁█▁█▁▁[0m[33m▁[0m[35m█▁▁▁█▁▁██[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

js-toml                      [1m[33m   1.10 s[0m[1m/iter[0m [90m   1.22 s[0m [36m    █    [0m[33m [0m[35m           [0m
                       [90m([0m[36m910.98 ms[0m[90m … [0m[35m1.36 s[0m[90m)[0m [90m   1.32 s[0m [36m▅▅ ▅█ ▅ ▅[0m[33m [0m[35m  ▅  ▅  ▅ ▅[0m
                    [90m([0m[33m219.24 mb[0m[90m … [0m[33m280.40 mb[0m[90m) [0m[33m265.50 mb[0m [36m██▁██▁█▁█[0m[33m▁[0m[35m▁▁█▁▁█▁▁█▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@decimalturn/toml-patch      [1m[33m553.04 ms[0m[1m/iter[0m [90m545.98 ms[0m [36m█████████[0m[33m [0m[35m         ██[0m
                    [90m([0m[36m471.51 ms[0m[90m … [0m[35m748.83 ms[0m[90m)[0m [90m663.06 ms[0m [36m█████████[0m[33m [0m[35m         ██[0m
                    [90m([0m[33m 49.63 mb[0m[90m … [0m[33m 50.68 mb[0m[90m) [0m[33m 50.23 mb[0m [36m█████████[0m[33m▁[0m[35m▁▁▁▁▁▁▁▁▁██[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

[1msummary[0m
  [1m[36mfast-toml[0m
   [32m1.03[0mx faster than [1m[36msmol-toml[0m
   [32m1.64[0mx faster than [1m[36m@decimalturn/toml-patch[0m
   [32m1.9[0mx faster than [1m[36m@ltd/j-toml[0m
   [32m3.27[0mx faster than [1m[36mjs-toml[0m
   [32m3.53[0mx faster than [1m[36mdeno's @std/toml[0m
   [32m4.01[0mx faster than [1m[36mnode-toml[0m

## Stringify Benchmark

[90mclk: ~2.96 GHz[0m
[90mcpu: AMD EPYC 7763 64-Core Processor[0m
[90mruntime: node 24.14.0 (x64-linux)[0m

benchmark                   avg (min … max) p75 / p99    (min … top 1%)
------------------------------------------- -------------------------------
• spec document
[90m------------------------------------------- -------------------------------[0m
smol-toml                    [1m[33m  8.44 µs[0m[1m/iter[0m [90m  7.10 µs[0m [36m█ [0m[33m [0m[35m                  [0m
                        [90m([0m[36m6.64 µs[0m[90m … [0m[35m2.37 ms[0m[90m)[0m [90m 21.90 µs[0m [36m█ [0m[33m [0m[35m                  [0m
                    [90m([0m[33m  6.77 kb[0m[90m … [0m[33m584.60 kb[0m[90m) [0m[33m  7.51 kb[0m [36m██[0m[33m▂[0m[35m▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@iarna/toml                  [1m[33m 30.80 µs[0m[1m/iter[0m [90m 25.49 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                       [90m([0m[36m22.60 µs[0m[90m … [0m[35m2.87 ms[0m[90m)[0m [90m 79.60 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m  1.22 kb[0m[90m … [0m[33m549.52 kb[0m[90m) [0m[33m 28.57 kb[0m [36m██▂[0m[33m▁[0m[35m▁▁▂▂▂▂▂▂▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@ltd/j-toml                  [1m[33m294.91 µs[0m[1m/iter[0m [90m368.98 µs[0m [36m █[0m[33m [0m[35m                  [0m
                      [90m([0m[36m153.13 µs[0m[90m … [0m[35m3.66 ms[0m[90m)[0m [90m  1.43 ms[0m [36m▃█[0m[33m [0m[35m                  [0m
                    [90m([0m[33m  9.16 kb[0m[90m … [0m[33m549.25 kb[0m[90m) [0m[33m 42.68 kb[0m [36m██[0m[33m▂[0m[35m██▂▂▂▁▁▁▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

deno's @std/toml             [1m[33m 15.75 µs[0m[1m/iter[0m [90m 14.48 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                       [90m([0m[36m10.71 µs[0m[90m … [0m[35m2.58 ms[0m[90m)[0m [90m 45.52 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m864.00  b[0m[90m … [0m[33m  1.18 mb[0m[90m) [0m[33m 20.87 kb[0m [36m█▅▂[0m[33m▁[0m[35m▂▂▃▂▂▂▂▁▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

js-toml                      [1m[33m 11.88 µs[0m[1m/iter[0m [90m  9.90 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                        [90m([0m[36m8.94 µs[0m[90m … [0m[35m2.73 ms[0m[90m)[0m [90m 29.03 µs[0m [36m█▃ [0m[33m [0m[35m                 [0m
                    [90m([0m[33m192.00  b[0m[90m … [0m[33m  1.45 mb[0m[90m) [0m[33m 19.73 kb[0m [36m██▂[0m[33m▁[0m[35m▁▁▁▁▁▂▂▂▂▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@decimalturn/toml-patch      [1m[33m167.11 µs[0m[1m/iter[0m [90m161.96 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                      [90m([0m[36m119.60 µs[0m[90m … [0m[35m1.84 ms[0m[90m)[0m [90m472.50 µs[0m [36m█  [0m[33m [0m[35m                 [0m
                    [90m([0m[33m624.00  b[0m[90m … [0m[33m  1.18 mb[0m[90m) [0m[33m103.90 kb[0m [36m██▃[0m[33m▂[0m[35m▁▁▂▃▃▂▂▂▁▁▁▁▁▁▁▁▁[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

[1msummary[0m
  [1m[36msmol-toml[0m
   [32m1.41[0mx faster than [1m[36mjs-toml[0m
   [32m1.87[0mx faster than [1m[36mdeno's @std/toml[0m
   [32m3.65[0mx faster than [1m[36m@iarna/toml[0m
   [32m19.81[0mx faster than [1m[36m@decimalturn/toml-patch[0m
   [32m34.96[0mx faster than [1m[36m@ltd/j-toml[0m

• 5MB document
[90m------------------------------------------- -------------------------------[0m
smol-toml                    [1m[33m 92.49 ms[0m[1m/iter[0m [90m 99.55 ms[0m [36m █        [0m[33m [0m[35m          [0m
                     [90m([0m[36m72.37 ms[0m[90m … [0m[35m141.27 ms[0m[90m)[0m [90m111.27 ms[0m [36m▅█ ▅▅ ▅   [0m[33m [0m[35m ▅▅▅▅    ▅[0m
                    [90m([0m[33m 35.52 mb[0m[90m … [0m[33m 35.71 mb[0m[90m) [0m[33m 35.56 mb[0m [36m██▁██▁█▁▁▁[0m[33m▁[0m[35m▁████▁▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@iarna/toml                  [1m[33m349.14 ms[0m[1m/iter[0m [90m358.49 ms[0m [36m          [0m[33m [0m[35m █        [0m
                    [90m([0m[36m307.17 ms[0m[90m … [0m[35m397.36 ms[0m[90m)[0m [90m391.41 ms[0m [36m▅▅   ▅▅ ▅▅[0m[33m▅[0m[35m █  ▅    ▅[0m
                    [90m([0m[33m 45.65 mb[0m[90m … [0m[33m 50.56 mb[0m[90m) [0m[33m 49.57 mb[0m [36m██▁▁▁██▁██[0m[33m█[0m[35m▁█▁▁█▁▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@ltd/j-toml                  [1m[33m   1.79 s[0m[1m/iter[0m [90m   1.85 s[0m [36m        █ [0m[33m [0m[35m          [0m
                          [90m([0m[36m1.69 s[0m[90m … [0m[35m1.90 s[0m[90m)[0m [90m   1.90 s[0m [36m       ██ [0m[33m [0m[35m    █     [0m
                    [90m([0m[33m  1.96 mb[0m[90m … [0m[33m 59.59 mb[0m[90m) [0m[33m 16.35 mb[0m [36m██▁▁▁▁███▁[0m[33m▁[0m[35m▁▁▁▁█▁▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

deno's @std/toml             [1m[33m179.36 ms[0m[1m/iter[0m [90m180.94 ms[0m [36m   █   [0m[33m [0m[35m             [0m
                    [90m([0m[36m155.83 ms[0m[90m … [0m[35m237.10 ms[0m[90m)[0m [90m225.66 ms[0m [36m  ▅█   [0m[33m [0m[35m             [0m
                    [90m([0m[33m 16.85 mb[0m[90m … [0m[33m 84.02 mb[0m[90m) [0m[33m 27.75 mb[0m [36m▇▇██▁▁▁[0m[33m▇[0m[35m▁▁▁▁▁▇▁▁▁▁▁▁▇[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

js-toml                      [1m[33m268.49 ms[0m[1m/iter[0m [90m283.37 ms[0m [36m █  █   [0m[33m [0m[35m █          [0m
                    [90m([0m[36m233.85 ms[0m[90m … [0m[35m323.91 ms[0m[90m)[0m [90m317.69 ms[0m [36m▅█▅ █   [0m[33m [0m[35m █ ▅ ▅     ▅[0m
                    [90m([0m[33m  1.28 mb[0m[90m … [0m[33m 64.94 mb[0m[90m) [0m[33m 50.67 mb[0m [36m███▁█▁▁▁[0m[33m▁[0m[35m▁█▁█▁█▁▁▁▁▁█[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

@decimalturn/toml-patch      [1m[33m   2.82 s[0m[1m/iter[0m [90m   2.85 s[0m [36m    █     [0m[33m [0m[35m █        [0m
                          [90m([0m[36m2.66 s[0m[90m … [0m[35m3.08 s[0m[90m)[0m [90m   2.97 s[0m [36m▅  ▅█ ▅ ▅▅[0m[33m [0m[35m █      ▅▅[0m
                    [90m([0m[33m119.33 mb[0m[90m … [0m[33m142.59 mb[0m[90m) [0m[33m121.84 mb[0m [36m█▁▁██▁█▁██[0m[33m▁[0m[35m▁█▁▁▁▁▁▁██[0m
                [1m[32m    NaN[0m[1m ipc[0m[90m ([0m[33m   NaN%[0m cache[90m)[0m [32m   0.00[0m branch misses
        [90m   0.00 cycles    0.00 instructions    0.00 c-refs    0.00 c-misses[0m

[1msummary[0m
  [1m[36msmol-toml[0m
   [32m1.94[0mx faster than [1m[36mdeno's @std/toml[0m
   [32m2.9[0mx faster than [1m[36mjs-toml[0m
   [32m3.77[0mx faster than [1m[36m@iarna/toml[0m
   [32m19.35[0mx faster than [1m[36m@ltd/j-toml[0m
   [32m30.49[0mx faster than [1m[36m@decimalturn/toml-patch[0m

# Results: 214 CUDA Memcpy Bandwidth Test (H2D, D2H, D2D)

**Main goal:** Measure H2D/D2H/D2D transfer bandwidth  
**Tools:** Compile cuda_memcpy.cu with nvcc; run bin/cuda_memcpy for H2D, D2H, D2D, and H2D_pageable

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 80GB HBM3 (81559 MiB) · Intel(R) Xeon(R) Platinum 8470 · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 595.112.07
- **Run:** 2026-11-22T10:57:08Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 00:31 · benchmark 00:35 · whole run 01:11
- **Source:** run 214_20261122_105708
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --direction all --pinned-memory true --min-bytes 1024 --max-bytes 268435456 --step-factor 2 --warmup-iters 1 --num-iterations 10`

| # | Metric | Result |
|---|---|---|
| 1 | H2D bandwidth at max transfer size, GB/s (bandwidth_h2d_gb_s) | 54.555225 |
| 2 | D2H bandwidth at max transfer size, GB/s (bandwidth_d2h_gb_s) | 55.40275 |
| 3 | D2D bandwidth at max transfer size, GB/s (bandwidth_d2d_gb_s) | 1498.554428 |
| 4 | H2D latency at min transfer size, us (latency_h2d_us) | 8.3328 |
| 5 | D2H latency at min transfer size, us (latency_d2h_us) | 7.7472 |
| 6 | D2D latency at min transfer size, us (latency_d2d_us) | 2.9312 |
| 7 | Pinned-over-pageable H2D bandwidth ratio (pinned_vs_pageable_bandwidth_ratio) | 7.112068291217756 |
<!-- /profile:smoke -->

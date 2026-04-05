**Tab. A.** FedRGL performance under Metis split.

| Dataset| Cora | Cora | Cora | CS | CS | CS | Physics | Physics | Physics |
|--------|------|------|------|----|----|----|---------|---------|---------|
| Method | Normal | Uniform | Pair | Normal | Uniform | Pair | Normal | Uniform | Pair |
| FedAvg   | 78.79±0.21    | 43.22±0.58     | 51.17±0.33   | 83.67±0.23    | 63.62±0.47     | 66.28±0.51  | 90.58±0.27       | 65.52±0.31        | 67.24±0.61     |
| FGSSL    | 79.11±0.34    | 47.35±0.40     | 51.45±0.60   | 86.02±0.35    | 65.29±0.51     | 66.83±0.78  | 90.33±0.39       | 71.72±0.66        | 72.27±0.85     |
| FedTAD   | 77.32±0.48    | 41.71±0.88     | 52.03±0.59   | 83.88±0.16    | 67.54±0.39     | 68.60±0.90  | 91.26±0.41       | 68.52±0.57        | 67.52±0.49     |
| FedSPA   | 77.35±0.45    | 42.84±0.67     | 49.82±0.73   | 84.28±0.35    | 63.65±0.56     | 63.67±1.32  | 89.73±0.38       | 65.40±0.66        | 69.51±0.57     |
| FedCorr  | 77.54±0.50    | 47.45±0.57     | 51.11±0.78   | 84.55±0.33    | 65.73±0.53     | 68.10±0.55  | 89.34±0.33       | 71.27±0.65        | 72.91±0.78     |
| FedNoro  | 79.92±0.39    | 41.38±0.68     | 45.38±0.91   | 78.21±0.30    | 53.49±0.46     | 58.79±0.58  | 89.17±0.59       | 54.29±0.77        | 52.17±0.84     |
| FedNed   | 76.30±0.33    | 46.20±0.63     | 52.22±0.67   | 84.62±0.46    | 65.37±0.40     | 64.36±0.54  | 90.02±0.38       | 65.63±0.56        | 69.79±0.64     |
| RHFL     | 77.52±0.28    | 46.39±0.47     | 48.79±0.88   | 85.53±0.50    | 54.29±0.68     | 56.61±0.77  | **91.46±0.20**       | 55.60±0.43        | 58.52±1.05     |
| CRGNN    | 79.25±0.61    | 56.42±0.63     | 58.45±0.77   | **86.54±0.53**| 75.31±0.72     | 72.03±0.91  | 89.77±0.32       | 78.57±0.69        | 77.39±0.60     |
| RTGNN    | 76.07±0.48    | 48.28±0.55     | 53.02±0.61   | 81.30±0.41    | 69.77±0.77     | 67.29±0.53  | 88.05±0.44       | 71.44±1.72        | 70.46±1.78     |
| DND-NET  | 78.55±0.70    | 52.44±0.94     | 51.72±1.33   | 85.35±0.48    | 72.49±1.35     | 67.34±0.85  | 88.36±0.62       | 76.39±0.78        | 71.36±0.99     |
| ERASE    | 72.82±0.46    | 48.03±0.52     | 49.82±0.65   | 84.22±0.36    | 70.66±0.86     | 68.46±0.92  | 89.40±0.58       | 73.55±0.63        | 68.55±0.80     |
| FedRGL   | **79.33±0.37**| **73.15±0.41** | **71.79±0.42**| 86.08±0.32   | **83.20±0.63** | **77.68±0.50** | 90.26±0.39       | **85.14±0.41**    | **83.42±0.65** |  

**Tab.B.** Per-client per-epoch training time and GPU memory usage for OGBN‑arxiv and OGBN‑products (seconds for time, GB for memory). Training configurations: single_view (single forward pass), dual_view_no_cl (two-view forward pass with pseudo-label prediction, contrastive-loss disabled), full (two-view with contrastive loss). In this work, we ran large-scale experiments using the dual_view_no_cl configuration on local subgraphs. Reported times and memory include only model forward pass, supervision, and pseudo-label prediction, excluding noise node filtering and global aggregation. Statistics are provided for multiple client counts under pair noise (0.4).

| Dataset         | Training Mode       | #Clients | Noise Type | Noise Rate | Avg Time (s) | Max Time (s) | Avg Peak Mem (GB) | Max Peak Mem (GB) |
|-----------------|-------------------|----------|------------|------------|--------------|--------------|-----------------|-----------------|
| OGBN-arxiv      | single_view        | 20       | pair       | 0.4        | 0.005273     | 0.013573     | 0.255247        | 0.312641        |
| OGBN-arxiv      | dual_view_no_cl    | 20       | pair       | 0.4        | 0.007659     | 0.022421     | 0.417646        | 0.483822        |
| OGBN-arxiv      | full               | 20       | pair       | 0.4        | 0.037562     | 0.048572     | 1.588015        | 1.944603        |
| OGBN-arxiv      | single_view        | 30       | pair       | 0.4        | 0.005236     | 0.016017     | 0.237133        | 0.290382        |
| OGBN-arxiv      | dual_view_no_cl    | 30       | pair       | 0.4        | 0.009401     | 0.032572     | 0.345574        | 0.405413        |
| OGBN-arxiv      | full               | 30       | pair       | 0.4        | 0.028642     | 0.044121     | 1.117883        | 1.121621        |
| OGBN-products   | single_view        | 40       | pair       | 0.4        | 0.037512     | 0.073223     | 4.305083        | 8.069542        |
| OGBN-products   | dual_view_no_cl    | 40       | pair       | 0.4        | 0.087293     | 0.149434     | 6.852625        | 10.01119        |
| OGBN-products   | full               | 40       | pair       | 0.4        | 0.534393     | 0.847719     | 21.48295        | 26.75273        |
| OGBN-products   | single_view        | 50       | pair       | 0.4        | 0.035286     | 0.062449     | 4.153792        | 7.172859        |
| OGBN-products   | dual_view_no_cl    | 50       | pair       | 0.4        | 0.076175     | 0.161852     | 6.181344        | 9.721092        |
| OGBN-products   | full               | 50       | pair       | 0.4        | 0.487724     | 0.819038     | 18.28653        | 24.87993        |  


**Tab.B1.** Definition of the profiling statistics used in Tab.B. Time is measured in seconds, peak memory in GB, and decomposed memory terms in MB.

| Column | Meaning |
|---|---|
| `Dataset` | Dataset used in profiling, i.e., `ogbn-arxiv` or `ogbn-products`. |
| `Training Mode` | Training configuration used for profiling: `single_view` (single forward pass), `dual_view_no_cl` (two-view forward with pseudo-label prediction, contrastive loss disabled), and `full` (two-view forward with contrastive loss enabled). |
| `#Clients` | Number of clients in the federated partition. |
| `Avg Time (s)` | Average per-client per-epoch training time. |
| `Max Time (s)` | Maximum per-client per-epoch training time among all clients. |
| `Avg Peak Mem (GB)` | Average peak GPU memory usage per client per epoch. |
| `Max Peak Mem (GB)` | Maximum peak GPU memory usage among all clients per epoch. |
| `Avg CL Inc (MB)` | Average additional memory associated with the contrastive-loss branch. This is nonzero only in the `full` setting. |
| `Max CL Inc (MB)` | Maximum additional memory associated with the contrastive-loss branch. |
| `Avg Feature (MB)` | Memory occupied by the node feature tensor of the original local subgraph. |
| `Avg Graph (MB)` | Memory occupied by the graph structure of the original local subgraph, such as edge indices or adjacency representation. |
| `Avg Aug X1 (MB)` | Memory occupied by the node features of the first augmented view. |
| `Avg Aug X2 (MB)` | Memory occupied by the node features of the second augmented view. |
| `Avg Aug E1 (MB)` | Memory occupied by the graph structure of the first augmented view. |
| `Avg Aug E2 (MB)` | Memory occupied by the graph structure of the second augmented view. |
| `Avg Aug Total (MB)` | Total memory occupied by the two augmented views, including both augmented node features and augmented graph structures. |
| `Avg Emb1 (MB)` | Memory footprint of the output representation or prediction tensor from the first view. |
| `Avg Emb2 (MB)` | Memory footprint of the output representation or prediction tensor from the second view. |
| `Avg Emb Total (MB)` | Total memory footprint of the outputs from the two views. |


**Tab.B.** Detailed profiling statistics on OGBN-arxiv and OGBN-products. Time is measured in seconds, peak memory in GB, and decomposed memory terms in MB. Training configurations include `single_view`, `dual_view_no_cl`, and `full`.

| Dataset | Training Mode | #Clients | Avg Time (s) | Max Time (s) | Avg Peak Mem (GB) | Max Peak Mem (GB) | Avg CL Inc (MB) | Max CL Inc (MB) | Avg Feature (MB) | Avg Graph (MB) | Avg Aug X1 (MB) | Avg Aug X2 (MB) | Avg Aug E1 (MB) | Avg Aug E2 (MB) | Avg Aug Total (MB) | Avg Emb1 (MB) | Avg Emb2 (MB) | Avg Emb Total (MB) |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| ogbn-arxiv | single_view | 20 | 0.026297 | 0.037390 | 0.257012 | 0.312730 | 0.000000 | 0.000000 | 4.134351 | 0.547827 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 1.291985 | 0.000000 | 1.291985 |
| ogbn-arxiv | dual_view_no_cl | 20 | 0.061733 | 0.103584 | 0.391315 | 0.452461 | 0.000000 | 0.000000 | 4.134351 | 0.547827 | 4.134351 | 4.134351 | 0.493065 | 0.383593 | 9.145360 | 8.268701 | 8.268701 | 16.537402 |
| ogbn-arxiv | full | 20 | 0.107479 | 0.154491 | 2.181101 | 2.185155 | 1163.182504 | 1165.511230 | 4.134351 | 0.547827 | 4.134351 | 4.134351 | 0.493065 | 0.383593 | 9.145360 | 8.268701 | 8.268701 | 16.537402 |
| ogbn-arxiv | single_view | 30 | 0.009542 | 0.012953 | 0.237752 | 0.290883 | 0.000000 | 0.000000 | 2.756234 | 0.301801 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.861323 | 0.000000 | 0.861323 |
| ogbn-arxiv | dual_view_no_cl | 30 | 0.013362 | 0.016636 | 0.327737 | 0.383397 | 0.000000 | 0.000000 | 2.756234 | 0.301801 | 2.756234 | 2.756234 | 0.271608 | 0.211344 | 5.995419 | 5.512467 | 5.512467 | 11.024935 |
| ogbn-arxiv | full | 30 | 0.033088 | 0.036003 | 1.113280 | 1.116016 | 532.728857 | 534.530273 | 2.756234 | 0.301801 | 2.756234 | 2.756234 | 0.271608 | 0.211344 | 5.995419 | 5.512467 | 5.512467 | 11.024935 |
| ogbn-products | single_view | 40 | 0.042180 | 0.076423 | 6.799004 | 11.063283 | 0.000000 | 0.000000 | 23.355761 | 33.007787 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 10.977207 | 0.000000 | 10.977207 |
| ogbn-products | dual_view_no_cl | 40 | 0.101767 | 0.193843 | 7.641119 | 12.530306 | 0.000000 | 0.000000 | 23.355761 | 33.007787 | 23.355761 | 23.355761 | 29.706714 | 23.105302 | 99.523537 | 59.790747 | 59.790747 | 119.581494 |
| ogbn-products | single_view | 50 | 0.033447 | 0.064263 | 5.530506 | 8.712912 | 0.000000 | 0.000000 | 18.684608 | 24.166058 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 0.000000 | 8.781766 | 0.000000 | 8.781766 |
| ogbn-products | dual_view_no_cl | 50 | 0.085347 | 0.154682 | 6.128679 | 9.444660 | 0.000000 | 0.000000 | 18.684608 | 24.166058 | 18.684608 | 18.684608 | 21.749480 | 16.916034 | 76.034731 | 47.832598 | 47.832598 | 95.665195 |
| ogbn-products | full | 50 | 2.538077 | 2.937716 | 65.845283 | 65.982554 | 36995.627186 | 37035.946777 | 18.684608 | 24.166058 | 18.684608 | 18.684608 | 21.749480 | 16.916034 | 76.034731 | 47.832598 | 47.832598 | 95.665195 |

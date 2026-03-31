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

# Tab.X. Per-client per-epoch training time and GPU memory usage on OGB‑arxiv (seconds for time, GB for memory). Training configurations: single_view (single forward pass), dual_view_no_cl (two-view forward pass with pseudo-label prediction, contrastive-loss disabled), full (two-view with contrastive loss). In this work, we ran large-scale experiments using the dual_view_no_cl configuration on local subgraphs. Reported times and memory include only model forward pass, supervision, and pseudo-label prediction, excluding noise node filtering and global aggregation. Statistics are provided for 20 and 30 clients under pair noise (0.4).

| Training Mode       | #Clients | Noise Type | Noise Rate | Avg Time (s) | Max Time (s) | Avg Peak Mem (GB) | Max Peak Mem (GB) |
|--------------------|----------|------------|------------|--------------|--------------|-----------------|-----------------|
| single_view         | 20       | pair       | 0.4        | 0.005273     | 0.013573     | 0.255247        | 0.312641        |
| dual_view_no_cl     | 20       | pair       | 0.4        | 0.007659     | 0.022421     | 0.417646        | 0.483822        |
| full                | 20       | pair       | 0.4        | 0.037562     | 0.048572     | 1.588015        | 1.944603        |
| single_view         | 30       | pair       | 0.4        | 0.005236     | 0.016017     | 0.237133        | 0.290382        |
| dual_view_no_cl     | 30       | pair       | 0.4        | 0.009401     | 0.032572     | 0.345574        | 0.405413        |
| full                | 30       | pair       | 0.4        | 0.028642     | 0.044121     | 1.117883        | 1.121621        |

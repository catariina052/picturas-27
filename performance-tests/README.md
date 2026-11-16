# Phase 2 - Media Upload Memory Performance Tests

## Objective
Evaluate memory usage before and after implementing disk-backed uploads and file streaming in PictuRAS.

## Test Environment
- Docker Compose
- Docker Stats for memory monitoring
- API Gateway, Projects Service, and Image Storage Service
- Video sizes: approximately 65 MB and 100 MB

## Results

### 65 MB Video

| Service | Baseline | Optimized Run 1 | Optimized Run 2 |
|---|---:|---:|---:|
| API Gateway | 266.3 MiB | 192.1 MiB | 172.5 MiB |
| Projects Service | 278.3 MiB | 215.3 MiB | 222.1 MiB |
| Image Storage Service | 182.3 MiB | 124.2 MiB | 122.0 MiB |

### 100 MB Video

| Service | Baseline | Optimized Run 1 |
|---|---:|---:|
| API Gateway | 351.6 MiB | 211.2 MiB |
| Projects Service | 269.0 MiB | 124.1 MiB |
| Image Storage Service | 241.5 MiB | 142.2 MiB |

## Validation
Both video sizes uploaded and played successfully.

## Evidence
- Five CSV files containing Docker memory measurements
- Two PNG graphs comparing baseline and optimized memory usage

## Limitations
Results are preliminary sampled peak-memory measurements.
The 65 MB test includes one baseline and two optimized runs.
The 100 MB test includes one baseline and one optimized run.
Further repetitions are recommended for stronger statistical confidence.

# MgBench
A new analytical benchmark for machine-generated log data.

## Data

1. **bench1:** http://cs.brown.edu/people/acrotty/mgbench/bench1.tar.gz
2. **bench2:** http://cs.brown.edu/people/acrotty/mgbench/bench2.tar.gz
3. **bench3:** http://cs.brown.edu/people/acrotty/mgbench/bench3.tar.gz

## Preliminary Results

All experiments were conducted on a `r5.12xlarge` EC2 instance (48 vCPU, 384 GiB memory).

### Benchmark 1

| System       | Load       | Q1        | Q2        | Q3        | Q4        | Q5        | Q6        |
| :----------- | :--------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| ClickHouse   | 35.811     | 0.019     | 0.046     | 0.065     | 0.035     | 0.058     | 0.047     |
| CrateDB      | 1088.347   | 0.013     | 0.011     | 0.023     | 0.015     | 1.387     | 0.337     |
| Druid        | 472.177    | 0.042     | N/A       | 0.061     | 0.032     | 0.134     | 0.137     |
| Hyper        | 32.561     | **0.004** | 0.003     | 0.024     | **0.003** | **0.009** | **0.035** |
| MonetDB      | 31.042     | 0.021     | 0.007     | 0.025     | 0.012     | 0.018     | 0.180     |
| PostgreSQL   | 133.738    | 0.879     | 0.766     | 0.958     | 0.868     | 1.198     | 2.574     |
|  +Index Time | 145.596    | 0.876     | 0.765     | 0.958     | 1.292     | 1.202     | 2.575     |
|  +Index All  | 403.432    | 0.129     | 0.005     | 0.047     | 0.563     | 1.501     | 0.457     |
| SparkSQL     | **14.812** | 0.106     | 0.081     | 0.213     | 0.109     | 0.259     | 0.282     |
| TimescaleDB  | 164.904    | 0.376     | 0.417     | 0.757     | 0.408     | 1.622     | 3.581     |
|  +Index All  | 375.263    | 0.010     | **0.001** | **0.015** | 0.071     | 1.341     | 0.188     |

### Benchmark 2

| System       | Load       | Q1        | Q2        | Q3        | Q4        | Q5        | Q6        |
| :----------- | :--------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| ClickHouse   | 32.006     | 0.032     | 0.116     | N/A       | 0.067     | 0.238     | **0.345** |
| CrateDB      | N/A        | 0.009     | 0.089     | 3.699     | 1.789     | 13.619    | 11.282    |
| Druid        | 1064.712   | 0.047     | 0.627     | N/A       | 3.147     | 2.865     | 0.964     |
| Hyper        | 26.421     | 0.049     | 0.056     | **0.051** | **0.061** | **0.208** | 0.390     |
| MonetDB      | 26.446     | 0.012     | **0.052** | 3.233     | 0.150     | 0.828     | 2.262     |
| PostgreSQL   | 145.774    | 1.123     | 1.866     | 2.019     | 2.044     | 54.801    | 17.835    |
|  +Index Time | 213.160    | 0.287     | 0.174     | 1.124     | 2.042     | 53.386    | 17.835    |
|  +Index All  | 610.496    | 0.281     | 2.172     | 4.099     | 2.043     | 53.389    | 17.834    |
| SparkSQL     | **16.936** | 0.449     | 0.249     | 3.264     | 0.511     | 0.974     | 1.078     |
| TimescaleDB  | 276.865    | 0.073     | 0.112     | 1.021     | 1.442     | 57.758    | 17.376    |
|  +Index All  | 522.875    | **0.001** | 0.117     | 1.017     | 1.447     | 57.694    | 17.374    |

### Benchmark 3

| System       | Load       | Q1        | Q2        | Q3        | Q4        | Q5        | Q6        |
| :----------- | :--------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| ClickHouse   | 66.872     | 0.026     | N/A       | N/A       | 0.071     | N/A       | 0.994     |
| CrateDB      |  |  |  |  |  |  |  |
| Druid        | 1207.445   | 0.041     | N/A       | N/A       | 0.061     | N/A       | 7.176     |
| Hyper        | 51.877     | 0.032     | **0.036** | **0.027** | **0.024** | **0.049** | **0.197** |
| MonetDB      | 34.871     | 0.104     | 4.099     | 0.042     | 0.043     | 0.081     | 18.873    |
| PostgreSQL   | 242.270    | 3.257     | 255.778   | 3.771     | 3.096     | 3.873     | 42.745    |
|  +Index Time | 310.320    | 0.127     | 254.876   | 3.803     | 3.095     | 3.891     | 42.744    |
|  +Index All  | 824.136    | 0.049     | 255.661   | 0.466     | 3.080     | 1.301     | 45.186    |
| SparkSQL     | **28.661** | 0.044     | N/A       | 0.511     | 0.141     | 1.563     | 2.055     |
| TimescaleDB  | 618.444    | 0.048     | 245.692   | 0.709     | 1.347     | 6.522     | 13.194    |
|  +Index All  | 961.328    | **0.001** | 242.173   | 0.078     | 0.088     | 0.821     | 13.199    |

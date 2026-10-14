# Mission 2 - Understand data

## Core vocabulary

- **Dataset:** the organised collection used for analysis or learning.
- **Sample / observation:** one recorded example in the dataset. In the table below, one design run is one observation.
- **Feature:** an input measurement used to describe an observation, such as cell count or average fanout.
- **Label / target:** the answer the model is asked to predict. For a supervised timing model, `timing_pass` is the target.
- **Labelled example:** an observation with a target answer.
- **Unlabelled example:** an observation with inputs but no supplied answer; it can still be used for clustering, anomaly detection, or later labelling.

A dataset can be **structured** (rows and named columns) or **unstructured** (waveforms, images, logs, or text). Features can be **numerical** (cell count, voltage) or **categorical** (process corner, library family). A categorical value may need an explicit encoding before a model can use it.

## Small synthetic dataset

The values below are illustrative, not measurements from a real chip. `timing_pass` is the target; the other columns are candidate features.

| run_id | cell_count_k | wirelength_mm | avg_fanout | voltage_v | temp_c | timing_pass |
|---|---:|---:|---:|---:|---:|---|
| R01 | 82 | 14.2 | 3.1 | 0.80 | 25 | yes |
| R02 | 95 | 16.8 | 3.8 | 0.80 | 25 | no |
| R03 | 77 | 13.1 | 2.9 | 0.85 | 0 | yes |
| R04 | 110 | 19.5 | 4.4 | 0.80 | 85 | no |
| R05 | 88 | 15.0 | 3.3 | 0.85 | 25 | yes |
| R06 | 101 | 17.7 | 4.0 | 0.75 | 25 | no |
| R07 | 73 | 12.4 | 2.7 | 0.85 | 0 | yes |
| R08 | 91 | 15.9 | 3.5 | 0.80 | 85 | no |

The row is the observation, `cell_count_k` through `temp_c` are features, and `timing_pass` is the target. If the target were absent, the same rows could be treated as unlabelled data for grouping similar design runs.

## Collection and preparation

An engineer should document how each value was produced: tool version, process corner, units, measurement conditions, and run identifier. Preparation may include removing duplicate runs, converting units consistently, detecting impossible values, handling missing values, and resolving inconsistent labels. Missing values can be imputed, represented with a missing indicator, or excluded when the reason for missingness makes the row unsafe to use. The choice should be recorded rather than hidden.

## Why more rows do not automatically mean better data

1. **Systematic bias:** one million samples from only a single process corner may not represent the corners used in deployment. A model can be precise for the observed corner and fail elsewhere.
2. **Noisy or inconsistent labels:** if two engineers label the same timing result differently, a larger dataset repeats the disagreement. The model then learns an unstable target instead of the engineering definition of pass.

Other risks include duplicate runs, measurements taken after the target was known, and features that are unavailable at prediction time. Data quality is about relevance, accuracy, coverage, and provenance, not only row count.

**Sources:** [S1], [S3], [S5] in [sources.md](sources.md).

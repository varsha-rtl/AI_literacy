# Mission 4 - Understand ML task types

A task type describes the requested output. It does not by itself specify whether training will be supervised, unsupervised, self-supervised, or reinforcement learning.

| Real-world problem | Task type | Likely input | Expected output | Possible learning approach |
|---|---|---|---|---|
| Decide whether a timing run meets the sign-off rule | Classification | Design features, corner, and operating conditions | `pass` or `fail` | Supervised |
| Estimate post-route critical-path delay | Regression | Netlist and physical-design measurements | A delay value in ns | Supervised |
| Group runs with similar congestion and power behaviour | Clustering | Vector of run metrics | Cluster assignment or group description | Unsupervised |
| Detect an unusual wafer sensor trace | Anomaly detection | Sensor time series and process context | Anomaly score and alert | Unsupervised or supervised if labelled failures exist |
| Summarise hundreds of correlated measurements for exploration | Dimensionality reduction | High-dimensional feature matrix | Two- or three-dimensional representation | Unsupervised or self-supervised |
| Rank candidate floorplans for engineer review | Recommendation / ranking | Candidate features, constraints, and past outcomes | Ordered list with scores | Supervised ranking or reinforcement learning |

Two semiconductor examples are included directly: timing pass/fail classification, delay regression, congestion or sensor anomaly detection, and floorplan ranking. The same problem can be addressed by multiple algorithms. For example, a classifier could be a decision tree, linear model, or neural network; the output task remains classification.

A task can also be reframed. If a team has no reliable labels for defects, it might begin with anomaly detection. After enough confirmed examples are collected, it could move to supervised defect classification. That change is about the available training signal, not a change in the underlying engineering problem.

**Sources:** [S1], [S2], [S7] in [sources.md](sources.md).

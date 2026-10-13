# Week 02 – Mission 4: Understand ML Task Types

## 1. Objective

The objective of this mission is to understand the different types of problems that machine learning can solve. These include classification, regression, clustering, anomaly detection, dimensionality reduction, and recommendation or ranking.

## 2. Classification

Classification is a machine learning task in which a model predicts a category or class for an input.

**Example:** Predict whether a chip design passes or fails timing requirements.

- **Input:** Timing measurements, clock period, and other design features.
- **Output:** Pass or fail.
- **Other example:** Classify a medical image as normal or abnormal.

Classification is useful when the required answer belongs to a set of categories.

## 3. Regression

Regression is a machine learning task in which a model predicts a numerical value.

**Example:** Predict the delay of a semiconductor circuit.

- **Input:** Circuit characteristics, cell information, and design measurements.
- **Output:** Estimated delay in nanoseconds.
- **Other example:** Predict the selling price of a house using its size and location.

Regression is useful when the expected result is a continuous numerical value.

## 4. Clustering

Clustering is a machine learning task that groups similar data points together without requiring predefined labels for each group.

**Example:** Group chip-design runs that have similar power, performance, and area (PPA) characteristics.

- **Input:** Power, performance, area, and other design measurements.
- **Output:** Groups of similar design runs.
- **Other example:** Group customers according to their purchasing behaviour.

Clustering helps engineers discover patterns and similarities in data.

## 5. Anomaly Detection

Anomaly detection identifies observations that differ significantly from expected or common patterns.

**Example:** Identify an unusual power measurement during semiconductor testing.

- **Input:** Historical and current power measurements.
- **Output:** An anomaly score or a normal/anomalous flag.
- **Other example:** Detect unusual transactions in banking.

Anomaly detection is useful for identifying potential faults, unusual behaviour, or measurements that need further investigation. An anomaly does not automatically mean that a fault exists.

## 6. Dimensionality Reduction

Dimensionality reduction represents data using fewer variables or dimensions while attempting to preserve useful information.

**Example:** Simplify hundreds of semiconductor design measurements so engineers can explore relationships between design runs.

- **Input:** A dataset containing many numerical features.
- **Output:** A smaller set of derived features or a lower-dimensional representation.
- **Other example:** Reduce a large collection of image features to make visual exploration easier.

Dimensionality reduction can simplify analysis and help visualise complex datasets. However, some information may be lost.

## 7. Recommendation and Ranking

Recommendation suggests suitable options, while ranking orders available options according to their estimated usefulness or a specified objective.

**Example:** Rank semiconductor design configurations according to predicted power, performance, and area.

- **Input:** Candidate design configurations, predicted measurements, and engineering constraints.
- **Output:** An ordered list of candidate configurations.
- **Other example:** Recommend products based on a user's preferences.

Recommendation and ranking help engineers prioritise candidates for further analysis. The final choice should still consider design constraints and verification results.

## 8. Real-World Problem Classification Table

| No. | Real-world problem | Task type | Input | Expected output |
|---|---|---|---|---|
| 1 | Predict whether a chip meets timing requirements | Classification | Timing measurements and design features | Pass or fail |
| 2 | Estimate circuit delay | Regression | Circuit characteristics and design measurements | Predicted delay in nanoseconds |
| 3 | Group similar semiconductor design runs | Clustering | Power, performance, and area measurements | Groups of similar runs |
| 4 | Detect unusual power measurements during chip testing | Anomaly detection | Power measurements and historical data | Anomaly score or flag |
| 5 | Simplify a dataset with hundreds of design features | Dimensionality reduction | High-dimensional design measurements | Lower-dimensional representation |
| 6 | Rank candidate chip configurations | Recommendation/ranking | Candidate configurations and estimated PPA | Ordered list of candidates |
| 7 | Predict the selling price of a house | Regression | House size, location, and other features | Estimated price |
| 8 | Classify a medical image | Classification | Image data | Predicted category |

The first six examples cover semiconductor-related problems and demonstrate how different task types support different engineering objectives.

## 9. Why Is Task Type Different from Learning Paradigm?

A **learning paradigm** describes how a model learns. A **task type** describes what problem the model is expected to solve.

Learning paradigms include supervised learning, unsupervised learning, reinforcement learning, and self-supervised learning.

Task types include classification, regression, clustering, anomaly detection, dimensionality reduction, and recommendation or ranking.

For example, supervised learning can be used to train a classification model that predicts whether a chip passes timing requirements. It can also train a regression model that estimates circuit delay.

Clustering is commonly associated with unsupervised learning, while reinforcement learning can be used to learn policies for selecting or ranking design actions. The exact combination depends on the problem and method.

Therefore, knowing the task type alone does not tell us which learning paradigm or algorithm was used.

## 10. Can Different Algorithms Solve the Same Task?

Yes. Multiple algorithms can solve the same type of problem.

For example:

- **Classification:** Decision trees, logistic regression, and support vector machines.
- **Regression:** Linear regression, decision-tree regression, and random forest regression.
- **Clustering:** K-means and hierarchical clustering.
- **Anomaly detection:** Isolation Forest and statistical threshold methods.
- **Dimensionality reduction:** Principal Component Analysis (PCA) and t-SNE.
- **Recommendation/ranking:** Learning-to-rank models and recommendation algorithms.

The most suitable algorithm depends on the amount and quality of data, the complexity of the problem, computational cost, interpretability, and required accuracy

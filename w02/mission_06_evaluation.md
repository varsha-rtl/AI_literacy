# Mission 6 - Understand evaluation and generalisation

## Roles of the data splits

- **Training set:** used to fit model parameters.
- **Validation set:** used during development to compare model choices, tune settings, and decide when to stop. It is not a final unbiased score.
- **Test set:** held back until the design is fixed. It estimates performance on unseen examples from the intended population.

**Generalisation** means the model performs usefully on new data drawn from the intended setting. **Overfitting** means the model memorises details or noise in the training set and performs worse on new data. **Underfitting** means the model is too limited or insufficiently trained to capture the useful pattern, so both training and unseen performance are poor.

## Worked example: why accuracy can mislead

Assume 1,000 timing runs contain 950 passes and 50 failures. A model predicts **pass for every run**.

| | Actual pass | Actual fail |
|---|---:|---:|
| Predicted pass | 950 | 50 |
| Predicted fail | 0 | 0 |

- Accuracy = `(950 + 0) / 1,000 = 95%`.
- Recall for the fail class = `0 / (0 + 50) = 0%`.
- Precision for predicted failures is undefined because the model predicted no failures; operational dashboards should report this explicitly rather than silently converting it to a good score.
- Balanced accuracy is `(recall_pass + recall_fail) / 2 = (100% + 0%) / 2 = 50%`.

The 95% accuracy sounds strong, but the model misses every failure. For a sign-off screen, fail-class recall, the confusion matrix, and the cost of false negatives are more informative. A simple baseline such as “always predict the majority class” should be reported so that a new model has to demonstrate value beyond it.

## What common metrics ask

- **Accuracy:** What fraction of all predictions is correct?
- **Precision:** When the model predicts a class, how often is that prediction correct?
- **Recall:** Of the real members of a class, how many did the model find?
- **False positive:** The model raises an alert for a case that is actually negative.
- **False negative:** The model misses a case that is actually positive or dangerous.
- **Absolute error:** How far is a numeric prediction from the measured value, ignoring direction?

Metric choice follows the decision. A safety or sign-off workflow may prioritise recall for failures; an expensive manual-review queue may also need high precision. Neither metric replaces checking data quality, calibration, and real operating cost.

**Sources:** [S2], [S4], [S5], [S7] in [sources.md](sources.md).

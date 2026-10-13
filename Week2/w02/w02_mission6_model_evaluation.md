# Week 02 – Mission 6: Model Evaluation and Generalization

## 1. Introduction

Model evaluation is the process of checking how well a machine learning model makes predictions.

A model should not only perform well on the data used for training. It should also make accurate predictions on new, unseen data.

In semiconductor engineering, model evaluation can help determine whether a model reliably detects defective chips or predicts manufacturing problems.

## 2. Training, Validation, and Test Data

A dataset is commonly divided into three parts.

### Training Data
Training data is used to teach the model. The model learns patterns and adjusts its parameters using this data.

### Validation Data
Validation data is used during model development to compare models and tune settings. It helps identify overfitting.

### Test Data
Test data is used for the final evaluation after model development. It provides an estimate of how well the model performs on unseen data.

**Example:** If we have 1,000 labelled chip measurements, we might use 700 for training, 150 for validation, and 150 for testing. This is only an example; the best split depends on the dataset and problem.

## 3. Generalization

Generalization is the ability of a trained model to make useful predictions on new data that it has not seen during training.

A model with good generalization learns meaningful patterns rather than simply memorizing training examples.

For example, a chip-defect detection model should identify defects in new chips, not just the chips present in its training dataset.

## 4. Overfitting and Underfitting

### Overfitting

Overfitting occurs when a model learns the training data too closely, including noise or accidental patterns.

- Training performance: Very good.
- Performance on unseen data: Poor.
- Possible solution: Use more representative data, simplify the model, or apply regularization.

### Underfitting

Underfitting occurs when a model is too simple or has not learned enough to capture the important patterns.

- Training performance: Poor.
- Performance on unseen data: Also usually poor.
- Possible solution: Improve the model, use more useful features, or train appropriately.

### Comparison

| Condition | Training Performance | Test Performance |
|---|---|---|
| Good generalization | Good | Good |
| Overfitting | Very good | Poor |
| Underfitting | Poor | Poor |

## 5. Common Evaluation Metrics

### Accuracy

Accuracy measures the proportion of all predictions that are correct.

Accuracy = Correct Predictions / Total Predictions

### Precision

Precision measures how many predicted positive cases are actually positive.

Precision = True Positives / (True Positives + False Positives)

### Recall

Recall measures how many actual positive cases the model successfully identifies.

Recall = True Positives / (True Positives + False Negatives)

### False Positive

A false positive occurs when the model predicts a positive result even though the actual result is negative.

Example: A good chip is incorrectly flagged as defective.

### False Negative

A false negative occurs when the model predicts a negative result even though the actual result is positive.

Example: A defective chip is incorrectly classified as good.

### Mean Absolute Error (MAE)

MAE measures the average absolute difference between predicted and actual numerical values.

For example, it can measure the average error when predicting chip temperature.

## 6. Worked Example: Why Accuracy Can Be Misleading

Suppose a factory examines 1,000 chips:

- 990 chips are good.
- 10 chips are defective.

A model predicts that every chip is good.

| Result | Number |
|---|---:|
| Correctly identified good chips | 990 |
| Correctly identified defective chips | 0 |
| Incorrectly flagged good chips | 0 |
| Missed defective chips | 10 |
| Total chips | 1,000 |

Accuracy = 990 / 1,000 × 100 = **99%**

Although the accuracy is 99%, the model fails to detect every defective chip.

Its recall for defective chips is 0%.

This demonstrates why accuracy alone is not enough when the classes are imbalanced. Recall, precision, confusion-matrix counts, and the real cost of errors should also be considered.

## 7. Choosing the Right Metric

The best evaluation metric depends on the task.

| Problem | Useful Metric | Reason |
|---|---|---|
| Defect detection | Recall | Helps measure how many defects are found |
| False alarms in defect inspection | Precision | Helps measure how many flagged chips are truly defective |
| Balanced classification | Accuracy | Gives the overall proportion of correct predictions |
| Chip temperature prediction | MAE | Measures average numerical prediction error |
| Rare failure detection | Recall and precision | Reveals performance on the rare failure class |

No single metric is best for every problem. Engineers should choose metrics based on the application and the consequences of different errors.

## 8. Baseline Models

A baseline is a simple method used as a reference point for evaluating a more advanced model.

For example, a defect detection model can be compared against a simple rule-based method or a model that always predicts the majority class.

A new model should be evaluated against a

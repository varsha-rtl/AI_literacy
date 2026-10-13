# Week 02 – Mission 7: Understand Why ML Systems Fail

## 1. Introduction

A machine learning model may perform well during testing but fail when used in the real world. This can happen because of poor-quality data, biased examples, incorrect labels, data leakage, or changes in real-world conditions.

In semiconductor engineering, an incorrect prediction could cause a defective chip to pass inspection or a good chip to be unnecessarily rejected.

## 2. Common Reasons Why ML Systems Fail

### 2.1 Poor-Quality Data

Poor-quality data contains errors, missing values, inconsistent measurements, or unwanted noise.

**Example:** A dataset contains incorrect temperature measurements from semiconductor manufacturing equipment. A model trained on this data may learn the wrong relationship between process conditions and chip quality.

**Possible mitigation:** Check data for errors, handle missing values appropriately, and verify measurements before training.

### 2.2 Unrepresentative Data

A dataset is unrepresentative when it does not adequately reflect the conditions in which the model will be used.

**Example:** A defect detection model is trained only on chips produced by one manufacturing line but is later used on chips from several different lines.

**Possible mitigation:** Collect representative data from different manufacturing lines, equipment, operating conditions, and relevant defect types.

### 2.3 Label Errors

Labels are the correct answers associated with training examples in supervised learning. If labels are incorrect, the model may learn incorrect patterns.

**Example:** A defective chip is labelled as a good chip in the training dataset.

**Possible mitigation:** Verify labels using reliable inspection results and review uncertain examples with qualified engineers.

### 2.4 Data Bias

Data bias occurs when the collected data systematically favours or underrepresents certain groups, conditions, or cases.

Model performance may differ across subsets of data.

**Example:** A defect detection model performs well on chips from one production line but poorly on another because the training data mostly represents the first line.

**Possible mitigation:** Compare model performance across production lines and operating conditions. Collect more representative examples where needed.

### 2.5 Data Leakage

Data leakage occurs when information unavailable at the intended prediction time improperly enters model training or evaluation.

Leakage can make a model appear more accurate during testing than it will be in actual use.

**Example:** A model predicts whether a chip will fail a test, but its input data accidentally includes a measurement recorded only after that test has finished.

The model may appear to predict failure accurately because it has indirectly received information about the outcome.

**Possible mitigation:** Ensure that input features would genuinely

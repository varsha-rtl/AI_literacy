# Mission 2 — Understand Data: What Does an ML System Learn From?

## 1. Objective

The objective of this mission is to understand how machine learning uses data to learn patterns and make predictions. This includes understanding datasets, samples, features, labels, targets, data types, and data quality.

## 2. Important Data Concepts

### Dataset

A dataset is a collection of examples used to study a problem or train a machine learning model.

Example: A table containing measurements from different chip-design runs.

### Sample or Observation

A sample is one individual example or record in a dataset.

Example: The measurements recorded for one chip-design run represent one sample.

### Feature

A feature is an input variable used by a model to make a prediction.

Example: Clock frequency and estimated delay can be features when predicting whether a chip design will pass timing.

### Label

A label is the known answer associated with an example in a labelled dataset.

Example: The timing result recorded as Pass or Fail.

### Target

The target is the outcome that the model is intended to predict.

Example: Timing Pass/Fail can be the target in a classification problem.

### Data Quality

Data quality describes how accurate, complete, consistent, and suitable the data is for the intended task.

Poor data quality can reduce model performance and produce incorrect predictions.

## 3. Illustrative Dataset

The following is a synthetic example created for learning purposes. It is not real chip-design measurement data.

| Run | Frequency (MHz) | Delay (ns) | Timing Result |
|---|---:|---:|---|
| 1 | 500 | 1.4 | Pass |
| 2 | 600 | 1.8 | Pass |
| 3 | 700 | 2.2 | Fail |
| 4 | 400 | 1.2 | Pass |
| 5 | 800 | 2.5 | Fail |
| 6 | 650 | 2.1 | Fail |

### Identifying the Dataset Components

- **Dataset:** The complete table containing six chip-design runs.
- **Samples:** Each individual row represents one sample.
- **Features:** Frequency and delay, when used as inputs.
- **Target:** Timing Result.
- **Labels:** Pass and Fail are the target labels for the six examples.

In this example, the model could learn from the input measurements and their known outcomes to predict the timing result for a new design run.

The choice of features depends on the prediction task. If the goal is to predict numerical delay, delay would be the target rather than an input feature.

## 4. Types of Data

### Structured Data

Structured data is organised in a defined format, such as rows and columns in a table.

Example: A spreadsheet containing frequency, delay, area, and timing results from chip-design runs.

### Unstructured Data

Unstructured data does not follow a simple fixed table structure.

Examples include design documents, engineering reports, images, and free-form text.

### Numerical Features

Numerical features represent quantities that can be measured or counted.

Examples:
- Clock frequency
- Delay
- Power consumption
- Chip area

### Categorical Features

Categorical features represent groups or named categories.

Examples:
- Design type
- Metal layer
- Operating mode
- Process category

Some categorical features may need to be encoded into numerical representations before being used by a model.

## 5. Labelled and Unlabelled Data

### Labelled Data

Labelled data contains examples with known target answers.

Example: Chip-design measurements accompanied by known Pass or Fail timing results.

Labelled data can be used to train a supervised learning model.

### Unlabelled Data

Unlabelled data contains examples without supplied target answers.

Example: A collection of chip-design measurements without known timing-result labels.

Unlabelled data can be used for tasks such as clustering, where the aim is to discover groups or patterns.

## 6. Data Collection and Preparation

Before training a model, engineers should check and prepare the dataset.

### Data Cleaning

Data cleaning involves identifying and correcting problems such as duplicate records, invalid values, and inconsistent entries.

### Missing Values

A missing value occurs when an expected measurement or field has not been recorded.

Example: A design run may have a missing delay measurement.

The engineer should investigate why the value is missing and choose an appropriate treatment rather than automatically assuming a value.

### Noisy Data

Noisy data contains unwanted variation, measurement errors, or inaccurate observations.

Example: A measurement tool may occasionally record an incorrect delay value.

### Inconsistent Labels

Inconsistent labels occur when similar examples are labelled incorrectly or using different criteria.

Example: Two design runs that meet the same timing criteria may have been recorded with different Pass/Fail labels because of a recording error.

## 7. Why More Data Does Not Always Mean Better Data

A large dataset does not guarantee good model performance. If the dataset contains incorrect measurements, missing values, biased examples, or inconsistent labels, the model may learn misleading patterns.

Quality, relevance, and representativeness are important alongside quantity.

## 8. Two Ways Data Quality Can Affect a Model

### Problem 1: Missing or Incorrect Measurements

If delay measurements are missing or incorrectly recorded, the model may learn from incomplete or misleading examples.

**Possible solution:** Check the source data, identify missing values, investigate measurement errors, and document the cleaning process.

### Problem 2: Incorrect or Inconsistent Labels

If timing results are incorrectly labelled, the model receives incorrect training answers. This can cause it to learn the wrong relationship between the input features and the target.

**Possible solution:** Verify labels against the original timing reports and apply consistent labelling criteria.

## 9. Conclusion

Machine learning depends on suitable data to learn useful patterns. Understanding samples, features, labels, and targets helps engineers prepare datasets correctly. Data cleaning and label verification are important because poor-quality data can lead to unreliable predictions.

## 10. Sources

Record the sources you actually consult and identify the concepts each source supports.

1. Google for Developers — Introduction to Machine Learning: https://developers.google.com/machine-learning/intro-to-ml
2. Google for Developers — Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course

Use these as starting resources. Verify the relevant explanations and update this section to reflect the sources you actually consulted.

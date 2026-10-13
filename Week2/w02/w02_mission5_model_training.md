# Week 02 – Mission 5: How Machine Learning Models Learn

## 1. Introduction

Machine learning allows computers to learn patterns from data and use those patterns to make predictions. A machine learning model learns during training and uses what it has learned during inference.

## 2. Algorithm vs Model vs Parameters

### Algorithm
An algorithm is the method or procedure used to learn patterns from training data.

Example: Linear regression is an algorithm that learns the relationship between input and output values.

### Model
A model is the result of the learning process. It uses learned patterns to make predictions on new data.

Example: A trained model predicts the temperature of a semiconductor chip using operating conditions.

### Parameters
Parameters are the values learned by the model during training.

In linear regression, the parameters are the slope and intercept. They determine how the model converts an input into a prediction.

## 3. Training vs Inference

**Training** is the process of learning from data. The algorithm adjusts model parameters to reduce prediction errors.

**Inference** is the process of using a trained model to predict an output for new input data.

Example:
- Training: Learn the relationship between chip temperature and power consumption using historical data.
- Inference: Predict chip temperature for a new power consumption value.

## 4. How a Model Learns

During supervised learning, the model receives input data and the correct target answers.

The model predicts an output. The prediction is compared with the target answer to calculate a loss, which measures the error. An optimization method adjusts the model parameters to reduce this loss.

This process repeats until the model has learned a useful relationship.

## 5. Training Flow Diagram

```text
Training Data
(Input + Correct Target)
          |
          v
   Learning Algorithm
          |
          v
   Model Makes Prediction
          |
          v
 Compare Prediction with Target
          |
          v
      Calculate Loss
          |
          v
 Adjust Model Parameters
          |
          v
 Repeat Training Process
          |
          v
      Trained Model
```

## 6. Inference Flow Diagram

```text
New Input Data
      |
      v
 Trained Model
      |
      v
 Predicted Output
```

During inference, the trained model uses its learned parameters to make a prediction. It does not normally update its parameters during inference.

## 7. Understanding Linear Regression

Linear regression is a supervised machine learning algorithm used to predict a numerical value.

It learns a relationship between an input variable and an output variable.

The basic equation is:

```text
y = mx + b
```

Where:
- `y` is the predicted output.
- `x` is the input.
- `m` is the slope.
- `b` is the intercept.

For example, a model can learn the relationship between chip power consumption and chip temperature.

If power consumption increases, the temperature may increase under similar operating conditions. Linear regression attempts to represent this relationship with a straight line.

The model learns suitable values of `m` and `b` from the training data.

## 8. Loss and Optimization

**Loss:** A numerical measure of how different a model's prediction is from the target value.

**Optimization:** The process of adjusting model parameters to reduce the loss.

For example, if the actual chip temperature is 70°C and the model predicts 75°C, the prediction error is 5°C. A suitable loss function measures this error.

The optimization process attempts to improve predictions by adjusting the model parameters.

## 9. Semiconductor Example

Consider a semiconductor manufacturing process where engineers want to predict whether a wafer's measured thickness will be within an acceptable range.

1. Collect historical process measurements and corresponding thickness values.
2. Use the data to train a machine learning model.
3. Compare the model's predictions with the actual measured thickness.
4. Calculate the loss and adjust model parameters.
5. Repeat the process to improve predictions.
6. Use the trained model to predict thickness for new process measurements.

The quality of the predictions depends on the quality and representativeness of the training data.

## 10. Conclusion

A learning algorithm uses training data to produce a model with learned parameters. Training adjusts those parameters to reduce prediction errors. Inference uses the trained model to make predictions on new inputs.

Understanding these concepts helps explain how machine learning can support semiconductor manufacturing, chip analysis, and other engineering applications.

## References

- Google Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
- IBM – What Is Machine Learning?: https://www.ibm.com/think/topics/machine-learning
- Scikit-learn User Guide: https://scikit-learn.org/stable/user_guide.html

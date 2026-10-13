# Week 02 – Mission 8: Does This Problem Actually Need ML?

## 1. Introduction

Machine learning is useful for identifying patterns in data and making predictions. However, machine learning is not always the best solution to every problem.

Sometimes, a simple rule-based program is faster, easier to understand, cheaper to maintain, and more reliable.

Before choosing machine learning, engineers should understand the problem, identify the desired outcome, check whether suitable data is available, and decide how success will be measured.

## 2. Define the Problem First

Before choosing a solution, answer these questions:

1. What problem needs to be solved?
2. What result do we want?
3. Can fixed rules solve the problem adequately?
4. Is suitable and reliable data available?
5. How will we measure success?
6. What could happen if the solution gives an incorrect result?

Defining the problem first helps engineers avoid using complex technology when a simpler solution would work.

## 3. Rule-Based Programming vs Machine Learning

### Rule-Based Programming

Rule-based programming uses rules explicitly written by a programmer. The program follows those rules to produce an output.

**Example:** A program checks whether a measured chip temperature exceeds a predefined safety threshold.

If the temperature exceeds the threshold, the program raises a warning.

Advantages:
- Easy to understand and debug.
- Predictable when the rules cover the relevant conditions.
- Does not require a training dataset.
- Often inexpensive to develop and run.

Limitations:
- Requires engineers to define the rules.
- May struggle with complex patterns that are difficult to describe explicitly.
- Rules may need manual updates when conditions change.

### Machine Learning

Machine learning uses data to learn patterns and generate predictions or classifications.

**Example:** A model learns from historical manufacturing measurements to predict whether a chip is likely to be defective.

Advantages:
- Can learn complex relationships from suitable data.
- Can identify patterns that are difficult to express as fixed rules.
- Can be updated using new data when appropriate.

Limitations:
- Requires suitable, representative data.
- Predictions can be incorrect.
- Training, evaluation, and monitoring require effort.
- May be difficult to interpret or maintain, depending on the model.

## 4. Comparison Table

| Factor | Rule-Based Solution | Machine Learning Solution |
|---|---|---|
| How it works | Follows explicit rules | Learns patterns from data |
| Data requirement | No training data required | Usually requires suitable training data |
| Best suited for | Clear, stable conditions | Complex patterns and data-driven predictions |
| Behaviour | Predictable within defined rules | Depends on learned patterns and input data |
| Maintenance | Update rules manually | May require monitoring and retraining |
| Explainability | Rules are usually easy to inspect | Depends on the model |
| Main risk | Rules may not cover all cases | Model may learn incorrect or biased patterns |

## 5. Worked Example: Semiconductor Chip Temperature

### Problem

A semiconductor engineering team wants to identify chips that exceed a specified temperature limit.

The goal is to warn engineers when a chip's measured temperature is too high.

### Option A: Rule-Based Solution

The engineer defines a temperature threshold.

```text
Input: Measured chip temperature

If temperature > specified limit:
    Raise warning
Else:
    No temperature warning
```

This is suitable when the temperature limit is known and the immediate task is simply to check whether the measured value exceeds it.

Advantages:
- Simple to implement.
- Easy to verify.
- Does not require historical training data.

Limitation:
- It does not predict future temperature or learn complex relationships between temperature and other operating conditions.

### Option B: Machine Learning Solution

A model learns from historical data containing chip temperature, power consumption, operating frequency, workload, and other relevant measurements.

It may predict the expected temperature under new operating conditions.

Advantages:
- Can learn relationships between multiple input variables and temperature.
- May help estimate temperature under conditions not covered by a single fixed rule.

Limitations:
- Needs reliable historical data.
- Predictions may be inaccurate when operating conditions differ from the training data.
- Must be evaluated before being used for engineering decisions.

### Which Option Is Better?

For checking whether a measured temperature exceeds a known limit, a rule-based solution is generally sufficient.

For predicting future temperature using several interacting variables, machine learning may be worth investigating if suitable data is available and the predictions provide measurable value.

A machine learning model should not replace a required safety or design constraint check.

## 6. Assessing Data Availability

Before selecting machine learning, engineers should determine whether the necessary data exists.

Useful questions include:

- Are there enough relevant examples?
- Are measurements accurate and consistent?
- Are the correct target labels available when supervised learning is needed?
- Does the dataset represent the conditions in which the model will be used?
- Can the data be collected and maintained responsibly?

More data does not automatically mean better data. Incorrect labels, missing values, and unrepresentative examples can reduce model performance.

If suitable data is unavailable, a rule-based approach may be more practical while the team investigates data collection.

## 7. Measuring Success

A solution should be evaluated against clear success criteria.

For a rule-based temperature check, success may mean correctly identifying every measurement that exceeds the specified limit.

For a machine learning temperature prediction model, success could be measured using mean absolute error (MAE), which measures the average absolute difference between predicted and actual temperatures.

For semiconductor defect detection, useful measures may include recall and precision, because missing a defect and incorrectly flagging a good chip have different consequences.

Engineers should also compare the solution against a simple baseline to determine whether the more complex approach provides a meaningful improvement.

## 8. What Happens When the Solution Is Wrong?

Incorrect outputs can have different consequences depending on the problem.

### Rule-Based Failure
A threshold rule may fail if the threshold is incorrect or the program does not account for an important condition.

**Mitigation:** Verify the engineering requirements, test boundary conditions, and review the implemented rules.

### Machine Learning Failure
A model may make an incorrect prediction because its training data is incomplete, biased, or different from real-world conditions.

**Mitigation:** Evaluate the model on representative unseen data, monitor performance, investigate errors, and maintain appropriate human oversight.

For high-impact engineering decisions, predictions should be verified according to the risks of the application.

## 9. Decision Checklist

Before choosing machine learning, use this checklist:

- [ ] The engineering problem is clearly defined.
- [ ] The desired output is specified.
- [ ] A simple rule-based solution has been considered.
- [ ] Suitable data is available or can realistically be collected.
- [ ] Success can be measured using appropriate metrics.
- [ ] The consequences of incorrect predictions are understood.
- [ ] The proposed ML solution provides a meaningful benefit over a simpler baseline.
- [ ] A plan exists for evaluation, monitoring, and human oversight.

## 10. Conclusion

Machine learning is not automatically the best solution just because a problem involves data.

Rule-based programming is often suitable for clear, stable conditions with known rules. Machine learning may be useful when a problem involves complex patterns that can be learned from representative data.

Engineers should begin by defining the problem, checking data availability, selecting measurable success criteria, and evaluating the consequences of errors. The simplest solution that reliably meets the requirements is often the best starting point.

## References

- Google Machine Learning Problem Framing: https://developers.google.com/machine-learning/problem-framing
- Google Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
- IBM – What Is Machine Learning?: https://www.ibm.com/think/topics/machine-learning

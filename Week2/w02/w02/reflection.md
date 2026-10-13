# Week 02 – Machine Learning Foundations: Reflection

## 1. Which ML concept became clearest to you this week, and what helped you understand it?

The concept that became clearest to me is the difference between training and inference.

Training is the process in which a machine learning model learns patterns from training data. During training, the model adjusts its parameters to reduce prediction errors.

Inference happens after training, when the trained model receives new input data and produces a prediction.

For example, in semiconductor engineering, a model can learn from previous chip-design data during training and later predict the expected temperature of a new chip during inference.

Comparing these two stages helped me understand how a model learns and how it is used.

## 2. Which two concepts are easy to confuse? Explain how you now distinguish them.

Two concepts that were easy to confuse were learning paradigms and ML task types.

Learning paradigms explain how a model learns. Examples include supervised learning, unsupervised learning, and reinforcement learning.

ML task types describe what the model is expected to do. Examples include classification, regression, clustering, and anomaly detection.

For example, supervised learning can be used for classification when predicting whether a chip will pass or fail, or for regression when predicting a numerical value such as chip temperature.

I now understand that the learning approach and the task type answer two different questions.

## 3. What is one claim you checked against a reliable source, and what did the source establish?

I examined the research paper *A Graph Placement Methodology for Fast Chip Design*, published in Nature in 2021.

Source: https://www.nature.com/articles/s41586-021-03544-w

The paper describes a reinforcement learning approach to chip floorplanning and reports experimental results from the authors' work.

This helped me understand that machine learning has been investigated for practical semiconductor-design problems. However, a research demonstration does not prove that the same method will work equally well for every chip, technology process, or physical-design flow.

## 4. Which stage of the ML lifecycle do you think is easiest to underestimate, and why?

I think data preparation is one of the easiest stages to underestimate.

A model may produce poor predictions when its training data contains errors, missing values, incorrect labels, or examples that do not represent real operating conditions.

For example, if a model is trained using data from only one manufacturing line, it may not perform well on data from a different line.

This taught me that collecting, cleaning, and checking data is as important as selecting a model. Good evaluation is also necessary to determine whether the model generalises to unseen data.

## 5. What is one question you want answered before moving into deep learning?

I want to understand how a neural network learns by adjusting its weights and biases during training.

I would like to learn how inputs pass through layers, how the prediction error is calculated, and how the model uses that error to improve its predictions.

I also want to understand why deep learning can be useful for complex problems and when a simpler machine learning model may be a better choice.

## Final Reflection

This week helped me understand the basic machine learning workflow: define the problem, understand and prepare the data, select an approach, train the model, evaluate its performance, and use it for inference.

I also learned that a high evaluation score does not automatically guarantee reliable real-world performance. Data quality, generalisation, data leakage, and changing conditions can all affect results.

In semiconductor engineering, machine learning can assist with tasks such as chip placement and defect detection, but predictions must be checked against engineering requirements and reliable evidence.

My next goal is to strengthen these foundations

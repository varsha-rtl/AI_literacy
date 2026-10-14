# Week 02 – Mission 3: Understand the Main ML Approaches

## 1. Objective

The objective of this mission is to understand how machine learning systems learn from labelled data, unlabelled data, and feedback from actions. This mission compares the major learning approaches and explains their applications and limitations.

## 2. Supervised Learning

Supervised learning is a machine learning approach in which a model learns from examples containing input data and correct target answers (labels).

**How it works:**

1. Collect labelled training data.
2. Provide the input features and target answers to the learning algorithm.
3. The algorithm learns patterns from the examples.
4. Use the trained model to predict outcomes for new inputs.

**Example:** A model learns from previous timing reports to predict whether a chip design will pass or fail timing requirements.

**Training signal:** Known labels or target answers.

**Output:** A trained model that predicts categories or numerical values.

**Limitation:** Incorrect, biased, or unrepresentative labels can lead to unreliable predictions.

### Diagram

Input data + correct labels → Training algorithm → Trained model → Prediction

## 3. Unsupervised Learning

Unsupervised learning is a machine learning approach in which a model works with data that does not have supplied target labels. It attempts to discover patterns, groups, or unusual observations.

**How it works:**

1. Collect unlabelled data.
2. Provide the data to an unsupervised learning algorithm.
3. The algorithm identifies similarities, structures, or unusual patterns.
4. Analyse the discovered groups or patterns.

**Example:** Group semiconductor design runs according to their power consumption, delay, and area.

**Training signal:** Structure and patterns present in the input data, without supplied target labels.

**Output:** Groups, patterns, or unusual observations.

**Limitation:** The discovered groups may not have an obvious engineering meaning and may require expert interpretation.

### Diagram

Unlabelled data → Unsupervised algorithm → Discovered patterns or groups → Engineering interpretation

## 4. Reinforcement Learning

Reinforcement learning is a machine learning approach in which an agent learns to select actions by interacting with an environment and receiving rewards or penalties.

**How it works:**

1. An agent observes the current state of an environment.
2. The agent selects an action.
3. The environment changes and provides feedback or a reward.
4. The agent uses experience to improve its future decisions.

**Example:** An agent explores chip-design configuration choices and receives rewards based on improvements in power, performance, and area (PPA), subject to design constraints.

**Training signal:** Rewards or penalties resulting from actions and their outcomes.

**Output:** A learned policy for choosing actions.

**Limitation:** Learning may require many interactions, and a poorly designed reward function may encourage undesirable behaviour.

### Diagram

State → Agent selects action → Environment responds with reward → Agent improves its policy → Repeat

## 5. Self-Supervised Learning

Self-supervised learning is an approach in which training targets are generated from the input data itself rather than being manually supplied for every example.

**How it works:**

1. Collect a large amount of data.
2. Hide, mask, or select part of the data to create a learning task.
3. Train the model to predict the missing or selected information.
4. Use the learned representations for further tasks.

**Example:** A language model learns to predict missing words or the next token in a sequence of text.

**Training signal:** Targets automatically derived from the data.

**Output:** A model that learns useful patterns or representations from the data.

**Limitation:** The automatically created learning task may not capture everything required for a specific engineering application.

### Diagram

Input data → Create a prediction task from the data → Model learns to predict the target → Learned representations

## 6. Comparison Table

| Learning approach | Training signal | Typical output | Example | One limitation |
|---|---|---|---|---|
| Supervised learning | Labelled examples | Predicted category or numerical value | Predict timing pass/fail | Requires suitable labelled data |
| Unsupervised learning | Patterns in unlabelled data | Groups or discovered structure | Group similar design runs | Patterns may be difficult to interpret |
| Reinforcement learning | Rewards or penalties | Policy for choosing actions | Explore design configurations | Reward design can be difficult |
| Self-supervised learning | Targets derived from the input data | Learned representations or predictions | Predict missing text tokens | The learning task may not match the final application |

## 7. Why Is Self-Supervised Learning Related to but Different from Unsupervised Learning?

Both approaches can learn from data without manually supplied labels for every example. However, self-supervised learning creates explicit training targets from the data itself, such as predicting a masked part of an input. Unsupervised learning is a broader term often used for discovering structure without supplied target labels.

The terminology can overlap, and self-supervised learning is sometimes discussed within the broader family of unsupervised methods. In modern machine learning, it is often treated as a distinct training approach because it creates a specific prediction task from the input data.

## 8. When Is Each Approach Suitable?

- **Supervised learning:** Suitable when historical examples have reliable target answers and the goal is to predict an outcome, such as timing pass/fail.
- **Unsupervised learning:** Suitable when labels are unavailable and the goal is to discover groups or unusual patterns in design measurements.
- **Reinforcement learning:** Suitable when a sequence of decisions must be improved through feedback, such as exploring design configurations under PPA constraints.
- **Self-supervised learning:** Suitable when large amounts of raw data are available and the goal is to learn useful representations before applying them to a particular task.

The choice depends on the available data, the engineering objective, the cost of obtaining feedback, and the risks of incorrect predictions.

## 9. Conclusion

Machine learning approaches differ mainly in the signals used to learn. Supervised learning uses labelled examples, unsupervised learning discovers patterns without supplied target labels, reinforcement learning learns from rewards or penalties, and self-supervised learning derives targets from the data itself.

Understanding these differences helps engineers select an appropriate approach for a problem instead of assuming that one method is suitable for every application.

## 10. References

1. IBM – What is Machine Learning?
   https://www.ibm.com/think/topics/machine-learning

2. Google Machine Learning Crash Course – Classification and other ML concepts
   https://developers.google.com/machine-learning/crash-course

3. OpenAI – Learning and research resources
   https://openai.com/research/

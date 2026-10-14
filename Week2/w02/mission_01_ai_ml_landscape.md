# Mission 1 — Build the AI and ML Landscape

## 1. Objective

The objective of this mission is to understand artificial intelligence (AI), conventional rule-based programming, machine learning (ML), deep learning, generative AI, and large language models (LLMs), and how they are related.

## 2. AI and ML Concept Map

```text
Artificial Intelligence (AI)
|
|-- Rule-based AI
|   |-- Uses explicitly programmed rules
|
|-- Machine Learning (ML)
|   |-- Learns patterns from data
|   |
|   |-- Deep Learning
|       |-- Uses neural networks with multiple layers
|
|-- Generative AI
|   |-- Generates new content such as text, images, and code
|
|-- Large Language Models (LLMs)
    |-- Process and generate language
    |-- Many modern LLMs use transformer architectures
```

Note: This is a simplified concept map. Deep learning is a type of ML. Generative AI describes systems that generate content, while LLMs are models designed for language. These concepts overlap rather than forming one strict hierarchy.

## 3. Five Important Distinctions

### 1. AI versus ML

Artificial intelligence is the broader field of creating systems that perform tasks associated with intelligent behaviour. Machine learning is one approach within AI that learns patterns from data.

### 2. Rule-based programming versus ML

Rule-based programming follows rules explicitly written by a programmer. Machine learning uses training data to learn patterns that can be used to make predictions on new inputs.

### 3. ML versus deep learning

Machine learning includes different techniques for learning from data. Deep learning is a type of ML that uses neural networks with multiple layers.

### 4. Generative AI versus LLMs

Generative AI systems create new content, such as text, images, or code. LLMs are designed to process and generate language. Many LLMs are used in generative AI applications, but generative AI is not limited to language models.

### 5. Automation versus AI

Automation allows a task to be performed with less manual intervention. For example, a script that automatically renames files is automation, but it does not necessarily use AI. AI systems can also be part of automated workflows.

## 4. What Is Explicitly Programmed and What Is Learned?

In conventional rule-based programming, the programmer writes the rules that determine the output. For example, a program can compare a chip's delay against a specified timing limit and report PASS or FAIL.

In machine learning, the programmer provides suitable training data and selects a learning method. The algorithm uses the examples to learn a model that can predict outcomes for new inputs.

ML still requires programming to prepare data, train or load the model, and use its predictions. A learned model can also make mistakes.

## 5. Three Examples and Their Classification

### Example 1: Checking a timing limit

A program compares a reported delay with a specified timing limit and prints PASS or FAIL.

**Classification:** Rule-based programming and automation.

**Reason:** The program follows an explicitly written comparison rule.

### Example 2: Predicting chip timing outcomes

A model learns from historical chip-design measurements with known timing pass/fail results. It predicts the likely outcome for a new design run.

**Classification:** Supervised machine learning, if the training data contains known pass/fail labels.

**Reason:** The model learns patterns from labelled examples and uses them to predict the outcome of a new example.

### Example 3: Generating a technical explanation

A language model receives a question about semiconductor design and generates an explanation in natural language.

**Classification:** Generative AI using an LLM.

**Reason:** The system generates language in response to an input. Its answer should be checked for technical correctness.

## 6. Limitations and Questions

- Poor-quality or unrepresentative training data can cause incorrect ML predictions.
- Rule-based systems can be easy to understand for simple problems, but maintaining many rules can become difficult.
- Generative AI can produce convincing explanations that contain factual errors.

**Question for further learning:** How does an ML algorithm learn patterns from training data and improve a model's predictions?

## 7. Sources

The following resources are starting points for researching AI and ML. I will consult them to verify the explanations and record the material each source supports.

1. Google for Developers — Introduction to Machine Learning: https://developers.google.com/machine-learning/intro-to-ml
2. IBM — What Is Machine Learning?: https://www.ibm.com/think/topics/machine-learning

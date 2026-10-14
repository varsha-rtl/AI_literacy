# Week 02 – Machine Learning Foundations: Sources

## 1. Purpose

This file records sources used to understand machine learning foundations and their applications in semiconductor engineering. Each source is linked to the claims it can help verify.

I will check the source content before submitting the assignment and distinguish established facts from examples, proposals, and research demonstrations.

## 2. Sources and What They Support

### Source 1: Google Machine Learning Crash Course

**Link:** https://developers.google.com/machine-learning/crash-course

**Source type:** Educational resource.

**Claims it can support:**
- Basic machine learning concepts.
- Features, labels, models, and predictions.
- Training and evaluation concepts.
- The importance of data when developing ML models.

**Where I use it:** Missions covering data, models, training, and evaluation.

**Verification note:** Check the relevant lessons and use only claims supported by the material consulted.

### Source 2: Google Machine Learning — Classification

**Link:** https://developers.google.com/machine-learning/crash-course/classification

**Source type:** Educational resource.

**Claims it can support:**
- Classification predicts categories.
- Classification models require appropriate evaluation.
- Classification performance should be examined using suitable metrics rather than accuracy alone in every situation.

**Where I use it:** Mission 4, which compares ML task types, and Mission 6, which discusses evaluation.

**Verification note:** Confirm the specific metric definitions against the relevant lesson.

### Source 3: Mirhoseini et al. — A Graph Placement Methodology for Fast Chip Design

**Link:** https://www.nature.com/articles/s41586-021-03544-w

**Source type:** Primary research paper published in *Nature* in 2021.

**Claims it can support:**
- Research into using deep reinforcement learning for chip floorplanning.
- The approach and experimental results reported by the authors.
- The distinction between a research demonstration and a claim that a technique is universally deployed.

**Where I use it:** Mission 9, the semiconductor case study, and the final synthesis map.

**Verification note:** Read the paper's abstract, methods, results, and limitations before making detailed claims. Do not generalise its reported results to every chip design or physical-design flow.

### Source 4: OpenROAD — Global Placement Documentation

**Link:** https://openroad.readthedocs.io/en/latest/main/src/gpl/README.html

**Source type:** Technical documentation for an open-source physical-design project.

**Claims it can support:**
- The role of global placement in a physical-design flow.
- Placement optimisation and congestion-related considerations documented by the project.
- The need to assess ML-assisted placement against practical engineering requirements.

**Where I use it:** Mission 9 and the final semiconductor application example.

**Verification note:** Use the current documentation to confirm the exact capabilities and options discussed.

## 3. Source-to-Claim Summary

| Assignment topic | Source to check |
|---|---|
| ML concepts, features, and labels | Google ML Crash Course |
| Classification and evaluation | Google ML Crash Course — Classification |
| Reinforcement learning for chip floorplanning | Mirhoseini et al

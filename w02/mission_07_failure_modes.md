# Mission 7 - Understand why ML systems fail

A test score is evidence about a test distribution. It is not a promise that every future input will be safe or useful.

## Failure analysis 1: unrepresentative process data

- **Scenario:** A timing classifier is trained mostly on one process corner and one library family. It looks accurate in the held-out sample but misses slow paths in a new corner.
- **Likely cause:** Coverage bias; the training distribution does not represent the deployment distribution.
- **Evidence to collect:** Performance broken down by corner, library, voltage, temperature, and design family; counts and error rates for each subset; a comparison of training and deployment feature distributions.
- **Mitigation:** Collect representative runs, stratify validation, set minimum coverage per important subset, report subgroup metrics, and route low-coverage cases to human review.

## Failure analysis 2: target leakage

- **Scenario:** A model predicts whether routing will pass, but one feature is a post-route congestion report generated after the pass/fail outcome is already known.
- **Likely cause:** Data leakage. The feature contains information that would not be available at the moment a prediction is supposed to be made.
- **Evidence to collect:** A feature-availability timeline, data-pipeline lineage, timestamps, and a retraining experiment with the suspect feature removed.
- **Mitigation:** Define the prediction time, enforce feature cut-off rules, split data by design or run before preprocessing, and review every feature with a domain engineer. A lower but honest score is preferable to a high leaked score.

## Failure analysis 3: changing data and noisy labels

- **Scenario:** A defect detector works after training but alert quality drops when the inspection tool is replaced and operators change the labelling convention.
- **Likely cause:** Data drift plus label inconsistency. The inputs and the meaning of the target have both changed.
- **Evidence to collect:** Input-distribution and missingness dashboards before and after the tool change, a sample of manually reviewed cases, inter-reviewer agreement, and a time-series of false positives and false negatives.
- **Mitigation:** Version the tool and label policy, recalibrate or retrain on representative new data, maintain a reviewed gold set, and monitor performance after deployment. Keep a human override for high-impact decisions.

Human oversight matters because an incorrect prediction can waste expensive runs, hide a real defect, or send an unsafe design toward sign-off. The model output should be treated as evidence to evaluate, with clear escalation rules.

**Sources:** [S3], [S5], [S7] in [sources.md](sources.md).

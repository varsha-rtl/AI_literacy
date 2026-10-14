# Mission 8 - Does this problem actually need ML?

## Problem framing

Consider the same engineering problem in two ways: **prioritising timing-closure experiments** for an engineer who can run only a limited number of physical-design configurations.

| Question | Rule-based solution | Possible ML solution |
|---|---|---|
| What happens? | Rank by a fixed score, for example lower estimated delay first, with hard constraints for legality. | Learn from historical runs to predict likely delay, congestion, or probability of meeting timing, then rank candidates. |
| Data requirement | A few engineering thresholds and current measurements. | A versioned history of designs, configurations, tool settings, measured outcomes, and failure cases. |
| Strength | Transparent, deterministic, cheap, and easy to audit. | Can combine weak signals and discover interactions that a single threshold misses. |
| Failure mode | Stale thresholds can reject good options or waste trials when conditions change. | Distribution shift, leakage, biased history, and confident wrong rankings can waste runs or hide feasible options. |
| Maintenance | Update rules when constraints change. | Monitor drift, recalibrate, retrain, and keep a baseline and human review. |

## Decision

Start with the rule-based score. It gives a safe baseline and clarifies the constraints. Add ML only if there is a repeated decision, enough representative historical data, a measurable improvement target, and a way to inspect or override predictions. Success might mean reducing the number of expensive runs while preserving the best-achieved timing and not increasing missed failure cases.

ML is a poor fit when the rule is already adequate, the target is not defined, the data is too sparse or biased, or the cost of a wrong prediction is unacceptable without a reliable review process. The presence of data alone is not a reason to use ML.

**Sources:** [S3], [S5] in [sources.md](sources.md).

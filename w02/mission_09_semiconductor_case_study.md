# Mission 9 - Semiconductor case study: learning chip floorplan actions

## Engineering problem

Early physical design must place large macro blocks and standard-cell regions on a chip while balancing wirelength, congestion, timing, power, and area. The search space is combinatorial: moving one block changes many net connections and can affect later routing. A useful system should propose legal placements that improve physical-design objectives without replacing sign-off analysis.

## What data and state are needed?

A placement environment can represent the current state with a netlist graph, macro dimensions, block coordinates, fixed constraints, available regions, and intermediate estimates of wirelength or congestion. An action places or moves a macro. After an action, a fast evaluator returns a reward based on the objective and constraints. The exact representation and reward must be versioned with the design and tool flow.

## Learning approach and output

This is naturally framed as **reinforcement learning** or a related search procedure: an agent chooses a sequence of placement actions, observes the updated state, and receives a reward. The output is a complete floorplan or a policy that proposes the next action. The engineering task is combinatorial optimisation; the output can also be evaluated with regression-style surrogate models, but those surrogates are not the same as the placement policy.

## Evidence

Mirhoseini et al. describe a graph-based placement method trained with reinforcement learning and report results on Google TPU floorplanning. Their Nature paper is a primary research source and reports comparisons with an established human-designed baseline. The paper supports calling this a research demonstration applied to industrial chip floorplans. It does not by itself establish that every design team, process node, or commercial flow will see the same benefit.

Google Research later described AlphaChip as a scalable system for chip-floorplan discovery. That is a useful engineering context source, but claims about current deployment should be checked against the latest company and project documentation rather than inferred from a research paper.

## Evaluation plan

A fair evaluation should compare the learned method with a fixed baseline using the same design constraints and physical-design tools. Record:

- wirelength and routing congestion;
- timing slack and any violated constraints;
- power and area proxies or sign-off measurements;
- runtime and compute budget;
- legality, reproducibility, and the number of manual repairs;
- performance across several netlists, design sizes, and operating corners.

Use held-out netlists or design families to test generalisation. An improvement in a proxy reward is not enough if detailed routing or sign-off reveals worse timing or power. Engineers should inspect the placements and retain a human approval gate for high-impact decisions.

## Limitations and risks

1. **Reward mismatch:** a weighted reward can improve wirelength while damaging timing or routability.
2. **Distribution shift:** a policy trained on one block style or process may not transfer to another.
3. **Tool and constraint dependence:** the result depends on the evaluator, legal constraints, and versions of the physical-design flow.
4. **Reproducibility and cost:** training may require substantial compute and careful experiment tracking.
5. **Human oversight:** generated placements still need conventional physical-design checks and sign-off evidence.

This case connects the Week 02 map: the engineering problem is defined first, graph and run data are prepared, an RL policy is trained, candidate placements are evaluated with engineering metrics, and the deployed decision remains subject to monitoring and review.

**Sources:** [S8] and [S9] in [sources.md](sources.md).

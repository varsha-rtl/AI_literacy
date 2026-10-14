# Mission 5 - Understand the anatomy of an ML model

## Algorithm, model, and parameters

An **algorithm** is the procedure used to fit or apply a model, such as linear regression or a decision-tree training procedure. A **model** is the fitted relationship that maps inputs to outputs. **Learned parameters** are the values inside that model, such as a slope, intercept, tree split, or neural-network weight. A model file stores the learned state plus enough information to interpret the inputs.

## Training to inference flow

```text
historical examples (features, targets)
                |
                v
     split and prepare training data
                |
                v
       choose algorithm and initialise parameters
                |
                v
       training: predict -> measure loss -> update parameters
                |
                v
              trained model
                |
new input ---> inference ---> prediction ---> decision or engineering review
```

During training, the model makes a prediction for an example, compares it with the target using a loss or error measure, and changes parameters to reduce the error over many examples. The loss is a numerical summary of how undesirable the current predictions are. Optimisation is the search procedure that proposes parameter changes; it is not the same thing as the model itself.

Inference is the use of the already-fitted model on a new input. It should be separated from training so that the evaluation data remains unseen and so that a deployed system does not accidentally update itself from unverified results.

## Linear regression intuition

Suppose the target is estimated delay and the inputs include cell count and wirelength. A linear model forms a weighted sum:

```text
estimated_delay = intercept + weight1 * cell_count + weight2 * wirelength
```

Training chooses the intercept and weights that make predictions close to measured delays on the training examples, according to a chosen error measure. The fitted line or plane is a compact approximation of a relationship; it is not proof that the relationship is truly linear. Validation should check whether it remains useful for new designs and corners.

A simple model can be valuable because its inputs, limits, and errors are easier to inspect. A more complex model may capture interactions that a line misses, but it can also be harder to validate and monitor.

**Sources:** [S1], [S2], [S4] in [sources.md](sources.md).

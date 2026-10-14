# Mission 1 - Build the AI and ML landscape

## Central idea

Artificial intelligence (AI) is the broad goal and field of building systems that perform tasks associated with intelligent behaviour, such as perception, reasoning, language use, prediction, or decision support. Machine learning (ML) is one family of methods inside AI: instead of writing every decision rule, an engineer gives a learning method data and lets it estimate useful patterns.

The relationship is overlapping rather than a list of equal-level technologies:

- **AI** is the umbrella field.
- **ML** is a data-driven approach within AI.
- **Deep learning** is ML built with neural networks containing multiple learned layers.
- **Generative AI** describes systems that produce new content; it may use deep learning, but generation is a capability rather than a single algorithm.
- **Large language models (LLMs)** are generative models specialised in language. Modern LLMs commonly use transformer architectures, but the term LLM describes the model's language role and scale, not every detail of its implementation.

See the visual map in [ml_mental_map.png](ml_mental_map.png).

## Five distinctions in my own words

| Distinction | Explanation |
|---|---|
| AI vs conventional rule-based programming | A rule-based program follows rules explicitly written by an engineer. AI includes rule-based systems, but also includes systems that learn patterns or choose actions under uncertainty. |
| Automation vs AI | Automation means a process runs with less manual effort. A fixed script that copies a file every night is useful automation, but it does not infer patterns or adapt from examples, so it is not necessarily AI. |
| ML vs rule-based programming | In rule-based code, the decision logic is mainly specified before execution. In ML, a training procedure estimates parameters from examples; the resulting model then applies the learned relationship to new inputs. |
| Classical ML vs deep learning | Classical ML includes methods such as linear models, trees, and clustering. Deep learning is a subset that uses multi-layer neural networks and usually needs more data and computation. |
| Predictive ML vs generative AI and LLMs | A predictive model may output a class or number, such as pass/fail or estimated delay. Generative AI produces a new artifact, such as text or an image. An LLM is a generative model whose main input and output are language tokens. |

What is explicitly programmed is the program structure, data checks, constraints, objective, and deployment policy. What can be learned is a set of parameters or a policy that captures regularities in the training data. Learned parameters do not replace engineering judgment: the training data, target definition, loss function, and operating limits still come from people.

## Three examples classified

1. **Thermostat with a fixed temperature threshold - automation/rule-based programming.** If the temperature is below 20 C, turn the heater on; otherwise turn it off. The behaviour is explicitly written and does not learn from historical examples. It is automated, but calling it ML would be misleading.
2. **Timing pass/fail predictor for design runs - supervised ML inside AI.** Each historical run has measured features and a known pass/fail result. A classifier can learn a decision boundary and estimate the result for a new run. The task is predictive ML, not generative AI.
3. **An assistant that drafts a verification checklist - generative AI using an LLM.** The model generates text from a prompt. It is still AI and usually deep learning, but it is solving a language-generation task rather than predicting a single numeric target.

## Limits and questions

The labels overlap. A production system may combine a learned model with hand-written safety rules, and an LLM may be one component in a larger application. The useful question is therefore: what is learned, what is fixed, and what evidence shows that the system works on the intended task?

**Sources:** [S1], [S2], [S6] in [sources.md](sources.md).

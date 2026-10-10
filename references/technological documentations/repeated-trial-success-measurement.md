# Repeated-trial success measurement

Use this reference when variable agent behavior requires repeated attempts or a consistency claim.

## Decision method

Specify the task, reset/isolation boundary, attempt budget, success check and sample denominator before running trials. Include failed, timed-out and retried work under the declared policy; distinguish a fresh trial from recovery within one trial.

Choose the quantity matching the product: pass@1 measures one-attempt success, pass@k measures success in at least one of k attempts, and pass^k measures success in every one of k trials. A best-of-k result requires a way to recognize and select a successful attempt; it does not establish single-attempt reliability.

Report per-task results and the agreed task aggregation with sample counts and uncertainty. Do not raise k between candidates without accounting for the changed attempt/cost budget. Keep model, fixtures, policy and success checks comparable.

Under identical independent Bernoulli trials with success probability p, the illustrative probabilities are 1 - (1 - p)^k and p^k respectively. Correlated attempts, unequal tasks or changing state do not justify those assumptions; use the declared empirical estimator. Hand trial fixtures and scoring implementation to their existing evaluation owners.

## Supporting guidance and sources

- [Agent evaluation and repeated trials](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.

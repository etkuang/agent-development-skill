# Grader selection and validity

Use this reference when implementing scores for formal criteria.

## Decision method

Choose reliable deterministic assertions or end-state comparisons for verifiable outcomes, and similarity/model/expert review only where that method matches the residual criterion.

Bind metric, grader version, input/evidence and score. Side-effecting tasks need trusted environment snapshots, comparison and reset/isolation, not a model's report of success.

Probe plausible wrong, unsupported and scoring-shortcut outputs using canonical cases; distinguish a defective grader from a valid alternative solution. Specify validity runner, expected decision, evidence, owner and pre-use gate.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.


# Evaluation case coverage

Use this reference when constructing canonical solvable task and grader fixtures.

## Decision method

Expand early real-task seeds with permitted logs, expert examples and reviewed failures; use labeled synthetic/adversarial examples for identified gaps.

Record case purpose, versioned input/environment/tools/data, acceptable end state, label/provenance and required/prohibited behavior. Establish solvability with expert review or a known valid solution, accepting alternative valid wording and paths.

Map approved tasks and reachable risks to cases, including paired required/non-required activation when relevant. Size follows diversity, risk and detectable effect; preserve partitions and label lineage. Calibration and grader-validity cases are canonical fixtures, not hidden copies inside rubrics.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.


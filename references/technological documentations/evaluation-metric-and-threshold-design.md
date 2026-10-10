# Evaluation metrics and evidence thresholds

Use this reference when approved needs must become observable acceptance criteria.

## Decision method

Define primary task outcome and only relevant quality, required-process, interaction, efficiency and safety guardrails/diagnostics. Ground truth may include verified persisted effects rather than a final success message.

Name observation boundary, unit, denominator, aggregation and repeated-trial policy. Cost per success includes unsuccessful and retried work; per-call success rates cannot be multiplied into task success unless independence and the requirement that every call succeeds have both been established.

Predeclare comparable baseline, task segment, threshold/regression margin, window, minimum evidence and hard no-go status before reading candidate results. Choose missed-harm and false-block limits from actual risk rather than universal percentages.

For repeated attempts, use [repeated-trial success measurement](repeated-trial-success-measurement.md) to choose one-attempt, at-least-one or all-trials success under the actual attempt budget.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI model optimization](https://developers.openai.com/api/docs/guides/model-optimization) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [Ragas agent/tool metrics](https://docs.ragas.io/en/v0.4.1/concepts/metrics/available_metrics/agents/) — Ragas 0.4.1; accessed 2026-10-10.
- [OpenAI evaluate agent workflows](https://developers.openai.com/api/docs/guides/agent-evals) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Google SRE error-budget policy](https://sre.google/workbook/error-budget-policy) — Google SRE Workbook; accessed 2026-10-10.
- [Microsoft Content Safety transparency note](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/content-safety/transparency-note) — Microsoft Foundry documentation; verify the selected service/API; accessed 2026-10-10.


# Trajectory scoring and failure attribution

Use this reference when required process behavior or a failed run needs diagnosis.

## Decision method

Extract observations for selected routing, planning, arguments/results, evidence, policy and state requirements, referencing formal metric semantics.

Score required/prohibited constraints while permitting other valid paths; require an exact or shortest sequence only when the task contract does.

Compare expected versus observed outcomes and inspect grader validity before blaming the agent. Isolate actual component boundaries with controlled fixtures/stubs, then rerun the full workflow to confirm a fix. Judge multi-agent integrated results against the task, with traces for required handoffs and constraints.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [OpenAI evaluate agent workflows](https://developers.openai.com/api/docs/guides/agent-evals) — OpenAI API v1 documentation; accessed 2026-10-10.


# Implementation readiness mapping

Use this reference when approved functions need a concrete implementation handoff.

## Decision method

Map each function to real steps, authoritative schemas, prompt/tool versions, settings/resources and acceptance criteria.

Specify runnable configuration/adapter/resource/interface checks with fixture, expected result, runner, run point and owner. Mechanical architectural boundaries help when actual system complexity requires them.

Separate verified design choices from proposed or untested choices and setup prerequisites such as credentials/access. Hand full task-evaluation and telemetry needs to their later owners without demanding future-stage approval first.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI harness engineering](https://openai.com/index/harness-engineering/) — OpenAI engineering article, 2026-02-11; accessed 2026-10-10.
- [testing](https://openai.github.io/openai-agents-python/testing/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [AWS Agentic AI Lens readiness](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentsus03-bp02.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [Microsoft Foundry hosted-agent testing](https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/test-hosted-agent) — Microsoft Foundry hosted-agent testing, updated 2026-07-21; accessed 2026-10-10.


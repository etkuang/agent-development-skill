# Release manifests and change review

Use this reference when operations correlate versions and control candidate changes.

## Decision method

Link existing code/model/prompt/Skill/tool/schema/policy/configuration/data IDs and dependencies to evaluation evidence, deployed releases/cohorts and a tested recovery baseline.

Assign manifest assembly and regression review owners; instantiate the approved affected/full-suite policy and pass/fail/inconclusive disposition.

When a change alters an approved design decision, identify affected stage documents and obtain renewed approval before dependent work. Ordinary implementation changes preserve the design through the existing versioned path.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS behavior versioning](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops02-bp03.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [Microsoft evaluation checklist](https://learn.microsoft.com/en-us/agents/agent-evaluation/evaluation-checklist) — Microsoft agent evaluation guidance; accessed 2026-10-10.
- [AWS CI practice](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops06-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [change management](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops07-bp03.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [OpenAI API version guidance](https://developers.openai.com/api/reference/overview) — OpenAI API v1 documentation; accessed 2026-10-10.


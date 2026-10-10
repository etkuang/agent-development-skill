# Dependency incident recovery

Use this reference when a deployed dependency degrades or fails.

## Decision method

Bind approved call deadline/retry/replay/fallback and stop/handoff rules to the actual client, SDK or gateway owner.

Define shared health/cutoff scope, suppression, activation, probe cadence/expiry and restoration evidence across concurrent callers.

Use approved alternatives only after quality, authority, state and data checks. Map denied and unknown-effect outcomes distinctly; reconcile durable results before retry. Operating an incident does not reselect provider or serving design.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [thinking in LangGraph](https://docs.langchain.com/oss/python/langgraph/thinking-in-langgraph) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [AWS tool recovery](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops04-bp03.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [operational recovery](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops07-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [Azure gateway choices](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/azure-openai-gateway-multi-backend) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [AWS failure classification](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentrel07-bp02.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


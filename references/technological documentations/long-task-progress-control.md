# Long-task progress control

Use this reference when long-running work can stall, repeat or lose continuation context.

## Decision method

Define progress by verified completed work and remaining obligations, with discoverable objective, decisions, next action and results.

Choose attempt, step, loop, time or resource limits for actual reachable behavior, and place the stop/replan/defer/authorized-handoff transition at its execution owner.

Persist only needed continuation context and reconcile completed actions before retry. Diagnose repeated state or drifting work from outcome-linked evidence rather than counting every long run as failure.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [persistence](https://docs.langchain.com/oss/python/langgraph/persistence) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [Anthropic long-running harnesses](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) — Anthropic engineering article, 2025-11-26; accessed 2026-10-10.
- [AWS workflow orchestration](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf05-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


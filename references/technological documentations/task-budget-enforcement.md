# Task budget enforcement

Use this reference when approved end-to-end ceilings need executable allocations.

## Decision method

Derive phase/call/task time, token and spend allocations from traces or explicit estimates within the approved service target.

Distinguish advisory model budgets, per-response caps and application/platform hard stops. Name the enforcement boundary and stop outcome; an already running call or unknown write may still need accounting and reconciliation.

Compare total spend and cost per attempt/success with quality and latency requirements. A change to the approved ceiling returns to its owner.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Claude Managed Agents sessions](https://platform.claude.com/docs/en/managed-agents/sessions) — Claude Managed Agents documentation; pin the selected API/runtime; accessed 2026-10-10.
- [OpenAI deployment checklist](https://developers.openai.com/api/docs/guides/deployment-checklist) — OpenAI API v1 documentation; accessed 2026-10-10.
- [AWS Agentic AI cost controls](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentcost07.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


# Staffed handoff operation

Use this reference when approved human referral or worker recovery must operate in production.

## Decision method

Bind permitted task identity, verified/attempted work, blocker, pending decision and evidence references to a staffed queue/rota with user notice and response deadline.

Specify unclaimed-referral outcome instead of assuming a recipient is always available. Transfer only the authorized context.

For selected worker agents, use approved task deadlines/liveness and reconcile durable outcomes before retry or reassignment. A smaller-model or single-worker substitute needs the same task and authority fit.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Amazon Connect escalation](https://docs.aws.amazon.com/connect/latest/adminguide/agentic-self-service.html) — Amazon Connect agentic self-service documentation; accessed 2026-10-10.
- [Copilot Studio live handoff](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-hand-off) — Microsoft Copilot Studio handoff documentation; accessed 2026-10-10.
- [operational recovery](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops07-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


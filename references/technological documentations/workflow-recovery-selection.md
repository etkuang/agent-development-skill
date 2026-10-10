# Workflow recovery selection

Use this reference when a reachable failure requires a continuation decision.

## Decision method

Separate transient service failures, model-correctable inputs, user-resolvable missing authority/data and terminal outcomes.

Use actual provider replay/outcome guarantees to select finite retry, correction, reconciliation, authority-equivalent fallback, defer, stop or authorized handoff.

Unknown write results require outcome reconciliation or a supported idempotent replay contract. Keep successful independent work under the approved completion rules; do not add reflection or answer-review loops without evidence.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Stripe idempotency](https://docs.stripe.com/api/idempotent_requests) — Stripe API idempotency documentation; pin the API version; accessed 2026-10-10.
- [thinking in LangGraph](https://docs.langchain.com/oss/python/langgraph/thinking-in-langgraph) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [persistence](https://docs.langchain.com/oss/python/langgraph/persistence) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [AWS failure classification](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentrel07-bp02.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


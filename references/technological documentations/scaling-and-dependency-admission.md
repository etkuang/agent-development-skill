# Scaling and dependency admission

Use this reference when application load must fit serving and shared-resource limits.

## Decision method

Size gateway/orchestrator concurrency and owned replicas from representative capacity evidence, including warm-up/replacement and durable-state needs.

Choose only scaling signals the platform supports. Tail latency can be an outcome without being a valid autoscaler input.

Assign normal-load request/token/API/store budgets and admit/wait/reject/defer ownership. For asynchronous work, bind status/result/cancellation and replay-safe consumers with backlog depth/age and priority limits. Size inference replicas only when owned.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI rate limits](https://developers.openai.com/api/docs/guides/rate-limits) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Kubernetes Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/) — Kubernetes Horizontal Pod Autoscaling; autoscaling/v2 where selected; accessed 2026-10-10.
- [Azure throttling pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/throttling) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [Azure asynchronous request-reply pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/asynchronous-request-reply) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) — Microsoft Azure architecture documentation; accessed 2026-10-10.


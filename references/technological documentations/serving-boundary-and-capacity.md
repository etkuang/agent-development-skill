# Serving boundary and capacity

Use this reference when designing inference capacity for managed or self-hosted service.

## Decision method

Use caller-visible API/quota measurements for managed models and per-owned-instance runtime/hardware measures for self-hosting.

Define representative arrivals/concurrency, input/output lengths, tool mix and observable cache state; measure accepted load, throughput, queue/completion latency and task quality. Add first-token/streaming or GPU measures only where relevant and observable.

Specify benchmark fixture, runner, expected evidence and owner/adoption gate; keep unexecuted settings provisional. Give the capacity result to application admission and owned replica sizing rather than claiming provider-internal control.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS workload criteria](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf01-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [benchmark CLI](https://docs.vllm.ai/en/stable/benchmarking/cli/) — vLLM stable documentation; verify the selected runtime version; accessed 2026-10-10.
- [vLLM performance dashboard](https://docs.vllm.ai/en/latest/benchmarking/dashboard/) — vLLM latest documentation; verify the selected runtime version; accessed 2026-10-10.
- [metrics](https://docs.vllm.ai/en/latest/design/metrics/) — vLLM latest documentation; verify the selected runtime version; accessed 2026-10-10.


# Production metric monitoring

Use this reference when approved measures need continuous sources and alerts.

## Decision method

Bind metric/evaluator/event IDs to a production query, task/version/cohort, collection or sampling window and explicit proxy/availability limitations.

Define ordinary level/constraint alert trigger, severity, delivery and runbook owner from approved targets or comparable baselines. Include billed-use delay treatment when monitoring cost per completion.

Show in-flight progress and outcome-linked retry/recovery diagnostics only for workflows needing them. Repeated steps alone do not prove task failure; link operational views to traces and response owners.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS workload criteria](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf01-bp01.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [AgentCore telemetry](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/observability.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.
- [MLflow production monitoring](https://docs.databricks.com/aws/en/mlflow3/genai/eval-monitor/production-monitoring) — Databricks MLflow 3 GenAI production monitoring; accessed 2026-10-10.
- [AWS cost attribution](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentcost05.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.
- [AWS workflow dashboards](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops05-bp05.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


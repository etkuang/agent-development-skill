# Agent-harness need assessment

## Selection method

1. Identify execution, recovery, inspection or integration responsibilities not already met by the selected runtime.
2. Compare adding a harness, gateway, queue or distributed executor with using the existing application/runtime.
3. Include each additional component only for a concrete task or operating need, and define its responsibility without choosing deployment placement prematurely.

## Supporting guidance and sources

Justify optional gateways, distributed execution, queues and memory services by task needs and operating burden. Component trust boundaries apply the actor, access and governance inputs; detailed enforcement, isolation, telemetry and deployed placement are later decisions. [OpenAI Agents API architecture](https://developers.openai.com/api/docs/guides/agents-api/architecture) (current) and [AWS Agentic AI Lens security design principles](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/security-design-principles.html) (current), accessed 2026-10-10.

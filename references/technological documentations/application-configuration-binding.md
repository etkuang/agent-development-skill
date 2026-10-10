# Application configuration binding

Use this reference when authoritative settings must be exposed and consumed by the app.

## Decision method

Map setting IDs to source precedence, storage, local validator, secret reference, user-changeability and real consumers.

Reference vendor, retrieval, store and budget value owners instead of copying their defaults/ranges into a second table.

Own only new application-specific setting defaults/ranges here, with rationale under approved constraints. Verify the effective setting reaches its intended consumer.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS Secrets Manager hardcoded-secret guidance](https://docs.aws.amazon.com/secretsmanager/latest/userguide/hardcoded.html) — AWS Secrets Manager documentation; accessed 2026-10-10.
- [Pydantic settings](https://pydantic.dev/docs/validation/latest/concepts/pydantic_settings/) — Pydantic Settings documentation; pin the installed release; accessed 2026-10-10.
- [OpenAI Agents SDK agents](https://openai.github.io/openai-agents-python/agents/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.


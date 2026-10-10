# Sensitive telemetry export

Use this reference when diagnostic or audit data leaves its capture boundary.

## Decision method

Give each field a purpose, capture/summary/redaction/omission rule, audience, access and retention/deletion binding. Prefer IDs and summaries to raw prompts, documents and errors where sufficient.

Order sanitization and export so required redaction failure drops the affected sensitive record rather than exposing the original through another path.

Keep restricted operator/auditor detail separate from an allowlisted user projection referencing existing output schemas. Test allowlist/redaction, access and safe projection with fixtures, expected evidence, owner and pre-exposure gate.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenTelemetry sensitive-data handling](https://opentelemetry.io/docs/security/handling-sensitive-data/) — OpenTelemetry documentation; pin exporter and semantic-convention versions; accessed 2026-10-10.
- [OpenAI Agents SDK tracing](https://openai.github.io/openai-agents-python/tracing/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.


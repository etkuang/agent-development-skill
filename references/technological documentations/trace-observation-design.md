# Trace observation design

Use this reference when selected metrics and graders need correlated workflow evidence.

## Decision method

Map actual workflow/model/tool/handoff events to safe run/span/parent/action IDs, version, status, timestamps, source/outcome pointers and relevant error category.

Capture usage and price-version inputs where exposed; compute formal cost through its authoritative accounting definition rather than assuming every span carries cost.

Add route/revision/retry/loop/recovery events only for selected behavior. Name required observation and emitter, separate telemetry from application state/display schemas and identify unavailable evidence. Provider-supported reasoning summaries need purpose/access approval; hidden reasoning is not a required field.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [reasoning practices](https://developers.openai.com/api/docs/guides/reasoning-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI Agents SDK usage](https://openai.github.io/openai-agents-python/usage/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [OpenAI Agents SDK tracing](https://openai.github.io/openai-agents-python/tracing/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [OpenTelemetry GenAI attributes](https://opentelemetry.io/docs/specs/semconv/registry/attributes/gen-ai/) — OpenTelemetry documentation; pin exporter and semantic-convention versions; accessed 2026-10-10.
- [OpenAI reasoning](https://developers.openai.com/api/docs/guides/reasoning) — OpenAI API v1 documentation; accessed 2026-10-10.


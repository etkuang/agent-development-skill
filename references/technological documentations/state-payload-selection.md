# State payload selection

Use this reference when steps or recovery need retained task data.

## Decision method

Retain a field only for a named downstream or recovery consumer and lifetime. Avoid duplicate derivable values and preformatted prompt strings.

Choose raw payload for content that is expensive or impossible to refetch, or stable references when resolution remains reliable. Record availability, source/version, retrieval prerequisites and size/refetch assumptions.

Keep clients, credentials and live model objects outside serializable state. Separate telemetry purpose from execution data, and preserve selected identifiers, constraints, action outcomes and open work in summaries.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [thinking in LangGraph](https://docs.langchain.com/oss/python/langgraph/thinking-in-langgraph) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [memory management](https://docs.langchain.com/oss/python/langgraph/add-memory) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [Anthropic context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — Anthropic engineering article, 2025-09-29; accessed 2026-10-10.
- [OpenTelemetry sensitive-data handling](https://opentelemetry.io/docs/security/handling-sensitive-data/) — OpenTelemetry documentation; pin exporter and semantic-convention versions; accessed 2026-10-10.


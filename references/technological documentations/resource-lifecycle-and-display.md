# Resource lifecycle and display

Use this reference when clients, sessions, background work or output events need application wiring.

## Decision method

Assign startup, shared-use/concurrency, cancellation and shutdown ownership to each actual resource; keep live objects outside serialized task data.

Bind cancellation to the provider protocol, including continuing background work and unknown result reconciliation.

Map progress/final artifacts to the approved user renderer, separate protected diagnostics and display final completion once. Check restored/shared session and client usage at their actual boundary.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [FastAPI lifespan](https://fastapi.tiangolo.com/advanced/events/) — FastAPI lifespan documentation; pin the installed release; accessed 2026-10-10.
- [OpenAI Agents SDK lifecycle](https://openai.github.io/openai-agents-python/ref/lifecycle/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [results](https://openai.github.io/openai-agents-python/results/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.


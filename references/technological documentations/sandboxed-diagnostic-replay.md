# Sandboxed diagnostic replay

Use this reference when a historical failure is replayed for investigation.

## Decision method

Capture permitted state/source-version/action-outcome references and mark the historical checkpoint and replay provenance.

Use sandboxed or stubbed tools to prevent repetition of external effects; checkpoint rewind does not undo a payment or deletion.

Selected runtimes can execute downstream model/API calls again, and model outputs need not reproduce exactly. Keep recovery payload, storage and retention with their authoritative design and data-policy owners.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [checkpointers](https://docs.langchain.com/oss/python/langgraph/checkpointers) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [interrupts](https://docs.langchain.com/oss/python/langgraph/interrupts) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.


# Context layer design

Use this reference when choosing active context, resumable session state or intentional cross-session recall.

## Decision method

Separate immediate model inputs, run-continuation state and deliberately retained facts by purpose and lifetime. A project file or progress record may restore continuity without a personal memory store.

Choose structured lookup for precise facts and semantic or relational recall only when a task needs it. Retain permitted, useful content with origin, scope and correction/deletion routes; resolve conflicting records by authority, provenance and time.

A session evidence cache can retain reusable content, but its lifetime does not make it the authoritative source. Preserve canonical project and source records.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [LangGraph memory overview](https://docs.langchain.com/oss/python/concepts/memory) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [memory management](https://docs.langchain.com/oss/python/langgraph/add-memory) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [Microsoft memory safety](https://learn.microsoft.com/en-us/security/zero-trust/sfi/manage-agentic-memory-safety) — Microsoft agentic memory safety guidance, updated 2026-06-03; accessed 2026-10-10.


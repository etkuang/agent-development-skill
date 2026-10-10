# Checkpoint payload mapping

Use this reference when the chosen runtime persists resumable work.

## Decision method

Inspect the runtime's actual checkpoint boundary and fields for state, pending tasks and write metadata before defining application payload.

Map completed/pending work, required input/evidence references and durable action outcomes to that platform contract; avoid duplicating an entire plan or raw tool history without a consumer.

Verify referenced content will still resolve on resume and bind replay to provider guarantees. Deployment owns backend, expiry and single-continuation mechanics; a direct path need not acquire graph state.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [persistence](https://docs.langchain.com/oss/python/langgraph/persistence) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [checkpointers](https://docs.langchain.com/oss/python/langgraph/checkpointers) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [OpenAI Agents API recovery](https://developers.openai.com/api/docs/guides/agents-api/errors) — OpenAI Agents API recovery, agents=v1 beta; pin the selected runtime; accessed 2026-10-10.


# Asynchronous operation protocol

Use this reference when a selected operation finishes beyond one request.

## Decision method

Choose supported polling, webhook/callback or task-result completion. Define handle identity, status/result, terminal states, deadline and cancellation effect.

Use bounded backoff only for a polling path; verify whether cancellation stops downstream work or still requires result reconciliation.

Assign state ownership to the selected application, platform or tool. MCP transport alone does not imply a LangGraph checkpoint or a particular long-running lifecycle.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI background mode](https://developers.openai.com/api/docs/guides/background) — OpenAI API v1 documentation; accessed 2026-10-10.
- [webhooks](https://developers.openai.com/api/docs/guides/webhooks) — OpenAI API v1 documentation; accessed 2026-10-10.
- [MCP 2026-07-28 release](https://blog.modelcontextprotocol.io/posts/2026-07-28/) — MCP release dated 2026-07-28; accessed 2026-10-10.


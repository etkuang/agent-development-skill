# Integration parameter verification

Use this reference when binding exact arguments to a selected API, SDK or runtime.

## Decision method

Check selected model, endpoint, API/SDK version, deployment mode and exposed controls in official documentation. Record supported type/unit, range/default, chosen value or omission and consumer.

Separate vendor support/default facts from application allocations and retrieval/storage values. Keep unresolved details visible with the missing evidence and owner.

Sampling, reasoning, trainer and token controls are model-specific. Verify restrictions instead of carrying an old model recipe forward; temperature zero does not establish identical behavior.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI GPT-6 model guidance](https://developers.openai.com/api/docs/guides/latest-model) — OpenAI API v1 / GPT-6 guidance; accessed 2026-10-10.
- [Claude Messages API](https://platform.claude.com/docs/en/api/go/messages/create) — Claude API documentation; accessed 2026-10-10.
- [OpenAI Responses create reference](https://developers.openai.com/api/reference/cli/resources/responses/methods/create) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI MCP server guide](https://developers.openai.com/api/docs/guides/tools-connectors-mcp) — OpenAI API v1 documentation; accessed 2026-10-10.


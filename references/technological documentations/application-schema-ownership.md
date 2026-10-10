# Application schema ownership

Use this reference when domain data crosses tool, model or application boundaries.

## Decision method

Own domain request, evidence, tool result/error and final-output meanings once. Bind vendor encoding and model envelopes to those schema IDs instead of copying field definitions.

Define a separate adapter only when application projection changes the model result; reference an unchanged model schema at transport boundaries.

Name producer, consumer, validator and unit for each real constraint. Character, encoded-byte and token limits differ. Trusted identity fields carry context but authorization remains at a trusted action boundary.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [LangGraph Graph API](https://docs.langchain.com/oss/python/langgraph/graph-api) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [OpenAI MCP server authorization](https://developers.openai.com/plugins/build/mcp-server) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [JSON Schema Draft 2020-12](https://json-schema.org/draft/2020-12/json-schema-validation) — JSON Schema Draft 2020-12; accessed 2026-10-10.
- [OpenAI token counting](https://developers.openai.com/api/docs/guides/token-counting) — OpenAI API v1 documentation; accessed 2026-10-10.


# Tool schema encoding

Use this reference when a provider must encode authoritative tool input fields.

## Decision method

Derive input encoding from the domain schema and verify the provider's accepted subset and strict mode for the selected endpoint.

OpenAI strict function schemas require every property to be required and additionalProperties to be false; nullable fields can express optional values. Current Claude helpers can remove unsupported numeric/string bounds from the sent schema and validate the original constraints in application code.

Keep those omitted constraints in the authoritative schema and bind a real validator. One provider's accepted schema is not portable proof for another.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI function calling](https://developers.openai.com/api/docs/guides/function-calling) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Anthropic structured outputs](https://platform.claude.com/docs/en/build-with-claude/structured-outputs) — Claude API documentation; accessed 2026-10-10.


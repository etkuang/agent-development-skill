# Structured output validation

Use this reference when a model result must satisfy a selected response contract.

## Decision method

Bind schema ID/version to the chosen supported strict/grammar mechanism and application validator. JSON syntax, schema adherence and factual/business correctness are separate checks.

Handle refusal, content filtering, truncated/incomplete output, malformed syntax, schema mismatch and extra prose as their actual reachable outcomes.

After parsing, validate required business rules and evidence references. Repair only recoverable format failures within the call budget; do not treat a refusal as malformed JSON. Use approved residual review only for a demonstrated need.

For self-hosted vLLM, verify the installed runtime and structured-output backend. Current documentation uses `structured_outputs`; the listed legacy `guided_json`, `guided_regex`, `guided_choice`, `guided_grammar` and request-level `guided_decoding_backend` fields were removed in v0.12.0. Bind supported schema or grammar options while retaining application semantic checks.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic structured outputs](https://platform.claude.com/docs/en/build-with-claude/structured-outputs) — Claude API documentation; accessed 2026-10-10.
- [OpenAI structured outputs](https://developers.openai.com/api/docs/guides/structured-outputs) — OpenAI API v1 documentation; accessed 2026-10-10.
- [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [vLLM structured outputs](https://docs.vllm.ai/en/stable/features/structured_outputs/) — vLLM stable documentation; legacy-field removal boundary v0.12.0; pin the installed runtime/backend; accessed 2026-10-10.

# Release control verification

Use this reference when approved security and data controls are deployed.

## Decision method

Map each actual obligation, authority or threat-control ID to deployed component/version and a representative fixture with expected safe outcome.

Test denied access/alternate paths, applicable execution isolation, injection, secret exposure and selected content misses/false blocks using canonical criteria. Controlled functions need their scoped-call tests rather than an invented code sandbox.

Inventory exact third-party provenance/permissions and verify required audit capture/access/redaction/retention/deletion. Record procedure, owner, evidence, residual-risk disposition and pre-exposure gate; pending tests are release prerequisites.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI plugin security](https://developers.openai.com/plugins/guides/security-privacy) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [OpenAI sandbox security](https://developers.openai.com/api/docs/guides/agents-api/environments/security) — OpenAI Agents API; pin the selected beta/runtime contract; accessed 2026-10-10.
- [OpenTelemetry sensitive-data handling](https://opentelemetry.io/docs/security/handling-sensitive-data/) — OpenTelemetry documentation; pin exporter and semantic-convention versions; accessed 2026-10-10.
- [Microsoft Content Safety transparency note](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/content-safety/transparency-note) — Microsoft Foundry documentation; verify the selected service/API; accessed 2026-10-10.
- [OpenAI moderation](https://developers.openai.com/api/docs/guides/moderation) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI red teaming](https://developers.openai.com/api/docs/guides/red-teaming) — OpenAI API v1 documentation; accessed 2026-10-10.


# Agent threat control selection

Use this reference when untrusted inputs or components can influence agent execution.

## Decision method

Map the actual request, source, tool result, third-party Skill/MCP description or retained record to its trust boundary and reachable malicious influence.

Preserve instruction origin; check argument/result structure and provenance before consequential use. Bind approvals to exact actions and arguments, and prevent recalled data from being promoted to governing instructions.

Choose a control, rejection outcome and evidence for that reachable path. Ordinary answer errors, missing context and replay races keep their functional owners unless unauthorized influence adds a separate threat.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft memory safety](https://learn.microsoft.com/en-us/security/zero-trust/sfi/manage-agentic-memory-safety) — Microsoft agentic memory safety guidance, updated 2026-06-03; accessed 2026-10-10.
- [OpenAI plugin security](https://developers.openai.com/plugins/guides/security-privacy) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [OWASP threat modeling](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) — OWASP Cheat Sheet Series; accessed 2026-10-10.
- [deep-research injection guidance](https://developers.openai.com/api/docs/guides/deep-research) — OpenAI API v1 documentation; accessed 2026-10-10.


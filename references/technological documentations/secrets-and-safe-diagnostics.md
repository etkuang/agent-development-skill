# Secrets and safe diagnostics

Use this reference when credentials and failure details cross application boundaries.

## Decision method

Choose a trusted secret manager, account-link flow or scoped broker with named provisioning, rotation and revocation owners.

Inspect actual process and diagnostic paths before treating environment variables or restricted files as safe. Keep secrets out of model context, tool returns, user errors and public telemetry.

Expose useful category/cause/correlation information to users while restricting operator details under the data policy. Apply selected sanitization before export and verify the paths that can disclose credentials.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI plugin security](https://developers.openai.com/plugins/guides/security-privacy) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [secrets management](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) — OWASP Cheat Sheet Series; accessed 2026-10-10.


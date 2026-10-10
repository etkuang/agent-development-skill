# Credential flow design

Use this reference when integrations use API keys or account-linked authorization.

## Decision method

Choose the integration's supported key, OAuth/account-link or broker protocol; record trusted secret reference and scoped consumer.

Specify refresh/challenge and missing/expired credential recovery where the protocol uses them, without putting credentials into model outputs or logs.

Local hidden-file/key-placeholder patterns are examples. Verify process exposure and provisioning under the selected secrecy policy rather than prescribing a universal credential location.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI production guidance](https://developers.openai.com/api/docs/guides/production-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI plugin authentication](https://developers.openai.com/plugins/build/auth) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [AWS Secrets Manager hardcoded-secret guidance](https://docs.aws.amazon.com/secretsmanager/latest/userguide/hardcoded.html) — AWS Secrets Manager documentation; accessed 2026-10-10.


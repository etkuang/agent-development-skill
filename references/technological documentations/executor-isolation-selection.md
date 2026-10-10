# Executor isolation selection

Use this reference when an execution path runs model-directed code or untrusted artifacts.

## Decision method

Identify the component that actually executes work and the authorized process/user/data, filesystem, network and credential resources it needs.

Compare isolation supported by that execution environment against reachable effects. Controlled remote functions can use trusted server enforcement without creating another sandbox; model-directed code may need stronger process and host separation.

Verify the chosen boundary with representative denied operations. A model's intended scope or provider hint does not enforce a permission boundary.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI plugin security](https://developers.openai.com/plugins/guides/security-privacy) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [OpenAI sandbox security](https://developers.openai.com/api/docs/guides/agents-api/environments/security) — OpenAI Agents API; pin the selected beta/runtime contract; accessed 2026-10-10.


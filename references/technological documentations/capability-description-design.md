# Capability description design

Use this reference when writing model-facing tool or Skill selection metadata.

## Decision method

Describe the user's goal, activation trigger, coherent action boundary, input constraints and exclusions. Distinguish neighboring capabilities and read/write scopes.

For an inventory lookup, require product and region identifiers and limit the description to stock availability; pricing or recommendation belongs to its selected neighboring capability.

Keep metadata accurate and derived from the same domain definition where feasible. If description work reveals a new permission/action scope, return to the capability decision owner.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Agent Skills specification](https://agentskills.io/specification) — Agent Skills specification; pin the supported revision; accessed 2026-10-10.
- [OpenAI tool design](https://developers.openai.com/plugins/plan/tools) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [OpenAI Skills](https://developers.openai.com/api/docs/guides/tools-skills) — OpenAI API v1 documentation; accessed 2026-10-10.


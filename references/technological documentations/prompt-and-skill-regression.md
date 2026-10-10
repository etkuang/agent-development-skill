# Prompt and Skill regression

Use this reference when authored behavior or activation metadata changes.

## Decision method

Treat prompt behavior, Skill name/description selection and Skill execution body as distinct selected surfaces with review owners and dependency checks.

Choose canonical positive, negative, ambiguous, contextual and reachable failure cases; include instruction/isolation/coexistence checks only for selected Skills.

Compare approved baseline and candidate versions against existing outcomes/graders, resolve missing files/packages/tools and hand tested metadata/content to publication. A prompt-only application need not test an unused Skill registry.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [OpenAI skill building](https://developers.openai.com/plugins/build/skills) — OpenAI Plugins/MCP documentation; accessed 2026-10-10.
- [Claude enterprise Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/enterprise) — Claude API documentation; accessed 2026-10-10.
- [OpenAI prompting](https://developers.openai.com/api/docs/guides/prompting) — OpenAI API v1 documentation; accessed 2026-10-10.


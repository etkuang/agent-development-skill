# Durable implementation handoff

Use this reference when implementation continues across sessions.

## Decision method

Keep objective, constraints, decisions, progress/next action, acceptance results and version history in discoverable project artifacts with update owners.

The next session checks those records against actual repository state before continuing.

Progress files and indexed repository documents are examples rather than a universal folder layout or mandatory initializer agent. Treat stale or untrusted file content as evidence to verify.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic long-running harnesses](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) — Anthropic engineering article, 2025-11-26; accessed 2026-10-10.
- [OpenAI harness engineering](https://openai.com/index/harness-engineering/) — OpenAI engineering article, 2026-02-11; accessed 2026-10-10.


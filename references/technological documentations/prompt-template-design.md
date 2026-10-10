# Prompt template design

Use this reference when an approved model-driven step needs an exact template.

## Decision method

Write a versioned template with role separation, task, response expectation, domain terminology, variables and minimum useful context slots.

Keep runtime/source/tool content in labeled data slots distinct from trusted instructions. Start with a zero-shot baseline and add schema-valid examples only for evaluated benefit.

Use the solving/formatting topology already approved and record rationale outside the prompt. No fixed example count, output wrapper or disclosed chain of thought is a universal requirement.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [reasoning practices](https://developers.openai.com/api/docs/guides/reasoning-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [OpenAI prompt engineering](https://developers.openai.com/api/docs/guides/prompt-engineering) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Claude prompting best practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) — Claude API documentation; accessed 2026-10-10.


# Request routing selection

Use this reference when supported requests may need different handlers.

## Decision method

Start with one handler. Use rules for stable unambiguous requests; compare a classifier, decomposition or specialists only for demonstrated request diversity or selection failures.

Define supported, ambiguous, excluded and multiple-intent cases, wrong-route consequences and rule/model precedence before choosing executable branches.

Preserve independent authorization and grounding checks. A fixed small-to-large model cascade, separate out-of-domain classifier or daily retraining schedule is not a general requirement.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic effective agents](https://www.anthropic.com/engineering/building-effective-agents) — Anthropic engineering article, 2024-12-19; accessed 2026-10-10.
- [OpenAI practical agent guide](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) — OpenAI practical agent guide; accessed 2026-10-10.


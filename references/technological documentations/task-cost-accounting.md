# Whole-task cost accounting

Use this reference when estimating or measuring resource charges for complete tasks.

## Decision method

Trace representative successful, failed, retried and handoff paths, counting model calls, uncached input, cache writes/reads, output and priced tool/service usage.

Include growing history and loaded tool/Skill context where billed. Reasoning tokens included in output billing must not be charged twice.

Pin prices and measured versus estimated workload inputs. Report total spend and cost per attempted/successful task, including failure and costly-tail behavior rather than comparing unit token prices alone.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI Agents SDK usage](https://openai.github.io/openai-agents-python/usage/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [Claude pricing](https://platform.claude.com/docs/en/about-claude/pricing) — Claude API documentation; accessed 2026-10-10.
- [Claude cost and intelligence guide](https://platform.claude.com/docs/en/about-claude/models/optimizing-for-cost-and-intelligence) — Claude API documentation; accessed 2026-10-10.


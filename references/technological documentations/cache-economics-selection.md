# Cache economics selection

Use this reference when repeated inputs or answers might justify caching.

## Decision method

Distinguish prefix caching, which still calls the model, from answer reuse, which can serve stale or unauthorized results.

Compare net read/write/refresh/invalidation charges and quality, freshness, audience isolation and latency against direct execution. State physical-mechanism assumptions when selecting an answer cache, then verify them during store configuration.

Provider automatic/on-demand compaction and cache charging differ; smaller context does not necessarily mean a smaller bill. Fixed savings percentages and compressor/checker pairings remain workload hypotheses.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Claude cost and intelligence guide](https://platform.claude.com/docs/en/about-claude/models/optimizing-for-cost-and-intelligence) — Claude API documentation; accessed 2026-10-10.
- [OpenAI prompt caching](https://developers.openai.com/api/docs/guides/prompt-caching) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Redis semantic cache](https://redis.io/docs/latest/develop/use-cases/semantic-cache/) — Redis current documentation; verify the selected deployment version; accessed 2026-10-10.


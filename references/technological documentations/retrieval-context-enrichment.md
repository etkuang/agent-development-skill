# Retrieval context enrichment

Use this reference when source fragments lose meaning when retrieved alone.

## Decision method

Compare title/heading metadata, parent context and concise chunk-specific enrichment against a no-enrichment baseline.

Check evidence relevance, storage/token cost and misleading generated context on representative questions; preserve original source pointers.

Generic document summaries attached to every chunk are not a universal remedy. Anthropic's contextual-retrieval experiment supports testing chunk-specific context rather than assuming its gain transfers to this corpus.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Azure chunking guide](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-chunk-documents) — Azure AI Search chunking guide, updated 2026-07-02; accessed 2026-10-10.
- [Anthropic contextual retrieval](https://www.anthropic.com/engineering/contextual-retrieval) — Anthropic engineering article, 2024-09-19; accessed 2026-10-10.


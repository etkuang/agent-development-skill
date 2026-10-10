# Source freshness maintenance

Use this reference when changing sources feed derived evidence stores.

## Decision method

Use stable source/version identifiers to detect inserts, updates and deletions, skip unchanged content and reprocess changes.

Regenerate affected embeddings when source or embedding model changes, retire withdrawn records and check query visibility under the chosen consistency model.

Bind mechanisms to the approved source-specific staleness target; use live access when index lag cannot satisfy timeliness. Change streams, tracking and TTL are candidates rather than universal defaults.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [LlamaIndex document management](https://developers.llamaindex.ai/python/framework/module_guides/loading/ingestion_pipeline/) — LlamaIndex Python documentation; pin the installed release; accessed 2026-10-10.
- [Azure SQL indexer change and deletion tracking](https://learn.microsoft.com/en-us/azure/search/search-how-to-index-sql-database) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.
- [Weaviate vectorizer migration](https://docs.weaviate.io/weaviate/tutorials/vectorizer-migration) — Weaviate Cloud v1.32+ migration guidance; verify the selected deployment; accessed 2026-10-10.
- [Pinecone ingestion freshness](https://docs.pinecone.io/guides/index-data/data-ingestion-overview) — Pinecone documentation; verify the selected API/index generation; accessed 2026-10-10.


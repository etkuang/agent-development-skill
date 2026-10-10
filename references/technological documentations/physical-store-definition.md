# Physical store definition

Use this reference when approved logical records require physical persistence.

## Decision method

Bind logical store and payload schema IDs to exact tables/collections/indexes, distinct metadata fields, keys, constraints and query/consistency assumptions.

Record durable backing, schema/index version, startup load path and connection/resource/lifecycle owners. Reuse vectorizer settings and existing domain/model schemas.

One store may hold operational and vector records; a separate index creates a synchronization path. Preserve stable source IDs for joins/deletions, and load unchanged persisted indexes instead of rebuilding on each restart.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Azure vector-search service choices](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/vector-search) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [Pinecone index creation](https://docs.pinecone.io/guides/index-data/create-an-index) — Pinecone API 2026-07 document-schema examples; verify the selected API/index generation; accessed 2026-10-10.
- [LlamaIndex persistence and loading](https://developers.llamaindex.ai/python/framework/module_guides/storing/save_load/) — LlamaIndex Python documentation; pin the installed release; accessed 2026-10-10.


# Retrieval parameter calibration

Use this reference when refining settings for an approved direct or indexed source route.

## Decision method

Bind selected query transformations to original intent/identifiers and domain artifact IDs. For vector stages, pin embedding model/version/dimensions and query/index compatibility.

Compare only existing lexical/vector/hybrid/rerank stages, with applicable initial, reranker-input and final counts. Authorization/version checks precede model exposure; ranking cannot grant access or recover omitted candidates.

Use local query fixtures, reference evidence and source/index/settings versions, naming metric implementation and quality/latency/cost observations. Rank-sensitive measures need ordered candidates; pending measurements are not results. Hand local evidence to formal evaluation.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [information retrieval](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/rag/rag-information-retrieval) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [Azure hybrid search](https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.
- [Azure semantic ranker](https://learn.microsoft.com/en-us/azure/search/semantic-search-overview) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.
- [Ragas context precision](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/context_precision/) — Ragas stable documentation; pin the installed implementation; accessed 2026-10-10.
- [context recall](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/context_recall/) — Ragas stable documentation; pin the installed implementation; accessed 2026-10-10.


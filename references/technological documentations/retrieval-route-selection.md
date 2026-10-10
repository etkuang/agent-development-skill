# Retrieval route selection

Use this reference when tasks need external evidence and a source-access route must be chosen.

## Decision method

Compare direct structured/live lookup with lexical, vector, hybrid and reranked search using reference questions, source format, filters, update rate and corpus scale.

Choose the simplest route meeting coverage, freshness and latency needs. Direct access may avoid an index; a reranker can reorder candidates but cannot recover evidence absent from them.

Distinguish knowledge sources from recalled dialogue and spell out fixed versus iterative source selection. Reconsider a derived index when required timeliness exceeds its update lag.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS direct/index options](https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/options.html) — AWS Prescriptive Guidance on RAG; accessed 2026-10-10.
- [Microsoft RAG design](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/rag/rag-solution-design-and-evaluation-guide) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [information retrieval](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/rag/rag-information-retrieval) — Microsoft Azure architecture documentation; accessed 2026-10-10.


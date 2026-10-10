# Retrieval metric selection

Use this reference when evaluation must distinguish evidence coverage, ranking and answers.

## Decision method

Name implementation/version and reference data for each metric. Evidence coverage, claim groundedness and correctness against a reference answer answer different questions.

Ragas Context Precision is rank-sensitive, using precision at relevant ranks; relevant chunks divided by all chunks is a different measure. Context Recall assesses reference-claim coverage by retrieved contexts. Ranking metrics apply only to ordered candidate lists.

Pin configurable correctness weights instead of assuming an anecdotal mix generalizes. Report local-setting versions and recommend parameter changes to their design owner.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft Foundry RAG evaluators](https://learn.microsoft.com/en-us/azure/foundry/concepts/evaluation-evaluators/rag-evaluators) — Microsoft Foundry documentation; verify the selected service/API; accessed 2026-10-10.
- [Ragas context precision](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/context_precision/) — Ragas stable documentation; pin the installed implementation; accessed 2026-10-10.
- [context recall](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/context_recall/) — Ragas stable documentation; pin the installed implementation; accessed 2026-10-10.
- [answer correctness](https://docs.ragas.io/en/v0.4.0/concepts/metrics/available_metrics/answer_correctness/) — Ragas 0.4.0; accessed 2026-10-10.


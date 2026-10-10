# Source processing and evidence lineage

Use this reference when selecting extraction and ingestion for documents.

## Decision method

Inspect representative native PDFs, scans, tables and images before choosing text extraction, OCR/layout or multimodal processing.

Preserve source ID/version and available page, clause, section, table and image locators through parsing, segmentation and indexing so a delivered citation can resolve to the original support.

Plan source correction and withdrawal propagation to derived evidence. Corpus cleansing preserves source meaning; training/evaluation example preparation has a separate reviewed-label purpose. Neither one vector per page nor one parsing stack is universal.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft RAG design](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/rag/rag-solution-design-and-evaluation-guide) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [Document Intelligence layout](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/prebuilt/layout?view=doc-intel-4.0.0) — Azure AI Document Intelligence 4.0.0; accessed 2026-10-10.


# Source segmentation selection

Use this reference when an approved indexed route needs document boundaries.

## Decision method

Compare no chunking, structural, fixed-size, semantic and parent/child segmentation on source shape and representative queries.

Record boundaries, size/unit, overlap, hierarchy and stable chunk/source/version/locator IDs. Citation pages need not be embedding units.

Choose service-supported, source-specific candidates rather than universal FAQ/technical-document character ranges. Direct source access can omit chunking and ranking entirely.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Bedrock no-chunk option](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html) — Amazon Bedrock documentation; verify the selected service/model; accessed 2026-10-10.
- [Azure chunking guide](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-chunk-documents) — Azure AI Search chunking guide, updated 2026-07-02; accessed 2026-10-10.
- [Azure semantic chunking](https://learn.microsoft.com/en-us/azure/search/search-how-to-semantic-chunking) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.


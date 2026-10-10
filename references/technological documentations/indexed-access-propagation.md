# Indexed access propagation

Use this reference when an index or cache serves content whose entitlements can change.

## Decision method

Choose access metadata and filters from the actual user/group/tenant policy, using verified caller context at the trusted query boundary.

Specify how entitlement removal and permission changes reach derived records and caches before they can expose stale access. Test both permitted and denied users across primary and alternate routes.

Keep source withdrawal, user-entitlement revocation and dialogue deletion distinct. A universal classification triplet or an identity vector shown to the model is not an enforcement design.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [secure multitenant RAG](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag) — Microsoft Azure architecture documentation; accessed 2026-10-10.
- [Azure indexed document access](https://learn.microsoft.com/en-us/azure/search/search-document-level-access-overview) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.


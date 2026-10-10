# Store initialization and migration

Use this reference when a selected store or index changes schema or representation.

## Decision method

Define reproducible initialization and ordered schema/index revisions with validation, cutover and a recovery point.

For an incompatible index, build and test the new version before switching an alias or equivalent query binding. Check dependent payload and vectorizer compatibility.

Select rollback, rebuild or forward repair according to the actual migration path; a downgrade is not guaranteed. Keep recovery tests linked to the deployed version.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Alembic migration tutorial](https://alembic.sqlalchemy.org/en/latest/tutorial.html) — Alembic 1.20.0 tutorial; verify the installed release; accessed 2026-10-10.
- [Azure AI Search index creation](https://learn.microsoft.com/en-us/azure/search/search-how-to-create-search-index) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.
- [index rebuild guidance](https://learn.microsoft.com/en-us/azure/search/search-howto-reindex) — Azure AI Search documentation; verify the selected API/features; accessed 2026-10-10.


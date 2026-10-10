# Aggregate spend enforcement

Use this reference when deployed traffic needs service-level allocations or ceilings.

## Decision method

Choose traffic/workflow allocations, protected traffic and alert-only versus enforced limits within approved financial objectives and task budgets.

Name the application/provider enforcement boundary and limit response. Usage/billing delays and propagation affect practical headroom, so test warning, cutoff and restoration rather than assuming an immediate hard stop.

Bind usage and billed sources, reconciliation owner/cadence and the formal cost-per-success measure to production collection. Compare estimates with billed evidence.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI spend limits](https://developers.openai.com/api/docs/guides/spend-limits) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Claude Usage and Cost API](https://platform.claude.com/docs/en/manage-claude/usage-cost-api) — Claude API documentation; accessed 2026-10-10.


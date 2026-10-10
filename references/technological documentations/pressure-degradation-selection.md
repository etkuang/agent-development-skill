# Pressure degradation selection

Use this reference when exceptional demand or spend needs overrides to normal configuration.

## Decision method

Order supported admission, model/provider-route or serving/cache overrides by the approved workload priorities.

Compare baseline/candidate quality, freshness, access/privacy/residency, latency and cost before using a substitute. Keep platform controls distinct from application controls.

Bind each trigger to its operator, expected/measured effect, validation gate, stop and restoration rule. Dependency outage probes remain operational incidents using the approved playbook.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI deployment checklist](https://developers.openai.com/api/docs/guides/deployment-checklist) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Azure throttling pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/throttling) — Microsoft Azure architecture documentation; accessed 2026-10-10.


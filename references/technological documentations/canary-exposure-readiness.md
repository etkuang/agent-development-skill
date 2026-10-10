# Canary exposure readiness

Use this reference when a pilot or staged release needs risk-appropriate traffic exposure.

## Decision method

Choose eligible traffic, explicit exposure authorization, assignment/allocation and observation stages. Use comparable control cohorts when the selected strategy needs a live comparison.

Reference accepted quality/safety/latency/cost/reliability criteria and minimum evidence; rare severe harms may need offline tests rather than a small live cohort.

Link each exposure increase to valid offline, deployed-control, capacity and applicable recovery evidence and action IDs. Separate evidence-readiness from traffic-exposure ownership. Pending required checks block exposure.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft Content Safety transparency note](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/content-safety/transparency-note) — Microsoft Foundry documentation; verify the selected service/API; accessed 2026-10-10.
- [Google SRE canarying](https://sre.google/workbook/canarying-releases/) — Google SRE Workbook; accessed 2026-10-10.
- [Argo Rollouts analysis](https://argo-rollouts.readthedocs.io/en/stable/features/analysis/) — Argo Rollouts stable documentation; pin the installed release; accessed 2026-10-10.


# Release recovery planning

Use this reference when a candidate release needs executable stop or restoration actions.

## Decision method

Map evaluation/readiness outcomes to authorized promote, pause, stop and application/configuration/traffic revert procedures.

Test retained-state/schema compatibility where a change affects stored state. For external writes, specify authorized reconciliation, compensation or forward repair; reverting code cannot undo completed effects.

Record environment/fixture, procedure, expected evidence, operator and gate. Supply passing applicable recovery evidence before exposure, while distinguishing a documented plan from a completed test.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Google SRE canarying](https://sre.google/workbook/canarying-releases/) — Google SRE Workbook; accessed 2026-10-10.
- [Argo Rollouts analysis](https://argo-rollouts.readthedocs.io/en/stable/features/analysis/) — Argo Rollouts stable documentation; pin the installed release; accessed 2026-10-10.
- [Azure compensating transaction](https://learn.microsoft.com/en-us/azure/architecture/patterns/compensating-transaction) — Microsoft Azure architecture documentation; accessed 2026-10-10.


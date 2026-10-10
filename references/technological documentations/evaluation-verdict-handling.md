# Evaluation verdict handling

Use this reference when a runner applies authoritative acceptance criteria.

## Decision method

Bind criterion IDs to their approved baseline, threshold, window and minimum evidence; check version comparability and observation validity before judging.

Emit pass, fail or inconclusive with result identity and responsible review/retest recipient. A confirmed hard breach fails; absent or insufficient evidence requires measurement rather than an invented pass.

Hand valid versions, verdict and evidence to the release owner. A noisy score drop does not itself define traffic rollback, and evaluation does not authorize compensation for external effects.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [Google SRE canarying](https://sre.google/workbook/canarying-releases/) — Google SRE Workbook; accessed 2026-10-10.
- [Argo Rollouts analysis](https://argo-rollouts.readthedocs.io/en/stable/features/analysis/) — Argo Rollouts stable documentation; pin the installed release; accessed 2026-10-10.


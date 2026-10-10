# Production drift comparison

Use this reference when input mix or behavior may change after deployment.

## Decision method

Compare input distribution separately from task behavior/quality using representative baselines, segments and windows.

Correlate deviations with release/source/configuration manifest versions and inspect corroborating outcomes before choosing a remedy.

Set investigation trigger and accountable reviewer, then route evidence to bad-case attribution or the component owner. Drift observation does not silently change metrics or model/provider routes.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS behavior monitoring](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentops05-bp02.html) — AWS Well-Architected Agentic AI Lens; accessed 2026-10-10.


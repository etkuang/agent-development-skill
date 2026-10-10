# Reviewed case admission

Use this reference when historical or production failures are proposed as future examples.

## Decision method

Require permitted provenance, reproducible setup, a reviewed expected outcome and label owner before admitting a candidate.

Choose a versioned regression destination or an already approved training use; preserve lineage and duplicate/split protections. A complaint or failed run is not automatically a valid training example.

Design the future admission interface even when production cases do not yet exist. Review label changes and comparison-set effects before using the new dataset version.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [overlap](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/raidp01-bp04.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.
- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.


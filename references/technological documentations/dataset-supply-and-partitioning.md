# Dataset supply and partitioning

Use this reference when planning authorized cases for evaluation, calibration or selected training.

## Decision method

Define purpose, permitted sources, source/label owner, task/user/risk coverage and version for each dataset. Evaluation data is needed even when training is absent.

Set label meaning, reviewer disagreement/adjudication and quality checks before admitting examples.

Choose partitions for the selected use and keep calibration and final evaluation separate. Protect exact and near-duplicate families and overlapping task variants from leaking across comparison splits.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AWS dataset planning](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/dataset-planning.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.
- [representation](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/raidp02-bp01.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.
- [label quality](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/raidp02-bp03.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.
- [overlap](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/raidp01-bp04.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.


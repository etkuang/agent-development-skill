# Dataset preparation selection

Use this reference when a documented coverage gap or supported model method needs data transformation.

## Decision method

Select cleansing, augmentation, sequence preparation or prior-task replay only for the demonstrated gap or method constraint.

Preserve source evidence and label semantics through the transformation, then check distribution, label quality and held-out outcomes.

Back-translation, injected noise and templates are candidates rather than compulsory steps. Retained-task replay composition follows the selected remedy and representative capability needs.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [memory guidance](https://huggingface.co/docs/trl/reducing_memory_usage) — Hugging Face TRL documentation; pin the selected release; accessed 2026-10-10.
- [AWS dataset planning](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/dataset-planning.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.
- [augmentation quality](https://docs.aws.amazon.com/wellarchitected/latest/responsible-ai-lens/raidp02-bp04.html) — AWS Well-Architected Responsible AI Lens; accessed 2026-10-10.


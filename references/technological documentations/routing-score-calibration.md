# Routing score calibration

Use this reference when numerical scores determine handlers or abstention.

## Decision method

Use held-out representative data to check what the score predicts; a model's self-reported confidence is not automatically calibrated.

Choose a decision threshold from misroute, harmful execution, clarification and abstention consequences. Inspect per-intent, multi-intent and changed-domain slices rather than aggregate accuracy alone.

A classifier reused for evidence sufficiency needs its own evidence decision and calibration data. Keep calibration cases separate from final evaluation.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [scikit-learn calibration](https://scikit-learn.org/stable/modules/calibration.html) — scikit-learn stable documentation; pin the installed release; accessed 2026-10-10.
- [thresholds](https://scikit-learn.org/stable/modules/classification_threshold.html) — scikit-learn stable documentation; pin the installed release; accessed 2026-10-10.


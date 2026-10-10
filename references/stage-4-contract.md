# Stage 4 — Evaluation

**Current deliverable:** `04-evaluation.docx`.

This contract defines the Stage 4 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain ordinary aspect headings and required end matter, briefly explain inapplicable ordinary aspects, and omit unselected optional aspects. Record unresolved information that affects a needed decision.

Define acceptance and observation needs before cases, scoring and capture implementation. Every selected check identifies its fixture/environment, procedure or runner, run point, expected evidence, owner and execution gate. Attach actual versioned results when available; unperformed checks remain pending. Approval of this plan does not satisfy required grader-adoption or release checks.

## 4.1 Metrics and acceptance evidence

### To clarify

- What observable task end state proves each approved acceptance criterion?
- Which quality, process, communication, latency, cost or safety dimensions affect acceptance, and which are diagnostic?
- What ground truth, denominator, aggregation and repeated trials make the comparison meaningful?
- Does the product need one-attempt success, success within a bounded set of attempts, or consistency across every repeated trial?
- Which baseline, threshold, minimum evidence and hard no-go conditions must be agreed before candidate results are examined?

### output

- **Formal metric definitions:** stable ID/version, approved criterion/target reference, task segment, acceptance/guardrail/diagnostic role, inclusion rationale, ground truth and observation need, units, calculation/denominator and aggregation. Include actual persisted effects when tasks change data.
- **Trial and comparison policy:** repeated-trial requirements for variable or decision-critical cases, task/reset boundary, attempt budget and selection rule, declared success estimator and aggregation, comparable baseline, measurement boundary/window and evidence needed to judge an effect. Distinguish one-attempt reliability, best-of-k success and all-trials consistency when applicable.
- **Acceptance/no-go contract:** criterion/metric IDs, segment, threshold/regression margin, minimum evidence, risk owner and confirmed hard breaches. Preserve 1.4 business targets; missing choices need an owner and resolution action.
- **Workflow-specific measures:** selection/harmful mis-execution for selected routes; evidence coverage, groundedness and answer correctness for retrieval; ranking only for ordered candidates; process constraints only for required behavior. Cost denominators include failed and retried work.
- **Grader acceptance needs:** when subjective scoring is needed, agreement and serious-error criteria for calibration/validity. Other aspects reference these definitions rather than choosing new thresholds.

### out of scope

This aspect defines what is measured and accepted. Cases belong to 4.2, score implementations/rubrics to 4.3, event fields/capture to 4.4, run verdicts to 4.5 and deployed exposure/recovery to Stage 5.

### Prerequisite

Consult approved 1.2 and 1.4, applicable Stage 2 policies/path and Stage 3 local checks, accounting assumptions and readiness hooks.

### Technical references

- When translating acceptance needs into measures and evidence thresholds, see [evaluation-metric-and-threshold-design.md](technological%20documentations/evaluation-metric-and-threshold-design.md) for reference.
- When selecting retrieval coverage, ranking or answer measures, see [retrieval-metric-selection.md](technological%20documentations/retrieval-metric-selection.md) for reference.
- When measuring success over repeated attempts or trials, see [repeated-trial-success-measurement.md](technological%20documentations/repeated-trial-success-measurement.md) for reference.

## 4.2 Evaluation cases and datasets

### To clarify

- Which real tasks, expert cases, authorized logs and reviewed failures cover approved segments and reachable risks?
- What initial state, source snapshot, tools and expected outcomes make each case solvable and gradeable?
- Which positive/negative pairs, judge-calibration cases or grader-validity probes are needed?
- How are labels, fixtures, partitions and new-case lineage reviewed and versioned?

### output

- **Canonical case catalogue:** ID/revision and purpose (task, calibration or grader validity), provenance/permitted use, segment, input/setup/environment/fixture version, tools/data, acceptable end states, expected labels and required/prohibited constraints.
- **Coverage matrix:** approved tasks/capabilities, reachable boundary/partial/failure risks, positive/negative behavior, case IDs/counts and material gaps with owner/action. Synthetic/adversarial cases fill identified gaps rather than replacing real tasks.
- **Dataset/label plan:** coverage-based size rationale, access/storage owner, preparation/partition rules under 2.8, solvability review, label adjudication and change lineage.
- **Comparison bindings:** 4.1 metric/trial-policy references and case configuration needs for 4.5. Supply calibration/validity fixtures before graders are selected; later missing-case requests revise this catalogue.

### out of scope

Do not embed grader implementations, choose trial counts independently of 4.1 or create a separate run manifest. Source-corpus processing stays with its Stage 2/3 owners.

### Prerequisite

Consult approved 1.2 acceptance seeds, 2.8 data policy, Stage 3 local fixtures and 4.1 evidence/coverage needs.

### Technical references

- When selecting solvable cases, paired behavior checks and versioned coverage, see [evaluation-case-coverage.md](technological%20documentations/evaluation-case-coverage.md) for reference.
- When admitting reviewed failures or revised labels, see [reviewed-case-admission.md](technological%20documentations/reviewed-case-admission.md) for reference.

## 4.3 Graders and scoring methods

### To clarify

- Which criteria can reliable assertions or environment comparisons score?
- Which residual criteria need similarity, model or authorized expert review?
- What exact rubric, calibration and wrong-answer probes establish a grader's validity?
- What observations distinguish system failures from defective grading and accept alternative valid paths?

### output

- **Metric-to-grader implementation:** metric ID, grader ID/version, evidence/input, score/output, deterministic feasibility, assertion/state-comparison/reset mechanism, limits and rationale.
- **Validity procedure/evidence:** canonical 4.2 cases for plausible wrong, unsupported or scoring-shortcut outputs; fixture, runner/run point, expected decisions, actual result or pending execution, owner and pre-use gate. Missing evidence cannot establish grader validity.
- **Model-judge contract:** when needed, exact rubric, capable baseline and candidate, canonical human-reviewed calibration cases, 4.1 agreement/error criteria, adjudicator, abstention, recalibration triggers and resource estimate. Adopt a cheaper judge only after measured human calibration passes.
- **Trajectory scoring and diagnosis:** selected process metric, required observation semantics, extraction/aggregation, required/prohibited behavior, allowed paths and missing-evidence outcome. Use real component boundaries for diagnosis and confirm a proposed fix on the full workflow.
- **Capture/scheduling handoff:** give observation requirements to 4.4 and eligible case types/per-grade cost to 4.5. These are requirements for later bindings, not prerequisites to load those aspects.

### out of scope

Metric formulas/thresholds remain in 4.1 and case/label definitions in 4.2. This aspect does not select deployed rollback, run cadence or trace-field names. A success message does not replace an environment end-state check.

### Prerequisite

Consult 4.1 metric/criterion definitions, 4.2 cases and available approved application/state boundaries from Stage 3.

### Technical references

- When choosing a reliable grader and verifying its validity, see [grader-selection-and-validity.md](technological%20documentations/grader-selection-and-validity.md) for reference.
- When a model judge scores residual subjective criteria, see [model-judge-calibration.md](technological%20documentations/model-judge-calibration.md) for reference.
- When scoring required process behavior or attributing a failed run, see [trajectory-scoring-and-failure-attribution.md](technological%20documentations/trajectory-scoring-and-failure-attribution.md) for reference.

## 4.4 Observability and tracing

### To clarify

- Which state, outcome, source, timing, usage and decision observations do selected measures need?
- Which components emit them, and how do run/span/action/version identifiers correlate evidence?
- Which fields may be captured, summarized, redacted or exported to operators and users?
- What sandboxed investigation and export/privacy checks are required?

### output

- **Observation/capture map:** actual component/event, safe correlation/version/status/timing and source/outcome references, provider usage/price inputs and bindings to 4.1 metrics and 4.3 graders.
- **Trace-field and protection contract:** field purpose, emitter, trusted source, capture/summary/redaction/omission, sensitivity, authorized audience, retention/deletion and approved audit references. Define selected retry/loop/revision/recovery events only where they exist.
- **Export path and verification:** sanitizer/export order, failure-drop for required redaction, operator access and a separate allowlisted user projection referencing 3.1/3.3/3.7 output contracts. Record fixture, runner/run point, expected completeness/privacy/access evidence, owner, pre-exposure gate and result or pending execution.
- **Diagnostic replay plan:** permitted state/source/outcome references, historical provenance, sandbox/stub boundaries preventing repeated external effects and nonreproducibility limits.
- **Observation handoff:** identify unavailable required signals and their resolution; give capture checks to 4.5 and protected production signals to Stage 6.

### out of scope

Do not duplicate application, citation, checkpoint or renderer schemas or metric calculations. Raw hidden reasoning is not a required observation; provider-supported summaries need an approved purpose/access rule.

### Prerequisite

Consult approved 1.4 and 2.4 protection policy, 3.1/3.7 artifact/display contracts, and 4.1–4.3 observation needs.

### Technical references

- When mapping actual workflow observations to metrics, see [trace-observation-design.md](technological%20documentations/trace-observation-design.md) for reference.
- When protecting and testing telemetry exports, see [sensitive-telemetry-export.md](technological%20documentations/sensitive-telemetry-export.md) for reference.
- When replaying historical runs for diagnosis, see [sandboxed-diagnostic-replay.md](technological%20documentations/sandboxed-diagnostic-replay.md) for reference.

## 4.5 Evaluation execution, versioning, and CI gates

### To clarify

- Which artifact/environment versions make a run reproducible and comparable?
- What changes require affected checks, full release suites or reviewed rebaselining?
- How does the runner verify minimum evidence and emit pass, fail or inconclusive?
- Which online cases can be sampled, at what justified coverage and judge cost?

### output

- **Run manifest and execution plan:** dataset/split/labels, prompt/tool/schema/model/settings, grader/rubric and fixture/environment versions; seeds where meaningful, runner/run point, check IDs, owner and result identity.
- **CI and comparability policy:** affected/full-suite triggers, required full release run, reviewed dataset/grader changes, pinned comparison set or authorized rebaseline and retest/review ownership.
- **Evaluator verdict handling:** reference 4.1 baseline/threshold/window/minimum evidence, verify comparability and evidence completeness, and emit pass/fail/inconclusive with criterion/run/result links and recipient action. A confirmed hard breach fails evaluation.
- **Online evaluation plan:** existing synchronous authorization/safety hook references and selected asynchronous quality segments, sampling/count rationale, evidence requirements, missing/harmful-result response and total resource estimate from 4.3.
- **Deployment evidence package:** valid versions, results or pending checks, verdict, material gaps and responsible reviewer; Stage 5 decides traffic exposure and recovery.

### out of scope

Do not redefine thresholds, canonical cases, grader rubrics or controls at action boundaries. Evaluation scheduling and verdicts do not authorize promotion, rollback or external-effect compensation.

### Prerequisite

Consult 4.1–4.4 criteria, cases, valid graders and capture/export checks, plus approved implementation/environment versions.

### Technical references

- When pinning evaluation runs or preserving score comparability, see [evaluation-run-versioning.md](technological%20documentations/evaluation-run-versioning.md) for reference.
- When implementing pass, fail and inconclusive verdicts, see [evaluation-verdict-handling.md](technological%20documentations/evaluation-verdict-handling.md) for reference.
- When choosing online quality-evaluation coverage, see [online-evaluation-sampling.md](technological%20documentations/online-evaluation-sampling.md) for reference.

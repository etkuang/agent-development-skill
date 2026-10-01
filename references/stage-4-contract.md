# Stage 4 — Evaluation

**Current deliverable:** `04-evaluation.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-4-evaluation.md](stage-4-evaluation.md).

### 4.1 Evaluation cases and datasets

Build the canonical versioned catalog of task, judge-calibration, and grader-validity cases from approved tasks, early seeds, Stage 3 calibration/check hooks, and reviewed failure examples. Specify each case's setup, inputs, acceptable outcomes, required/prohibited constraints, provenance, and solvability, plus purpose tags, label/fixture versions, coverage, storage, access, and split policy. Bind case measures and trial requirements to 4.2 and grader implementations to 4.3. 4.5 owns run manifests, version pinning, CI scheduling, and evaluation verdicts.

**Requirements**
- Record real-task/log/expert/failure sources, including 4.3 judge-calibration and grader-validity case needs and permitted use, selection rules, coverage gaps filled by labeled synthetic/adversarial cases, and dataset size justified by task diversity, risk and 4.2 evidence requirements.
- For each task, judge-calibration or grader-validity case, record its canonical ID/purpose, initial input/environment/fixture version, tools/data, acceptable outcome and expected label/version, provenance and required/prohibited constraints; bind the 4.3 grader and document solvability/label review.
- Map approved task segments, capabilities, workflow steps and reachable boundary/partial/failure risks to canonical task, judge-calibration and grader-validity case IDs; record counts, missing coverage and the owner/action for each material gap.
- Include case pairs where relevant behavior must occur and must not occur, identifying the shared capability and expected action/nonaction; add unavailable/confusing tool probes only for reachable catalog/dependency risks.
- Tag stochastic or decision-critical cases and bind them to 4.2 repeated-trial policy IDs; record their environment/fixture version and configuration needs for 4.5's pinned run manifest rather than defining an independent run policy.
- For each approved new-task or production-failure case, record its reviewed source, expected outcome/label change, dataset revision and partition assignment under 2.8 preparation controls; retain prior case lineage and notify 4.5 when comparison baselines are affected.

**Output**
- An evaluation-case table with ID/revision and purpose tag (task, judge-calibration or grader-validity), provenance/permitted source, task segment, setup/environment/fixture version, tools/data, input, acceptable outcomes/end states and expected labels/versions, required/prohibited constraints, paired-case/variance tags, solvability evidence, 4.2 trial-policy and 4.3 grader references, and dataset revision.
- A coverage table linking approved segments, capabilities/steps, reachable risks and positive/negative behavior and calibration/validity needs to canonical case IDs, counts and material gaps with owner/action.
- An evaluation dataset plan with sources/selection, coverage/evidence-based size, storage/access owner, preparation/label references to 2.8, split and case-version/admission policy, change lineage, and configuration needs passed to 4.5.

*Technique reference: `references/stage-4-evaluation.md` (cases and datasets).*

### 4.2 Metrics and acceptance thresholds

Translate approved business acceptance criteria and limits into formal, machine-observable metrics for the selected workflow. Define each metric's ID, role, task segment, ground truth, calculation, denominator, aggregation, repeated-trial policy, baseline, and risk-based threshold/evidence requirements. Identify hard no-go conditions here. 4.3 implements scoring, 4.4 captures observations, 4.5 applies evaluation verdicts and schedules checks, and 5.6 executes deployed stop/recovery actions.

**Requirements**
- Name the primary task-success metric and select necessary quality, process, latency, cost and safety guardrails/diagnostics for each approved segment; record each role and why a candidate measure is included or inapplicable.
- For each relevant 1.2 acceptance criterion and 1.4 limit, define its observable measurement boundary, ground truth, aggregation/unit and threshold or authorized pending decision, preserving the approved business target.
- Define what counts as successful end state for each task, including persisted effects; specify necessary process violations/selection/argument/recovery measures and latency/token/cost-per-success calculations with denominators that include failed/retried attempts.
- For routing, define per-intent success and harmful mis-execution including critical segments; for retrieval, name implementation/version/reference data for evidence coverage and answer correctness/groundedness, adding ranking measures only where ordered candidates exist.
- Before examining candidate results, record comparable baseline, task segment, acceptance/regression threshold, measurement window, minimum evidence and hard no-go designation for each gating metric; link evaluator verdict handling to 4.5 and deployed response to 5.6.
- Assign stable IDs/versions to all selected outcome, trajectory, cost and compliance metrics, record required observation/state sources, and use these IDs in grader, telemetry, CI and production plans instead of redefining calculations.
- For each task segment, record whether result, required process, interaction/style and efficiency affect acceptance, are diagnostic only, or are inapplicable, with the approved need/risk and separate metric/threshold binding for each selected dimension.

**Output**
- A formal metric table with ID/version, approved criterion/limit reference, role and inclusion rationale, task segment/dimension, implementation/version, observation boundary, definition/ground truth, units/denominator, aggregation/repeated-trial policy, required state/trace source, comparable baseline, threshold and applicability.
- An authoritative acceptance/no-go contract with criterion/metric IDs, comparison baseline, segment, threshold/regression margin, observation window, minimum evidence and risk owner, linking evaluator verdicts to 4.5 and deployed recovery to 5.6 without duplicating their actions.

*Technique reference: `references/stage-4-evaluation.md` (metrics, formulas).*

### 4.3 Judges and scoring methods

Implement the scoring methods for metrics defined in 4.2 and cases defined in 4.1. Specify deterministic assertions and environment comparisons where possible, and exact rubrics, human-calibration and validity procedures/results using canonical 4.1 cases/label versions, judge selection, abstention/adjudication, and cost where model review is needed. Define trajectory score extraction and procedures that distinguish system failures from defective graders. Consume 4.4 trace observations; 4.5 chooses run scheduling and online sampling.

**Requirements**
- For each metric, record whether an assertion/end-state comparator can reliably score it, the evidence needed and limits; use a model/human grader only for residual criteria that lack a reliable deterministic method.
- For each 4.2 metric, record the chosen assertion, end-state comparator, validated similarity implementation, model rubric or expert review, with version, input artifact, output score and rationale; write the exact rubric for model judgments. Record eligible criterion/case types and per-grade resource/cost estimates for 4.5 scheduling.
- For side-effecting task metrics, specify the trusted database/file/sandbox snapshot and exact expected-versus-observed state comparison, reset/isolation needs and artifact linkage; do not accept a model success message as outcome evidence.
- For each model-judged criterion, start with a capable judge and specify calibration using canonical 4.1 case/fixture/expected-label versions: rubric, runner/run point, agreement/serious-error thresholds from 4.2, expected evidence, owner/gate, adjudication and recalibration. Attach available candidate/human results or mark execution pending; adopt a cheaper candidate only after measured human calibration meets those thresholds.
- Select canonical 4.1 grader-validity cases for plausible wrong, unsupported and reward-hacking responses, requesting missing fixtures there; specify validity procedure/runner/run point, expected decisions, abstention and authorized expert adjudication. Record available judgment results or pending execution with owner and the gate required before grader use.
- When scoring a failure, specify how to compare expected/observed state and trace evidence, detect a defective grader, and run isolated component/stub comparisons at real boundaries; require a full-workflow case rerun before accepting the evaluated fix.
- For each 4.2 process metric, identify the required trace fields/state observations, ordered or unordered constraint rule, score aggregation and handling of missing evidence; reference allowed alternative paths instead of demanding an invented exact trajectory.

**Output**
- A metric-to-grader decision/implementation record with deterministic feasibility, grader type/ID/version, exact input/evidence and output score, assertion/state-comparison/reset mechanics, limitations/rationale, and diagnostic comparison/confirmation procedure. For every selected grader, include canonical validity fixture IDs, procedure/runner/run point, expected decisions, actual evidence or pending execution, owner and required pre-use gate; specialized model-judge or trajectory details reference O-4.3-02/O-4.3-03 when applicable.
- For each model-judged criterion, the exact rubric and calibration/validity procedure referencing canonical 4.1 case, fixture and expected-label versions; capable-baseline/candidate versus human judgment results, 4.2 threshold IDs, cheaper-judge eligibility only after meeting them, chosen judge, authorized adjudication results, missing-case requests, abstention and recalibration plan. Mark not applicable when no model judge is used. Include executable calibration/validity fixture references, runner/run point, expected acceptance evidence, owner/adoption gate and actual results or pending execution; cheaper-judge selection stays pending until measured calibration passes.
- A trajectory-scoring contract per process metric with required 4.4 fields/state evidence, extraction/aggregation, required/prohibited constraints, optional valid paths, missing-evidence/abstention handling, and diagnostic component/full-workflow confirmation procedure.
- A judge resource estimate with eligible criterion/case types, per-grade tokens/calls/cost, calibration/adjudication overhead and assumptions, supplied to 4.5 for scheduling/online sampling; mark not applicable when no model judge is used.

*Technique reference: `references/stage-4-evaluation.md` (judges and scoring).*

### 4.4 Observability and tracing

Design the trace and audit observation pipeline needed by 4.2 metrics, 4.3 graders, and the selected workflow. Specify span/event fields, correlation, capture points, usage/price inputs, omitted data, privacy/export controls, access, retention, and sandboxed diagnostic replay. Reference 3.2 state/outcome schemas and 3.7 user-display bindings rather than redefining them. Provide instrumentation/privacy verification hooks to 4.5 and protected signals to production monitoring.

**Requirements**
- For each selected workflow/model/tool event, record safe run/span/parent IDs, component/version, status/timestamps/error category, available provider usage and priced-tool inputs; bind these observations/rate versions to 4.2 metrics and 3.6 accounting without redefining their formulas.
- Record trace references to 3.2 state transitions, source versions and durable action outcomes; specify sandbox/stub replay inputs and isolation preventing external side-effect repetition, with replay provenance and known nonreproducibility limits.
- For selected route, plan, tool and review decisions, record each observable event/field and capture source; include a provider-supported reasoning summary only with an approved purpose/access rule, and mark unavailable or prohibited reasoning data omitted.
- For selected plan revisions, recovery/compensation, loops and retries, define event type, reason, count, linked attempt/action and version fields with their emitting component; reference workflow/action contracts rather than inventing new event categories for absent behavior.
- Assign operator/auditor access to diagnostic event fields and bind the approved 3.2/3.7 progress/final/provenance artifacts to a separate authorized export path; do not redefine their schemas or renderer behavior.
- For each trace field, choose allowlisted capture, summary/redaction or omission under 1.4/2.9 policy; specify sanitizer/exporter order, access, exact retention/deletion binding and sanitized errors. Where redaction is selected, drop affected export on redaction failure.
- Specify telemetry export tests for approved allowlist/redaction, operator access and user-safe projection, with fixture, runner/run point, expected evidence, owner and pre-exposure gate; attach existing results or pending execution. Require export to drop unredactable sensitive records, and reference 3.2/3.3 user-output contracts.

**Output**
- An observability design with span/event linkage, capture points and metric/grader bindings, usage and price inputs, captured/omitted data, approved access/retention/deletion controls, audit references, sandbox/stub replay procedure and limits, and capture-completeness/privacy verification hooks for 4.5.
- A trace-field table with span/event type and emitter, field, purpose, artifact/state/source reference, capture/summary/redaction/omission rule, sensitivity, audience/access, retention/deletion binding, timestamp/version/correlation and required metric/grader observation.
- A Mermaid observation-path figure with workflow/tool spans, sanitizer/redaction/failure-drop/export, audit/metric sinks, and a separate allowlisted path to the existing 3.2/3.7 user provenance/artifact contracts. Include export/access/projection test fixture, runner/run point, expected evidence, owner/pre-exposure gate and available result or pending execution.

*Technique reference: `references/stage-4-evaluation.md` (observability).*

### 4.5 Evaluation versioning and CI gates

Integrate the Stage 4 dataset, metric, grader, and telemetry contracts into reproducible offline/online evaluation. Specify run manifests, affected/full-suite CI triggers, online sampling, evidence-validity checks, and evaluator pass/fail/inconclusive outcomes. Reference 4.2 thresholds and evidence windows instead of restating them. Publish verdicts and their responsible review/retest actions for later deployment decisions; Stage 5 owns exposure, promotion, stop, rollback, and compensation.

**Requirements**
- For each evaluation run, pin dataset/split/labels, grader/rubric, prompt/tool/schema/model and supported settings in one manifest; record environment/seeds where meaningful, result identity, affected-check triggers and the full-suite run required before release approval.
- For each 4.2 criterion ID, specify how the runner verifies baseline/version comparability and minimum evidence, emits pass/fail/inconclusive, and routes the result to the responsible reviewer, retest or release decision; a confirmed hard breach fails evaluation rather than defining rollback here.
- Record which approved safety/telemetry checks run synchronously at their existing enforcement point, and define asynchronous eligible segments, sampling/count policy, missing-evidence response and estimated judge cost using 4.3 per-grade estimates and 4.2 evidence needs.
- Before comparing runs after a dataset/label/rubric change, verify the reviewed 4.1 dataset or 4.3 grader version, use a pinned comparable set or document authorized rebaselining, and record score-comparability status and the required retest/review.

**Output**
- An evaluation execution/CI table and run-manifest record with suite/check IDs, artifact/environment/configuration versions, affected/full run triggers, runner and owner, 4.2 criterion references, comparability/evidence validity checks, result links and pass/fail/inconclusive handling; do not repeat authoritative thresholds.
- An online evaluation plan by approved risk segment with existing synchronous safety/telemetry hook references, asynchronous eligibility and sampling/count rule, 4.2 evidence requirements, missing/harmful-result response, and total judge cost from 4.3 per-grade estimates.
- An evaluator verdict and evidence-handoff rule with criterion/run/result IDs, pass/fail/inconclusive, comparable/rebaseline status, missing-evidence retest/review, responsible decision recipient and release evidence package; deployed promotion/stop/rollback/compensation is specified in Stage 5.

*Technique reference: `references/stage-4-evaluation.md` (CI gates).*

**Deliver and confirm:** Stage 4 Word document with the evaluation sets, metrics, thresholds, judges, trajectory scoring, observability design, and CI gates.


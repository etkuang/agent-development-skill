# Stage 5 — Deployment

**Current deliverable:** `05-deployment.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-5-deployment.md](stage-5-deployment.md).

### 5.1 Release strategy and gray rollout

Plan candidate and control cohorts, their exposure sequence and the evidence collected before each wider release. This aspect owns traffic exposure and rollout evidence readiness. Reference the metric and gate definitions in 4.2/4.5, the deployed safety-test evidence in 5.5 and the executable release recovery actions in 5.6. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- In the exposure and comparison decision, record the candidate and control cohort comparability checks and reference the applicable task-quality, safety, latency, cost and reliability measures from 4.2; name the evidence source for each measure.
- Ask the user to confirm exposure risk and eligible traffic, then record cohort assignment, initial allocation, exposure stages and observation windows in the rollout plan; link the exposure and comparison decision to the minimum-evidence rule in 4.5 and the action table in 5.6.
- In the rollout plan and evidence-readiness table, specify the offline verdict, deployed-control checks and exposure authorization required before each traffic increase, with expected evidence IDs, execution/readiness owner and Stage 6 destinations; attach existing results and label unperformed checks as release prerequisites.
- Where content risk applies, reference the labeled-test plan and any available results from 5.5 in the exposure/comparison decision; choose feasible missed-violation/false-block cohort comparisons and identify rare/severe risks needing offline evidence, with a readiness gate before exposure.
- In the rollout evidence-readiness table, link each exposure stage to the 5.6 revert/external-effect recovery procedure and required compatibility-test evidence, naming owner and current result or pending prerequisite; require passing recovery evidence before that exposure begins.

**Output**
- A rollout plan with eligible traffic, comparable cohorts, assignment method, exposure stages, observation windows, exposure owner, readiness prerequisites and links to Stage 6 monitoring.
- An exposure and comparison decision recording initial allocation, comparability checks, approved metric and gate references, evidence sources, feasible safety comparisons and minimum-evidence reference.
- A rollout evidence-readiness table with exposure stage, prerequisite, evidence reference, recovery-action reference from 5.6, readiness disposition and exposure owner. Include expected test/evidence ID, actual-result or pending-prerequisite status, execution/readiness owner and pre-exposure gate. Name the evidence-readiness owner separately from the traffic-exposure owner. Include the required stored-state compatibility and recovery-test evidence references.

*Technique reference: `references/stage-5-deployment.md` (release and rollout).*

### 5.2 Serving and inference acceleration

Specify the inference service for the approved managed API or self-hosted deployment. This aspect owns supported serving configuration and measured capacity at the available boundary: caller-visible API/quota workload for managed services, and runtime/hardware/per-instance capacity for self-hosting. Reference model/compression choices in 2.2/2.7 and request contracts in 3.1; give capacity evidence to 5.3 for concurrency, replica and admission design. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- In the serving table, record deployment mode and observable service boundary, choose controls exposed by the managed API or self-hosted runtime, and check hardware support only for self-hosting; specify representative benchmark fixtures/procedure and 1.4/4.2 acceptance references, attaching results when available.
- For each exposed serving optimization, specify comparable baseline/candidate latency, throughput, cost and task-quality checks, plus memory when observable; record expected acceptance evidence, benchmark owner and release gate, attaching available measurements or marking execution pending. Require the 4.2 quality gate before adopting lossy settings.
- For self-hosting, specify supported instance parallelism, batching, scheduler, KV-cache and offload values in the runtime record; for managed serving, reference the 3.1 API contract and exposed controls. In capacity evidence, specify workload/fixture, API quota or instance boundary, accepted-load/throughput/latency/quality procedure, owner and gate, with conditional streaming/GPU fields; attach available results or a pending execution record.
- For compression candidates justified in 2.7, specify comparison of deployable artifacts against the approved baseline for selected-service compatibility, performance and quality; add hardware/runtime and memory-fit checks for self-hosting. Record available results or the benchmark plan/owner/gate, and reopen 2.7 if evidence requires a different method.
- For self-hosting, specify hardware and supported weight/activation/KV precision candidates, compatibility sources and memory/latency/throughput/cost/quality comparison procedure; record proposed values, owner/gate and available results or pending execution in the serving/runtime records. For managed APIs, record provider ownership of unexposed internals and available service controls.

**Output**
- A serving decision table with approved model/deployment references, managed API/quota or self-hosted instance boundary, runtime/API version, exposed controls, conditional hardware/precision and memory evidence, baseline/candidate measurements, disposition and rationale. Include benchmark fixture/procedure, expected acceptance evidence, owner/gate and available result or pending execution; label proposed settings.
- A versioned runtime-configuration record with exact inference parameter names, selected values, support evidence and rationale; managed API entries reference the 3.1 request contract and record only serving/caching configuration distinct from that contract.
- Capacity evidence at the caller-visible API/quota boundary for managed serving or per serving instance for self-hosting, with representative arrivals/concurrency, prompt/output lengths, cache state where observable, accepted load, request/token throughput, queue/completion latency, quality/objective references and conditional streaming/GPU measures. Include executable load-test procedure, expected acceptance evidence, owner/pre-exposure gate and observed result or pending implementation/pilot execution.

*Technique reference: `references/stage-5-deployment.md` (serving and acceleration).*

### 5.3 Model routing and scaling

Allocate the approved model and effort choices to deployed workload categories and size application replicas and app concurrency/admission against the managed API/quota boundary, or inference replicas when self-hosted. This aspect owns deployment routing and normal-load scaling, backlog and quota admission. Reference request/capability routing in 2.1, model roles in 2.2, exact asynchronous contracts in 3.1, measured serving capacity in 5.2 and the state backend in 5.4. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- Specify a comparable fixed-versus-routed model/effort experiment among approved 2.2 candidates on representative workload categories, with fixture/environment, runner/run point, 4.2 acceptance references, expected quality/latency/cost evidence and owner/pre-exposure gate. Record available results or pending execution and a provisional route/no-router decision, preserving any required direct route.
- Specify router overhead, category-error, escalation and cost-per-success checks in the deployment routing table with expected evidence, owner and gate; attach available results or mark execution pending. Choose provisional eligibility and direct/stronger-model routes for uncertain or high-impact tasks using approved 2.1 policy and 4.2 quality gates; require executed acceptance evidence before exposing a changed allocation.
- Use the 5.2 capacity evidence to set supported scaling signals, targets and limits in the scaling description; assign normal-load model quota, store connection and other dependency budgets in the shared-resource protection plan, with enforcement and admit/wait/reject/defer behavior.
- For horizontal scaling, record gateway and orchestration replica ownership, supported metrics, capacity limits, warm-up and replacement behavior in the scaling description; bind required run state to the backend and recovery contract in 5.4.
- For work beyond the approved synchronous deadline, choose the deployment asynchronous transport in the scaling description and reference the 3.1 status/result/cancellation contract; record backlog depth/age limits and dependency rate/concurrency enforcement in the shared-resource protection plan.

**Output**
- A deployment routing table by approved workload category, model/version and effort, fixed baseline, measured router and task results, allocation eligibility, quality-gate reference, required direct route and selected route/no-router decision. Include representative fixture/environment, runner/run point, expected acceptance evidence, owner/pre-exposure gate and actual results or pending execution; label unvalidated allocation choices provisional.
- A scaling description by component with 5.2 managed API/quota or self-hosted instance-capacity reference and inference-replica sizing only when self-hosted, replica ownership, supported signal/target, minimum/maximum capacity, warm-up/replacement behavior, normal overload response, async transport/contract reference and durable-state binding.
- A shared-resource protection plan with dependency, normal-load quota or concurrency budget, enforcement owner/boundary, backlog depth/age limits where used, admit/wait/reject/defer behavior and monitoring-signal reference.

*Technique reference: `references/stage-5-deployment.md` (routing and scaling).*

### 5.4 State persistence and lifecycle

Bind the approved pause, checkpoint and replay contracts to the deployed run-state backend. This aspect owns store topology, durability and loss limits, expiry execution and restart/resume coordination. Reference approval policy in 1.3, workflow routes in 2.3, checkpoint payload in 3.2 and call replay guarantees in 3.1; memory and business-store definitions remain with 2.4/3.5. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- In the storage decision table, select the run/checkpoint backend for the actual topology, concurrency and consistency needs; record its persistence mode, measured or documented loss/recovery limit, retention-policy reference, owner and operating trade-offs.
- Check that backend retention and platform limits support the approval window in 1.3; record retention in the storage decision table, expiry/deletion execution in the lifecycle sequence and the approved expired-run outcome in the recovery contract, reopening 1.3 if the window cannot be supported.
- In the lifecycle sequence, specify persisted outcome and restart route for each interruption point, with a recovery fixture/procedure, expected preserved/pending/expired outcome, owner and pre-exposure gate; attach actual results for an existing environment or pilot and mark unperformed tests pending.
- Reference the 3.2 checkpoint payload in the lifecycle sequence and specify deployment write cadence, interruption boundaries, sensitive-data handling and rerunnable steps; define the resume-validation procedure and expected payload evidence, attaching available results or owner/gate for pending execution.
- In the recovery contract, specify trusted checkpoint loading, verification of the saved owner/version and pending action against the 3.2 schema, binding to the authorized 1.3 decision and the mechanism that claims one continuation; record rejection of stale or duplicate resumes.
- For each side-effecting action, reference the 3.1 replay contract and 3.2 operation identity in the deployment idempotency record; specify durable outcome location, atomic write/claim boundary and key lifetime, plus ambiguous-result reconciliation fixture, expected outcome, owner and pre-exposure gate, with actual result or pending execution.
- In the recovery contract, bind consequential resume to the 2.3/2.6 mutable-fact, permission and dependency checks; name source/owner and specify tests for replan, renewed approval or stop after changed premises, with expected outcome and required pre-exposure result or pending execution.

**Output**
- A run/checkpoint storage decision table with topology, concurrent writers, persistence mode, consistency, durability/loss and recovery limits, retention and approval-window references, ownership and operating trade-offs.
- A deployed run-state lifecycle sequence with checkpoint-schema reference, creation/write cadence, interruption boundaries, rerunnable step IDs, pause, expiry/deletion job, restart routes and safe-restart evidence. Include restart fixture/procedure, expected evidence, owner/gate and current result or pending execution. Include the approved sensitive-data handling/minimization binding for checkpoint writes and retained payloads.
- A deployed recovery contract referencing the approved run/checkpoint schema and authority policy, with trusted load/owner/action checks, decision binding, single-continuation claim, live revalidation sources, stale/duplicate/expired outcomes and test evidence. Include stale/duplicate/changed-premise test procedures, expected outcomes, owner/gate and actual results or pending execution. Name each live revalidation check's source/owner and approved changed-premise replan, renewed-approval or stop route.
- A deployment idempotency and reconciliation record per side-effecting action with 3.1 call-contract and 3.2 identity references, durable outcome-ledger location, atomicity/claim boundary, key-lifetime realization and ambiguous-result recovery test. Include ambiguous-effect test fixture/procedure, expected recovery evidence, owner/gate and available result or pending execution.

*Technique reference: `references/stage-5-deployment.md` (state persistence).*

### 5.5 Release security and compliance checks

Verify the approved authority, security, data and audit controls in the actual release environment. This aspect owns release-candidate test evidence, third-party review and residual-risk disposition. Reference obligations in 1.4, enforcement/security design in 2.6/2.9 and evaluation/telemetry definitions in Stage 4; supply safety and readiness evidence to 5.1 and 5.6. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- Where model-directed code or untrusted artifacts execute, specify deployment tests for 2.9 isolation, filesystem/network and credential separation in the release checklist; for controlled function paths, specify scoped-call authorization tests. Record fixture/procedure, expected outcome, owner/gate and available results or pending execution.
- For each applicable 1.4 obligation and 2.6 access control, bind its ID to the proposed enforcement point/version and verification procedure in the release checklist; record expected evidence, accountable owner, pre-exposure gate and actual result/exception disposition or pending prerequisite.
- Where content risk applies, specify deployment moderation/action-guardrail tests using 4.1 cases and 4.2 measures in the release checklist; name expected missed-harm/false-block evidence, version, owner and gate, attach results when available, and pass the test-plan/result references to 5.1.
- In the release checklist, inventory proposed or existing third-party Skills, MCP servers, models, dependencies and sources by version/provenance/permissions; specify injection and secret-exposure verification with expected evidence, owner/gate and current result or pending execution, including model-visible content and telemetry.
- Select reachable 2.9 misuse, injection and consequential-action paths for the adversarial test summary; specify release component/fixture, procedure, expected safe outcome, reviewer and gate, recording available results/mitigations/residual risk or pending execution and proposed mitigations.
- In the release checklist, specify deployment tests of required 4.4 audit capture, redaction, access, retention and deletion; bind expected evidence and owner to each obligation and pre-exposure gate, attaching current results or a pending implementation/release prerequisite.

**Output**
- A release security and compliance checklist with approved obligation/control reference, deployed component/version, control owner, case/evaluator or test reference, evidence, result, exception, residual-risk acceptance and release disposition. For unperformed checks, specify fixture/procedure, expected evidence, execution owner, pre-exposure gate and pending prerequisite; attach actual results only where available.
- Where adversarial testing applies, a scenario and result summary with approved threat/path reference, release version, test, result, mitigation, residual risk and reviewer. Include executable scenario/fixture and expected safe outcome, owner/gate and actual results or pending execution/proposed mitigation.

*Technique reference: `references/stage-5-deployment.md` (release checks).*

### 5.6 Rollback and cost governance

Specify executable release actions and aggregate spend controls for the deployed service. This aspect owns the promotion, pause, stop, revert and reconciliation playbook, traffic-class spend enforcement and ordered response to budget or load pressure. Reference Stage 4 verdicts, the targets in 1.4, task-call budgets in 3.6 and supported capacity/controls in 5.2–5.4; provide signal and action references to Stage 6. At design time, specify executable checks and expected evidence; attach available environment/pilot results and label unperformed checks with owner and pre-exposure gate.

**Requirements**
- In the release-action table, map 4.5 verdicts and 5.1 exposure stages to promotion/pause/stop/revert; specify operator and traffic/config/code procedure, state-compatibility and irreversible-effect reconciliation/compensation tests, expected evidence and pre-exposure gate, with available results or pending execution.
- Ask the user to confirm protected traffic and alert-only versus enforced service limits; record aggregate workflow/traffic-class allocations, enforcement boundary and limit response in the cost-governance decision, referencing the 1.4 financial objective and 3.6 per-task enforcement.
- In the pressure-degradation ladder, order supported overrides to 5.3 normal admission/model allocation, serving caches and permitted provider routes; specify trigger reference, quality/freshness/privacy/residency/cost validation, expected evidence, owner, stop/restoration rule and gate, recording measured effects when available or pending validation.
- In the cost-governance decision, select usage and billed-cost sources, reporting-delay assumptions, reconciliation owner/cadence and limit-warning headroom; reference the 4.2 cost-per-success/token/tool measures and require their collection and anomaly alerts through 6.4.

**Output**
- A release-action and recovery table with 4.5 gate/verdict reference, 5.1 exposure stage, promotion/pause/stop/revert action, operator, tested traffic/config/code procedure, state-compatibility disposition and external-effect reconciliation/compensation evidence. Distinguish planned recovery procedures from completed tests; include expected evidence, test owner/gate and result or pending prerequisite before exposure.
- A cost-governance decision with approved financial/task-budget references, aggregate workflow/traffic-class allocations, alert/enforcement choice and boundary, protected traffic, limit response, usage/billed sources, delay/reconciliation owner/cadence and warning headroom. Include the 4.2 cost/token/tool metric references and the 6.4 collection/alert handoff.
- A prioritized pressure-degradation ladder with approved trigger/metric reference, selected supported override, measured quality/data/cost effect, stop condition, owner and restoration rule, referencing normal-load configuration from 5.2/5.3. Include validation procedure and expected acceptance evidence, owner/gate and measured effect or pending validation before use.

*Technique reference: `references/stage-5-deployment.md` (rollback and cost).*

**Deliver and confirm:** Stage 5 Word document with the rollout plan, serving and scaling decisions, persistence design, and the release security, rollback, and cost-governance rules.


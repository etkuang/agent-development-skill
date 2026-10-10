# Stage 5 — Deployment

**Current deliverable:** `05-deployment.docx`.

This contract defines the Stage 5 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain ordinary aspect headings and required end matter, briefly explain inapplicable ordinary aspects, and omit unselected optional aspects. Record unresolved information that affects a needed decision.

Establish serving, state, capacity, controls and recovery before planning exposure. Each selected deployment check identifies environment/version, fixture, procedure or runner, run point, expected evidence, owner and gate. Attach actual implementation/pilot results when available; otherwise mark execution pending. Required quality, capacity, security and recovery evidence must pass before the corresponding adoption or exposure.

## 5.1 Serving and capacity

### To clarify

- Is inference managed or self-hosted, and which service boundary and controls does the application own?
- What arrivals, prompt/output sizes, cache state and task mix represent load?
- Which supported serving optimization or approved compression artifact needs a baseline comparison?
- What accepted load meets task quality, latency and cost objectives at that boundary?

### output

- **Serving decision/runtime record:** approved model/API/runtime revision, managed quota boundary or owned inference instance, exposed settings and support sources. Record hardware/precision only for self-hosting; managed internals remain provider-owned.
- **Optimization comparison:** when a change is proposed, comparable workload, baseline/candidate settings, quality/latency/throughput/cost and observable memory effects, result or pending check, rationale and adoption gate.
- **Capacity plan/evidence:** representative fixture and arrivals/concurrency, input/output sizes, observable cache state/tool mix, accepted request/token load, queue/completion latency and quality criterion references. Include streaming/GPU measures only when relevant and observable.
- **Capacity handoff:** versioned procedure/runner/run point, expected evidence, owner/pre-exposure gate and actual result or pending execution for 5.3 sizing. Revisit the model-method owner when a deployment test invalidates an approved compression choice.

### out of scope

Do not change model roles/methods or request arguments here. Application replicas, gateway/dependency admission and workload allocation belong to 5.3; recovery/pressure overrides to 5.5.

### Prerequisite

Consult approved 1.4 and 1.6, 2.5 and selected 2.7 model decisions, 3.2 calls, 3.5 budgets and 4.1/4.5 quality/evidence criteria.

### Technical references

- When defining managed or owned serving capacity, see [serving-boundary-and-capacity.md](technological%20documentations/serving-boundary-and-capacity.md) for reference.
- When self-hosted inference needs supported runtime optimization, see [self-hosted-serving-optimization.md](technological%20documentations/self-hosted-serving-optimization.md) for reference.

## 5.2 Run-state persistence and lifecycle (optional)

### To clarify

- Which approved pause, checkpoint, async or replay path needs durable run state?
- What topology, concurrent writers, consistency and loss/recovery limit must the backend support?
- Do retention/platform limits support the approved pause or approval window?
- How are saved ownership/action/version, duplicate continuation, uncertain effects and changed premises checked on resume?

### output

- **Run/checkpoint backend decision:** persistence mode, topology/writers, consistency, durability/loss/recovery limits, retention/approval-window references, owner and operating trade-offs. Reference an owned platform backend instead of inventing another store.
- **Lifecycle sequence:** 3.1 payload binding, write cadence and interruption boundaries, sensitivity/minimization, pause, expiry/deletion and restart routes. Record preserved/pending/expired outcomes and selected recovery fixtures/checks.
- **Trusted resume contract:** saved owner/version/pending-action checks, exact authorized decision binding, single-continuation claim, stale/duplicate rejection and live permission/fact/dependency revalidation with source/owner and approved replan/reapproval/stop outcomes.
- **Effect reconciliation binding:** when writes exist, 3.2 replay/key contract and 3.1 operation identity, durable outcome ledger, atomic claim/write boundary, key lifetime and ambiguous-result reconciliation.
- **Recovery evidence:** interruption, duplicate/stale/expired/changed-premise and applicable uncertain-effect fixture, procedure, expected evidence, owner/pre-exposure gate and actual result or pending execution.

### out of scope

Do not add checkpointing to a path that does not need it. Logical workflow/context policy and payload fields stay with their earlier owners; application/evidence/memory store definitions remain in 3.6.

### Prerequisite

Consult approved 1.3–1.4, 2.3–2.4 and 2.9 authority/recovery, 3.1 checkpoint payload and 3.2 call replay/cancellation.

### Technical references

- When deploying durable checkpoint retention and restart, see [deployed-checkpoint-lifecycle.md](technological%20documentations/deployed-checkpoint-lifecycle.md) for reference.
- When resuming approved work with mutable facts or external effects, see [trusted-resume-and-effect-reconciliation.md](technological%20documentations/trusted-resume-and-effect-reconciliation.md) for reference.

## 5.3 Workload allocation, scaling, and admission

### To clarify

- Does the approved model/effort assignment remain fixed, or is a changed deployment allocation justified?
- What application concurrency/replicas and dependency quotas fit measured capacity?
- Which supported scaling signal and backlog/overload response serve the actual workload?
- Does work beyond the synchronous deadline require a selected asynchronous transport?

### output

- **Deployment allocation:** fixed approved route or workload-category mapping among approved model/effort candidates. Only a proposed changed/router allocation needs a fixed-versus-candidate experiment, including category errors, overhead, quality, tail latency and cost per success with expected evidence and pre-exposure gate.
- **Scaling description:** component and replica owner, 5.1 capacity reference, supported signal/target, minimum/maximum limits, warm-up/replacement and ordinary overload response. Size inference replicas only when self-hosted.
- **Shared-resource admission:** model request/token, store connections and third-party rate/concurrency budgets, enforcement boundary/owner and admit/wait/reject/defer behavior.
- **Async/backlog binding:** when selected, transport, 3.2 status/result/cancel/replay contract, backlog depth/age and optional 5.2 durable-state reference.
- **Verification record:** relevant load/admission/allocation fixture, runner/run point, criterion, evidence, owner/gate and observed result or pending assumptions.

### out of scope

Request/capability routing belongs to 2.6, model roles to 2.5 and call retry semantics to 3.2. This aspect owns normal-load deployment; incident suppression and exceptional pressure actions have later owners.

### Prerequisite

Consult approved 2.5–2.6, 3.2 and 3.5, 4.1 acceptance criteria, 5.1 capacity and selected 5.2 state binding.

### Technical references

- When changing deployed model or effort allocation, see [deployment-model-allocation.md](technological%20documentations/deployment-model-allocation.md) for reference.
- When sizing components, asynchronous backlogs or dependency admission, see [scaling-and-dependency-admission.md](technological%20documentations/scaling-and-dependency-admission.md) for reference.

## 5.4 Release security and compliance checks

### To clarify

- Which approved authority, threat, data and audit controls need verification in this release environment?
- Which reachable denial, injection, leakage or consequential-action cases test those controls?
- Which third-party versions/provenance/permissions and credential paths are being released?
- Who accepts residual risk or resolves missing control evidence?

### output

- **Release-control checklist:** approved obligation/control ID, deployed component/version, fixture/test/evaluator, expected safe result, execution owner, pre-exposure gate, actual evidence or pending prerequisite, residual-risk/exception owner and disposition.
- **Authority/isolation checks:** denied principals and alternate paths; selected executor filesystem/network/credential controls where execution exists. Ordinary controlled functions use their approved scoped-call enforcement.
- **Adversarial/content checks:** selected injection, secret exposure, misuse, missed-harm and false-block cases/measure references with result/mitigation or pending execution.
- **Third-party and audit verification:** exact artifact versions/provenance/access; credential and required trace allowlist/redaction/access/retention/deletion checks. Supply release readiness and the later operational audit baseline.

### out of scope

Verify selected controls without inventing new legal obligations or security architecture. New control or permission needs return to their Stage 1/2 owner. Continuous review belongs to Stage 6.

### Prerequisite

Consult approved 1.3–1.4, 2.3–2.4, 3.2 credentials, 4.1–4.5 cases/graders/export checks and applicable 5.1–5.3 deployment boundaries.

### Technical references

- When verifying selected controls in a release environment, see [release-control-verification.md](technological%20documentations/release-control-verification.md) for reference.
- When testing protected trace export in the deployment, see [sensitive-telemetry-export.md](technological%20documentations/sensitive-telemetry-export.md) for reference.

## 5.5 Release recovery and cost governance

### To clarify

- Which evaluation/readiness outcomes authorize promotion, pause, stop or revert, and who executes each action?
- What application/configuration/traffic recovery is possible, and are retained-state compatibility or external effects involved?
- Which aggregate traffic-class limits are alert-only or enforced, and which traffic is protected?
- What supported pressure override preserves approved quality/data constraints, and how is normal service restored?

### output

- **Release-action playbook:** verdict/condition reference, promotion/pause/stop/revert action, authorized operator, traffic/config/code procedure and restoration evidence. Include state compatibility only where retained state is affected and external-effect reconciliation/compensation only where effects exist.
- **Recovery test plan/results:** applicable environment/fixture, runner/run point, expected outcome, owner/gate and completed evidence or pending prerequisite before exposure.
- **Aggregate spend governance:** 1.4 objective and 3.5 task-budget references, workflow/traffic-class allocations, protected traffic, warning versus enforced boundary/response, usage/billed sources, delay/headroom and reconciliation owner/cadence.
- **Pressure-response ladder:** selected overrides to normal 5.1/5.3 configuration, trigger, expected/measured quality/freshness/privacy/residency/latency/cost effect, validation gate, operator, stop/restoration rule. Hand tested action/limit IDs to operations.

### out of scope

Do not redefine evaluation thresholds, per-task budgets or normal serving/scaling settings. This aspect defines executable release and pressure actions; 5.6 maps them to exposure stages, and Stage 6 operates dependency-specific incidents.

### Prerequisite

Consult approved 1.3–1.4, 3.2 and 3.5, 4.1/4.5 verdict conditions and applicable 5.1–5.4 deployment, state and control evidence.

### Technical references

- When defining release revert and applicable external-effect recovery, see [release-recovery-planning.md](technological%20documentations/release-recovery-planning.md) for reference.
- When choosing aggregate limits and reconciling delayed billing, see [aggregate-spend-enforcement.md](technological%20documentations/aggregate-spend-enforcement.md) for reference.
- When selecting exceptional load or spend-pressure overrides, see [pressure-degradation-selection.md](technological%20documentations/pressure-degradation-selection.md) for reference.

## 5.6 Rollout and exposure readiness

### To clarify

- Which users/traffic may be exposed, who authorizes it, and what release risk is accepted?
- Is a pilot, staged rollout or comparable candidate/control canary appropriate?
- What allocation, observation window and minimum evidence permit each exposure increase?
- Which quality, capacity, deployed-control and recovery checks must pass first?

### output

- **Rollout plan:** eligible traffic, assignment/exposure stages, initial allocation, observation windows, exposure owner and explicit execution authorization. Use comparable control cohorts when that comparison is selected.
- **Comparison design:** quality/safety/latency/cost/reliability criterion references from 4.1, comparability checks and evidence source. For rare/severe risks, identify required offline evidence rather than relying on a small live cohort.
- **Evidence-readiness table:** exposure stage, prerequisite/test ID, expected evidence, actual result or pending status, execution/readiness owner, gate and applicable 5.5 recovery-action reference. Name the readiness owner separately from the traffic-exposure owner.
- **Promotion/stop binding and handoff:** map stage evidence/verdicts to the existing 5.5 playbook; hand cohort/version and collection needs to Stage 6 monitoring. Pending required checks block the corresponding traffic exposure.

### out of scope

Do not redefine metric/evidence thresholds, serving capacity, security checks or recovery procedures. A design document is not a live release authorization or passing test result.

### Prerequisite

Consult approved 1.3–1.4, 4.1/4.5 acceptance/verdict contracts and applicable 5.1–5.5 capacity, controls and tested recovery readiness.

### Technical references

- When choosing staged exposure or a comparable canary and its readiness gates, see [canary-exposure-readiness.md](technological%20documentations/canary-exposure-readiness.md) for reference.

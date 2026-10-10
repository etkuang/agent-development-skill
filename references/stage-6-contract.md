# Stage 6 — Operations and iteration

**Current deliverable:** `06-operations-and-iteration.docx`.

This contract defines the Stage 6 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain ordinary aspect headings and required end matter, briefly explain inapplicable ordinary aspects, and omit unselected optional aspects. Record unresolved information that affects a needed decision.

Operate approved policies, deployed controls and existing evaluation definitions. Establish change/version governance before monitoring and response; maintain authored content before publishing capability versions. Planned initial checks identify fixture/environment, procedure or runner, expected evidence, owner and execution gate; operational records attach actual results. A new design, permission or limit returns to its authoritative stage owner.

## 6.1 Change governance and release manifests

### To clarify

- Who assembles the deployed artifact/version record and approves routine changes?
- Which material changes alter approved design decisions or require additional regression evidence?
- How do code, model, prompt/Skill, tool/schema, policy/configuration and relevant data versions map to releases/cohorts?
- Which tested recovery baseline and action apply to a candidate change?

### output

- **Change-review procedure:** affected owner/artifact, applicable 4.5 affected/full-suite policy, execution/review owner, evidence and pass/fail/inconclusive disposition under 5.5. Changed design decisions identify affected Word documents and renewed approval before dependent work.
- **Release-manifest scheme:** assembly owner, existing artifact IDs/versions/dependencies, evaluation evidence, deployed release/cohort mapping and tested recovery-baseline/action reference.
- **Change record:** candidate/comparison versions, reviewed reason, approved decision references, check results or pending prerequisites and authorized publication/exposure handoff. Do not fabricate production evidence for a new project.

### out of scope

This aspect owns the cross-artifact record and change gate, not prompt/Skill authoring, registry publication, case triage, obligation adjudication, metric definitions or execution of release actions.

### Prerequisite

Consult approved Stage 1 governance, 4.5 evaluation/version policy and Stage 5 deployment, recovery and exposure decisions.

### Technical references

- When linking artifact versions, regressions and renewed design approvals to releases, see [release-manifest-and-change-review.md](technological%20documentations/release-manifest-and-change-review.md) for reference.

## 6.2 Production monitoring and drift detection

### To clarify

- Which approved outcome, latency, cost, process and control measures can production observe?
- What source/query, segment, collection/sampling window and proxy limitation apply?
- Which ordinary level alerts and separate input-mix/behavior comparisons warrant investigation?
- Who receives each alert and which approved response or review does it invoke?

### output

- **Production observation map:** 4.1 metric and applicable 4.3 grader/4.4 event ID, source/query, task/version/cohort, collection/sampling window, unavailable evidence and online-proxy limitation.
- **Ordinary alert plan:** approved target/limit or comparable baseline, trigger/severity, delivery destination, accountable response role and selected runbook reference. Include token/tool/cost-per-success sources and reporting-delay/reconciliation bindings from 5.5.
- **Drift comparison:** separate input-mix and behavior/quality comparators, representative baseline/window, 6.1 manifest correlation, investigation trigger and owner.
- **Operational views:** where useful, end-to-end outcomes/duration, in-flight work, selected retry/repeated-state/revision/recovery series, cost per completion and trace/runbook links. Hand signals to incident, case-review, maintenance and applicable audit owners.

### out of scope

Do not redefine measures, thresholds, telemetry fields or deployed budget/scaling values. This aspect detects and routes evidence; incident action and root-cause disposition have separate owners.

### Prerequisite

Consult approved 4.1, 4.3–4.5, Stage 5 capacity/limits/cohorts and 6.1 version/manifest scheme.

### Technical references

- When binding approved metrics to production collection and alerts, see [production-metric-monitoring.md](technological%20documentations/production-metric-monitoring.md) for reference.
- When comparing input mix or behavior across production versions, see [production-drift-comparison.md](technological%20documentations/production-drift-comparison.md) for reference.

## 6.3 Dependency incidents and restoration

### To clarify

- Which reachable dependency failures activate shared cutoff, suppression, approved alternatives or handoff?
- Who owns health state across callers, probes and restoration evidence?
- Which deployed client/gateway and serving/admission controls implement the approved response?
- Who staffs a human referral, and what happens if it remains unclaimed?

### output

- **Dependency incident policy:** approved 3.2 failure/deadline/retry/replay/alternative contract, deployed control owner, activation signal, shared health/cutoff scope, suppression, probe cadence/expiry and restoration check.
- **Operational response map:** reachable transient, correctable, user-resolvable, denied and ambiguous-effect class, incident owner, approved continuation/stop/fallback and task-outcome/restoration evidence. Reconcile uncertain writes before retry or reassignment.
- **Staffed handoff binding:** authorized 1.3 context and 2.9 continuation, recipient queue/rota, user notice, response deadline and unclaimed action.
- **Restoration evidence:** selected baseline/alternate/restored route quality, state and data/authority checks; use 5.5 release/pressure actions and reference 5.1/5.3 configuration owners. Worker liveness/reassignment checks apply only to selected worker workflows.

### out of scope

This aspect operates approved dependency responses. New providers, serving values, route semantics or action permissions require their owning design revision; capability publication belongs to 6.6.

### Prerequisite

Consult approved 1.3, 2.9, 3.2, applicable 5.1–5.5 control/recovery contracts and 6.1–6.2 manifest/alert bindings.

### Technical references

- When operating dependency cutoff, probes and safe restoration, see [dependency-incident-recovery.md](technological%20documentations/dependency-incident-recovery.md) for reference.
- When an incident needs a staffed referral or worker reassignment, see [staffed-handoff-operation.md](technological%20documentations/staffed-handoff-operation.md) for reference.

## 6.4 Bad-case review and improvement loop

### To clarify

- Which permitted feedback and alert channels supply candidate issues?
- Which verified task outcome corroborates an explicit complaint or implicit signal?
- What reproducible evidence distinguishes a source, route, tool, state, policy, model or grader defect?
- Who owns the repair, regression-case admission and before/after outcome review?

### output

- **Intake/triage procedure:** permitted channels, trace/source/manifest references, urgent response target, routine review cadence, domain/engineering owners and disposition such as confirmed defect, non-defect or unresolved evidence.
- **Failure-attribution record:** issue, symptom, corroborating outcome/trace, reproducible input/environment, expected outcome/reviewer, cause hypothesis, affected decision, component/repair owner and selected validation check.
- **Versioned improvement loop:** issue-to-cause-to-fix-to-evaluation-to-release-to-observed-outcome links; submit reviewed cases to 4.2 under 2.8 admission rules. Use existing metric/verdict and release gates from 4.1/4.5/5.5/6.1.
- **Iteration view:** show urgent/routine intake and owner handoffs when useful; keep confirmed production failures distinct from training examples, which require an approved model-level remedy.

### out of scope

Do not redefine monitoring, canonical labels/fixtures, release gates or component implementation policy. Repeated requests, abandonment and negative feedback alone do not establish an agent defect.

### Prerequisite

Consult approved 1.3–1.4 data/handoff policy, 2.8 case admission, Stage 4 evaluation evidence and 6.1–6.3 change, signal and incident records.

### Technical references

- When reviewing bad cases and linking causes to validated improvements, see [bad-case-attribution-loop.md](technological%20documentations/bad-case-attribution-loop.md) for reference.

## 6.5 Prompt and Skill maintenance

### To clarify

- What approved prompt or selected Skill surface needs review?
- Is the problem in authored behavior, activation metadata or a missing runtime/file dependency?
- Which positive, negative, ambiguous, contextual and failure cases exercise the changed surface?
- What baseline/candidate evidence permits the content revision?

### output

- **Maintenance plan:** prompt version and selected Skill body/name/description surfaces, review trigger, owner, dependency/required-step check and repair handoff.
- **Affected regression mapping:** canonical 4.2 case versions, expected activation/outcome, applicable 4.1 metric/4.3 grader and isolation/coexistence coverage for selected Skills. Submit coverage gaps to the case owner.
- **Candidate evidence:** tested content/metadata versions, baseline comparison, verdict and recovery reference through 6.1; hand approved capability versions to 6.6 when publication is needed.

### out of scope

Do not require Skill activation checks for a prompt-only application. This aspect authors prompt/Skill content and Skill activation metadata; tool metadata and contracts return to 3.2. It does not publish registries, define new metrics or authorize releases.

### Prerequisite

Consult approved 3.2 capability metadata, 3.3 prompts, Stage 4 cases/criteria/graders and 6.1, 6.2 and 6.4 change, signals and reviewed issues.

### Technical references

- When maintaining prompts or selected Skill activation/execution surfaces, see [prompt-and-skill-regression.md](technological%20documentations/prompt-and-skill-regression.md) for reference.

## 6.6 Capability publication and routing maintenance (optional)

### To clarify

- Does the deployed design have a registry, discovery index or routing rules requiring version synchronization?
- Who publishes reviewed tool/Skill versions and confirms that advertised capabilities match deployment?
- Which misselection, recall, task-outcome or rule-regression checks are applicable?

### output

- **Publication/synchronization procedure:** owner, approved 3.2 tool and 6.5 Skill artifact references, registry/index/rule versions, deployment-health checks and tested restoration reference.
- **Discovery/rule maintenance record:** approved 2.6 design, deterministic rule owner, change/review trigger, selected canonical cases and 6.2 signals; recall checks only for retrieval-based discovery.
- **Change evidence handoff:** published versions and outcome/regression evidence to 6.1. Route authored Skill metadata changes to 6.5 and tool metadata or contract changes to 3.2.

### out of scope

Do not introduce discovery infrastructure for a single direct capability path or author another copy of tool/Skill descriptions. Incident health/suppression remains in 6.3.

### Prerequisite

Consult approved 2.6 routing/discovery, 3.2 tool contracts, and 6.1–6.2 plus 6.5 approved capability versions.

### Technical references

- When publishing capability versions or maintaining a selected discovery/routing registry, see [capability-registry-publication.md](technological%20documentations/capability-registry-publication.md) for reference.

## 6.7 Memory lifecycle operations (optional)

### To clarify

- Which retained memory classes selected in 2.1 need ongoing expiry, correction or deletion?
- Which raw/source and derived records must change together, and how is completion verified?
- Which write/access/provenance checks detect contamination or unauthorized use?
- What permitted history can support restoration without repeating external effects?

### output

- **Memory operations plan:** approved content/access/trust/store references, retention/expiry/growth jobs, correction/deletion owner and raw/derived completion checks. Check authorization after identity/permission changes and retrieval quality after pruning/consolidation.
- **Control verification:** risk-selected samples/triggers, reviewer, expected or actual evidence for write authority, intent, provenance, excluded secrets and permitted sensitive input; failed-control route.
- **Contamination response:** detection/containment owner, quarantine, source-to-derived impact tracing, correction/deletion and policy-permitted restoration verification; hand external effects to the recovery owner.
- **Lifecycle audit binding:** memory IDs, operation/reason, provenance and completion/retrieval-check evidence mapped to the approved 4.4 capture contract. New common telemetry fields return to its owner; this aspect owns memory-specific lineage semantics.

### out of scope

Active-context reduction remains in 2.1, payload/store design in Stage 3 and checkpoint operational resume in 5.2. Logs or a knowledge index alone do not establish selected agent memory. Do not redefine permitted retention or access.

### Prerequisite

Consult approved 2.1, 2.3–2.4 memory policy, selected 3.6 stores, 4.1/4.4 checks/capture and 6.1–6.3 change, signal and recovery bindings.

### Technical references

- When operating retention, correction or raw/derived memory deletion, see [memory-retention-and-deletion.md](technological%20documentations/memory-retention-and-deletion.md) for reference.
- When responding to poisoned, stale or harmful memory, see [memory-contamination-recovery.md](technological%20documentations/memory-contamination-recovery.md) for reference.
- When binding memory lifecycle evidence to audit capture, see [memory-lifecycle-audit.md](technological%20documentations/memory-lifecycle-audit.md) for reference.

## 6.8 Compliance evidence review (optional)

### To clarify

- Which confirmed obligations or required audit controls need recurring evidence review?
- What cadence, labeled samples or material changes trigger review?
- Who adjudicates missing evidence, missed harm, false blocks or changed applicability?

### output

- **Recurring review plan:** confirmed 1.4 obligation/control, deployed 5.4 test baseline, 4.1 measure and 4.4 audit reference, evidence sample/cadence, accountable reviewer and disposition/escalation.
- **Control-evidence checks:** completeness, attribution/integrity, authorized access and retention/deletion execution; selected adversarial rechecks after material tool/capability/permission/control changes.
- **Review record:** actual evidence and version, adjudication under approved criteria, missing-evidence action and affected owner. Changed obligation applicability returns to Stage 1; changed design follows 6.1 renewed approval.

### out of scope

This aspect reviews confirmed obligations and controls. It does not invent compliance duties, redefine common telemetry, assemble another release manifest or take ownership of incident restoration.

### Prerequisite

Consult approved 1.4 obligations, 4.1/4.4–4.5 evidence policy, 5.4 deployed baseline and applicable 6.1–6.7 change/operation records.

### Technical references

- When confirmed obligations require recurring protected evidence review, see [compliance-evidence-review.md](technological%20documentations/compliance-evidence-review.md) for reference.

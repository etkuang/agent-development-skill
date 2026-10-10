# Stage 2 — Development and model layer

**Current deliverable:** `02-workflow-and-technology-selection.docx`.

This contract defines the Stage 2 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain ordinary aspect headings and required end matter, briefly explain inapplicable ordinary aspects, and omit unselected optional aspects. Record unresolved information that affects a needed decision.

Use approved Stage 1 decisions as inputs. The order below establishes policies and capability needs before selecting integrations, routes and executable steps. Later-stage handoffs identify owners of additional detail; they are not prerequisites for approving this stage. If a candidate cannot satisfy an earlier decision, revise that owning decision rather than redefining it here.

## 2.1 Context and memory design

### To clarify

- What instructions, task state, dialogue, evidence and recalled records does each task need?
- Which information must survive another turn or a resumed run? Is cross-session memory selected in Stage 1?
- What content may be retained, for what purpose, scope and lifetime? How are corrections, conflicts and deletion handled?
- Is context reduction needed, and what identifiers, constraints, decisions, action outcomes and open work must it preserve?

### output

- **Context-layer decision:** distinguish active model context, resumable session state and selected cross-session memory; record purpose, logical backing, content/source pointers, read/write triggers, scope, lifetime and keep/exclude reasons. State when cross-session memory is absent.
- **Assembly and preservation policy:** instruction precedence, approved content sources, dialogue updates, evidence interface, continuity requirements and selected trimming, summarization, compaction or offloading method. Record preserved/discarded content, correction and recovery rules, and required continuity checks.
- **Memory lifecycle policy:** for selected retained records, define provenance, conflict/duplicate resolution, expiry and correction/deletion intent under Stage 1 data policy. A session evidence cache follows this lifecycle while source authority remains in 2.2.
- **Context-flow view:** show selected read/write, assembly and carry-forward relationships when a figure clarifies them. Hand payload fields to Stage 3 and operational procedures to Stage 6.

### out of scope

Evidence suitability and grounding belong to 2.2; authorization and threat controls to 2.3 and 2.4. This aspect does not select vendors, executable nodes, physical schemas, numerical reduction triggers or deployed checkpoint storage.

### Prerequisite

Consult approved 1.2–1.5 decisions for required outputs, evidence, authority, data retention and selected memory needs.

### Technical references

- When choosing active, session and cross-session context layers, see [context-layer-design.md](technological%20documentations/context-layer-design.md) for reference.
- When selecting a context-preservation or reduction method, see [context-reduction-selection.md](technological%20documentations/context-reduction-selection.md) for reference.

## 2.2 Evidence retrieval and knowledge sources (optional)

### To clarify

- Which approved sources supply the needed evidence, and what authority, scope, version and freshness make them suitable?
- Can direct structured or live access meet the task, or is a derived search index justified?
- What extraction and provenance do representative documents require?
- What evidence makes an answer supported, partial or insufficient? When should another search or authorized referral occur?
- Which domain terms, formulas or dimensions need an authoritative definition?

### output

- **Source catalogue and route decision:** source ID, owner, format, authority/scope/version, freshness, correction/withdrawal needs, required access features and direct, lexical, vector, hybrid or reranked route. Compare viable routes on representative questions and reference evidence.
- **Processing and lineage design:** selected access, parsing/OCR/layout, metadata, segmentation, embedding and ranking responsibilities; preserve source/version and page, section, table or image locators. Show lineage when useful and define propagation of source changes to derived evidence.
- **Evidence-adequacy and grounding policy:** fixed or iterative search, query-preservation needs, adequacy/further-search/termination meanings, source precedence and conflict handling, claim/citation support and insufficient-evidence outcomes under 1.2.
- **Domain semantic definitions:** authoritative terminology, formulas, dimensions/filters, owner and effective version where needed. Identify retrieval-setting and storage handoffs to Stage 3.

### out of scope

This aspect owns source meaning and evidence adequacy. It does not own caller entitlements, context retention, provider selection, executable search-loop transitions, exact retrieval parameters or evaluation/training dataset preparation.

### Prerequisite

Consult approved 1.2, 1.4 and 1.5 for claim support, accepted sources and retrieval scope, and 2.1 for dialogue/context inputs.

### Technical references

- When choosing direct access or a search/index route, see [retrieval-route-selection.md](technological%20documentations/retrieval-route-selection.md) for reference.
- When choosing document processing and preserving evidence lineage, see [source-processing-and-lineage.md](technological%20documentations/source-processing-and-lineage.md) for reference.
- When defining evidence adequacy, source precedence and supported claims, see [evidence-adequacy-and-grounding.md](technological%20documentations/evidence-adequacy-and-grounding.md) for reference.
- When queries depend on business terminology or formulas, see [domain-semantic-definition.md](technological%20documentations/domain-semantic-definition.md) for reference.

## 2.3 Identity and access control

### To clarify

- What verified subject and acting identity apply to each protected resource and action?
- Should the application delegate user access or use an accountable service identity?
- Where will trusted code enforce authorization before protected content or an action reaches a consumer?
- How do permission changes reach indexes, caches and alternate paths?

### output

- **Identity and permission design:** protected path, verified subject/actor, delegation or service identity, resource/action, consent/scope, conditions, accountable policy owner and allow/deny outcome. A uniform single-user path may use a short record.
- **Enforcement map:** least-privilege scopes and default-deny rules under approved authority; source, gateway, tool and alternate-path checks; trusted caller filtering; denial behavior; and approved masking/audit hooks. Routing confidence cannot grant access.
- **Access-propagation plan:** when derived stores exist, define ACL/tenant metadata scope, entitlement-change/removal propagation and denied-principal/alternate-route verification needs. Hand exact authentication and storage bindings to Stage 3.

### out of scope

Do not redefine Stage 1 authority or data policy. Source withdrawal belongs to 2.2; instruction, argument and executor integrity to 2.4; credential protocols and physical ACL fields to Stage 3.

### Prerequisite

Consult approved 1.3 and 1.4, 2.1 retained-content scope, and 2.2 protected sources when retrieval is selected.

### Technical references

- When choosing identities and trusted permission enforcement, see [trusted-authorization-enforcement.md](technological%20documentations/trusted-authorization-enforcement.md) for reference.
- When permissions must propagate to indexed or cached content, see [indexed-access-propagation.md](technological%20documentations/indexed-access-propagation.md) for reference.

## 2.4 Trust boundaries and security

### To clarify

- Which untrusted requests, sources, tool results, third-party components or retained records can influence execution?
- Which reachable misuse or authority-confusion path needs an additional control?
- Does the actual executor require isolation, and which filesystem/network/credential resources may it use?
- How are secrets, safe user diagnostics and exact-action approvals protected?

### output

- **Threat/control map:** reachable input/component, provenance, trust boundary, control and reject outcome, permission reference, owner, verification need and residual risk. Cover selected injection, argument/result integrity, memory poisoning and approval-mismatch paths.
- **Executor-isolation decision:** selected process/user/data separation and permitted host/filesystem/network resources for an actual execution path, with owner and rationale.
- **Secret and diagnostic policy:** trusted secret source and scoped consumers, provisioning/rotation/revocation ownership, exclusion from model and public outputs, safe error category/correlation information and protected diagnostics.
- **Approval-integrity design:** for gated actions, bind the authorized decision to the action, arguments and call identity, with expiry/mismatch outcomes. Hand controls to 2.9 for placement.

### out of scope

Authorization belongs to 2.3. Ordinary quality, evidence, replay, race and progress decisions remain with their functional owners; add security controls only for reachable threats. Exact schemas, credential calls and deployed verification belong to later stages.

### Prerequisite

Consult approved 1.3 and 1.4, 2.1 content semantics, 2.2 evidence inputs where selected, and 2.3 authorization.

### Technical references

- When selecting controls for reachable agent threats, see [agent-threat-control-selection.md](technological%20documentations/agent-threat-control-selection.md) for reference.
- When an execution path needs isolation, see [executor-isolation-selection.md](technological%20documentations/executor-isolation-selection.md) for reference.
- When protecting credentials and diagnostic outputs, see [secrets-and-safe-diagnostics.md](technological%20documentations/secrets-and-safe-diagnostics.md) for reference.

## 2.5 Tools, services, providers, and model roles

### To clarify

- Which existing infrastructure, user preferences and local/hosted constraints shape viable integrations?
- Which required features does each capability need at its actual endpoint, account, region and deployment mode?
- Can one model/effort assignment meet the roles, or does representative evidence justify separation?
- What source metadata, write guarantees, failure behavior and authorized alternatives must a dependency support?
- Does a remote participant need a delegated goal rather than an ordinary tool/service call, and which discovery, authentication, task and artifact capabilities must its protocol support?
- Do account eligibility or scheduled product restrictions affect the project's intended operating period?

### output

- **Integration catalogue and selection record:** top-level services and their adapters/providers, capability purpose and read/write scope, Skill/application/API/provider-tool/MCP form, product/version, execution owner, connection mode, required-feature evidence, limitations and viable alternatives.
- **Model-role decision:** shared versus separate model/effort assignments, representative quality/latency/cost/failure evidence or measurement needs, selected roles and rationale.
- **Source-to-integration binding:** map selected 2.2 routes to integrations that support required live/snapshot access and source/version/locator metadata.
- **Dependency guarantees:** supported replay, idempotency, transaction and outcome-query behavior for writes; failure limits and authority-equivalent alternatives for critical dependencies. Hand exact call defaults and protocols to Stage 3.
- **Applicable interoperability and lifecycle evidence:** selected remote-agent protocol/revision/binding and supported discovery, task, update and artifact capabilities; account eligibility and relevant dependency retirement dates, alternative and migration owner. The workflow aspect consumes these guarantees; Stage 3 binds exact calls and state fields.

### out of scope

This aspect selects capabilities and products. It does not redefine evidence, authorization or threat policy, choose request routes or executable recovery, or write exact tool metadata, arguments and deployment settings.

### Prerequisite

Consult approved 1.4 and 1.6 constraints/architecture and 2.1–2.4 capability, data, access and security needs.

### Technical references

- When selecting integration products and model roles, see [integration-and-model-role-selection.md](technological%20documentations/integration-and-model-role-selection.md) for reference.
- When a selected integration can change external state, see [safe-retry-and-write-reconciliation.md](technological%20documentations/safe-retry-and-write-reconciliation.md) for reference.
- When selecting integration with an agent across a system boundary, see [remote-agent-integration-selection.md](technological%20documentations/remote-agent-integration-selection.md) for reference.
- When account eligibility or scheduled provider changes affect a proposed dependency, see [provider-lifecycle-availability-check.md](technological%20documentations/provider-lifecycle-availability-check.md) for reference.

## 2.6 Intent recognition and routing

### To clarify

- Does one supported path suffice, or do distinct requests need different handlers?
- Which requests require clarification, exclusion, abstention or authorized referral?
- How are multiple intents and rule/model disagreements resolved?
- Do scores or capability discovery add enough measured benefit to justify their cost?

### output

- **Request-selection decision:** compare one path with justified rule/model/routing alternatives on representative approved requests; record selected handlers, request boundaries, multi-intent treatment and wrong-route consequences.
- **Selection-outcome map:** task IDs and supported, ambiguous, excluded, abstaining and handoff outcomes under 1.2 and 1.3; reference independent access/security checks.
- **Arbitration and score policy:** when used, rule/model precedence, disagreement outcome and calibrated score-based decision with held-out checks and consequence-aware thresholds. Record unused scores or arbitration as inapplicable.
- **Capability-discovery decision:** direct/shared selection or selected deferred loading/candidate retrieval, its context/selection rationale and recall/task-outcome/overhead checks. Hand exact descriptions to Stage 3 and transitions to 2.9.

### out of scope

Evidence adequacy belongs to 2.2, permission to 2.3, product/model roles to 2.5 and executable branching to 2.9. Do not introduce a router or classifier when a single path meets the approved tasks.

### Prerequisite

Consult approved 1.1–1.3 and 2.2–2.5 for supported tasks, outcomes, independent checks and available capabilities.

### Technical references

- When choosing request handlers or multi-intent arbitration, see [request-routing-selection.md](technological%20documentations/request-routing-selection.md) for reference.
- When numerical scores select routes, see [routing-score-calibration.md](technological%20documentations/routing-score-calibration.md) for reference.
- When capability-catalogue size or selection errors warrant discovery, see [capability-discovery-selection.md](technological%20documentations/capability-discovery-selection.md) for reference.

## 2.7 Model customization (optional)

### To clarify

- What measured behavior, quality, cost or latency gap remains after the strongest feasible untuned baseline?
- Which training, alignment, distillation, quantization or context-adaptation methods are available for the selected model and account?
- What data roles, compute, exposed controls and retained-capability checks does a candidate require?

### output

- **Method decision:** residual gap, untuned baseline, supported candidates, capability/compute/memory/cost trade-offs, selection or rejection and supporting evidence.
- **Training/control strategy:** when training is selected, exposed controls/defaults and fix/search/omit choices, required demonstration/preference/reward data roles, validation needs and supported retained-capability remedies. Inference-only compression omits training controls.
- **Comparison plan:** target and retained-task needs, common held-out comparison, adoption criteria and pending experiments. Hand dataset supply to 2.8, exact controls to Stage 3, formal scoring to Stage 4 and serving compatibility to Stage 5.

### out of scope

Do not prepare datasets, invent unavailable provider controls, select final evaluation graders or deployment hardware here. Dataset composition belongs to 2.8; exact training values belong to Stage 3.

### Prerequisite

Consult approved 1.2, 1.4 and 1.5, and 2.5 model roles plus applicable 2.6 routing choices and existing representative baseline evidence.

### Technical references

- When a residual gap justifies model customization or compression, see [model-customization-selection.md](technological%20documentations/model-customization-selection.md) for reference.

## 2.8 Dataset engineering

### To clarify

- What permitted reviewed cases support evaluation, route calibration or selected training?
- What labels, task/user coverage and adjudication establish usable examples?
- Which partitions and duplicate-family protections prevent leakage?
- Which preparation or augmentation addresses an actual gap, and how will reviewed failures be admitted?

### output

- **Dataset-supply plan:** purpose, source/permitted use, version/size rationale, access/owner, coverage/gaps, label meaning and quality/adjudication, applicable partitions and calibration/final-test separation.
- **Preparation decision:** selected cleaning, augmentation, sequence preparation or replay composition, documented need, evidence/label preservation and held-out checks.
- **Reviewed-case admission procedure:** permission, provenance, reviewed expected outcome/label, approved destination/version, overlap checks and offline validation. Future production cases need not already exist.
- **Handoff record:** case and dataset needs for workflow checks and Stage 4; selected training roles reference 2.7 rather than creating another model-method plan.

### out of scope

Source-corpus parsing and cleansing belong to 2.2. This aspect supplies data; Stage 4 owns canonical executable evaluation fixtures, measures, graders and run verdicts.

### Prerequisite

Consult approved 1.2 acceptance seeds, 1.4 data policy, 2.5–2.6 role/routing needs and 2.7 data requirements when customization is selected.

### Technical references

- When planning reviewed data supply and leakage-resistant partitions, see [dataset-supply-and-partitioning.md](technological%20documentations/dataset-supply-and-partitioning.md) for reference.
- When data needs cleaning, augmentation or sequence preparation, see [dataset-preparation-selection.md](technological%20documentations/dataset-preparation-selection.md) for reference.
- When admitting reviewed historical or production cases, see [reviewed-case-admission.md](technological%20documentations/reviewed-case-admission.md) for reference.

## 2.9 Workflow and node responsibilities

### To clarify

- What direct, code or graph path executes the selected decisions?
- Which step belongs to trusted code, a model or a human, and what conceptual input/result does it own?
- Which dependencies permit parallel work, and who joins results and resolves shared updates?
- Which reachable failures need retry, correction, reconciliation, deferral, stop or handoff?
- Which progress, attempt, loop, time and concurrency controls are needed for actual tasks?

### output

- **Executable workflow view:** selected entry/exit, steps, routes, conditions, loops, joins and pause/resume boundaries; use Mermaid when useful. For a selected graph, identify real registered nodes and distinguish conditions/stores from executable work. Label proposed versus verified implementation.
- **Step-responsibility table:** exclusive purpose, trusted-code/model/human owner and rationale, conceptual inputs/result or update, referenced policies and next outcome. Map retained/replaced/new components for an existing project.
- **Coordination contract:** selected branches/workers, prerequisites/readiness, delegated authority, minimum worker context, shared-field ownership, acceptance/join rule and independent/failed-branch treatment under 1.2.
- **Recovery and progress controls:** reachable failure categories, finite replay/retry/cutoff and approved alternative/handoff, uncertain-write reconciliation, preserved successes, stalled/drifting/repeated-work response, trigger/limit basis, enforcement point and verification need. Hand typed state and numerical limits to Stage 3 and deployed durability to Stage 5.

### out of scope

Execute the preceding aspects' decisions by reference; do not repeat their policies or invent another answer-review layer. Exact schemas, prompts, call deadlines, budget values, checkpoint backends and release actions belong to later stages.

### Prerequisite

Consult approved 1.2, 1.3 and 1.6 and applicable 2.1–2.8 decisions for task outcomes, architecture, policies, selected capabilities, routes and available cases.

### Technical references

- When translating the selected path into executable steps, see [executable-workflow-design.md](technological%20documentations/executable-workflow-design.md) for reference.
- When coordinating parallel branches or worker agents, see [branch-coordination-design.md](technological%20documentations/branch-coordination-design.md) for reference.
- When selecting recovery for reachable workflow failures, see [workflow-recovery-selection.md](technological%20documentations/workflow-recovery-selection.md) for reference.
- When long tasks need progress or stalled-work controls, see [long-task-progress-control.md](technological%20documentations/long-task-progress-control.md) for reference.

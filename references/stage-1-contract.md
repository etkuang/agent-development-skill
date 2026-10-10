# Stage 1 — Requirements and architecture

**Current deliverable:** `01-requirements-and-architecture.docx`.

This contract defines the Stage 1 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain the shared aspect headings and required end matter, and briefly explain inapplicable aspects. Record unresolved information that affects a needed decision.

The Mermaid layer diagram in 1.6 is required for every project; scale its detail to the design.

## 1.1 Business goals, scope, and users

### To clarify

- What business problem should the first release solve?
- Who performs and receives each task? What steps, handoffs, exceptions and bottlenecks exist today?
- Which tasks are included, excluded or deferred? What business prerequisites constrain the first release?
- What observable improvement would justify the project? Which baselines are available?

### output

- **Business and scope decision:** problem, first-release tasks, exclusions, deferrals and business prerequisites.
- **User and current-workflow description:** task participants, business responsibilities, current steps, handoffs, exceptions and bottlenecks.
- **Business-indicator table:** priority need, observable benefit, indicator, baseline or collection action, desired improvement and measurement approach.
- **Assumption log:** uncertain premise, evidence or status, owner, validation action and effect on scope or benefit.

### out of scope

Functional acceptance belongs to 1.2; acting permissions and approvals to 1.3; service responsibilities, governance and per-task cost or latency targets to 1.4. Technique and architecture choices belong to 1.5 and 1.6.

### Prerequisite

None.

### Technical references

- When translating a business need into a measurable improvement, see [requirement-to-indicator-translation.md](technological%20documentations/requirement-to-indicator-translation.md) for reference.

## 1.2 Functions, outputs, and acceptance

### To clarify

- For each included task, what input, audience, output format and observable end state define completion?
- Which functions have priority, and what constraints distinguish an acceptable result from an unacceptable one?
- Which outputs require sources? What identifiers or locators must let the user check a supported claim?
- Which missing-input, ambiguous, partial, failed or stopped outcomes are reachable? What should the user see, and when can verified completed parts remain useful?
- Which real task examples can demonstrate functional correctness and communication quality separately?

### output

- **Prioritized function table:** function ID, linked scope item, priority, input, audience, output format, end state, constraints, completion evidence, communication criteria and representative acceptance case.
- **Claim-support requirements:** source-dependent output, required citation identifiers and locators, and the response when support is insufficient.
- **Outcome and failure table:** reachable condition, user-visible response, completion status and whether verified partial results may be retained. Record the visible review-pending outcome if relevant; 1.3 determines when approval is required.
- **Out-of-scope response table:** reference the exclusions in 1.1 and state the decline, redirect or handoff response.
- **Real-task acceptance seed:** real input and source, linked function, acceptable end state, required or prohibited constraints and review criterion. Keep correctness and communication checks distinct.

### out of scope

Do not redefine the scope in 1.1. Permission and approval policy belongs to 1.3, accepted-source policy and cost or latency targets to 1.4. Routing, retries, grounding implementation and executable limits belong to Stages 2 and 3; Stage 4 expands the seed and defines scoring.

### Prerequisite

Consult 1.1 for included tasks, users, expected benefits and scope boundaries.

### Technical references

- When choosing representative real-task acceptance examples, see [task-acceptance-seed.md](technological%20documentations/task-acceptance-seed.md) for reference.
- When choosing responses to reachable ambiguity, missing inputs or incomplete execution, see [output-failure-behavior.md](technological%20documentations/output-failure-behavior.md) for reference.
- When defining traceable support for source-dependent answers, see [answer-evidence-traceability.md](technological%20documentations/answer-evidence-traceability.md) for reference.

## 1.3 Authority and human involvement

### To clarify

- Which user, agent or service identity acts on each task? Which resources may it read or change, and who grants that authority?
- Which consequential actions require clarification, review, explicit approval or a stop? What authority and evidence must exist before proceeding?
- Who may approve each action, what action and context must they see, and what happens if approval is denied or unavailable?
- When is human referral needed? Which role may receive it, and what task information may be transferred?

### output

- **Actor-and-access matrix:** task, acting identity, logical role, permitted resources and actions, data visibility and accountable authority owner.
- **Approval matrix:** action, impact and reversibility, applicable authority policy, evidence conditions, review or stop trigger, authorized reviewer, information presented, decision window where needed, and denial or unavailable outcome linked to 1.2. Include expiry or revocation rules when applicable. Model confidence does not grant authority.
- **Human-handoff policy:** trigger, authorized receiving role, user notice and permitted payload covering the goal, verified and attempted work, blocker, pending decision and evidence or artifact references. Link the visible outcome to 1.2; record when approval or referral is unnecessary.

### out of scope

Business participation belongs to 1.1 and visible result requirements to 1.2. Service preparation, operation and technical-change governance belong to 1.4. Trusted enforcement, credential handling, pause/resume mechanisms and isolation belong to later design stages.

### Prerequisite

Consult 1.1 for scoped tasks and participants, and 1.2 for completion evidence and user-visible outcomes.

### Technical references

- When defining approval criteria for consequential actions, see [authority-and-approval-policy.md](technological%20documentations/authority-and-approval-policy.md) for reference.
- When defining a permitted human referral and its context, see [human-handoff-policy.md](technological%20documentations/human-handoff-policy.md) for reference.

## 1.4 Operating constraints and governance

### To clarify

- Which organizational, legal or compliance obligations apply to the actual workflow, jurisdiction, data and actors? Who confirms applicability?
- Who prepares and operates the service, and who changes or reviews prompts, tools, databases, knowledge sources and policy?
- Which source classes are acceptable, who accepts them, and which source checks are needed?
- Which data objects may be used or retained, for what purpose and duration? Is an operational audit trail required, and who needs access to it?
- What per-task cost and workload-specific latency targets are needed? What are the measurement boundaries, evidence, owners and target-change approval paths?

### output

- **Constraint summary:** constraint ID, category, affected function or data, owner, target or pending decision, verification evidence, release gate and owning-record reference.
- **Obligation matrix:** authoritative source and version, jurisdiction, applicability, duty, affected action or data, required control outcome, evidence, owner, status and review trigger. Unconfirmed applicability needs an owner and confirmation action.
- **Service and change-governance decision:** preparation, operation, change and review responsibilities; accepted source classes, acceptance owner and required source checks. Reference 1.3 permissions and 1.2 claim-support requirements.
- **Data and audit policy:** data object, purpose, permitted use, access-policy reference and retention. Distinguish chat history, request/checkpoint state, reusable evidence and audit records. When audit is needed, state its purpose, event classes, actor/version/result/correlation information, minimization, reviewer access and retention.
- **Cost and latency target table:** linked function or workload, metric, measurement boundary, objective or ceiling, percentile or attainment goal where relevant, window, owner and change-approval path. Missing targets need a measurement action. This table owns service targets; consumers reference it.

### out of scope

Do not redefine 1.1 business indicators, 1.2 claim-support requirements or 1.3 action permissions. Later stages design controls, allocate budgets, define instrumentation and verification procedures, and choose deployed placement.

### Prerequisite

Consult 1.1 for business scope, 1.2 for functions and evidence needs, and 1.3 for acting identities, permissions and approval policy.

### Technical references

- When determining obligation applicability and accountable roles, see [obligation-applicability-assessment.md](technological%20documentations/obligation-applicability-assessment.md) for reference.
- When selecting workload-specific cost and latency targets, see [cost-and-latency-target-selection.md](technological%20documentations/cost-and-latency-target-selection.md) for reference.
- When deciding whether an operational audit trail is needed, see [audit-trail-need-assessment.md](technological%20documentations/audit-trail-need-assessment.md) for reference.

## 1.5 Technique scope

### To clarify

- Which tasks need external evidence, and is adequate, sufficiently fresh evidence accessible within the approved permissions and source policy?
- Which tasks need a reusable procedure? Which separately need live data access or an external action?
- Which facts or preferences must intentionally be recalled across sessions? Would ordinary conversation history, request state, checkpoints or reusable evidence already meet the need?
- Which input and output modalities are required?
- For each candidate technique, what task benefit justifies inclusion, what condition activates it, and what feasibility limit could change the scope?

### output

- **Technique decision table:** technique, linked task, need and evidence, yes/no/conditional inclusion, rationale, constraint references, feasibility limits and downstream design owner.
- **Capability scope:** evidence need and feasible coverage/freshness for retrieval; separate procedure and live-access needs; intended cross-session recall purpose; required input/output modalities. Reference existing source, access and data policies.
- **Conditional-work summary:** selected and omitted optional work, activation conditions and scope changes that require revision of 1.1. Declining a technique does not remove general tool, context or integration responsibilities.

### out of scope

Do not select detailed connectors, retrieval routes, memory content schemas or customization methods here. Stage 2 designs the selected capabilities and integrations; Stage 3 defines exact contracts and settings. Source acceptance and data retention remain owned by 1.4, and component state responsibility by 1.6.

### Prerequisite

Consult 1.1–1.4 for task scope, accepted outcomes, permissions, source policy, data policy and operating constraints.

### Technical references

- When deciding whether tasks need retrieval, see [retrieval-need-assessment.md](technological%20documentations/retrieval-need-assessment.md) for reference.
- When deciding whether tasks need a reusable procedure, see [reusable-procedure-need-assessment.md](technological%20documentations/reusable-procedure-need-assessment.md) for reference.
- When deciding whether tasks need live data or external actions, see [live-access-need-assessment.md](technological%20documentations/live-access-need-assessment.md) for reference.
- When deciding whether intentional cross-session recall is needed, see [agent-memory-need-assessment.md](technological%20documentations/agent-memory-need-assessment.md) for reference.
- When establishing required input/output modalities, see [modality-requirements-assessment.md](technological%20documentations/modality-requirements-assessment.md) for reference.

## 1.6 Architecture and framework

### To clarify

- Can direct calls or deterministic code meet the agreed tasks? Where does execution require a model to choose the next action?
- Which planning, coordination, state, durability, recovery, review and observability capabilities do the approved tasks require?
- Which tasks depend on each other or share mutable resources? Which can run independently, and who integrates their results?
- Which layers does the user want in the project, such as frontend, backend and memory, and how should they connect?
- Which architecture and runtime satisfy these needs with the least operating burden? What evidence supports the selection and rejection of alternatives?
- Is a separate harness, gateway, queue, distributed executor or state/memory service justified by a concrete need?

### output

- **Architecture decision and alternatives table:** representative task, candidate approach, fixed/model-directed/hybrid control, required capabilities, supporting evidence, limitations, operating burden, selection or rejection reason and decision owner.
- **Framework/runtime selection:** implementation approach, viable candidates and documented versions, fit to the selected architecture, state/durability/recovery/approval support, integration limits and reasons for the choice.
- **Mermaid layer diagram (required):** show the user's chosen project layers and the connections between them.
- **Task-coupling assessment:** task dependencies, shared resources, read/write effects, serial or parallel feasibility, synchronization responsibility, result-integration owner and partial-result requirements referenced from 1.2.

### out of scope

Do not redefine task scope, acceptance, authority, governance or technique inclusion from 1.1–1.5. This aspect records the user's chosen project layers and their connections. Executable nodes, guards, routing, retries, exact limits and enforcement mechanisms belong to Stages 2 and 3; Stage 5 selects concrete deployment topology, infrastructure sizing and placement using these architectural decisions.

### Prerequisite

Consult 1.1–1.5 for scoped tasks, acceptance criteria, authority, operating constraints and selected capabilities.

### Technical references

- When selecting an agent architecture, see [agent-architecture-selection.md](technological%20documentations/agent-architecture-selection.md) for reference.
- When assessing serial or parallel task execution, see [task-coupling-assessment.md](technological%20documentations/task-coupling-assessment.md) for reference.
- When selecting a framework or runtime, see [agent-framework-selection.md](technological%20documentations/agent-framework-selection.md) for reference.
- When deciding whether a separate agent harness or infrastructure component is needed, see [agent-harness-need-assessment.md](technological%20documentations/agent-harness-need-assessment.md) for reference.

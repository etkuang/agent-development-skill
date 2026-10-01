# Stage 1 — Requirements and architecture

**Current deliverable:** `01-requirements-and-architecture.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-1-requirements-and-architecture.md](stage-1-requirements-and-architecture.md).

### 1.1 Goals, business scenario, and users

Establish the business problem, current workflow, user groups, desired improvement, initial scope, and material assumptions. This aspect owns the canonical inclusion, exclusion and deferral decisions and business-outcome indicators. Use 1.2 for function acceptance, 1.3 for acting authority and human escalation, and 1.4 for operating governance and cost/latency targets; link those decisions when the business scenario depends on them.

**Requirements**
- Ask the user which business problem and observable improvement justify the project, and record the confirmed purpose in the scope decision before evaluating technical options.
- For each priority business need, agree on an observable business-outcome indicator, its baseline or baseline-collection action, and desired improvement in the business-need table; reference 1.2 acceptance and 1.4 cost/latency targets when relevant.
- Record current business steps, handoffs, exceptions and bottlenecks in the user/workflow list, and connect their observed baseline outcomes to the desired improvement in the business-need table.
- Ask who performs and receives each business task, and record those participants and business responsibilities in the user/workflow list; refer to 1.3 for authorized escalation roles and 1.4 for system operation/change ownership.
- Agree the first-release in-scope and out-of-scope business tasks with the user and record the sole canonical scope lists in the scope decision.
- Identify assumptions that could change the project scope or expected benefit, and record each premise, evidence or status, owner, validation action and decision consequence in the assumption log.
- When several business workflows are requested, agree the coherent first-release slice, deferred slices and business prerequisites in the scope decision; leave execution coupling and synchronization choices to 1.5.

**Output**
- A confirmed scope decision stating the business problem, desired improvement, evidence of need, canonical in-scope and out-of-scope tasks, first-release slice, deferrals and business prerequisites.
- A user/workflow list naming user groups, representative tasks, business responsibilities, current steps, handoffs, exceptions and bottlenecks, with links to authority or governance decisions when relevant.
- A business-need-to-indicator table with observable outcome, business indicator, baseline or collection action, desired improvement, measurement approach, and references to 1.2 acceptance and 1.4 cost/latency targets where applicable.
- An assumption log naming each material premise, evidence or status, owner, validation action and possible scope consequence.

*Technique reference: `references/stage-1-requirements-and-architecture.md` (constraint translation).*

### 1.2 Functions, outputs, and success criteria

Specify prioritized functions, their inputs and user-facing outputs, audience, acceptable end states and communication criteria, with a small real-task evaluation seed. This aspect owns functional and response contracts, including partial, failed and insufficient-evidence outcomes. Consume the scope in 1.1, approval and human-handoff decisions in 1.3, and cost/latency targets in 1.4; leave routing, retry mechanics, schemas and scoring implementations to later aspects.

**Requirements**
- For reachable missing-input and ambiguous requests, agree the clarification or missing-information response in the failure-mode table; for approval-paused actions, reference the 1.3 approval rule and specify only the user-visible pending state.
- For each prioritized function, agree the task end state, required constraints and observable completion evidence, and record them in the function table separately from communication-quality criteria.
- Ask which functions permit useful partial results, and record in the failure-mode table when to show verified completed parts, identify missing work and label the overall task incomplete; record failure or escalation for functions requiring an atomic outcome.
- For reachable execution failures, agree the permitted user-visible partial, deferred, stopped or escalated outcome in the failure-mode table, referencing 1.3 handoff and 1.4 budgets; defer retry classification, counters and replay mechanics to 2.3 and 3.1.
- For source-dependent outputs, agree the retrievable source identifiers, available page/section/record locators and unsupported-claim behavior, and record those requirements in the function table; 2.5 and 3.3 will choose the grounding and validation mechanisms.
- Ask the user what makes each result clear and useful to its audience, and record the output format and communication-quality criteria in the function table; mark unmeasured performance expectations as open instead of inventing claims.
- Prioritize the scoped functions with the user and record a representative acceptance case and agreed review criterion for each outcome in the function table; for excluded task IDs from 1.1, agree the decline, redirect or authorized handoff behavior in the out-of-scope response table.
- Capture a small seed of real highest-priority tasks in the early evaluation seed, recording each input, acceptable end state, key required or prohibited constraints and linked function; hand the approved seed to 4.1 for expansion and versioning.
- Record references to the applicable 1.4 cost and latency target IDs in each affected function and seed case; ask the constraint owner to resolve missing targets through 1.4 rather than entering independent target values.

**Output**
- A prioritized function table with input, user-visible outcome and audience, output format, verified end state and evidence, communication-quality criteria, citation requirements, representative acceptance case, review criterion and applicable constraint references.
- An early real-task evaluation seed linked to priority functions, with input, acceptable end state, required and prohibited constraints, source and references to applicable approved targets.
- A failure-mode table for reachable missing-input, ambiguity, approval-paused, partial, failed, deferred and stopped outcomes, stating trigger, user-visible behavior, completion status and references to the governing approval/handoff or budget decision.
- An out-of-scope response table referencing the canonical excluded task IDs in 1.1 and recording the intended decline, redirect or authorized handoff behavior without repeating the scope list.

*Technique reference: `references/stage-1-requirements-and-architecture.md` (success definition).*

### 1.3 Authority levels and human involvement

Establish acting identities, logical role and data-visibility entitlements, consequential-action approval rules, and the authorized human-escalation contract. This aspect owns which actions require approval, who may decide, the decision window and denial or unavailable paths, and the permitted handoff context. Consume the business scope, output/evidence contract and applicable obligations from 1.1, 1.2 and 1.4; Stage 2 selects trusted enforcement and pause/continuation mechanics.

**Requirements**
- Ask which user, agent or service acts on each scoped task, and record its logical role, permitted resource/action scope, data visibility and accountable authority owner in the actor/access decision; defer enforcement mechanisms to 2.6 or the baseline security boundary in 2.9.
- For each consequential action, agree which missing intent, authority, required evidence or risk condition requires clarification, review or a safe stop, and record that policy in the approval matrix using 1.2 evidence requirements; do not use model self-confidence as authorization.
- For each approval-gated action, agree the authorized reviewer, action and context presented, decision window, and denial or reviewer-unavailable path, and record them in the approval matrix.
- Inventory scoped consequential actions and decide each approval trigger from the applicable policy, reversibility, actor permissions and impact, recording the classification in the approval matrix before execution mechanics are designed.
- Agree human-handoff triggers and an authorized receiving role, then record the user notice and permitted context package—goal, attempted and verified completed work, current state, blocker, pending decision and evidence identifiers—in the human-escalation contract.
- Agree the policy for absent, expired, revoked or insufficient authority for a consequential action, and record whether to seek clarification or renewed approval, defer, or stop in the approval matrix; refer to 1.2 for the user-visible completion message.

**Output**
- A confirmed actor-and-access decision naming user, agent or service identities, logical roles, resource/action entitlements, data visibility and the accountable authority owner, without prescribing enforcement mechanics.
- An approval matrix recording consequential action, policy/risk/reversibility classification, trigger and authority conditions, required evidence references, authorized reviewer, review subject and context, decision window, denial/unavailable path and missing or expired authority outcome.
- A human-escalation contract naming trigger, authorized receiving role, user notice and permitted goal, attempted/verified work, state, blocker, pending decision and evidence or case/artifact identifiers.

*Technique reference: `references/stage-2-development-and-model-layer.md` (routing, guardrails).*

### 1.4 Compliance, governance, cost, and latency constraints

Confirm applicable obligations, organizational governance and change ownership, required audit policy, and the canonical per-task cost and workload-specific latency targets. This aspect owns constraint applicability and accountability, including audit purpose, content exposure, access and retention. Use 1.3 for acting and approval authority; later aspects select enforcement controls, allocate phase budgets, define telemetry fields and verify compliance against these approved constraints.

**Requirements**
- For each material governance, data, cost or latency constraint, confirm its owner and target or pending decision, and record a summary row with required verification evidence and any release-gate reference in the constraints table.
- Have the accountable legal, compliance or policy owner confirm each applicable obligation, and record its source/version, concrete duty, affected data/action, required control outcome and verification evidence in the obligation matrix; bind concrete control designs by later aspect reference.
- When an obligation or governance need requires an audit trail, agree the consequential decision/change classes to retain and the permitted actor/version/result/correlation information, content minimization, access and retention policy in the governance/audit decision; leave concrete event fields and export mechanics to 4.4.
- Record each uncertain legal or policy applicability question in the obligation matrix with the accountable reviewer and confirmation gate, and keep it pending until that owner determines whether it applies.
- Agree the runtime owner and authorized changers and reviewers for prompts, tools, knowledge and policy, and record their versioned change, review and audit responsibilities in the governance decision; use 1.3 for actor/action approval policy.
- Agree a per-task cost ceiling and workload-specific end-to-end latency objective, and record their metric, measurement boundary, percentile or attainment goal where relevant, window and owner in the cost/latency decision; defer phase allocation and trace-based validation to 3.6 and 4.4.
- Give each approved cost and latency target a canonical constraint ID and decision owner in the cost/latency decision, link the constraints summary to that record, and route later target changes through revision and approval of 1.4.

**Output**
- A constraints summary table with canonical ID, affected workflow or data, governance/data/cost/latency category, owner, confirmed target or pending decision, verification-evidence requirement, release-gate reference and link to the authoritative detailed decision.
- A versioned obligation matrix with rule source and jurisdiction, concrete duty, affected data/action, required control outcome, accountable owner, required verification or audit evidence, applicability status and review/confirmation trigger, linked to later concrete control designs.
- A canonical per-task cost and workload-latency decision naming target ID, metric, measurement boundary, ceiling or objective, percentile or attainment goal where applicable, window, owner and target-change approval path.
- A governance and audit decision naming runtime/change/review responsibilities, required consequential event classes, audit purpose, permitted content, minimization, access and retention rules, and reasons any proposed audit need is unnecessary.

*Technique reference: `references/stage-1-requirements-and-architecture.md` (compliance, governance).*

### 1.5 Architecture pattern and framework

Select the high-level architecture pattern and implementation approach from approved tasks, authority, constraints and technique scope, considering a deterministic workflow or direct model/API call before additional autonomy. This aspect owns the optional framework/runtime choice, component responsibility sketch and task-coupling assessment. Specify required orchestration, durability, approval, isolation and observability capabilities at architecture level; Stage 2 defines executable steps and control mechanisms, and Stage 5 defines deployed topology.

**Requirements**
- Compare the viable direct call, deterministic workflow and agent patterns on approved representative tasks, and record the simplest sufficient pattern in the architecture decision with evidence and reasons for rejecting added routing or coordination in the alternatives table.
- Assess each task's dependencies, shared mutable resources and read/write effects, then record the serial or parallel feasibility and synchronization/result-integration owner in the coupling assessment; defer launch, join and failure transitions to 2.3.
- Locate the approved workflow's runtime uncertainty, choose fixed, model-directed or hybrid control, and record the required planning, durability, recovery and monitoring capabilities in the architecture decision and alternatives comparison.
- Where approved tasks span sessions or approvals, compare candidate runtime support for durable state and pause/resume against the 1.3 approval contract, and record support evidence and limitations in the alternatives table.
- Justify each selected architectural component and optional framework by the approved task, representative benefit and operating burden, recording viable simpler alternatives and rejection reasons in the architecture decision and comparison table.
- Draw the chosen component-level pattern with control/data flow, state ownership and required approval or inspection boundaries in the high-level Mermaid diagram; annotate needed loop, recovery or pause capabilities without defining executable transitions or numerical limits.
- Decide whether an execution harness is required, and record its component-level ownership of state, execution, authority, recovery and observability in the architecture decision and diagram; hand isolation/enforcement mechanisms to 2.6/2.9 and deployed placement to Stage 5.

**Output**
- A confirmed high-level architecture pattern and implementation approach, optional framework/runtime, architectural component responsibilities, required capabilities, supporting evidence and decision owner.
- An alternatives table comparing viable patterns and implementation runtimes against approved tasks, state/recovery, approval, validation, integration capability and operating burden, with support evidence, simpler alternatives and selection/rejection reasons.
- A high-level Mermaid component diagram showing control/data flow, state ownership, tools and stores as component roles, required approval/inspection boundaries and downstream capability owners without executable node or guard definitions.
- A task-coupling assessment naming dependencies, shared mutable resources, read/write effects, concurrency feasibility, serial or parallel judgment, synchronization and result-integration owner.

*Technique reference: `references/stage-1-requirements-and-architecture.md` (pattern catalogue, framework comparison).*

### 1.6 Technique scope decisions

Decide whether approved tasks need retrieval, cross-session memory, reusable procedures (Skills), live connectivity or particular input/output modalities. This aspect owns technique inclusion, conditional activation and downstream responsibility. Record the user need and feasibility evidence without selecting connectors, retrieval topology, memory content/lifecycle controls or custom model methods; Stage 2 makes those architectural decisions and Stage 3 supplies detailed contracts.

**Requirements**
- For each candidate technique, ask which approved task needs it and record the yes/no inclusion decision, task evidence and rationale in the technique decision table.
- Compare representative question classes with no retrieval and feasible evidence-access options, and record whether external retrieval is required and the coverage/freshness/authority constraints in the technique table; leave the selected direct-source or indexed route to 2.5.
- Decide separately whether a reusable Skill procedure and live capability access are needed, and record the approved task, required capability and integration/authority constraints in separate technique rows; hand application/API/provider-tool/MCP selection to 2.2.
- Ask which approved facts or preferences must be available across sessions, decide whether durable memory is needed within 1.3/1.4 constraints, and record the purpose, inclusion and 2.4 design handoff in the technique table; record no durable memory when none is needed.
- Agree the input and output modalities required by each approved task and record them in the technique table, assigning model/API capability selection to 2.2 and any justified customization to 2.7.
- Map each approved technique to its downstream owner and activated conditional aspects in the technique table, recording scope only; retain general aspects for baseline responsibilities when an optional technique is absent.
- For each declined technique, record the omitted optional design work and the general responsibilities that still apply in the technique table, so later documents omit only the matching conditional work.

**Output**
- A technique decision table naming approved task or evidence, technique and required capability, inclusion decision, rationale and constraint references, required modalities or memory purpose where relevant, downstream owner, activated conditional aspects, omitted optional work and continuing general responsibilities for declined techniques.

*Technique reference: `references/stage-2-development-and-model-layer.md` (tools, RAG scope) and `references/stage-1-requirements-and-architecture.md`.*

**Deliver and confirm:** Stage 1 Word document. Resolve scope-changing questions before advancing; leave detailed technology choices for Stage 2.


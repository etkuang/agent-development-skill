# Stage 2 — Development and model layer

**Current deliverable:** `02-workflow-and-technology-selection.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-2-development-and-model-layer.md](stage-2-development-and-model-layer.md).

### 2.1 Intent recognition and routing

Choose a single path or request-routing approach and define supported request boundaries, multi-intent handling, arbitration, clarification, abstention and handler selection. This aspect also owns capability-discovery strategy when a catalogue warrants it. Consume scope, response and authority policies, selected capabilities and trusted action checks; leave exact tool metadata to 3.1, executable workflow transitions to 2.3 and formal metric definitions to 4.2.

**Requirements**
- Compare a single path and viable routing alternatives on representative approved requests, and record the simplest sufficient approach, baseline evidence and selection rationale in the recognition decision.
- When distinct routes are needed, map the approved task IDs from 1.1/1.2 to handlers and record route boundaries, multi-intent handling and stable rule-based cases in the routing table.
- For each request-selection outcome, record the handler, clarification, out-of-scope, abstention or authorized handoff condition and wrong-route consequence in the routing table/rule list, referencing 1.2/1.3 policy; leave dependency recovery to 2.3.
- If numeric classifier scores select routes, use held-out cases to calibrate the scores and choose thresholds from misroute versus abstention consequences, recording the evidence and decision rule in the recognition decision/rule list; otherwise record that scores are unused.
- Agree rule/model signal precedence and the clarification, review or abstention result for disagreements, and record the arbitration rule in the rule list with 1.3 authority and 2.6/2.9 check references that routing cannot override.
- Distinguish ambiguous supported requests from requests excluded by 1.1, and record their clarification or out-of-scope route with the corresponding 1.2 response-contract reference in the routing table/rule list.
- Show the independent action-check dependency from 2.6/2.9 and its denied or paused result in the routing Mermaid view, so no selected route grants authority; use 2.3 to place the actual execution transition.
- Name the routing outcomes and consuming workflow handlers in the routing table and Mermaid view, handing their executable transitions to 2.3 without maintaining a second node graph.
- Using 2.2's selected capability purposes/scopes and provisional selection examples, compare direct selection with deferred loading or candidate retrieval when measured context pressure or selection errors warrant it, and record the chosen discovery method and candidate handoff in the recognition decision/routing table; hand exact metadata requirements to 3.1 for refinement/verification and consume permission boundaries from 2.6/2.9.
- Record routing validation needs by request type in the recognition decision/rule list, including selection and task outcome, false acceptance, abstention/handoff, harmful mis-execution, overhead and candidate recall where retrieval is selected; assign formal metric definitions to 4.2.

**Output**
- A confirmed recognition/single-path and capability-discovery decision with alternatives, simpler baseline, representative selection/context evidence, score-calibration evidence when used, rationale and routing validation needs.
- A routing table where distinct routes exist, referencing approved task IDs and recording request boundary, handler, multi-intent/discovery rule, selection/clarification/abstention outcome, named result and consuming workflow handler.
- A rule list for selection precedence, numeric-score use where applicable, ambiguity, out-of-scope and policy dependencies, with request-slice validation needs; mark arbitration not applicable for a single path.
- A Mermaid request-selection view showing handler or single-path selection, named outcomes, referenced independent action-check dependency and stop/handoff results, without duplicating the executable workflow.

*Technique reference: `references/stage-2-development-and-model-layer.md` (intent and routing).*

### 2.2 Tools, services, providers, and model roles

Select the tools, services, providers and model roles required by the approved workflow, recording product/version, deployment mode, invocation and execution owner, required connection, capability evidence and alternatives. This aspect owns integration selection and bindings. Consume retrieval source/freshness requirements from 2.5, permission and security controls from 2.6/2.9 and recovery needs from 2.3; later aspects specify exact calls, parameters, schemas and deployment settings.

**Requirements**
- Ask about existing infrastructure, vendor preferences and local/hosted and data-handling constraints, then record the relevant confirmed constraints or pending decisions in the selection table using the approved 1.4 budget references.
- Compare viable mature integrations on approved capability, operating burden, cost and data-handling needs, and record the recommended choice, trade-offs and meaningful alternative in the selection table and confirmed decision.
- Verify each selected model/service's required tool-calling, structured-output, streaming or other feature support for its product/version, endpoint and deployment region, and record evidence and limits in the selection table; leave exact call values to 3.1.
- Compare shared and separate model/service assignments across the required roles, and record the simplest sufficient combination and any evidence-based separation rationale in the role-selection rows and confirmed decision.
- Evaluate model and supported reasoning-effort candidates for each role on representative task quality, latency and cost, and record the model assignment and selection evidence in the role table; hand exact supported call defaults to 3.1.
- Separate documented support, external benchmark claims and representative workload evidence in each selection row, and record its verified or proposed status and project-specific rationale rather than importing a reference project's stack.
- Using 2.5's source-route, freshness and provenance requirements, verify that each candidate evidence tool supports the required live/snapshot access and metadata, then record the capability evidence and source-route-to-tool/consumer binding in the selection table and integration binding view.
- For each selected write capability, record the trusted execution owner, advertised read/write scope and available transaction, idempotency or outcome-query guarantees in the integration classification/selection table, referencing authority, security and workflow-control owners instead of designing those controls here.
- For each critical tool, compare its documented failure/replay guarantees and any authority-equivalent alternative against 2.3 recovery needs, and record the selected dependency and limitations in the selection table and confirmed decision; 2.3 owns recovery transitions and 3.1 exact call limits.

**Output**
- A role/integration selection table with product/model and version, deployment mode, invocation/execution owner, required connection, constraints, supported features and guarantees, representative evidence, status, rationale and alternative.
- An integration classification identifying Skill procedure, provider tool, application function/direct API or MCP connection, invocation/execution owner, advertised read/write capabilities and references to permission/security controls.
- A confirmed decision on the selected tool, service, provider and model-role combination, its sharing/separation rationale and accepted dependency limitations.
- An integration binding figure or list referencing each 2.5 source-route ID and mapping its selected access integration to the consuming workflow step, with metadata-support evidence and links to canonical freshness/citation requirements.

*Technique reference: `references/stage-2-development-and-model-layer.md` (tools and skills).*

### 2.3 Graph workflow and node responsibilities

Specify the selected executable direct path, code workflow or graph, with entry/exit, step responsibilities, named transitions, joins, loops, failure and pause/continuation paths. This aspect owns runtime control flow and operational progress/attempt guards. Consume 2.1 routing, 2.4 context/session contracts, 2.5 retrieval policy and 2.6/2.9 trusted controls by reference; leave exact call limits, typed state and deployed checkpoint mechanics to Stages 3 and 5.

**Requirements**
- Render the selected direct path, code workflow or graph in the workflow Mermaid diagram, including parent and used subgraphs only when selected, with consistent direction and named transition/result labels.
- Map the named routing and stop outcomes from 2.1 to executable steps and terminal transitions in the workflow diagram and step/node table, rather than selecting routes by parsing unstructured generated prose.
- For each reachable dependency/action path, choose the retry, cutoff, equivalent fallback, reconciliation or stop transition using 2.2 guarantees, and record it in the recovery paths; refer to 3.1 for exact replay/deadline/backoff contracts before implementation.
- Classify reachable failures as transient, model-correctable, user-resolvable or terminal in the recovery paths, and choose repeated/drifting-action checks and responses in the workflow-control table; consume sanitized error and context-reduction contracts from 2.9 and 2.4.
- Choose task-specific progress, step and retry controls and their safe breach transitions in the workflow-control table, referencing 1.4 targets and later 3.1/3.6 deadline/spend values; decide whether breach permits verified partial output, deferral, replan or 1.3 handoff.
- For multi-turn workflows, place the dialogue-state/changed-intent operations from 2.4 and any query-processing operation from 2.5 in the step table and workflow diagram, identifying their conceptual inputs/results without redefining those policies.
- For each selected parallel or dependent branch, record launch/readiness, join/merge and failed-branch recovery behavior in the workflow/recovery views, preserving independently completed results and exposing partial results only under 1.2's contract.
- When multi-agent execution is selected, record collaboration topology, delegation authority, authoritative shared-field/namespace owner, branch acceptance references, concurrency/resource controls and minimum sufficient worker context/evidence in the workflow views and step/control tables; use 3.2 for typed handoff fields.
- For long-running tasks, identify the pause/resume and recoverable progress boundaries in the workflow diagram and choose stalled/drifted-work responses in the control table, consuming 2.4 continuity needs; leave checkpoint fields to 3.2 and deployed persistence to 5.4.
- Assign each executable step to trusted code, human review or model-directed work using approved uncertainty, risk and representative-task evidence, and record its owner and rationale in the step table with applicable 1.3/2.6/2.9 control references.
- Label workflow steps and routes as implemented or proposed in the diagram and step table; when existing LangGraph code is present, verify registered nodes, START/END and compiled conditional routes, and label dependencies/placeholders separately from executable nodes.
- For each selected step/node, record its exclusive responsibility, required conceptual inputs, result/state update, model/tool/code action and next route in the step table; split steps only where reachable failure isolation, observability or checkpoint needs justify it.
- For an existing project, map current components and routes to the proposed step table, deciding which are retained, replaced or new and recording unresolved implementation/design discrepancies; otherwise record that the workflow is a new design.

**Output**
- An authoritative Mermaid diagram of the selected executable workflow, showing entry/exit, named routes/results, parent/used subgraphs when selected, branch coordination and required pause/resume boundaries, with current/proposed status.
- A step/node overview table recording exclusive responsibility, model/tool/code or human owner and rationale, conceptual inputs/results, next route and current-to-proposed component mapping; for multi-agent work, include authoritative shared-field ownership, delegation authority, branch acceptance references and minimum worker-context/handoff references.
- A recovery-path list or Mermaid view mapping each reachable failure class to bounded retry/cutoff, safe fallback, reconciliation, partial/deferred/stopped result or authorized handoff, with branch recovery and exact call-contract references.
- A workflow-control table recording operational progress/loop/step/attempt and selected concurrency/resource controls, trigger basis or canonical limit reference, enforcement placement, breach transition, owner and planned verification; reference permission/security/context/retrieval controls without redesigning them.

*Technique reference: `references/stage-2-development-and-model-layer.md` (workflow and reliability).*

### 2.4 Context and memory design

Design active context, session/dialogue continuity and any approved cross-session memory, including layers, content/provenance policy, read/write flow, conflict handling and context preservation. This aspect owns context and memory semantics and architectural lifecycle policy. Consume 2.5's evidence interface, 2.6's access enforcement and 2.9's trust controls; Stage 3 refines schemas, store configuration and numerical cost/token triggers, while Stages 5/6 refine deployed persistence and operating procedures.

**Requirements**
- Distinguish active context, resumable session state and cross-session memory in the layer table, deciding each layer's purpose and permitted retention/content within 1.3/1.4 constraints and referencing access enforcement from 2.6/2.9.
- Classify required memory by scope and purpose, choose its architectural persistence/recall pattern, and record the choice in the memory architecture and layer table; leave physical store fields and configuration to 3.5.
- For each candidate preference, project fact/decision or feedback class, decide whether it is approved and task-relevant enough to persist, and record the keep/exclude rationale and provenance in the store-policy table; keep temporary state in-session and reference canonical project sources.
- Choose structured memory concepts and source pointers where retrieval or correction needs them, and record those requirements in the architecture/store-policy table; retain raw evidence only when permitted and needed, handing exact fields to 3.2/3.5.
- Choose whether trimming, summarizing, provider compaction or offloading is needed, and record each selected method's trigger basis, preserved/discarded state and continuity check in the context-management table; let 3.6 calibrate numerical token/cost triggers.
- Agree when memory is written/read and how dialogue references or changed intent update session state, and record the triggers and carry-forward/result-to-context flow in the layer table and memory Mermaid view for 2.3 to invoke.
- Choose the current task state, governing instructions, evidence and authorized recalled records included in active context, and record their inclusion/precedence and assembly flow in the memory architecture/diagram within the approved 1.4 cost/latency constraints; use the reduction policy in R-2.4-05 and hand numerical context allocation and reduction triggers to 3.6.
- Agree how memory conflicts and duplicates are resolved by provenance, authority, scope and time, and record consolidation, expiry and correction/deletion intent in the store-policy table;6.3 will define operating schedules and recovery procedures.
- Apply 1.3/1.4 memory-use constraints to the store-policy table and show read/write control dependencies from 2.6 and 2.9 in the memory diagram, recording the permitted scope and user correction/deletion contract without creating a second permission or security design.
- Define the memory-to-evidence boundary in the memory architecture and diagram, referencing 2.5's source/evidence interface instead of copying its corpus, retrieval routes or grounding rules.

**Output**
- A context/memory architecture description naming selected layers, logical persistence/recall pattern, record concepts, active-context inclusion/precedence, continuity needs and the 2.5 evidence interface; state when cross-session memory is absent.
- A layer table with purpose/content, logical backing or none, dialogue-update and read/write triggers, carry-forward behavior, permitted lifetime and access-control references.
- A memory store-policy table with candidate content, keep/exclude rationale, provenance, authorized use scope, retention/correction/deletion intent, conflict/consolidation rules and permission/trust-control references.
- A context-management table for selected reduction methods with trigger basis, preserved/discarded state, continuity validation/recovery, retention constraint and numerical calibration handoff to 3.6, or a decision that reduction is unnecessary.
- A Mermaid context/memory view showing dialogue update, context assembly, authorized read/write dependencies, selected reduction flow, carry-forward and the distinct 2.5 evidence handoff.

*Technique reference: `references/stage-2-development-and-model-layer.md` (memory and context).*

### 2.5 RAG and knowledge-base design (conditional)

When retrieval is approved, design the authoritative source catalogue, direct-source or indexed query route, logical storage/search roles, parsing needs, evidence lineage and grounding/conflict policy. This aspect owns retrieval and business-source semantics, including conversational query processing. Consume selected integrations, context and trusted access/security controls; Stage 3 refines parameters, record/store definitions and prompts, and Stage 4 formalizes retrieval and answer scoring.

**Requirements**
- Decide whether each approved source needs direct access or a derived index, and record the logical search/storage role and corpus/query/update/scale rationale in the retrieval architecture/source table; use 2.2 for product selection and 3.5 for physical configuration.
- Describe and draw the selected access/query path in the retrieval architecture and Mermaid view, including ingestion, parsing, metadata, segmentation, embeddings, rewriting or reranking only where selected, and show how evidence reaches answer synthesis.
- Compare feasible direct, lexical, structured, vector, hybrid or reranked routes on representative queries, and record the selected architecture and source/version/citation lineage in the architecture/source table; defer parameter tuning to 3.4.
- Decide whether conversation context or query rewriting is needed for follow-up retrieval, and record the selected transform and preservation of original intent/exact identifiers in the retrieval architecture/diagram, consuming 2.4 dialogue state for 2.3 execution.
- Choose fixed or iterative/model-directed retrieval from measured source-choice and search needs, and record its rationale and conceptual search/termination interface in the retrieval architecture/diagram;2.3 owns executable loop and failure transitions.
- Where tasks use business terms or metrics, obtain their authoritative domain definitions and record formula, dimensions/filters, owner and effective version in the glossary/semantic layer; distinguish those domain measures from agent-evaluation metrics in 4.2.
- Agree source precedence by authority, scope, effective date and version, and record unresolved-conflict disclosure and authorized escalation under 1.3 in the grounding policy instead of silently choosing incompatible evidence.
- Inspect representative PDFs/scans and choose native-text extraction, OCR/layout analysis or multimodal processing, recording the route and required page/section/table/image provenance in the source table/diagram;Stage 3 fixes parameters.
- Using 1.2's output/completion contract, decide how retrieved support bounds each claim, preserves citations and marks missing evidence, and record the supported/partial/defer/escalate policy in the grounding policy;3.3 supplies concrete prompt/schema/validation.
- Record retrieval validation needs and representative reference-evidence requirements in the architecture description, separating evidence coverage, ranking where present and answer synthesis; hand detailed baseline/settings to 3.4 and metric definitions/acceptance to 4.2.

**Output**
- A retrieval architecture description recording selected direct/no-index or indexed route, logical storage/search roles, route-comparison evidence, conversation-query and autonomy choices, and retrieval validation/reference-evidence needs.
- An authoritative source/access table with source ID, format, authority/version, freshness/update need, selected route, logical store/no-index decision, processing/provenance requirements, owner and references to 2.2 integration and 2.6/2.9 controls.
- An authoritative business glossary or semantic-layer definition where needed, with term/domain metric, formula, dimensions/filters, source authority, owner and effective version.
- A Mermaid retrieval view of selected source-access/query and evidence lineage, including processing/index/segmentation/embedding/rewrite/rerank stages only where chosen and references to workflow and access-control interfaces.
- A grounding and insufficient-evidence policy recording supported-claim/citation linkage, source precedence and conflicts, evidence gaps, permitted partial answers and authorized escalation, referencing 1.2 response/completion requirements.

*Technique reference: `references/stage-2-development-and-model-layer.md` (RAG and knowledge base).*

### 2.6 Permission architecture (conditional)

When the approved workflow has distinct principals, scopes or action permissions, design the acting identity mode, protected resource/action rules and trusted enforcement on every read/action path. This aspect owns permission decisions, source/gateway/tool enforcement and indexed permission freshness. Consume 1.3 policy and 1.4 data/audit constraints; reference 2.9 trust/isolation controls and let Stage 3 refine authentication calls and Stage 5 verify deployed denial behavior.

**Requirements**
- For each protected path, choose verified user delegation or a distinct narrowly scoped agent/service identity consistent with 1.3, and record downstream subject/actor, consent/scope and trusted authority owner in the permission-model decision.
- Map each protected document/row/field or action rule to its principal/resource/condition in the permission matrix and trusted source/gateway/tool enforcement point in the enforcement map, before protected content or action reaches the model/executor.
- For protected indexed content, choose the logical ACL/tenant/classification metadata scope, verified-caller filtering and permission-change/removal propagation path, and record these with an owner in the enforcement map;3.5 refines storage fields and update configuration.
- Identify every protected path that would otherwise rely on prompt restrictions and assign a model-independent trusted authorization check in the enforcement map, including alternate retrieval or tool routes.
- Where 1.4 obligations require sensitive-field minimization, choose the permission-related masking/redaction point and protected-access decision/outcome audit hooks in the enforcement map, referencing approved access/retention policy and 4.4's later event fields; masking supplements authorization.
- Agree the least-privilege allow/deny rules and default-deny conditions in the permission matrix, and record denied-principal and alternate-route test needs/evidence in the permission-model decision with enforcement owners.

**Output**
- A permission matrix with principal/role, resource scope, action, attributes/conditions, allow/deny/default-deny decision and policy owner, bound to 1.3 entitlements.
- A trusted enforcement map covering indexed permission metadata and ACL-change propagation, verified-caller filtering, source/gateway/tool checks, permission-related masking and audit hooks, alternate paths and enforcement owners.
- A confirmed permission-model decision naming downstream subject/actor, delegated/application authority, scopes/consent, trusted enforcement owner for each protected path and planned or available denied-path verification evidence.

*Technique reference: `references/stage-2-development-and-model-layer.md` (permissions).*

### 2.7 Model layer: fine-tuning, alignment, and compression (conditional)

When model training, alignment or compression is approved, establish the residual need versus the strongest feasible untuned baseline and select a supported method, compute approach and comparison strategy. This aspect owns model-change method and mitigation decisions, including supported training-control strategy. Use 2.8 for data preparation and partitions,3.1 for exact trainer/model arguments,Stage 4 for formal scoring and Stage 5 for deployed serving configuration.

**Requirements**
- Compare the best feasible untuned approach using prompting, supported structured output and retrieval when needed against approved task needs, then record the residual behavior/quality/cost/latency gap and verified method availability in the method decision table before choosing a model change.
- For trainable open-weight candidates, compare full training and supported parameter-efficient methods, including LoRA or QLoRA where relevant, on compute/memory/cost and task-quality needs; for managed candidates compare only documented methods, recording the choice in the method decision table.
- Identify retained capabilities at risk from the selected weight change, and record candidate supported mitigations and when to compare them in the retained-capability plan; use 2.8 for any replay dataset mix and the comparative protocol for acceptance references.
- Verify the trainer/provider's exposed controls and defaults, and record which learning-rate, epoch, batch, schedule or other controls will be fixed, searched or omitted and how validation/task results choose among candidates in the training-control table;3.1 records exact chosen arguments.
- Compare the selected model's supported training-context envelope with the long-input task need, and record any measured context-extension method and evidence-preservation requirement in the method/control tables;2.8 chooses compatible sequence preparation and 3.1 exact supported limits/arguments.
- If the untuned baseline has a measured alignment gap, choose a supported supervised, preference or reward-based method and record its demonstration/pair/grader prerequisites, platform availability and rationale in the method decision table, referencing 2.8 data and 4.3 grader ownership.
- Compare quantisation and distillation where training memory, model fit or serving cost/latency needs justify them, and record purpose, supported method and quality/latency/memory/cost evidence in the method decision table;5.2 refines deployed runtime/hardware settings.
- Record the selected method's required training/validation/held-out dataset roles and constraints as 2.8 dataset-plan references in the method/control tables, instead of maintaining separate source, label, preparation or split records.
- Define the changed-model versus best untuned baseline comparison protocol using the same 2.8 held-out dataset references and the acceptance/constraint needs from 1.2/1.4, and record target/retained checks, trial needs and adoption rule in the comparison plan; hand formal metric definitions and release gates to 4.2.

**Output**
- A model-method decision table with best untuned baseline, measured residual need, candidate method, provider/model availability, compute/memory/cost evidence, long-input or alignment/compression prerequisites, rationale and data-role references.
- A retained-capability mitigation plan for selected weight changes, naming at-risk capabilities, mitigation candidates and comparison triggers, with 2.8 dataset andO-2.7-04 comparison references; otherwise not applicable.
- A training-control strategy table listing supported exposed settings/defaults, fix/search/omit strategy, validation/task selection criterion, long-input preservation and dataset references, and exact-argument handoff to 3.1; mark not applicable without training.
- A baseline-versus-changed-model comparison plan with pinned held-out dataset references, target and retained-capability checks, approved acceptance/constraint references, trial policy, adoption rule and formal metric/gate handoff to Stage 4.

*Technique reference: `references/stage-2-development-and-model-layer.md` (model layer).*

### 2.8 Data engineering

Plan evaluation-data supply and selected training/validation data, including sources, permitted use, coverage, labels, preparation, partitions, versioning and overlap controls. This aspect owns dataset engineering and the admission procedure for already reviewed historical cases or future reviewed cases. Consume model-method needs from 2.7 and design the interface for 6.1's later production-review inputs; Stage 4 refines the actual evaluation case/environment/grader suite and its executed versions without creating a second training-data plan.

**Requirements**
- Assess required dataset coverage across approved tasks, users and reachable edge cases, and record material representation gaps, label needs and quality checks in the per-dataset plan.
- Define each dataset's task, purpose, source and permitted use, then choose applicable training/validation/evaluation partitions and duplicate/overlap controls in the dataset plan;4.1 refines the evaluation cases and pinned suite versions.
- Where labels are required, agree their meaning and annotation guidance and choose disagreement, bias and erroneous-label review/adjudication appropriate to the source, recording these with an owner in the dataset plan.
- Choose cleaning, augmentation or sequence preparation only for a documented data gap or 2.7 method constraint, and record its purpose, evidence-preservation rule and label/representation/held-out validation in the preparation record before retaining the transformation.
- When 2.7 selects replay as a mitigation candidate, choose its representative prior-task data composition and preparation in the dataset/preparation records, linking target/retained comparison evidence and agreed gates rather than reselecting the model-level remedy.
- Design permission/label review and admission of already available historical reviewed cases or future root-cause-reviewed cases to a versioned regression or approved training dataset, and record the reviewed-input contract, destination/version rule, split/overlap protection and offline validation in the failure-to-data flow; 6.1 later supplies production-review inputs.
- Link each selected 2.7 training method to its authoritative dataset-plan rows and reviewed-case admission flow, recording source/version owner and required dataset role so no separate training-data plan is maintained.

**Output**
- A per-dataset engineering plan with task/purpose, source and permitted use, version/estimated size, task/user/edge coverage and gaps, label meaning/guidance/quality/adjudication, partition/overlap policy, access owner and model-method/replay references.
- A preparation record listing selected cleaning, augmentation, sequence preparation or replay composition, documented purpose, evidence-preservation rules and checks for label validity, representative coverage and held-out outcomes.
- A reviewed-case-to-data procedure with an input contract for available historical or future root-cause-reviewed cases, permission/label review, versioned regression or approved training assignment, source/version ownership, partition/overlap protection and offline validation.

*Technique reference: `references/stage-2-development-and-model-layer.md` (data engineering).*

### 2.9 Security and isolation

Design the security controls for the workflow's reachable trust boundaries: execution/resource isolation, untrusted inputs and components, credentials, argument/result validation, safe error exposure, memory poisoning and approval integrity. This aspect owns threat and trust controls. Consume 1.3 approval policy,2.4 memory content/lifecycle and 2.6 access enforcement;Stages 3,5 and 6 refine exact contracts, deployed verification and incident procedures.

**Requirements**
- For each reachable executor or controlled-tool path, choose process/user/data isolation and allowed filesystem/network/host resources, and record the executor owner, credential boundary and rationale in the isolation decision; use 2.6 for protected resource/action authorization.
- Map retrieved content, tool results and third-party Skills/MCP components to reachable injection or authority-confusion threats, and record their version/provenance review and controls preventing content from granting authority in the threat/control table.
- Choose the trusted secret source or credential broker and scoped consumers for selected integrations, and record provisioning, model/chat/tool-result/log exclusion, rotation and revocation owners/triggers in the secrets-handling rule.
- Choose trusted validation of model-proposed arguments and external result structure/provenance before consequential use, and record the validation boundary, reject outcome and 2.6 authorization dependency in the threat/control table;Stage 3 supplies the exact supported schemas.
- Using 2.3's failure categories, choose the safe category/cause/correlation information visible to the model and the protected operator-diagnostic path, and record the allowed/omitted fields and secret redaction in the threat/control and secrets rules.
- When durable memory is selected, choose provenance and instruction-origin controls that stop untrusted entries becoming governing authority, and record risk-selected behavior-change review and traceable correction/recovery interfaces in the memory trust summary, consuming 2.4 content/lifecycle and 2.6 access policy; otherwise record absence.
- For actions gated by 1.3, choose controls binding the authorized decision to the exact action/arguments and call identity, and record mismatch, denial or expired-decision rejection in the threat/control table;2.3 wires pause/continuation and 5.4 refines deployed resume integrity.

**Output**
- A threat/control table naming each reachable threat, input/provenance and trust boundary, selected validation/injection/error-exposure/approval-integrity control, referenced permission policy, owner, planned or available test evidence and residual risk.
- A confirmed isolation decision per reachable execution path naming executor owner, process/user/data separation, allowed filesystem/network/resources, credential boundary, rationale and protected-action permission references.
- A secrets-handling rule covering trusted provisioning/brokering, scoped consumers, model/chat/tool-result/log/error exclusion, protected diagnostics and rotation/revocation owner and trigger.
- A durable-memory trust-protection summary covering provenance/instruction-origin and poisoning controls, risk-selected behavior-change review, referenced 2.4 content/lifecycle and 2.6 access contracts, and traceable correction/recovery interface to 6.3; otherwise an explicit no-durable-memory decision.

*Technique reference: `references/stage-2-development-and-model-layer.md` (security).*

**Deliver and confirm:** Stage 2 Word document with the routing decision, the selected tools and model roles, the Graph, node overview, memory design, retrieval design, permission model, model layer decision, data plan, and security foundation. Resolve architectural choices before advancing.


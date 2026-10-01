# Stage 3 — Detailed design

**Current deliverable:** `03-detailed-agent-design.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-3-detailed-design.md](stage-3-detailed-design.md).

### 3.1 Model, service, tool, and server arguments

Specify the exact model, selected trainer, tool, service, and server call contracts for the integrations approved in Stage 2. Verify applicable official documentation and record supported parameters, chosen defaults, authentication, per-call failure handling, and long-running operation protocols. Bind tool arguments to 3.2 input schemas and write model-facing capability metadata. Reference approved workflow and security decisions; 3.3 owns node model output schemas and 3.7 owns configuration exposure and overrides.

**Requirements**
- For each proposed integration parameter, record support for the selected model, endpoint, API/SDK version, and deployment mode; omit unsupported options and cite the documented restriction in the argument table.
- Mark unverifiable parameter details unresolved in the argument table, naming the missing official evidence and the owner or action required to verify them before approval.
- For each external write, record the provider's idempotency or outcome-query mechanism, operation-key rules, and reconciliation step for unknown timeout results; specify permitted replay and reference the approved 2.3 recovery transition.
- For each reachable integration failure class, record correction, authorization recovery, bounded transient retry, measured capability fallback, or terminal action; include SDK retries, replay eligibility, per-attempt/total deadlines, backoff, attempt cap, and the 2.3 transition reference.
- For each approved tool or Skill, write its exact name, user goal, activation trigger, limits, exclusions, and accurate metadata; reference its 2.2 action/permission scope and reopen that decision if separate permissions require separate actions.
- Derive each model-facing tool input schema from its 3.2 artifact schema, record the provider-supported strict mode/subset, and name the application validator for constraints the vendor schema cannot express.
- For each integration, record its supported authentication method, approved credential/secret reference, applicable account-link or refresh steps, and missing/expired credential recovery under 2.9 provisioning and secrecy controls.
- For long-running operations, define the completion mechanism (polling, webhook or callback, or task result), deadline, cancellation, terminal statuses, and failure reporting; set backoff when polling.
- Record supported model-call correctness controls and their values for each approved role, and exact exposed trainer controls/defaults and chosen values when 2.7 selects training; cite endpoint/version sources, reference 3.3 output schemas, and consume 3.6 budget allocations for call caps.
- Assign stable IDs to vendor parameter support/default records and name each call consumer; record chosen values here except where retrieval settings in 3.4 or numerical allocations/triggers in 3.6 own them, using their value IDs. Let 3.7 reference these records for configuration exposure.

**Output**
- Model-call, selected-trainer, tool-call, and service/server-connection argument tables with stable parameter/default IDs, consumer, name, type/unit, required/conditional status, support/verification status, documented range/default or not specified, chosen value or omission, or a reference to an authoritative 3.4 retrieval/3.6 numerical value, rationale, official source URL, version, and access date. Tool rows bind 3.2 schemas to strict encoding and validators; model rows reference 3.3 output schemas.
- A tool and Skill description table with name, user goal, selection description, exclusions, trigger, accurate metadata, and approved 2.2 action/permission scope.
- A per-call failure-class table referencing 2.3 transitions, with correction/terminal action, replay eligibility, write idempotency/outcome-query and key rules, unknown-result reconciliation, SDK retries, deadlines, backoff, attempt cap, and approved fallback.
- An authentication/credential-flow note per integration with method, approved secret-source reference, linking/refresh where used, and missing/expired recovery under 2.9 controls.
- A long-running-operation note per applicable integration with completion mechanism, deadline, cancellation effect, terminal statuses, bounded polling backoff where used, and failure reporting.

*Technique reference: `references/stage-3-detailed-design.md` (integration arguments, tool descriptions).*

### 3.2 Node data flow and schemas

Define authoritative application input/output and inter-step artifact schemas for the path approved in 2.3, recording field meanings, types, constraints, producers, consumers, validators, and owners. Define graph channels only for a selected graph and summary/checkpoint payloads only where used. Reference model output schemas in 3.3 and call/replay contracts in 3.1. Persistent record/index schemas belong to 3.5; checkpoint storage, retention, and operational resume belong to 5.4.

**Requirements**
- Record permitted intermediate states and required success/failure invariants for terminal application results; remove redundant fields or assign one authoritative source where values could contradict each other.
- For each large evidence/content field, choose retained payload or retrievable reference, record retrieval prerequisites and lifetime, and justify continuation needs; pass size/refetch assumptions to 3.6 for cost estimation.
- For each history, evidence, tool-result, error, or output field, name its downstream/resume consumer and required lifetime; omit fields without a use and list telemetry observations for the later 4.4 design instead of storing duplicate audit payloads in workflow state.
- Record actor/access references as application-supplied fields with a trusted producer and 2.6 enforcement reference; exclude live clients, model instances, and credentials from serializable state and reference their resource owner in 3.7.
- When 2.4 selects summarisation, specify fields for task identifiers, constraints, decisions, completed actions, evidence references, and open work; bind source/consumer fields and reference approved correction/retention policy.
- When recovery is required, map completed/pending work, required input/evidence references, action outcome IDs, and execution metadata to platform checkpoint fields and actual resume boundary; reference 3.1 replay guarantees and 5.4 backend/expiry/resume activation.
- For each bounded text, binary, or model-context artifact, record character, encoded-byte, or token units and the validator/consumer enforcing the constraint; repeat validation only at a distinct reachable boundary.
- Map each 2.3 step input/result to its schema ID and producer/consumer; label data-flow edges and terminals, referencing a 3.3 schema when a model result passes unchanged.

**Output**
- An authoritative schema table per application/inter-step artifact with ID/version, field, meaning, type, required/nullable, constraints/unit, invariant, producer/trust source, consumer, validator, owner, representation and lifetime. Reference unchanged 3.3 model results; record absent inter-step artifacts for direct paths. For large retained or referenced content, include continuation justification, retrieval prerequisite/resolution path, availability/lifetime and size/refetch-cost assumptions passed to 3.6. Record omitted-telemetry observation handoff needs for 4.4 without defining event fields here.
- For a selected graph, a state description with channels, writers/readers, update/merge rules, legal intermediate states, terminal invariants, input/internal/terminal scope, trusted identity references and excluded live resources; otherwise direct-path input/output ownership and absent graph state.
- If summarisation is selected, the retained summary schema with source bindings, evidence references, continuation consumers and 2.4 correction/retention references.
- A Mermaid data-flow figure of the approved path with artifact/schema IDs on edges and success/failure terminal artifacts, complementing 2.3 control flow.
- If checkpointing is used, a payload/platform mapping for identity references, state values, completed/pending work, required inputs, outcome IDs, execution metadata and actual resume boundary, with 3.1 replay-contract and 5.4 lifecycle references. Reference the large-content representation/prerequisite rows and their resume-availability checks from O-3.2-01.

*Technique reference: `references/stage-3-detailed-design.md` (state and schemas).*

### 3.3 Prompts and structured output

Write the full versioned prompt template and model output schema for every approved model-driven step, with role separation, input variables, context-source bindings, terminology, and selected examples. Bind the schema to the provider mechanism supported in 3.1 and define parsing, application validation, refusals, incomplete output, and bounded format recovery. Consume 2.3's step topology and 2.4/2.5's context and grounding policies. 3.2 references these schemas for transport and application output; 4.3 owns evaluation graders and calibration.

**Requirements**
- In each model output schema, record field meanings, required/nullability rules, allowed values, cross-field relationships, and empty/failure shapes for the approved task; reference application artifact schemas rather than maintaining a second final-output definition.
- Write each template's task, response format, domain terminology/context, safety, and style instructions from approved requirements and node responsibilities; record any required node-topology change for reconfirmation in 2.3 before writing new node prompts.
- Record a zero-shot decision or representative normal/boundary input-output examples for each prompt, explaining the task need and verifying that example fields and values conform to the same model output schema.
- For each model step, bind its schema version to a supported structured-output API/engine and application validator; record bounded repair for recoverable format/validation failures with a link to 3.1 call limits, and separate refusal/incomplete paths.
- For each reachable syntax, schema, semantic/evidence, extra-content, refusal, and truncated/incomplete failure, record the detector, user/application result, and repair, review, or terminal handling in the failure checklist.
- Where 2.3 selects separate solving and formatting steps, define the exact input/output handoff and prompt for each, excluding hidden chain-of-thought from the contract; otherwise record the single-step decision and its available performance evidence.
- For prompts with long or heterogeneous context, specify variable/context-slot boundaries and which approved subtask each slot supports; link observed output errors to a proposed context/template change, and reopen 2.3 for changes to executable steps.
- After parsing/schema validation, name deterministic business-rule and source-support validators and their failure handling; for approved high-risk residual review, record the authorized reviewer role, trigger, and reviewed artifact, then hand off judge measurement/calibration needs to 4.3.
- Record the selected schema's compatibility with the provider-supported subset and complexity limits, the unsupported constraints handled by application validators, and a representative adherence check or untested status.
- For each prompt version, verify that instructions, example fields, enum meanings, and output-encoding configuration reference the same schema version; record any mismatch and resolution in the prompt rationale.
- Label template roles and runtime user/context/source slots, bind each slot to its approved source artifact, and record the minimum inputs needed for that node; keep design rationale outside model-visible text.
- For evidence-based outputs, add source IDs/locators and qualifications to the model schema or compatible citation channel, bind them to authorized 3.2/3.4 evidence records, and name the support validator and insufficient-evidence handling from 2.5.
- Give each model output schema a stable ID/version and name the 3.2 adapter or unchanged-artifact consumer; reference the same schema at each handoff instead of redefining its fields.

**Output**
- The exact versioned, role-separated prompt template for each approved model step, including task/terminology/style boundaries, variables/context slots with source artifact IDs, and model-schema version, excluding runtime values.
- Selected schema-valid normal/boundary input-output examples bound to prompt/schema versions, or a recorded zero-shot decision per prompt.
- A per-model-step structured-output contract with schema ID/version and field/invariant definitions, provider engine/encoding and supported-subset compatibility, application-schema/adapter references, ordered validators, authorized runtime reviewer/trigger/artifact and later calibration needs where used, refusal/incomplete handling, and bounded repair linked to 3.1 call limits.
- A reachable output-failure checklist with syntax, schema, semantic/evidence, extra-content, refusal and incomplete class, detector, application/user result, and repair/review/terminal path.
- A prompt-design rationale recording context partition, example selection, selected solve/format topology reference, available performance/adherence evidence or untested status, and prompt/example/schema consistency disposition.

*Technique reference: `references/stage-3-detailed-design.md` (prompts and structured output).*

### 3.4 Retrieval and chunking settings (conditional)

Include this aspect only when retrieval is approved. Specify exact segmentation, source-access, query-processing, embedding, candidate-count, and ranking settings for the route selected in 2.5, marking absent index/chunk/rank stages inapplicable. Bind authorization and provenance to approved policies and artifact schemas. Record focused local calibration fixtures, named measure implementations, and available or pending comparison evidence; Stage 4 later expands these into formal datasets, metrics, and thresholds. 3.5 owns storage initialization and lifecycle and references these retrieval settings.

**Requirements**
- Choose no-chunk/direct access or segmentation by source and query; where segmented, define boundaries, size unit, overlap and hierarchy. Preserve stable source/chunk IDs, version and available locations.
- For sources whose fragments lose meaning, record the selected title, section, parent, or chunk-specific enrichment rule and a setting-comparison fixture; include available relevance/cost evidence or mark the choice untested.
- Reference the 2.5 route/store decision; for vector stages, record a stable embedding-configuration ID with model/version, dimensions, and query/index compatibility, which 3.5 will reference for its index definition.
- For each approved query/corpus route, record concrete source lookup or lexical/vector/hybrid/rerank settings and the 2.6 authorization/source-version check boundary; add a rerank stage only through reconfirmed 2.5 design and measured or planned benefit evidence.
- Record initial-candidate, reranker-input, and final-evidence counts for existing stages, with setting-comparison queries and 1.4 budget constraints; record not applicable for an unranked exact lookup.
- For each query-processing step selected in 2.5, record its trigger, exact rewrite/synonym/filter rule, preserved original wording/identifiers, and resulting query artifact; omit unselected transformations.
- For local retrieval-setting calibration, record representative query fixtures, reference evidence, source/index versions, applicable counts, named measure implementation/version, and coverage/ranking/latency/cost observations; include available measured values with provenance or pending measurement, and pass them to Stage 4 for formalization.
- Assign stable IDs to segmentation, vectorizer, query, and ranking settings and identify their consumers; reference 3.5 store/index definitions for persistence without repeating connection or lifecycle setup here.

**Output**
- A per-source segmentation table with approved source reference, direct no-index/no-chunk decision or boundary, size/unit, overlap/hierarchy, stable source/chunk IDs and locations, version/provenance, and selected enrichment rule/reason.
- A retrieval-settings record referencing the approved 2.5 route and 3.5 store/index, with stable setting IDs/consumers, applicable source/query/rank parameters, vectorizer model/version/dimensions/compatibility, query transformation triggers and preservation rules, candidate counts, and approved authorization/version check bindings. Include the input/resulting query artifact and canonical 3.2 schema IDs for selected transformations.
- A focused local retrieval calibration record with query fixtures, reference evidence, source/index/setting versions, applicable counts, named measure implementations/versions, required observations, available values and provenance or pending measurement, and relevance/cost trade-offs; mark ranking inapplicable to unranked lookup and hand the record to Stage 4.

*Technique reference: `references/stage-3-detailed-design.md` (retrieval and chunking).*

### 3.5 Database configuration and lifecycle

Configure the application, memory, knowledge, and answer-cache stores approved in Stage 2 or the answer cache selected in 3.6. Define physical records, tables, collections, indexes, constraints, startup loading, initialization, migration, and source-specific freshness/update/delete mechanisms. Reference 3.1 connection/authentication records and 3.4 embedding/retrieval settings. 3.2 owns workflow and checkpoint payload schemas; 5.4 owns the deployed checkpoint backend and run-state retention/resume lifecycle.

**Requirements**
- For each store definition, record the 3.1 connection/credential contract ID and the 3.7 resource/setting consumer; configure physical storage through those bindings instead of repeating integration parameter values.
- For each approved persistent application, retrieval or memory store from 2.2/2.3/2.4/2.5, and answer cache selected in 3.6, record physical record/key/index definitions and migration bindings; reference unchanged 3.2/3.3 payload fields and the 3.4 embedding configuration ID rather than redefining them. Keep in-flight checkpoint deployment in 5.4.
- Document durable backing, index or collection identifiers, and the startup connection or load path for each selected index, so unchanged content is not rebuilt on restart.
- Name the store, lifecycle, and connection/resource owners in the definition table, using only the 3.1 approved credential/secret reference and no secret value.
- Define reproducible initialization, schema or index versioning, migration validation, and cutover; include a rebuild path for incompatible changes.
- For each changing source, reference its approved freshness/staleness target and specify change/deletion detection, incremental reprocessing, embedding-version rebuild, stale-record retirement, and query-visibility checks needed to meet it.
- For each answer cache selected in 3.6, define audience/authorization-aware keys, source/index version scope, expiry/write invalidation, and a concurrent refresh mechanism satisfying approved staleness; record exact cache settings and their consumers.
- Assign stable schema/index IDs to persistent application, memory, knowledge, and cache records; reference 3.2 workflow/checkpoint payload schemas and identify checkpoint storage/lifecycle requirements for the later 5.4 deployment design without redefining them here.

**Output**
- A physical store-definition table with approved logical-store reference, store/lifecycle/resource owner, table/collection/index and schema version, source/record IDs, distinct storage fields/types, unchanged-payload schema references to 3.2/3.3, keys/constraints, query/consistency assumptions, durable backing and startup load path, 3.1 connection/credential reference, 3.4 vectorizer-setting references, cache settings where used, and 3.7 consumers. Link checkpoint stores to 5.4 rather than defining them here.
- An ordered initialization and migration sequence or Mermaid figure with startup/load path, schema/index revisions, replayable steps, validation, cutover, and supported recovery/rebuild.
- A source-specific freshness and cache-validity implementation plan referencing approved staleness targets, with change/delete detection, incremental reprocessing/re-embedding, stale retirement, index visibility checks, exact cache key/expiry/invalidation bindings, and concurrent refresh sequence.

*Technique reference: `references/stage-3-detailed-design.md` (databases).*

### 3.6 Cost and token control

Estimate cost and token use for representative approved workflow paths, including failed/retried work and handoffs, and allocate phase/call budgets within 1.4's end-to-end ceilings. Record unit prices, measured or untested assumptions, economic trade-offs, exact numerical token/cost triggers for selected context-reduction methods, and task-stop enforcement. Reference approved model/context policies and physical cache mechanisms; revise their owning aspect when economics requires a design change. 4.2 owns formal cost metric definitions and thresholds, and 5.6 owns deployed traffic-class spend governance.

**Requirements**
- For representative 2.3 paths, record per-node/turn input/output and cached-read/write tokens, calls, retries/handoffs, tool/service fees and unit-price versions; allocate phase/call latency, token and spend limits within 1.4 ceilings using available traces or explicitly estimated assumptions.
- Record each cost-control recommendation, its effect on approved quality/latency needs, the user's chosen trade-off and decision status; reopen 1.4 only if the approved ceiling itself must change.
- Compare supported prefix caching, selected answer caching, approved context reduction and candidate model/effort routing by net charges, quality/freshness/isolation/latency effects; record selected/rejected controls and exact settings/policy references in 3.1, 3.5 and 2.4, handing deployment-routing needs to 5.3.
- For each context-reduction method selected in 2.4, calibrate its numerical token/cost trigger from history growth, cache/compaction charges and task-continuity evidence; record a stable trigger ID, unit/value, rationale, measured or pending status, preserved-state policy reference and 3.7 configuration consumer.
- Estimate or measure representative and costly-tail task success, latency and total charges for approved model/effort roles and any proposed route; record the direct/candidate economic comparison, recommended 2.2 role changes, and deployment-routing requirements to refine in 5.3.
- Within 1.4 ceilings, record phase/call/task token or spend allocations and the application enforcement point that blocks further calls on breach; distinguish advisory budgets, 3.1 per-response caps and hard ceilings, including in-flight calls and uncertain write outcomes.
- Include failed/retried attempts in spend and cost-per-attempt/success estimates, reporting success assumptions and costly-tail scenarios; record calculation inputs, price versions and available evidence so Stage 4 can formalize the cost measures and acceptance protocol.

**Output**
- A per-path/node/turn estimate with calls, token classes, cache reads/writes, retry/handoff and failed-attempt costs, tool/service fees, price/version, assumptions and measured/estimated status, total/attempt/success cost and costly-tail scenarios.
- A cost-control decision record with candidates, selected/rejected measures, net charge effects, quality/freshness/isolation/latency trade-offs, user choice/status and implementation-owner references. For each selected 2.4 reduction method, include stable numerical trigger ID, unit/value, history/cache/compaction and continuity evidence, rationale, measured/pending status, semantic-policy reference and 3.7 setting consumer; pass validation observations to Stage 4.
- A budget-allocation and enforcement contract referencing 1.4 ceilings, with derived phase/call/task time/token/spend limits, trace/estimate evidence, enforcement point, no-further-call/breach action, in-flight/uncertain-write treatment, 3.1 cap references, and accounting inputs and observed/pending measures passed to Stage 4.

*Technique reference: `references/stage-3-detailed-design.md` (cost and tokens).*

### 3.7 Application settings, consistency, and readiness

Specify how the application stores, validates, overrides, exposes, and consumes configuration defined in 3.1–3.6 and application-only settings owned here, and how it starts, shares, cancels, and shuts down clients, sessions, and background work. Bind internal results to the application output and streaming display contract. Map functions to approved steps, schemas, prompts/tools, settings, and checks, then record implementation handoff and readiness prerequisites. 4.1–4.5 own full evaluation datasets, metrics, graders, telemetry, and CI verdicts; 5.4 owns deployed run-state lifecycle.

**Requirements**
- For each exposed setting, record its source precedence, local validation and consumer; reference the chosen/default value and allowed range from its 3.1–3.6 owner when already defined. For application-only lifecycle, concurrency or presentation settings introduced here, choose and justify their defaults and allowed values in the setting table; use secret references/placeholders.
- For each client/tool/session/background resource, record startup/shared-use/shutdown owner, concurrency limits, history/state consumer and cancellation wiring to 3.1 protocols; identify checkpoint/resume deployment needs for 5.4 and state whether cancel stops downstream work or needs result reconciliation.
- Map 3.2 application progress/final artifacts and 3.3 model results to renderer events; define final-result completion/deduplication, restricted diagnostic separation, and instrumentation needs handed to 4.4.
- Specify runnable checks for configuration, artifact adapters, resource lifecycle and approved functional interfaces, with fixture/expected result/runner/run point; record task-outcome and stochastic-regression hooks from 1.2 for the later 4.1/4.2 evaluation design rather than a second full suite.
- For long-running implementation, identify canonical paths for instructions, objective/decisions, progress/next action, acceptance results and version history, with update owner and discovery sequence for a later session.
- For each required complex-system boundary, name the lint/schema/dependency rule or runnable component/integration check and owner; record required instrumentation and end-to-end task-evaluation hooks for Stage 4 rather than designing a parallel trace/evaluation system.
- For each implementation prerequisite and contract verification, record evidence/status, owner and verification gate, linking design status to the end-matter decision ID; resolve design-changing blockers before approval and identify credentials/access that remain setup prerequisites.

**Output**
- An application settings and resource-lifecycle record with setting ID, purpose/type, authoritative default/allowed-value reference, source precedence/storage, local validator, secret reference, user-changeability and consumer; resource rows specify startup/shared-use/shutdown owner, concurrency, state/history binding, cancellation/protocol references, renderer events and final-completion deduplication. Identify application-only settings owned here and record their justified defaults/allowed values, while existing parameter rows reference their value owner.
- A consistency table linking each approved function to its step/node, authoritative input/output/model schemas, prompt/tool, setting/resource consumer, renderer binding, required interface boundary and acceptance criterion, with planned Stage 4 evaluation/instrumentation hooks.
- A runnable implementation-check plan for settings, schemas/adapters, resources and functional interfaces, with boundary/check ID, fixture, expected result, runner, run point and owner; include task/regression hooks from 1.2 for Stage 4 formalization.
- A readiness and implementation-handoff checklist with decision references, prerequisites, evidence/status, owner and verification gate; for long implementation, include canonical instruction/decision/progress/acceptance/version artifact paths, update owner and discovery sequence.

*Technique reference: `references/stage-3-detailed-design.md` (settings, consistency, readiness).*

**Deliver and confirm:** Stage 3 Word document with parameter tables, schemas, full prompts and examples, retrieval settings, database definitions, cost estimate, settings, verification criteria, and implementation prerequisites. After approval, the six documents form the implementation brief.


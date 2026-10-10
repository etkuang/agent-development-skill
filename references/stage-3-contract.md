# Stage 3 — Detailed design

**Current deliverable:** `03-detailed-agent-design.docx`.

This contract defines the Stage 3 decisions and document content. Apply the shared workflow and document rules in [SKILL.md](../SKILL.md).

**Output applicability:** The `### output` lists describe candidate content, not mandatory artifact or field checklists. Select the outputs and level of detail useful for the project's size, complexity and actual decisions. Small projects may use short paragraphs, simplify tables or omit unnecessary outputs. Retain ordinary aspect headings and required end matter, briefly explain inapplicable ordinary aspects, and omit unselected optional aspects. Record unresolved information that affects a needed decision.

Refine approved Stage 1 and Stage 2 decisions. Establish application data before vendor bindings and model outputs, and select cost controls before configuring their stores. Use available local measurements or name pending checks; Stage 4 formalizes full evaluation. A later configuration that invalidates an earlier assumption returns to that assumption's owner.

## 3.1 Application artifacts and state schemas

### To clarify

- What application inputs, evidence, tool results, progress and final outcomes cross each selected step boundary?
- Which fields have a downstream or resume consumer, and what legal intermediate and terminal states exist?
- Should large content be retained or referenced, and will it still be available when needed?
- Does the chosen path require graph channels, a continuation summary or checkpoint payload?

### output

- **Application/artifact schemas:** stable ID/version, field meaning/type/nullability, constraints and units, invariants, trusted producer, consumer, validation boundary, representation and lifetime. Give each domain field one owner; avoid duplicate derivable state.
- **Selected state design:** for a graph, channels, readers/writers, merge rules and input/internal/terminal scope; for a direct path, application input/output ownership and only actual inter-step artifacts.
- **Representation and continuation decision:** retained payload versus resolvable reference, large-content purpose, retrieval prerequisites, availability/lifetime and size/refetch assumptions for 3.5. Summaries preserve selected task-critical identifiers, constraints, decisions, action outcomes, evidence and open work.
- **Checkpoint payload mapping:** when selected, platform identity/values/pending work, durable outcome references and actual resume boundary. Exclude clients, models and credentials from serializable state.
- **Data-flow view and observation needs:** identify artifact IDs at real boundaries when useful; hand telemetry-only observations to Stage 4. Reserve model-only output fields for 3.3; adapters reference its completed schema rather than copying it.

### out of scope

Vendor encoding belongs to 3.2; model-only schemas and prompts to 3.3; physical records/indexes to 3.6; trace fields to Stage 4; deployed checkpoint retention and resume coordination to Stage 5. Trusted identity fields carry context but do not authorize access.

### Prerequisite

Consult approved 1.2–1.4 and 2.1–2.4 policies plus 2.9 step, state and recovery decisions.

### Technical references

- When assigning domain schema and adapter ownership, see [application-schema-ownership.md](technological%20documentations/application-schema-ownership.md) for reference.
- When selecting retained state fields and payload/reference representation, see [state-payload-selection.md](technological%20documentations/state-payload-selection.md) for reference.
- When the selected runtime checkpoints or resumes work, see [checkpoint-payload-mapping.md](technological%20documentations/checkpoint-payload-mapping.md) for reference.

## 3.2 Model, service, tool, and server call contracts

### To clarify

- Which arguments and defaults are supported by each selected model, endpoint, SDK/API version and deployment mode?
- Which application schemas must tools encode, and which constraints need application validators?
- How do authentication, expired credentials and long-running completion/cancellation work?
- For selected remote agents, which protocol/binding, discovery metadata and task/context/artifact contracts must the client encode?
- What retries already occur in SDKs, and what replay or reconciliation is safe for each reachable failure?
- What descriptions distinguish neighboring tools and Skills accurately?

### output

- **Versioned argument/connection tables:** parameter/default ID, consumer, type/unit, supported range/default, chosen value or omission, rationale, official source/version/access date and verification status. Cover selected trainer controls only when training is approved.
- **Tool-input encoding:** reference 3.1 domain schema IDs, provider-supported strict subset and application validators for unsupported constraints. Record supported output mechanisms for 3.3 without defining its model-result fields.
- **Capability metadata:** exact name, user goal, trigger, scope, exclusions and accurate permission/safety metadata under 2.5. A newly discovered action boundary requires revisiting that selection.
- **Authentication and asynchronous protocol:** approved secret reference, account linking/refresh where used, missing/expired recovery; completion/status/result mechanism, terminal states, deadline, cancellation effect and bounded polling where used. For selected remote-agent integrations, bind discovery metadata and protocol/version negotiation to exact calls, and reference 3.1 for task/context/artifact fields.
- **Call failure/replay table:** reachable class, correction/stop/fallback, SDK and application attempt accounting, per-attempt/total deadline, backoff/cap, replay eligibility, write operation key/outcome query and unknown-result reconciliation linked to 2.9. Hand call-price and resource assumptions to 3.5.

### out of scope

Product/model selection belongs to 2.5 and recovery transitions to 2.9. Do not duplicate application fields, prompt/model schemas, retrieval values, application budget allocations or configuration precedence. Unsupported or unverifiable vendor details remain unresolved.

### Prerequisite

Consult approved 2.4, 2.5, 2.7 when selected, 2.9, and 3.1 domain schemas and trusted boundary definitions.

### Technical references

- When choosing exact supported integration arguments, see [integration-parameter-verification.md](technological%20documentations/integration-parameter-verification.md) for reference.
- When encoding tool input schemas for a provider, see [tool-schema-encoding.md](technological%20documentations/tool-schema-encoding.md) for reference.
- When binding authentication or account-linked access, see [credential-flow-design.md](technological%20documentations/credential-flow-design.md) for reference.
- When an operation completes asynchronously, see [asynchronous-operation-protocol.md](technological%20documentations/asynchronous-operation-protocol.md) for reference.
- When binding a selected remote-agent protocol to exact calls, see [remote-agent-integration-selection.md](technological%20documentations/remote-agent-integration-selection.md) for reference.
- When specifying retries or uncertain write outcomes, see [safe-retry-and-write-reconciliation.md](technological%20documentations/safe-retry-and-write-reconciliation.md) for reference.
- When writing tool or Skill activation descriptions, see [capability-description-design.md](technological%20documentations/capability-description-design.md) for reference.

## 3.3 Prompts and structured output

### To clarify

- What exact task, context and response does each approved model step require?
- Which domain fields can reuse 3.1 schemas, and which model-only fields need a distinct schema?
- What output mode supports the selected provider and citation channel?
- Which reachable parsing, schema, business-rule, evidence, refusal and incomplete-output failures need distinct handling?
- Do examples or a separately approved reviewer improve measured behavior?

### output

- **Full versioned prompt templates:** roles, task/terminology/style boundaries, variables and labeled runtime context/source slots, minimum node inputs and schema references. Keep rationale outside model-visible text.
- **Model-result and encoding contract:** stable schema ID/version for model-only fields or a reference to unchanged 3.1 domain fields, provider-supported mode/subset, adapter/consumer, ordered application/business/evidence validators and compatible citation binding.
- **Examples and consistency evidence:** selected schema-valid normal/boundary examples or a zero-shot decision, prompt/example/schema version consistency and observed adherence or pending checks.
- **Output-failure handling:** reachable syntax, schema, semantic/evidence, extra-content, refusal and incomplete conditions, detector and application/user outcome, bounded repair under 3.2 or approved review/terminal path.
- **Prompt rationale:** context partition, evidence support, examples and approved solve/format topology. For residual runtime review, record authorized reviewer, trigger and artifact; hand grader calibration needs to Stage 4.

### out of scope

Do not silently introduce new executable steps, disclose hidden reasoning or use structural validity as proof of truth. Domain schemas remain in 3.1, vendor call limits in 3.2, grounding policy in 2.2 and offline evaluation graders in Stage 4.

### Prerequisite

Consult approved 1.2, applicable 2.1–2.4 policies, 2.9 model-step responsibilities, 3.1 domain artifacts and 3.2 supported mechanisms.

### Technical references

- When writing a node's prompt and context slots, see [prompt-template-design.md](technological%20documentations/prompt-template-design.md) for reference.
- When choosing structured output and reachable failure handling, see [structured-output-validation.md](technological%20documentations/structured-output-validation.md) for reference.
- When binding claims to an output-mode-compatible citation channel, see [citation-output-binding.md](technological%20documentations/citation-output-binding.md) for reference.

## 3.4 Retrieval and chunking settings (optional)

### To clarify

- Which settings refine the approved direct or indexed source route?
- Does source shape require segmentation or contextual enrichment?
- Which selected query, embedding and ranking stages need exact parameters and counts?
- What representative queries and reference evidence can compare those settings within the approved budget?

### output

- **Source segmentation settings:** direct/no-chunk decision or boundary, size/unit, overlap/hierarchy, stable source/chunk/parent IDs, source version and available locators; selected enrichment and rationale.
- **Retrieval parameter record:** setting ID/consumer, approved route and integration reference, selected query-preservation/transformation/filter rules and query artifact IDs, vectorizer model/version/dimensions and query/index compatibility, and candidate/reranker/final counts only for stages that exist.
- **Authorization/provenance binding:** identify checks implementing 2.2–2.3 policy before evidence reaches consumers, referencing 3.1 artifacts.
- **Local calibration plan/results:** representative queries, reference evidence, source/index/settings versions, named measure implementation, quality/latency/cost observations and available evidence or pending execution. Hand fixtures and measurements to Stage 4 and vector settings to 3.6.

### out of scope

Source-route architecture and grounding stay in 2.2. Exact lookup does not require ranking, segmentation or embeddings. This aspect does not initialize stores or define the full evaluation suite and acceptance thresholds.

### Prerequisite

Consult approved 2.2 route/lineage and 2.3 access design, plus 3.1–3.3 artifact, integration and evidence-output contracts.

### Technical references

- When a selected source route needs segmentation, see [source-segmentation-selection.md](technological%20documentations/source-segmentation-selection.md) for reference.
- When fragments need additional context to retain meaning, see [retrieval-context-enrichment.md](technological%20documentations/retrieval-context-enrichment.md) for reference.
- When choosing query, vector or ranking settings using local evidence, see [retrieval-parameter-calibration.md](technological%20documentations/retrieval-parameter-calibration.md) for reference.

## 3.5 Cost and token control

### To clarify

- What calls, token classes, tool fees and failure/retry paths determine total task charges?
- Which estimates are measured, and which prices or workload assumptions need confirmation?
- Which supported cost controls preserve approved quality, freshness, access and latency?
- What numerical reduction triggers and phase/call/task allocations enforce the approved ceilings?

### output

- **Whole-path cost estimate:** representative and costly-tail paths, calls/node/turn, uncached and cached input/write/read tokens, output/reasoning-token accounting, tool/service fees, price/version, success/failure/retry assumptions and cost per attempt/success.
- **Cost-control decision:** direct baseline, selected/rejected prefix or answer caching, model/effort or context controls, net charges and quality/freshness/isolation/latency effects. Select any answer cache here using explicit mechanism/cost assumptions; 3.6 realizes its keys and lifecycle and returns material assumption changes here.
- **Numerical context-reduction triggers:** for methods selected in 2.1, stable trigger ID, unit/value, preserved-state policy reference, growth/cache/compaction and continuity evidence, rationale and measured/pending status.
- **Budget allocation/enforcement:** derive phase/call/task time/token/spend values within 1.4 ceilings, distinguish advisory limits from response caps and hard stops, and name enforcement point, no-further-call outcome, in-flight and uncertain-write handling. Hand values to 3.7 and accounting observations to Stage 4.

### out of scope

Do not change the service ceiling, model role or context meaning here without revisiting its approved owner. Vendor support/default facts belong to 3.2, cache physical validity to 3.6, formal measures to Stage 4 and aggregate deployed spend controls to Stage 5.

### Prerequisite

Consult approved 1.4 targets and 2.1, 2.5, 2.9 policies/path, plus 3.1–3.4 payload sizes, supported calls and selected settings.

### Technical references

- When estimating total task charges and cost per success, see [task-cost-accounting.md](technological%20documentations/task-cost-accounting.md) for reference.
- When selecting prefix or answer caching for economic benefit, see [cache-economics-selection.md](technological%20documentations/cache-economics-selection.md) for reference.
- When calibrating a selected context-reduction trigger, see [context-reduction-trigger-calibration.md](technological%20documentations/context-reduction-trigger-calibration.md) for reference.
- When allocating and enforcing application budgets, see [task-budget-enforcement.md](technological%20documentations/task-budget-enforcement.md) for reference.

## 3.6 Database configuration and lifecycle (optional)

### To clarify

- Which approved application, evidence, memory or answer-cache stores need physical configuration?
- What keys, indexes, consistency and startup paths satisfy the logical need?
- Which initialization, migration, source changes or deletion events must the store handle?
- How will a selected answer cache preserve audience authorization and freshness during concurrent changes?

### output

- **Physical store definitions:** logical-store/cache reference, store/lifecycle owner, table/collection/index and schema version, distinct storage metadata/types, keys/constraints, query/consistency assumptions, durable backing, startup load path and 3.2 credential/connection reference.
- **Schema/setting bindings:** reuse unchanged 3.1/3.3 payload IDs and 3.4 vectorizer settings; record exact store/cache settings with consumers for 3.7.
- **Initialization/migration sequence:** reproducible revisions, validation, cutover and supported recovery/rebuild; load unchanged persisted indexes instead of recreating them on every restart.
- **Source freshness/cache validity:** source-specific update/delete detection, incremental processing, embedding-version rebuild, stale retirement and query visibility under 2.2; selected cache audience/source-version keying, expiry/invalidation and concurrent refresh.

### out of scope

Do not introduce an unselected database or cache. Application/model fields remain in 3.1/3.3, embedding settings in 3.4, cache selection in 3.5 and checkpoint backend/expiry/operational resume in Stage 5.

### Prerequisite

Consult applicable approved 2.1–2.5 store needs and 3.1–3.5 schemas, connections, retrieval settings and selected cache decisions.

### Technical references

- When configuring an approved physical store and its durable startup path, see [physical-store-definition.md](technological%20documentations/physical-store-definition.md) for reference.
- When planning schema or index initialization and migration, see [store-initialization-and-migration.md](technological%20documentations/store-initialization-and-migration.md) for reference.
- When source changes or withdrawals must reach derived stores, see [source-freshness-maintenance.md](technological%20documentations/source-freshness-maintenance.md) for reference.
- When a selected answer cache needs valid concurrent reuse, see [answer-cache-validity.md](technological%20documentations/answer-cache-validity.md) for reference.

## 3.7 Application settings, resources, and readiness

### To clarify

- Where do settings originate, what precedence/validation applies and which component consumes each value?
- Who starts, shares, cancels and closes clients, sessions and background work?
- How do approved progress/final artifacts reach the user once, with safe diagnostic separation?
- What consistency checks and setup prerequisites make the design implementable and discoverable later?

### output

- **Configuration binding:** setting ID/purpose/type, authoritative value/range reference from 3.2–3.6, source precedence/storage, local validator, secret reference, user-changeability and consumer. Own justified defaults/ranges only for new application-only settings.
- **Resource/display lifecycle:** startup/shared-use/shutdown owner, concurrency, state binding and 3.2 cancellation/reconciliation protocol; renderer bindings to 3.1/3.3 progress/final artifacts and final-completion deduplication.
- **Function-to-contract consistency map:** approved function, step, input/output/model schema, prompt/tool, setting/resource, display binding, boundary check and acceptance requirement.
- **Runnable implementation-check plan:** selected settings/schema/adapter/resource/interface fixture, expected result, runner/run point and owner. Hand full task/regression and telemetry requirements to Stage 4.
- **Readiness/handoff record:** resolved design versus setup prerequisites, evidence/status, owner and verification gate. For long implementation, identify canonical instruction, objective/decision, progress/next-action, acceptance and version-history paths and their update/discovery owner.

### out of scope

Do not copy authoritative settings or build a second evaluation/telemetry system. Stage 4 owns formal task cases, measures, graders, trace fields and CI verdicts; Stage 5 owns deployed checkpoint and release lifecycle.

### Prerequisite

Consult approved 1.2 and 2.9 and applicable 3.1–3.6 schemas, calls, prompts, settings and budgets.

### Technical references

- When exposing and consuming authoritative application settings, see [application-configuration-binding.md](technological%20documentations/application-configuration-binding.md) for reference.
- When wiring client lifecycle, cancellation and final display, see [resource-lifecycle-and-display.md](technological%20documentations/resource-lifecycle-and-display.md) for reference.
- When checking implementation consistency and readiness, see [implementation-readiness-mapping.md](technological%20documentations/implementation-readiness-mapping.md) for reference.
- When implementation must continue across sessions, see [durable-implementation-handoff.md](technological%20documentations/durable-implementation-handoff.md) for reference.

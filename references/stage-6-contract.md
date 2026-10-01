# Stage 6 — Operations and iteration

**Current deliverable:** `06-operations-and-iteration.docx`.

Use this contract only when this stage is active. Follow the shared workflow, document rules and required end matter in [the skill entrypoint](../SKILL.md).
Read earlier approved project-document decisions only when a current aspect depends on them. References to other stages identify consumed decisions or future handoff owners; they do not request another stage's requirement contract.
All `references/...` paths in the aspect instructions below resolve from the directory containing the selected `SKILL.md`, even outside the project; use absolute resolved paths with file tools. Markdown links resolve from this contract's directory. Inspect technique headings and select only the paragraphs/procedures needed at this aspect's current design depth; broad links do not request every subsection. Use heading-only navigation in cross-stage technique files, without broad body-keyword searches. For guidance from another stage's technique file, identify the active decision it informs and omit instructions for that stage's authoritative choices; do not load its contract.

**Technique guidance:** [stage-6-operations-and-iteration.md](stage-6-operations-and-iteration.md).

### 6.1 Bad-case reflow and iteration loop

Turn permitted feedback and production alerts into reviewed improvement issues. This aspect owns intake, severity triage, root-cause attribution and the evidence chain from issue to validated outcome. Consume telemetry and monitoring from 4.4/6.4, submit reproducible case candidates to 4.1 and route repairs to their component owners; reference the release and design-change processes instead of redefining them.

**Requirements**
- In the review-cadence and ownership decision, record permitted direct-feedback channels and alert/evidence inputs from 6.4, trace/version references, urgent queue and response target, routine review cadence and accountable business/domain and engineering owners.
- In the failure-attribution guide, record the reproducible input, expected outcome, reviewer and affected decision for each proposed regression case; show submission to the 4.1 dataset owner and any design-change request through 6.6 in the iteration-loop figure.
- In the failure-attribution guide, map each observed symptom and trace/outcome evidence to the responsible data, retrieval, prompt/model, routing, tool, state, policy or evaluator component; name the repair owner, supported cause hypothesis, candidate remedy and validation check.
- In the review-cadence and ownership decision, choose severity routing for explicit negative feedback and selected implicit signals; in the failure-attribution guide, record the corroborating task outcome and reviewer disposition before treating repeated attempts, abandonment or escalation as an agent failure.
- Show issue states and owner handoffs in the iteration-loop figure, and include issue, cause, fix, validation, release-manifest and outcome-evidence references in the failure-attribution guide; compare before/after results using the existing 4.2 measures and 6.4 observations.

**Output**
- A Mermaid iteration-loop figure with intake, review, attribution, repair-owner handoff, regression-case submission, validation, release-process reference and monitored outcome, including urgent and routine branches.
- A review-cadence and ownership decision with permitted feedback channels, monitoring inputs, candidate/severity rules, urgent queue and response target, routine cadence and business/domain and engineering owners.
- A failure-attribution guide with issue ID, symptom and corroborating trace/outcome evidence, component/cause, review disposition, repair owner/remedy, reproducibility admission evidence, affected decision, validation check and fix/release/outcome links. Include reproducible candidate input/environment, proposed expected outcome and reviewing owner for submission to the canonical evaluation-case owner.

*Technique reference: `references/stage-6-operations-and-iteration.md` (bad-case loop).*

### 6.2 Skill and prompt maintenance

Maintain prompt behavior and skill activation/execution using the approved templates, metadata and evaluation definitions. This aspect owns component review triggers, dependency diagnostics and regression coverage for each affected surface. Reference the cases, metrics and graders in Stage 4, monitoring in 6.4 and manifest/release processes in 6.6/5.6. Own Skill content and name/description activation-metadata changes; hand approved versions to 6.5 for registry publication and discovery checks.

**Requirements**
- In the maintenance success-criteria mapping, select the 4.2 task-outcome, process/safety, output-convention and efficiency measures applicable to each prompt or skill; reference their 4.3 graders and acceptance rules, preserving valid alternative execution paths.
- In the maintenance plan, assign review triggers, owner and evidence checks for selection drift, missing runtime/file dependencies and required-step dependency violations; link the affected 3.1 metadata or 3.3 prompt version and route confirmed failures through 6.1.
- List skill name/description and execution body as separate surfaces in the maintenance plan, with owner and review trigger for each; link their selected measures, regression checks and 6.4 monitoring signals in the maintenance success-criteria mapping.
- In the versioned regression coverage list, select 4.1 case IDs for positive, negative, ambiguous, contextual and reachable failure requests for each skill; record expected activation/outcome references and isolation/coexistence coverage, and submit uncovered cases to the 4.1 owner.
- In the maintenance plan, choose prompt-behavior checks for prompt edits and activation/instruction/isolation/coexistence checks for skill edits; compare affected outcomes with the approved baseline and submit versioned evidence through 4.5/6.6, referencing the 5.6 recovery action.

**Output**
- A prompt/skill maintenance plan with content/activation-metadata surface owner, change/failure review triggers, dependency checks, affected test selection, tested version/evidence and 6.5 publication handoff, shared manifest/release references and recovery-action reference.
- A versioned regression coverage list per skill with canonical 4.1 case ID/version, trigger/body surface, request category, expected activation/outcome reference, isolation/coexistence coverage and gaps submitted to the case owner.
- A maintenance success-criteria mapping with prompt/skill surface, selected 4.2 metric and 4.3 grader, acceptance-rule reference, valid-path allowance and 6.4 monitoring-signal reference.

*Technique reference: `references/stage-6-operations-and-iteration.md` (skill maintenance).*

### 6.3 Memory governance

Operate the memory policy selected in 2.4 using the stores and controls designed in 3.5/2.6/2.9. This aspect owns retention, correction and deletion execution, stored-memory growth review, contamination response and source-to-derived lifecycle evidence. Reference common metric and audit definitions from Stage 4; keep active-context reduction and permitted-content/access decisions with their original owners.

**Requirements**
- For each retained memory class, reference the 2.4 policy and record retention/expiry jobs, correction-request handling, owner and deletion completion checks for raw events and derived records in the memory operations and governance plan.
- In the memory operations and governance plan, choose verification triggers/samples for the 2.6/2.9 write-authority, user-intent, provenance, harmful-content and retrieved-memory-use controls; name evidence, reviewer and the 6.3 contamination-response route when a control fails.
- Schedule the approved 2.4 stored-memory retention, pruning or consolidation methods in the memory operations and governance plan, with growth trigger and owner; record source/derived changes and post-reduction retrieval checks using 4.2 measures in the memory lifecycle audit definition.
- In the memory operations and governance plan, reference the trusted user/agent/tenant enforcement from 2.6 and schedule checks after identity, namespace or permission changes; record the check owner and evidence that unauthorized memory reads/writes remain denied.
- In the memory-contamination response plan, name detection and containment owners, quarantine affected records, trace source-to-derived propagation, correct/delete affected data and verify restoration from history permitted by 2.4; route consequential external effects to the appropriate recovery owner.
- In the memory operations and governance plan, reference the 2.4 keep/exclude and sensitive-data rules; assign candidate-write review samples and checks for secrets, prohibited identifiers, authorized sensitive input and consequential-fact provenance, routing policy changes to the original decision owner.
- In the memory lifecycle audit record definition, extend the 4.4 event schema with source/derived record IDs, lifecycle operation and reason, provenance, completion/retrieval-check evidence and permitted-history reference; cover creation, retrieval, update, deletion and consolidation using the approved log-access and retention policy.

**Output**
- A memory operations and governance plan with approved memory/content/access/trust-policy references, retention/expiry and growth jobs, correction/deletion routes and completion checks, control-verification triggers/samples, owner and user review. Include memory-control verification evidence, risk-selected reviewer/failure route and denied-access evidence bindings.
- A memory-contamination response plan with detection, containment owner, affected-record quarantine, source/derived impact tracing, correction/deletion, policy-permitted recovery history, restoration verification and external-effect recovery handoff.
- A memory lifecycle audit record definition extending the common 4.4 event schema with source/derived record IDs, create/read/update/delete/consolidate operation and reason, provenance, completion/post-reduction evidence and retained-history policy reference.

*Technique reference: `references/stage-6-operations-and-iteration.md` (memory governance).*

### 6.4 Production monitoring and drift detection

Specify continuous production observation using the metric, evaluator and telemetry definitions approved in Stage 4. This aspect owns collection/sampling, ordinary level alerts, drift comparison and operational views. Reference deployed cohorts and spend/capacity rules from Stage 5; route alerts to the incident, maintenance and audit owners instead of restating their response procedures.

**Requirements**
- For multi-step or long-running work, record the 4.2 completion, duration and task-constraint metric IDs, production source/query, segment and collection window in the monitoring plan table; include task outcome and in-flight progress views in the dashboard definition where long-running work exists.
- In the drift-detection plan, choose separate input-mix and behavior/quality comparisons, representative baseline and comparison window; correlate deviations with 6.6 release-manifest versions and name investigation trigger, owner and the 6.1 review route.
- In the monitoring plan table, map token and tool-call measures from 4.2 to task/version usage sources and windows; reference applicable 3.6/5.6 budget controls, choose comparable-baseline anomaly triggers and record alert severity, delivery and response owner.
- For each selected metric, record its 4.2 definition, 4.3 evaluator reference, production observation/sampling method and online-proxy limitation in the monitoring plan table; mark unavailable observations and the evidence needed instead of redefining the measure.
- Select available retry, loop/repeated-state, plan-revision and recovery event series from 4.4 in the monitoring plan table; record collection windows and outcome-linked anomaly routes, and include relevant diagnostic panels and trace/runbook links in the dashboard definition.
- In the monitoring plan table, select the 4.2 cost-per-success measure by workflow/version and record success-outcome linkage, usage/billed sources and reporting-delay treatment from 5.6, aggregation window and anomaly response; include cost per completed task in applicable dashboard views.

**Output**
- A monitoring plan table for ordinary level/constraint alerts with approved metric/evaluator/event reference, task/version segment, source/query, collection/sampling window, proxy limitation, baseline or limit reference, alert trigger/severity/delivery, response owner and response-runbook reference.
- A drift-detection plan with separate input-mix and behavior/quality comparators, representative baselines and comparison windows, release-manifest correlation, investigation trigger, owner and review handoff.
- For long-running workflows, a dashboard definition with task outcomes/duration, in-flight progress, selected failure/recovery series, cost per completed task and trace/response-runbook links.

*Technique reference: `references/stage-6-operations-and-iteration.md` (monitoring and drift).*

### 6.5 Degradation, routing maintenance, and failure handling

Operate dependency incidents and maintain registry/discovery/routing after deployment. Own shared outage activation, probes/restoration, incident staffing, approved capability-version publication and routing/index maintenance. Consume Skill content/activation-metadata changes from 6.2 and tool contracts from 3.1; reference workflow/handoff rules in 2.3/1.3, monitoring in 6.4 and release/restoration in 6.6/5.6.

**Requirements**
- For each reachable dependency, reference its 3.1 timeout/retry/replay/fallback contract in the dependency incident and degradation policy; choose outage activation signals, shared cutoff scope, incident owner, approved substitute/stop route and restoration probe/test.
- In the routing-maintenance plan, name the registry publication owner and synchronization path for approved Skill content/activation-metadata versions from 6.2 and tool-contract versions from 3.1; record separate registry/index/route versions, reference 2.1 discovery, choose 4.1 selection/outcome checks and 6.4 signals, and route content or routing-design changes to their owning aspect.
- In the dependency incident policy and incident error-response table, bind the approved 1.3 handoff context and 2.3 continuation to a staffed recipient/queue, user notice, incident response deadline and unclaimed-handoff action; preserve the authorized context limits.
- In the dependency incident and degradation policy, choose the unavailable-tool health-state owner and scope across concurrent runs, call-suppression rule, probe cadence/expiry and restoration evidence; reference the authorized alternate/replan or stop/handoff route from 2.3/3.1.
- In the dependency incident and degradation policy, bind the 3.1 provider timeout/retry/defer and permitted alternate-route contracts to the deployed client, SDK or gateway owner; record throttling/cutoff activation and tests that alternate/restored routes preserve task quality, state and data constraints.
- In the incident error-response table, reference the reachable 3.1 failure classes and retry/reconciliation rules; map each to incident triage owner, approved recovery/fallback/handoff action and the evidence that confirms task outcome or safe restoration, including denied and ambiguous-effect cases.
- In the routing-maintenance plan, assign deterministic routing/business-rule owners, update review and affected regression checks; link their artifact versions and monitoring signals to the 6.6 manifest and 4.5 verdict, and reference the tested 5.6 restoration action for a confirmed regression.

**Output**
- A dependency incident and degradation policy with approved call/failure/alternative references, deployed control owner, incident activation, shared cutoff/health scope, suppression, probe cadence/expiry, staffed handoff/notice/deadline, unclaimed action and restoration evidence.
- A routing-maintenance plan with registry publication/rule owner, approved 6.2 Skill and 3.1 tool artifact references, version synchronization, separate registry/index/route versions, discovery/rule review path, selected cases/signals, misroute triggers and shared manifest/release/restoration references.
- An incident error-response table with approved failure-class/rule reference, incident trigger and triage owner, recovery/fallback/handoff reference, denied/ambiguous-effect handling and task-outcome/restoration evidence.

*Technique reference: `references/stage-6-operations-and-iteration.md` (degradation and routing).*

### 6.6 Compliance audit and version regression

Operate recurring compliance review and the cross-artifact change record. This aspect owns evidence-review execution, material-change rechecks, renewed approval for changed design decisions and release manifests linking deployed artifacts, evaluation evidence and recovery baselines. Reference obligations in 1.4, audit capture in 4.4, metrics/CI policy in 4.2/4.5 and component maintenance and recovery procedures in their owners.

**Requirements**
- For each applicable obligation, reference its 1.4 control and 4.4 audit schema in the compliance and audit review plan; assign evidence review, tamper-evidence/access/retention-deletion verification, sample or cadence, accountable reviewer and missing-evidence disposition.
- In the regression execution and review decision, assign owners and evidence-review steps for the 4.5 affected-CI/full-suite triggers, including component checks from 6.2/6.5; when a change alters an approved decision, record affected documents and obtain renewed approval before dependent work.
- In the compliance and audit review plan, assign risk-based adversarial rechecks to confirmed obligation/control references and the deployed 5.5 threat-test baseline; in the regression execution decision, record material capability, tool, permission or control-change triggers and route changed applicability to the 1.4 owner.
- In the compliance and audit review plan, select the 4.2 violation/intervention and missed-harm/false-block measures and 6.4 alert routes; choose labeled evidence-review samples, cadence and accountable adjudicator, then record review disposition and escalation under the approved thresholds.
- In the release-manifest scheme, choose the assembly owner and link existing code, model snapshot, prompt/skill, tool/schema, policy/configuration and relevant knowledge/training-data versions to evaluation evidence and deployed traffic cohorts; identify the tested recovery baseline and 5.6 recovery-action reference.

**Output**
- A compliance and audit review plan with confirmed obligation/control and audit/metric references, deployed-test baseline, evidence review/sample/cadence, integrity/access/retention verification, adversarial recheck scope, accountable adjudicator, disposition and escalation.
- A regression execution and review decision instantiating the 4.5 change/risk trigger policy with required-check references, component test selection, execution/review owner, evidence and failed/inconclusive release-action references, plus affected-design-document approval handling.
- A release-manifest scheme with assembly owner, existing artifact IDs/dependencies, manifest-to-evaluation/deployment/traffic-cohort mapping, tested recovery-baseline ID and 5.6 recovery-action reference.

*Technique reference: `references/stage-6-operations-and-iteration.md` (compliance and regression).*

**Deliver and confirm:** Stage 6 Word document with the iteration loop, maintenance plan, memory governance, monitoring, degradation and routing policy, and the compliance and regression practices.


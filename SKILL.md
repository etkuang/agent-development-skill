---
name: agent-development
description: Plan new LLM agent applications or substantial redesigns one approved Word stage at a time. Exclude routine fixes and isolated prompt or configuration edits.
---

# Agent Development

Turn an agent idea into an agreed implementation design through six Word stages. Work on one stage per planning context. Load its requirement contract and the earlier approved project decisions it needs. Keep discussion accessible and make each requirement direct a concrete decision or reviewable output.

## Resolve skill and project paths

Derive the **skill root** from the absolute location of the selected `SKILL.md` supplied by the skill catalog or loading tool; expand any catalog path alias first. It is the directory containing that file, even when the skill is installed outside the project. Resolve literal `references/...` paths from this root and use the resulting absolute paths with file tools. Markdown links remain relative to the file containing the link: a stage contract's `../SKILL.md` returns to the root, and its sibling technique link stays in `references/`.

Resolve `plan/`, project instructions, approved Word inputs and generated deliverables from the active project workspace or the user's selected project planning directory. Keep the project working directory and outputs there. Install or distribute this skill as a folder containing `SKILL.md` and its `references/` resources; copying only the entrypoint omits required contracts. If a required bundled file is unavailable, report its resolved path and keep dependent work pending.

## Select the current stage

Use the stage explicitly requested by the user or the stage whose canonical document is being revised. Otherwise inspect the project filenames and available approval record or stage handoff to identify the earliest unfinished or unapproved stage. For a new project, start with Stage 1. If status is unclear, clarify it before choosing; file existence, discussion agreement and receipt do not prove document approval.

The table is navigation metadata. Read exactly one current-stage contract; future stages' requirement bodies are not part of the current context.

| Stage | Current-stage contract |
| --- | --- |
| Stage 1 — Requirements and architecture | [Stage 1 contract](references/stage-1-contract.md) |
| Stage 2 — Development and model layer | [Stage 2 contract](references/stage-2-contract.md) |
| Stage 3 — Detailed design | [Stage 3 contract](references/stage-3-contract.md) |
| Stage 4 — Evaluation | [Stage 4 contract](references/stage-4-contract.md) |
| Stage 5 — Deployment | [Stage 5 contract](references/stage-5-contract.md) |
| Stage 6 — Operations and iteration | [Stage 6 contract](references/stage-6-contract.md) |

## Read only necessary context

1. Read this shared entrypoint and the selected stage contract. Keep every current-stage requirement available; omit conditional aspects from the document when the approved design does not use them.
2. Inspect technique-reference headings, then read only the paragraphs or procedures needed by the current aspect at its present design depth. A broad section link is not permission to load every subsection or later configuration/calibration detail. Navigate cross-stage technique files with heading-only searches; do not use broad body-keyword searches that load unrelated later instructions. A current aspect may point to a technique file bearing another stage number. Before reading such guidance, identify the current aspect decision it informs; select only the excerpt answering that decision and omit instructions directing another stage's authoritative choices. Do not read a section's first paragraph by default or load its stage contract.
3. When a current decision consumes an earlier result, read the necessary section or decision record from its **approved project Word document**. Use its revision, decision/artifact IDs, owner and approval evidence. Earlier skill contracts are not substitutes for determined project decisions. Do not preload all earlier documents, the full maintenance overview, review reports or certificates.
4. Treat later-owner references as handoff labels. Record the present decision and what the later owner will receive; do not load future contracts to fill their design detail now. Peer decisions within the active stage can be developed together and consumed by reference.

If a required earlier decision is absent, unapproved or inconsistent, keep the dependent current decision pending and clarify or locate its evidence. Independent current-stage clarification may continue. If its design must change, identify the affected decision and prepare a handoff to its owning earlier stage; revise and obtain approval there before dependent work proceeds. Load that earlier contract only when it becomes active in its own stage context. Record affected downstream documents in the handoff; review each in its own stage context and update/reapprove any changed design before its dependents resume. Pending implementation or release checks in an approved design remain owned prerequisites; they do not make that design unapproved or require retrospective execution during planning.

Strict context separation requires a fresh stage session: changing a stage label cannot erase requirements already read in a conversation. At stage completion or an owning-stage revision, provide a concise handoff with approved document/version, approval evidence, necessary input decision IDs and pending prerequisites. Start the next stage with this entrypoint, its one contract and those required approved-document excerpts. Do not read the next contract into the completed stage's context.

## Current-stage workflow

1. **Listen and clarify.** Ask focused questions about missing decisions, using the user's existing information. Clarify priorities when the user cannot answer a technical question.
2. **Research and recommend.** Use relevant mature examples and current documentation. Explain a recommendation, meaningful alternatives and trade-offs; distinguish facts, recommendations and assumptions.
3. **Create or revise the Word document.** Incorporate decisions, reasons, sources and open questions into the current canonical `.docx`. Use the available documents skill to create a real Word file, render it and inspect its layout. Reopen the saved file and verify its filename and Heading 1 sequence after each revision. If generation is blocked, explain the blocker and keep the stage pending.
4. **Obtain document approval.** Deliver that version and request explicit approval; stop until it is approved. Revise the same stage when feedback changes it. Agreement during discussion or acknowledgement of receipt is not approval of the delivered document.

For a new project, create `plan/`, `plan/distilled-experiences.md` and `plan/temp/`; keep temporary planning files in `plan/temp/`. Reuse an existing experiences file instead of duplicating it. Add a lesson only when the user explicitly requests distillation; after a major correction, ask whether to distil the lesson. Keep lessons short and reusable. Read applicable project instructions and `DEVELOPER_README.md` when available.

## Shared document contract

| Stage | Deliverable |
| --- | --- |
| 1 | `01-requirements-and-architecture.docx` |
| 2 | `02-workflow-and-technology-selection.docx` |
| 3 | `03-detailed-agent-design.docx` |
| 4 | `04-evaluation.docx` |
| 5 | `05-deployment.docx` |
| 6 | `06-operations-and-iteration.docx` |

Keep one canonical file per deliverable with exactly this basename. If it is locked, wait for release; do not bypass the lock or create a substitute. Align an existing filename/heading mismatch on revision and request approval of the aligned version.

Number headings hierarchically. Use the active contract's aspect titles, in order, as the exact Heading 1 text after the number prefix. Include each ordinary aspect, explaining inapplicability briefly within it. Omit a **(conditional)** aspect entirely when the approved design does not use it. End with numbered Heading 1 sections **Decisions and unresolved questions** and **References**, specified below. These are the only Heading 1 sections; put project-specific topics and diagrams under the appropriate aspect with lower-level headings, tables or figures. A project title/status/date can precede the first section without Heading 1.

Each decision and artifact has one authoritative owner within the stage; peers consume it by reference. A recurring topic in a later stage states its approved inputs, additional design detail and handoff. Produce the specified outputs rather than copying the instructions. Missing information needs a decision, owner and evidence or check; abstract concepts alone do not satisfy a requirement.

The documents specify executable evaluation, deployment and operations plans with fixture/environment, procedure/runner, expected evidence, owner and execution gate. Attach actual results from an existing implementation or authorized pilot when available; record unperformed checks as pending prerequisites. Document approval approves the design plan. Required calibration, security, capacity and recovery checks must actually pass before the corresponding adoption, production action or traffic exposure.

Changes to earlier approved decisions require revision and renewed approval of their owning documents before dependent work. Superpowers can support discussion and later implementation while preserving these six document gates. After Stage 6 approval, hand off the approved documents and await the user's instruction to implement; do not start coding automatically.

## Required end matter in every document

### Decisions and unresolved questions

Maintain one canonical decision and unresolved-question register for the current stage. Reference technical choices in their owning aspects, record reasons/status/owners and actual document approval evidence, and distinguish design-changing blockers from implementation setup prerequisites. Record material source conflicts with their evidence and authorized ruling or open status. Revise the owning aspect when a decision changes its specification.

**Requirements**
- For each decision, record proposed, open or confirmed status; mark confirmed only with evidence of the user's approval of the delivered document version, leaving assumptions/recommendations unconfirmed until that evidence exists.
- For each open question, record the decision needed, affected aspect/decision ID and whether it blocks current-stage design approval or only implementation setup; resolve design-changing blockers before approval and link setup prerequisites to their owner and verification gate.
- Where sources or reference files materially disagree, record competing claims and source IDs, their effect on the owning decision, recommended resolution, authorized ruling or open status, and the responsible owner's next action.

**Output**
- A canonical decision table with ID, owning-aspect decision reference, reason, proposed/open/confirmed status, owner, approved document revision and approval evidence where confirmed, plus material source-conflict evidence/ruling references.
- An unresolved-question list with ID, question/decision needed, affected aspect/decision, design-approval versus implementation-setup impact, owner, next action and linked verification gate; include unresolved source conflicts.

### References

List identifiable sources supporting the current document's material claims and decisions, with citations near those claims. Record project paths or URLs, relevant headings/pages, product/API version or document revision, and online access dates. Mark whether a claim is sourced fact, recommendation, assumption, or unverified. For technique-backed sections, identify the exact reference file and heading used.

**Requirements**
- Cite a stable source ID near each material supported claim and include that ID, source title/path or URL, and relevant page/heading/section locator in the reference list.
- Label each material claim as sourced fact, recommendation, assumption or unverified, linking factual claims to source IDs and recording missing evidence or verification action where needed; include these classifications/links in the reference record.
- For each substantive document section that uses a technique reference, identify the relevant `references/stage-*.md` file and heading.

**Output**
- A reference list with source ID, supported claim/section locator and classification, title and URL/project path, relevant page/heading/section, product/API version or document revision where applicable, online access date, and missing-evidence/verification action for unverified claims. Identify the exact technique-file path and heading used by each substantive section.


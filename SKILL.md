---
name: agent-development
description: Planning and design guidance for new LLM agent applications and substantial redesigns through six individually approved Word stages, excluding routine fixes and isolated prompt or configuration edits.
---

# Agent Development

This skill guides the planning and design of new LLM agent applications and substantial redesigns through focused technical research and six explicitly approved Word documents, covering requirements and architecture, workflow and model choices, detailed design, evaluation, deployment, and ongoing operations and improvement.

## Resolve skill and project paths

The **skill root** is the folder containing the catalog-selected `SKILL.md`; expand path aliases first. Resolve bundled `references/...` from that root and Markdown links from their containing file. Use absolute paths with file tools. Distribute `SKILL.md` with `references/`; report missing required resources by their resolved paths and keep dependent work pending.

Project plans, experiences, deliverables and temporary files belong in the workspace's `plan/` directory or the user's selected planning directory.

## Planning stages

Use the stage explicitly requested by the user or the stage whose canonical document is being revised. If status is unclear, clarify it before choosing.

| Stage | Reference contract |
| --- | --- |
| 1 — Requirements and architecture | [Stage 1 contract](references/stage-1-contract.md) |
| 2 — Development and model layer | [Stage 2 contract](references/stage-2-contract.md) |
| 3 — Detailed design | [Stage 3 contract](references/stage-3-contract.md) |
| 4 — Evaluation | [Stage 4 contract](references/stage-4-contract.md) |
| 5 — Deployment | [Stage 5 contract](references/stage-5-contract.md) |
| 6 — Operations and iteration | [Stage 6 contract](references/stage-6-contract.md) |

This table is navigation metadata. Read one current-stage contract. Detailed questions, decisions and outputs belong in that contract; future stages' requirement bodies are outside the current planning context.

## Context composition

```text
Necessary context = SKILL.md
                  + current-stage contract
                  - unselected optional aspects
                  + relevant technical-reference excerpts when their stated conditions apply
                  + earlier-stage document excerpts only when needed to consult approved decisions
                  + source-code excerpts only when necessary
```

## Stage workflow

1. **Listen and clarify.** Ask focused questions about missing decisions using the user's existing information. Clarify priorities when the user cannot answer a technical question.
2. **Research and recommend.** Locate `### Technical references` under the current aspect. When an entry's condition applies, read the named technique file and relevant section. Verify changing provider availability, protocol and version-specific details against current official sources even when a bundled reference applies. If no applicable technique file is specified, search the web for the latest suitable solution using official documentation and implementation examples. Propose concrete components, settings or steps at the current stage's level of detail, citing relevant versions and access dates.
3. **Create or revise the Word document.** Incorporate decisions, reasons, sources and open questions into the canonical `.docx`. Apply this file's document style and shared contract. Use the available documents skill to generate a real Word file, render it and inspect its layout. If generation is blocked, explain the blocker and keep the stage pending.
4. **Obtain explicit document approval.** Deliver the saved version and request approval; stop until that version is approved. Revise the same stage when feedback changes its design. Discussion agreement or acknowledgement of receipt does not approve the delivered document.

Document approval approves the design plan. Evaluation, deployment and operations plans must identify their fixture/environment, procedure or runner, expected evidence, owner and execution gate. Attach actual results from an existing implementation or authorized pilot when available; record unperformed checks as pending prerequisites. Required calibration, security, capacity and recovery checks must pass before the corresponding adoption, production action or traffic exposure.

After Stage 6 approval, hand off the approved documents and await the user's instruction to implement.

## Projects, experiences, and skill maintenance

For a new project, create `plan/`, `plan/distilled-experiences.md` and `plan/temp/`, or their equivalents in the selected planning directory. Keep temporary planning files in `plan/temp/`. Reuse an existing experiences file.

Add a lesson only when the user explicitly requests distillation; after a major correction, ask whether to distil the lesson. Keep lessons concise and useful for general agent development rather than specific to one project.

Use applicable recorded lessons when composing the project planning context. Before incorporating an experience into the skill, compare its meaning with the entrypoint and relevant references; add only missing guidance.

Adding an experience to `SKILL.md` requires explicit user approval of its exact wording, placement and word-count effect. During work in an agent-development project, record proposed skill changes in that project's `plan/distilled-experiences.md` and leave installed skill files unchanged.

## Document style

Apply these reusable Word defaults unless the user requests another style. Preserve the active contract's headings, order and decision ownership.

| Element | Default style |
| --- | --- |
| Title | Two-line navy title, 26 pt, with a thin blue rule below it. |
| Headings | Aptos Display in teal; 15 pt for major headings and 11 pt for subordinate headings. |
| Body text | Aptos, 9 pt, with readable paragraph spacing and wrapping. |
| Tables | Blue-banded tables with 7.5–8 pt text, readable cell spacing and wrapping. |
| Bold emphasis | Bold headings and key labels; use selective emphasis for important decisions within paragraphs. |

For Mermaid graphs:

- Use solid arrows (`-->`) for unconditional connections and dashed arrows (`-.->`) for conditional connections. Label conditional arrows with their triggers.
- Arrange the main flow down the center from top to bottom; place branches, retries and error paths to its sides.
- Use rectangles for actions, diamonds for decisions and rounded nodes for start/end points. Keep labels short and concrete.
- Avoid crossing connectors and overlapping labels.

## Shared document contract

| Stage | Canonical Word filename |
| --- | --- |
| 1 | `01-requirements-and-architecture.docx` |
| 2 | `02-workflow-and-technology-selection.docx` |
| 3 | `03-detailed-agent-design.docx` |
| 4 | `04-evaluation.docx` |
| 5 | `05-deployment.docx` |
| 6 | `06-operations-and-iteration.docx` |

Keep one canonical file per deliverable with exactly this basename. If it is locked, wait for release; do not bypass the lock or create a substitute. Align an existing filename or heading mismatch when revising and request approval of the aligned version.

Number headings hierarchically. Use the active contract's aspect titles, in order, as the exact Heading 1 text after the number prefix. Include ordinary aspects, explaining inapplicability briefly within them. Omit aspects marked `(optional)` or `(conditional)` when the approved design does not use them. The aspect headings and mandatory closing sections defined below are the only Heading 1 sections. Put project-specific topics and diagrams under the appropriate aspect with lower-level headings, tables or figures. A project title, status and date can precede the first section without Heading 1.

Write concise complete paragraphs with one main point each. Use compact tables or matrices for comparable records and lists for sequential or parallel items. Keep decision IDs in their owning subheadings, with claim classifications and source citations near the relevant text.

Each decision and artifact has one authoritative owner within the stage; peers consume it by reference. Follow the current-stage contract's output applicability and level of detail, and write project decisions instead of copying instructions. Record unresolved information that affects a needed decision with an owner and evidence or check.

Distinguish sourced facts, explicit user direction, recommendations, assumptions and unverified claims. Compact labels may use `[F]` fact, `[D]` direction, `[R]` recommendation, `[A]` assumption and `[U]` unverified. User direction and delivered-document approval are separate evidence.

Cite a stable source ID near each material supported claim. Record missing evidence or a verification action for unverified claims.

## Required end matter in every document

End every document with numbered Heading 1 sections **Decisions and unresolved questions** and **References**.

- **Decisions and unresolved questions:** Use one register with IDs, owning-aspect links, reasons, status, owners and next actions. Link confirmed decisions to the approved revision and approval evidence; resolve design blockers before approval and retain implementation prerequisites and material source conflicts.
- **References:** List cited source IDs, titles, URLs or exact file paths, relevant pages/headings, applicable product versions or document revisions, and access dates for online sources.


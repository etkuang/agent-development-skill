# Agent Development Skill

A reusable skill for turning an AI agent idea into a clear, reviewable implementation design. It helps an AI assistant clarify user needs, compare design options, document decisions, and guide a project through six planning stages.

The skill is intended for new LLM agent applications and substantial redesigns. Each stage produces a Word document for explicit user approval. The six approved documents form the implementation handoff.

## How I Developed This Skill

I organized 100 Bilibili tutorial videos about agent development and used transcription software to turn their content into Markdown notes. These notes gave me a broad collection of development approaches, techniques, and examples.

I combined what I learned from the tutorials with my own practical experience in agent development to shape the skill's structure. I organized the material into stages, defined the responsibilities of each aspect, and identified the decisions and outputs needed at each stage.

I then asked Codex to research public technical documentation and supporting evidence for every requirement and output. This review aimed to align the guidance with current techniques at the time of review. Sources retain relevant product or version information and access dates so the evidence can be revisited as technology changes.

I also asked Codex to review the practical usefulness and scope clarity of the requirements and outputs. Each requirement should clarify a real user need or a concrete design decision and direct an identifiable output or check. Within a stage, every decision and artifact has one authoritative aspect owner. When a topic appears again in a later stage, its additional design detail and approved inputs must be clear.

These drafting and review steps produced the current skill. The tutorial notes informed its development; the released skill and its technical references are self-contained and use public website sources.

## Review Certificate

The [requirement review certificate](requirement-review-certificate.md) lists the 429 audited requirement and output IDs, the public website resources used in their review, and the batch evidence IDs. It records the review completed from September 29 to October 1, 2026.

## Six Planning Stages

| Stage | Main focus | Word deliverable |
| --- | --- | --- |
| [1. Requirements and architecture](references/stage-1-contract.md) | User needs, scope, success criteria, constraints, and the high-level architecture. | `01-requirements-and-architecture.docx` |
| [2. Development and model layer](references/stage-2-contract.md) | Workflow, models, tools, data, and control mechanisms. | `02-workflow-and-technology-selection.docx` |
| [3. Detailed design](references/stage-3-contract.md) | Concrete prompts, schemas, configurations, interfaces, and execution contracts. | `03-detailed-agent-design.docx` |
| [4. Evaluation](references/stage-4-contract.md) | Cases, metrics, scoring, observations, and evaluation gates. | `04-evaluation.docx` |
| [5. Deployment](references/stage-5-contract.md) | Environments, serving, capacity, release procedures, and recovery. | `05-deployment.docx` |
| [6. Operations and iteration](references/stage-6-contract.md) | Feedback, monitoring, lifecycle responsibilities, and controlled improvement. | `06-operations-and-iteration.docx` |

Earlier stages establish scope and constraints. Later stages refine the design using approved decisions and confirmed information. Conditional aspects apply only when the approved design uses the corresponding capability.

## Using the Skill

1. Make the complete skill folder available to your AI assistant, including [SKILL.md](SKILL.md) and `references/`.
2. Provide a project brief describing the intended users, tasks, desired outcomes, available data or tools, and known constraints. Start with Stage 1 for a new project.
3. Work through the current stage's questions and decisions. Review its Word document and explicitly approve the delivered version before advancing.
4. Start each subsequent stage in a fresh conversation. Provide the approved document versions and only the earlier decision excerpts needed for that stage.
5. After Stage 6 approval, use the six approved documents as the design handoff and give a separate instruction to begin implementation.

For example:

> Use the agent-development skill to plan an internal policy assistant. Start with Stage 1, clarify the missing requirements, and prepare the requirements and architecture document for my review.

`SKILL.md` contains the shared workflow and routes to six separate stage contracts. The assistant loads only the current stage's requirements, relevant technical guidance, and necessary approved project inputs. Keeping all references on disk does not require loading them all into the conversation.

Bundled reference paths resolve from the directory containing the loaded `SKILL.md`, even when the skill is installed outside the project. Project planning documents and generated outputs belong in the project or its selected planning directory.

## Self-Evolution During Use

For a new project, the skill creates `plan/distilled-experiences.md` in the project workspace. When the user explicitly requests distillation, the assistant records a short, reusable lesson from the work. After a major correction, it asks whether that lesson should be distilled. This turns practical experience into a record that the developer can review.

A developer can use those lessons to revise their copy of `SKILL.md` and the relevant `references/` while using the skill. For example, a lesson may reveal a question that needs clarification, a missing output field, an unclear aspect boundary, or technical guidance that needs updating. The revised skill can guide later stage sessions. Approved project documents still need their own review and approval when a design decision changes.

I will continue improving the skill through this process as I use it and revisit its supporting evidence when techniques change.

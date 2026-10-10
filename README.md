# Agent Development Skill

A reusable skill for turning an AI agent idea into a clear, reviewable implementation design. It helps an AI assistant clarify user needs, compare design options, document decisions, and guide a project through six planning stages.

The skill is intended for new LLM agent applications and substantial redesigns. Each stage produces a Word document for explicit user approval. The six approved documents form the implementation handoff.

## What's New in v2.0.0

Compared with the [legacy edition](https://github.com/etkuang/agent-development-skill), this version makes the guidance easier to select and the planning documents easier to apply:

- **Focused technical guidance:** Six broad technical reference files have been replaced by 106 technique guides. Each aspect states when to consult a guide, so the assistant can load the material needed for the current decision.
- **Restructured stage contracts:** Each aspect separates clarification questions, document outputs, scope exclusions, prerequisites, and conditional technical references. Aspects follow their dependencies, with each decision and artifact assigned to one authoritative owner.
- **Deliverables scaled to the project:** Output lists are candidate content that can be simplified according to the project's size, complexity, and actual decisions, while preserving the required document structure and approval gates.
- **Expanded technical coverage:** New focused guides address [remote-agent integration](references/technological%20documentations/remote-agent-integration-selection.md), [repeated-trial success measurement](references/technological%20documentations/repeated-trial-success-measurement.md), and [provider lifecycle and availability checks](references/technological%20documentations/provider-lifecycle-availability-check.md). Existing guidance has also been reviewed against public technical sources.

When continuing a project planned with the legacy edition, align its document headings, aspect IDs, and reference paths with the current stage contracts. Review and explicitly approve each revised document before relying on it in later stages.

## How I Developed This Skill

I collected agent development tutorials from across the internet and organized them into Markdown notes. With Codex, I designed six planning stages, defined each aspect's scope, decisions, outputs, and prerequisites, and connected them to technical guidance.

I asked Codex to research official documentation and primary sources, develop focused technique guides, and record product versions and access dates. I also defined context selection, the clarification and approval workflow, and shared Word document standards. Each stage produces a Word document for explicit approval before the next stage begins.

Feedback, structural and reference checks, and planning walkthroughs helped reveal gaps, clarify ownership, and scale outputs to project needs. The resulting skill contains six stage contracts and 106 technique guides, linked to public sources through the review certificate. The released skill is self-contained; tutorial notes and development records remain private.

## Review Certificate

The [requirement review certificate](requirement-review-certificate.md) maps all 106 technique documents to the public website resources supporting them. The latest technical review was completed on October 10, 2026. Each guide records relevant product or version information and source access dates.

## Six Planning Stages

| Stage | Main focus | Word deliverable |
| --- | --- | --- |
| [1. Requirements and architecture](references/stage-1-contract.md) | User needs, scope, success criteria, constraints, and the high-level architecture. | `01-requirements-and-architecture.docx` |
| [2. Development and model layer](references/stage-2-contract.md) | Context, memory, evidence, security, integrations, models, and workflow design. | `02-workflow-and-technology-selection.docx` |
| [3. Detailed design](references/stage-3-contract.md) | Concrete schemas, call contracts, prompts, settings, resource lifecycles, and implementation checks. | `03-detailed-agent-design.docx` |
| [4. Evaluation](references/stage-4-contract.md) | Metrics, cases, graders, tracing, evaluation runs, and CI gates. | `04-evaluation.docx` |
| [5. Deployment](references/stage-5-contract.md) | Serving, persistence, scaling, release checks, recovery, cost governance, and rollout. | `05-deployment.docx` |
| [6. Operations and iteration](references/stage-6-contract.md) | Change governance, monitoring, incident recovery, feedback, and controlled maintenance. | `06-operations-and-iteration.docx` |

Earlier stages establish scope and constraints; later stages refine approved decisions. Keep ordinary aspect headings and briefly explain any inapplicability. Include optional aspects only when the approved design uses the corresponding capability, and end every document with **Decisions and unresolved questions** and **References**.

## Using the Skill

1. Provide the complete skill folder: [SKILL.md](SKILL.md) and `references/`.
2. Describe users, tasks, outcomes, data, tools, and constraints. Begin with Stage 1.
3. Review and explicitly approve each delivered Word document before advancing.
4. Use a fresh conversation for each subsequent stage, identifying approved versions, approval evidence, and necessary earlier decisions.
5. After Stage 6 approval, separately instruct implementation using the six approved documents.

> Use agent-development to plan a policy assistant; start at Stage 1.

The assistant loads shared instructions, applicable current-stage aspects, and necessary technique, approved-document, and code excerpts. It verifies changing details against official sources and researches the web when no guide applies.

Reference paths resolve from the skill folder; project outputs belong in the selected planning directory. Document approval covers the design. Required calibration, security, capacity, and recovery checks must pass before their corresponding adoption, production action, or traffic exposure.

## Project Experience and Skill Maintenance

Each project uses one experiences file, normally `plan/distilled-experiences.md` or its equivalent in the selected planning directory. Record concise, reusable lessons only on explicit request; after a major correction, the assistant asks whether to record one. Relevant lessons inform later planning.

Record proposed skill changes in that file. Compare them with `SKILL.md` and `references/` for missing guidance. Adding a lesson to `SKILL.md` requires explicit user approval of its exact wording, placement, and word-count effect; implement approved changes in a separate maintenance task. Changes to approved project designs require revised documents and renewed approval.

I will refine the skill through use and revisit sources as techniques change.

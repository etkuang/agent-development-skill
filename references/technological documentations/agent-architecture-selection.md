# Agent architecture selection

## Selection method

1. Test whether a direct model call or deterministic code can satisfy the scoped task.
2. Locate decisions whose next action is uncertain: model-directed control is justified only where that uncertainty requires it.
3. Compare viable single-agent, planning, routing or multi-agent patterns against the task's coordination, state, approval and recovery needs.
4. Choose the simplest sufficient combination on representative tasks, accounting for operating burden and rejected simpler alternatives.

## Supporting guidance and sources

Compare direct calls and deterministic code with single-agent, ReAct, Plan-and-Execute, router and Skill, multi-agent, blackboard and graph or workflow candidates. These are composable options. Use predictable steps, uncertain next actions, separable task classes and independent subtasks to distinguish needs; graphs can contain cycles. [Anthropic building effective agents](https://www.anthropic.com/engineering/building-effective-agents) (2024-12-19), accessed 2026-10-10.

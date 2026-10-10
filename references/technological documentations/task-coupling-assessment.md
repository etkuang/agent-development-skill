# Task-coupling assessment

## Selection method

1. Identify ordering dependencies and shared resources for the tasks considered for parallel execution.
2. Check read/write effects and whether workers can maintain independent state.
3. Choose ordering or coordination for conflicting work, and name the result integrator for parallel work; preserve useful partial results according to the outcome policy.

## Supporting guidance and sources

Use dependencies and shared writable effects to assess coupling. Parallel work needs independent state and an accountable integrator; dependent or conflicting work needs ordering or coordination. Added routing and agents must justify their coordination burden on representative tasks. [AWS efficient workflow orchestration](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf05-bp01.html) (Agentic AI Lens current) and [Anthropic orchestrator-workers](https://www.anthropic.com/engineering/building-effective-agents) (2024-12-19), accessed 2026-10-10.

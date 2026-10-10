# Requirement-to-indicator translation

## Selection method

1. Identify the current task outcome and the business improvement sought.
2. Choose an observable indicator that measures that improvement, then establish its baseline or a collection action.
3. Check whether the proposed technique changes the indicator enough to justify its complexity; keep service cost and response-time targets distinct.

## Supporting guidance and sources

Use discovery to test assumptions that could change the decision to proceed, using observed workflow outcomes and baseline evidence. [AWS organizational-workflow guidance](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentsus03-bp02.html) (current), [AWS agent performance criteria](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf01-bp01.html) (current), and [UK Government Service Manual discovery guide](https://www.gov.uk/service-manual/agile-delivery/how-the-discovery-phase-works) (updated 2021-06-21), accessed 2026-10-10.

Match the business indicator to the desired improvement. Interaction patterns inform the latency decision; a universal P99 target is unnecessary. [AWS agent performance criteria](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/agentperf01-bp01.html) (current), accessed 2026-10-10.

Consider reasoning, memory, tools, recovery and coordination only after identifying the business need or material assumption they address. [Anthropic building effective agents](https://www.anthropic.com/engineering/building-effective-agents) (2024-12-19), [AWS Agentic AI Lens design principles](https://docs.aws.amazon.com/wellarchitected/latest/agentic-ai-lens/design-principles.html) (current), and [Azure architecture decision records](https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record) (updated 2026-04-13), accessed 2026-10-10.

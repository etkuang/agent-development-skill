# Agent framework selection

## Selection method

1. Derive the necessary orchestration, integration, state, approval and recovery capabilities from the selected architecture.
2. Compare viable frameworks and direct SDK/workflow code using their current official documentation and the specific release or deployment mode under consideration.
3. Verify persistence and pause/resume against the actual state backend and recovery lifetime rather than the framework label.
4. Choose the lowest-burden option meeting the required capabilities; leave exact storage configuration and executable settings to later design.

## Supporting guidance and sources

Compare LangGraph, CrewAI, Microsoft Agent Framework, PydanticAI and direct SDK or workflow code against task needs and current documentation; ecosystem labels and historical rankings are insufficient selection evidence. [Anthropic building effective agents](https://www.anthropic.com/engineering/building-effective-agents) (2024-12-19), accessed 2026-10-10.

LangGraph separates thread-state checkpointers from stores for cross-thread application data. Embedded graphs configure these capabilities; Agent Server manages persistence infrastructure. In-memory checkpoints do not survive process restarts, and interrupt workflows require a checkpointer. [LangGraph persistence](https://docs.langchain.com/oss/python/langgraph/persistence) and [interrupts](https://docs.langchain.com/oss/python/langgraph/interrupts) (LangGraph Python OSS, rolling documentation; accessed 2026-10-10). These examples inform capability comparison rather than prescribing a backend.

Consult the selected runtime's actual checkpoint documentation, including [Microsoft Agent Framework checkpoints](https://learn.microsoft.com/en-us/agent-framework/workflows/checkpoints) when relevant (Microsoft Agent Framework, rolling documentation; source access recorded 2026-10-10). A LangChain-ephemeral/LangGraph-persistent dichotomy is not a product-wide selection rule. Current [LangChain agents](https://docs.langchain.com/oss/python/langchain/agents) are built on LangGraph and can use a checkpointer (LangChain Python OSS, rolling documentation; accessed 2026-10-10).

Use current [CrewAI Flows](https://docs.crewai.com/en/concepts/flows) and [Pydantic AI documentation](https://pydantic.dev/docs/ai/overview/) for state, orchestration, validated outputs and dependency support when comparing those candidates. CrewAI documentation resolved to v1.15.27 during this review; pin the chosen installed release. Pydantic AI uses rolling documentation; verify the chosen release (accessed 2026-10-10).

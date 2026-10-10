# Memory contamination recovery

Use this reference when retained records may be poisoned, stale or harmful.

## Decision method

Use risk-selected checks for approved write authority, intent, provenance, secrets exclusion and authorized sensitive facts; correlate retrieved use with the affected source.

Assign detection/containment ownership, quarantine affected records, trace derived propagation and correct/delete both source and derived content.

Restore only from policy-permitted history and verify retrieval and denied-access outcomes. External actions still need their own reconciliation owner; active-context compaction is a different lifecycle.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Microsoft memory safety](https://learn.microsoft.com/en-us/security/zero-trust/sfi/manage-agentic-memory-safety) — Microsoft agentic memory safety guidance, updated 2026-06-03; accessed 2026-10-10.
- [AgentCore strategies](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/built-in-strategies.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.


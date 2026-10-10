# Memory retention and deletion

Use this reference when selected retained memory needs ongoing lifecycle execution.

## Decision method

Schedule approved expiry, correction, deletion and growth/consolidation operations with owners and completion checks.

Trace raw/source records to derived records and verify both lifecycles. In AgentCore, deleting an event does not delete structured long-term memory derived from it.

For AgentCore, `eventExpiryDuration` is bound when each event is written. A policy change applies to later events; existing event deadlines cannot be extended and expired events are unrecoverable. Plan an authorized source-preservation or migration action before expiry when the approved retention policy requires it.

Recheck trusted namespace/user/tenant access after permission changes and retrieval behavior after pruning. Keep source/index lifecycle and checkpoint retention with their separate owners.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [AgentCore retention](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/memory-create-a-memory-store.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.
- [event deletion](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/short-term-delete-event.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.
- [namespace IAM controls](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/memory-organization.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.
- [AgentCore strategies](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/built-in-strategies.html) — Amazon Bedrock AgentCore documentation; accessed 2026-10-10.


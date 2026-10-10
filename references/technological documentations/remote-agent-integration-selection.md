# Remote agent integration selection

Use this reference when an approved task needs delegation to an agent operated across a system or organizational boundary.

## Decision method

Compare an ordinary service/tool call with a delegated goal. Select agent interoperability, such as A2A, only when the remote participant must manage its own task and return messages, progress or artifacts. Several agents inside one runtime do not by themselves require a network protocol.

Record the selected protocol revision, SDK and transport binding; advertised endpoint, skills, input/output modes, authentication and supported interaction capabilities. An Agent Card describes a candidate; it does not grant authority or prove that the endpoint is trusted. Reuse the approved identity, data-transfer and threat policies when accepting it.

Check whether a request returns a completed message or a tracked task. Distinguish task identity from conversation context, returned artifacts from status messages, and waiting for input/authorization from terminal outcomes. Select supported polling, streaming or push updates, and verify cancellation and reconnection semantics before promising them.

Hand the selected capability guarantees to the workflow owner for delegation, deadlines, acceptance and joins; Stage 3 binds the exact calls, state fields and credential flow. Test compatibility on a representative delegated task before adoption. MCP tool access and A2A agent collaboration can coexist; neither substitutes for the other's task contract.

## Supporting guidance and sources

Pin the deployed revision rather than copying examples from another protocol generation. The reviewed specification describes protocol generation 1.0. Its negotiated wire version uses major/minor numbers rather than a specification patch number; confirm the released specification and SDK compatibility with the selected implementation.

- [A2A specification](https://a2a-protocol.org/latest/specification/) — A2A specification, reviewed protocol generation 1.0, rolling URL; accessed 2026-10-10.
- [A2A core concepts](https://a2a-protocol.org/latest/topics/key-concepts/) — A2A current concepts documentation; accessed 2026-10-10.
- [A2A task lifecycle](https://a2a-protocol.org/latest/topics/life-of-a-task/) — A2A current task-lifecycle documentation; accessed 2026-10-10.

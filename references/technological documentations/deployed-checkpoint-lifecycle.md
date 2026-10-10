# Deployed checkpoint lifecycle

Use this reference when approved work needs durable pause, checkpoint or restart.

## Decision method

Choose a backend for actual topology, writer concurrency, consistency, recovery point, retention and operating burden. A backend name alone does not prove durability; Redis RDB/AOF choices have different loss/latency behavior.

Map the approved payload to actual writing/interrupt boundaries and sensitive-data policy. Check retention/platform limits against the authorized approval window and define expiry/deletion and expired-run outcome.

Test interruption, preserved/pending work and restart at selected boundaries with fixture, expected result, owner and pre-exposure gate. A managed platform's checkpoint contract can avoid a second store; planned recovery is not passing evidence.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Agents SDK approval/resume](https://openai.github.io/openai-agents-python/human_in_the_loop/) — OpenAI Agents SDK for Python; pin the installed release; accessed 2026-10-10.
- [checkpointers](https://docs.langchain.com/oss/python/langgraph/checkpointers) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.
- [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) — Redis current documentation; verify the selected deployment version; accessed 2026-10-10.
- [interrupts](https://docs.langchain.com/oss/python/langgraph/interrupts) — LangGraph OSS Python documentation; pin the installed release; accessed 2026-10-10.


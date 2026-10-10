# Safe retry and write reconciliation

Use this reference when integration failures may be retried or can leave uncertain external effects.

## Decision method

Classify actual argument, authorization, transient and unknown-effect failures. Correct invalid arguments, recover authority or stop, and replay safe transient requests within total deadline/attempt limits.

Count SDK retries as well as application attempts; use supported Retry-After or bounded backoff. A fallback must have the required capability and equivalent authority.

For writes, verify provider operation keys, preconditions, transaction or outcome-query guarantees. Reconcile an unknown timeout result before replay unless that guarantee makes repetition safe; specify key lifetime and durable outcome identity.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Stripe idempotency](https://docs.stripe.com/api/idempotent_requests) — Stripe API idempotency documentation; pin the API version; accessed 2026-10-10.
- [OpenAI rate limits](https://developers.openai.com/api/docs/guides/rate-limits) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Anthropic tool-call errors](https://platform.claude.com/docs/en/agents-and-tools/tool-use/handle-tool-calls) — Claude API documentation; accessed 2026-10-10.
- [Google Cloud Storage retry strategy](https://docs.cloud.google.com/storage/docs/retry-strategy) — Google Cloud Storage documentation; accessed 2026-10-10.


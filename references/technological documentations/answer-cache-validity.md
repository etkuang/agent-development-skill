# Answer cache validity

Use this reference when an economically selected answer cache is configured.

## Decision method

Define key or validity scope for authorized audience and source/index versions; choose expiry and explicit write invalidation under the freshness requirement.

Design refresh and invalidation order for concurrent source changes. A version stamp alone does not prevent a stale read if the race still serves old content.

Test the actual read/update/delete boundaries, including cross-audience reuse. Keep answer cache, workflow state and checkpoint backend ownership distinct.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Redis cache-aside](https://redis.io/docs/latest/develop/use-cases/cache-aside/) — Redis current documentation; verify the selected deployment version; accessed 2026-10-10.
- [Redis caching race conditions](https://redis.io/docs/latest/develop/reference/client-side-caching/) — Redis current documentation; verify the selected deployment version; accessed 2026-10-10.
- [Redis semantic cache](https://redis.io/docs/latest/develop/use-cases/semantic-cache/) — Redis current documentation; verify the selected deployment version; accessed 2026-10-10.


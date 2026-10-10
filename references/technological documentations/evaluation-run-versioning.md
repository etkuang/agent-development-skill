# Evaluation run versioning

Use this reference when comparing model or application behavior across runs.

## Decision method

Pin datasets/splits/labels, fixtures/environment, model snapshot/settings, prompt/tool/schema and grader/rubric with each result. Seeds help only where the selected system supports meaningful control.

Apply affected checks after changes and the declared full suite before release. Review changed labels/rubrics and use a pinned comparable set or explicit authorized rebaseline.

Report comparability status alongside scores; changing examples is not evidence of an improved candidate. Existing local calibration can feed the formal protocol without becoming an independent run policy.

When a runner uses a managed evaluation service, check [provider lifecycle and availability](provider-lifecycle-availability-check.md) before adoption. Retained evaluation-method documentation does not establish that the hosted endpoint remains supported.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [Anthropic agent evaluation](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — Anthropic engineering article, 2026-01-09; accessed 2026-10-10.
- [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — OpenAI API v1 documentation; accessed 2026-10-10.
- [LangSmith dataset management](https://docs.langchain.com/langsmith/manage-datasets-programmatically) — LangSmith dataset management documentation; pin the installed SDK release; accessed 2026-10-10.


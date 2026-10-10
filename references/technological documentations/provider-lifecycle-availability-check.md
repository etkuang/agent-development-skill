# Provider lifecycle and availability check

Use this reference when a proposed model, endpoint or managed feature must remain available through the project's intended operating period.

## Decision method

Confirm access for the actual organization, account, region, model and deployment mode. Read current lifecycle notices as well as feature documentation: an accessible methodological guide is not evidence that its hosted product remains available.

Record the selected dependency, eligibility evidence, retirement or restriction dates affecting the project, supported alternative and migration owner. Compare migration candidates with the same task-quality, authority, data and operating constraints. Later release and operations owners schedule the change and require comparable verification before exposure.

The following OpenAI notices were checked on 2026-10-10; recheck them before committing a project to those services:

- Self-serve fine-tuning eligibility changed on 2026-05-07 for organizations without previous training, and on 2026-07-02 based on fine-tuned inference in the preceding 60 days. New jobs for remaining eligible customers end on 2027-01-06; inference follows the base model's retirement.
- OpenAI Evals becomes read-only on 2026-10-31 and its dashboard/API, including associated graders, is scheduled to close on 2026-11-30.
- Managed reusable prompt objects and Agent Builder are scheduled to close on 2026-11-30. Application-owned templates and evaluation methods remain separate choices.

These are provider-specific eligibility and lifecycle facts, not a rejection of tuning, evaluation or reusable prompts as techniques.

## Supporting guidance and sources

- [OpenAI lifecycle notices](https://developers.openai.com/api/docs/deprecations) — OpenAI API lifecycle documentation, notices checked 2026-10-10; accessed 2026-10-10.
- [Production dependency practices](https://developers.openai.com/api/docs/guides/production-best-practices) — OpenAI API production documentation; accessed 2026-10-10.

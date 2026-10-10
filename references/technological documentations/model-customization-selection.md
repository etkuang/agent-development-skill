# Model customization selection

Use this reference when a measured residual model gap remains after feasible untuned approaches.

## Decision method

Establish the strongest feasible prompting, structured-output, tool and retrieval baseline. Verify current provider/model/account availability before proposing training.

For managed training, check the selected provider's current eligibility and retirement notices using [provider lifecycle and availability](provider-lifecycle-availability-check.md). Method documentation alone does not establish that a new organization can create training jobs.

Compare supported full or parameter-efficient tuning, managed supervised/preference/reward methods, distillation, quantization or context adaptations against the actual gap and compute/memory/quality/cost need. Demonstrations, preference pairs or valid reward evidence constrain method eligibility.

Choose exposed-control fix/search/omit strategy and compare target gains with retained capabilities on common held-out tasks. Select replay or other mitigation only with a task need; no fixed ratio, learning-rate recipe or forgetting percentage is universal.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [OpenAI model optimization](https://developers.openai.com/api/docs/guides/model-optimization) — OpenAI API v1 documentation; accessed 2026-10-10.
- [deprecations](https://developers.openai.com/api/docs/deprecations) — OpenAI API v1 documentation; accessed 2026-10-10.
- [Bedrock customization](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html) — Amazon Bedrock documentation; verify the selected service/model; accessed 2026-10-10.
- [hyperparameters](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models-hp.html) — Amazon Bedrock documentation; verify the selected service/model; accessed 2026-10-10.
- [PEFT methods](https://huggingface.co/docs/peft/en/methods/overview) — Hugging Face PEFT documentation; pin the selected release; accessed 2026-10-10.
- [TRL PEFT](https://huggingface.co/docs/trl/peft_integration) — Hugging Face TRL documentation; pin the selected release; accessed 2026-10-10.
- [memory guidance](https://huggingface.co/docs/trl/reducing_memory_usage) — Hugging Face TRL documentation; pin the selected release; accessed 2026-10-10.
- [TensorRT-LLM quantisation](https://nvidia.github.io/TensorRT-LLM/latest/features/quantization.html) — TensorRT-LLM latest documentation; verify hardware and runtime version; accessed 2026-10-10.
- [retained-capability study](https://arxiv.org/abs/2306.10181) — Primary research paper, arXiv:2306.10181; accessed 2026-10-10.


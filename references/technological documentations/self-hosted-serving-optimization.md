# Self-hosted serving optimization

Use this reference when an owned inference runtime needs workload-specific tuning.

## Decision method

Verify hardware/runtime/model compatibility before comparing batching, parallelism, speculative decoding, prefix reuse, KV management, precision or offload candidates.

Pin exact supported settings and compare quality, accepted throughput, tail latency, memory and cost against baseline. Prefix reuse saves repeated prefill rather than decoding; speculative gains depend on the workload.

For vLLM, distinguish scheduler sequence/token limits from API admission/backlog controls and distinguish weight offload from KV offload. Do not reuse old defaults without selected-version evidence. Lossy artifacts must pass the inherited task-quality gate.

## Supporting guidance and sources

Apply provider and runtime details only to the selected model, endpoint, deployment mode and version. Access dates below identify the retained source checks; confirm changing API details during project research.

- [TensorRT-LLM quantisation](https://nvidia.github.io/TensorRT-LLM/latest/features/quantization.html) — TensorRT-LLM latest documentation; verify hardware and runtime version; accessed 2026-10-10.
- [vLLM engine arguments](https://docs.vllm.ai/en/latest/configuration/engine_args/) — vLLM latest documentation; verify the selected runtime version; accessed 2026-10-10.
- [vLLM speculative decoding](https://docs.vllm.ai/en/latest/features/speculative_decoding/) — vLLM latest documentation; verify the selected runtime version; accessed 2026-10-10.
- [automatic prefix caching](https://docs.vllm.ai/en/latest/features/automatic_prefix_caching/) — vLLM latest documentation; verify the selected runtime version; accessed 2026-10-10.
- [vLLM quantization and hardware support](https://docs.vllm.ai/en/stable/features/quantization/index.html) — vLLM stable documentation; verify the selected runtime version; accessed 2026-10-10.


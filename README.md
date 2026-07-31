# Yin Li

**LLM systems engineer building reproducible evaluation, post-training, retrieval, traceable agent infrastructure, and upstream AI tooling fixes.**

[Portfolio](https://kevin-li-2025.github.io/) | [Selected repositories](https://github.com/Kevin-Li-2025?tab=repositories)

I work on the engineering layer around model behavior: data pipelines, benchmark harnesses, retrieval diagnostics, verifier-guided inference, trace capture, security/correctness bug reports, and regression tests that make LLM systems measurable instead of anecdotal.

## Upstream Open Source

- [Inspect AI PR #4371](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4371): merged sandbox JSON-RPC transport fix that safely chunks oversized tool-response frames, preserves host-configured output limits, and isolates continuation storage per UID.
- [Triton PR #10411](https://github.com/triton-lang/triton/pull/10411): merged runtime cache-group integrity fix that treats incomplete cache groups as misses.
- [Triton PR #10413](https://github.com/triton-lang/triton/pull/10413): merged benchmarking reliability fix for single pruned autotune configs.
- [Ray PR #64184](https://github.com/ray-project/ray/pull/64184): merged autoscaler metrics reporter fix for deleted node types.
- [PyTorch TorchTitan PR #3456](https://github.com/pytorch/torchtitan/pull/3456): merged LoRA freezing fix for non-linear modules.
- [Apache DataFusion PR #23066](https://github.com/apache/datafusion/pull/23066): merged execution/physical-plan feature adding configurable spill merge fan-in.
- [Apache DataFusion PR #23226](https://github.com/apache/datafusion/pull/23226): merged partition-path correctness fix preserving conservative prefix pruning for encoded and unencoded values.
- [Apache DataFusion PR #23043](https://github.com/apache/datafusion/pull/23043): merged `any_value` SQL aggregate, with order-insensitive semantics and coverage for grouped, null-only, empty-input, and return-type cases.
- [Apache TVM PR #19818](https://github.com/apache/tvm/pull/19818): merged ONNX frontend correctness fix preserving BatchNormalization inference mode.
- [ONNX Runtime PR #29140](https://github.com/microsoft/onnxruntime/pull/29140): merged CUDA/FMHA kernel initialization fix for large-head variants.
- [FlashAttention PR #2671](https://github.com/Dao-AILab/flash-attention/pull/2671): merged FA4 CuTe frontend fix for SM120/SM121 compile-time argument handling.
- [CARLA PR #9791](https://github.com/carla-simulator/carla/pull/9791): merged LiDAR smoke-helper signature fix into the official `ue5-dev` branch.
- [scikit-learn PR #34380](https://github.com/scikit-learn/scikit-learn/pull/34380): merged Array API/DLPack interop correctness fix avoiding a `torch.from_dlpack` crash for NumPy arrays with negative strides.
- [xgrammar PR #667](https://github.com/mlc-ai/xgrammar/pull/667): merged structured-generation parser fix for negative-zero float ranges.
- [Gradio issue #13556](https://github.com/gradio-app/gradio/issues/13556): reported a `/component_server` multipart upload-limit bypass where `max_file_size` enforcement was skipped; confirmed by maintainers and fixed upstream in [PR #13580](https://github.com/gradio-app/gradio/pull/13580).
- [PyTorch issue #187284](https://github.com/pytorch/pytorch/issues/187284): independently reproduced and diagnosed a high-priority `torch.compile` forward-mode AD silent-correctness failure, and proposed a dual-input guard; upstream subsequently fixed the issue with a Dynamo eager-fallback in [PR #189644](https://github.com/pytorch/pytorch/pull/189644).
- [PyTorch issue #188023](https://github.com/pytorch/pytorch/issues/188023): reported a negative-stride DLPack crash in `torch.from_dlpack`, triaged as a crash/error-checking/numpy/dlpack bug with a follow-up fix PR opened.

## Operating Thesis

- Treat every model claim as an artifact-backed systems claim: data version, command, hardware, metric, and failure boundary.
- Build evaluation loops that survive refactors: golden sets, deterministic runners, CI checks, and report provenance.
- Keep agent behavior inspectable: tool calls, retrieved sources, validators, retries, and escalation paths should be first-class data.
- Optimize for reproducible learning velocity: small models, single-GPU runs, tight ablations, and clear error analysis before scale.

## System Map

| Surface | What I build | Representative repos |
| --- | --- | --- |
| Post-training and verifier-guided inference | SFT/DPO-style pipelines, executable checks, reward-labeled traces, benchmark exports | [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge), [l20-edu-135m-pretrain](https://github.com/Kevin-Li-2025/l20-edu-135m-pretrain) |
| Retrieval and ranking evaluation | Query planning, citation checks, recall/MRR regression tests, reranker snapshots | [signal-rag](https://github.com/Kevin-Li-2025/signal-rag), [arabic-retrieval-lab](https://github.com/Kevin-Li-2025/arabic-retrieval-lab), [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota), [coreb-retrieval-sota](https://github.com/Kevin-Li-2025/coreb-retrieval-sota) |
| Structured generation benchmarks | NL2SQL, ordering reliability, emotion classification, cost and robustness reporting | [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark), [goemotions-roberta-large-focal](https://github.com/Kevin-Li-2025/goemotions-roberta-large-focal), [order-delta-bench](https://github.com/Kevin-Li-2025/order-delta-bench) |
| Agent trace infrastructure | Scientific workflows, semantic judges, deterministic validators, trace review | [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl), [CodeGraph](https://github.com/Kevin-Li-2025/CodeGraph) |
| Efficient model systems | Quantization experiments, serving benchmarks, GPU instrumentation, compiler/runtime fixes, and AI tooling bug reports | [scikit-learn PR #34380](https://github.com/scikit-learn/scikit-learn/pull/34380), [Triton PR #10411](https://github.com/triton-lang/triton/pull/10411), [Triton PR #10413](https://github.com/triton-lang/triton/pull/10413), [Ray PR #64184](https://github.com/ray-project/ray/pull/64184), [TorchTitan PR #3456](https://github.com/pytorch/torchtitan/pull/3456), [DataFusion PR #23066](https://github.com/apache/datafusion/pull/23066), [DataFusion PR #23226](https://github.com/apache/datafusion/pull/23226), [DataFusion PR #23043](https://github.com/apache/datafusion/pull/23043), [FlashAttention PR #2671](https://github.com/Dao-AILab/flash-attention/pull/2671), [ONNX Runtime PR #29140](https://github.com/microsoft/onnxruntime/pull/29140), [TVM PR #19818](https://github.com/apache/tvm/pull/19818), [xgrammar PR #667](https://github.com/mlc-ai/xgrammar/pull/667), [Gradio issue #13556](https://github.com/gradio-app/gradio/issues/13556), [PyTorch issue #188023](https://github.com/pytorch/pytorch/issues/188023), [Single-GPU Inference Lab](https://github.com/Kevin-Li-2025/single-gpu-inference-lab), [llm-quant-bench](https://github.com/Kevin-Li-2025/llm-quant-bench), [l20-edu-135m-pretrain](https://github.com/Kevin-Li-2025/l20-edu-135m-pretrain) |

## Selected Systems

| Project | Signal | Evidence surface |
| --- | --- | --- |
| [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge) | Single-L20 post-training and verifier-guided inference for executable code benchmarks | Reproduction scripts, artifact hashes, result boundaries |
| [l20-edu-135m-pretrain](https://github.com/Kevin-Li-2025/l20-edu-135m-pretrain) | From-scratch 135M Transformer pretraining on 10B FineWeb-Edu tokens using one NVIDIA L20 | Public checkpoint, lm-eval comparisons, single-GPU training recipe |
| [Single-GPU Inference Lab](https://github.com/Kevin-Li-2025/single-gpu-inference-lab) | Single-L20 infra reference stack for kernels, dispatch policy, serving, and QLoRA smoke runs | Triton RMSNorm/RoPE+KV kernels, L20 benchmark reports, CUDA telemetry |
| [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark) | Text-to-SQL fine-tuning and multi-path inference with Qwen2.5-Coder-7B | Spider/BIRD-style evaluation, cost curves, export paths |
| [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota) | FinanceMTEB Chinese reranking snapshot with Qwen3-Reranker-8B | Public report, CI checks, leaderboard snapshot context |
| [signal-rag](https://github.com/Kevin-Li-2025/signal-rag) | Retrieval workbench with query planning, citation checks, and extractive fallback | Recall evaluation, source-trust tiers, benchmark examples |
| [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl) | Trace, validation, and reward infrastructure for scientific agents | Adversarial cases, semantic judge, deterministic validators |
| [coreb-retrieval-sota](https://github.com/Kevin-Li-2025/coreb-retrieval-sota) | Reproducible CoREB retrieval benchmark snapshot | CI-backed artifacts, result provenance, and [upstream submission issue](https://github.com/hq-bench/coreb/issues/1) |
| [Upstream model-system PRs and reports](https://github.com/search?q=author%3AKevin-Li-2025+is%3Apr+is%3Amerged&type=pullrequests) | Merged fixes in FlashAttention, scikit-learn, Triton, Ray, PyTorch TorchTitan, Apache DataFusion, Apache TVM, ONNX Runtime, xgrammar, plus confirmed Gradio and PyTorch bug reports | Runtime/cache correctness, autoscaler metrics robustness, LoRA freezing behavior, spill execution configuration, CuTe/SM120 compile handling, Array API/DLPack interop safety, benchmarking reliability, ONNX frontend behavior, CUDA/FMHA initialization, parser edge cases, upload-limit enforcement, DLPack crash triage |

## Engineering Standard

I try to make serious repositories answer five questions quickly:

| Question | Expected answer |
| --- | --- |
| What is the exact task? | Dataset, benchmark, workflow, or user problem is named up front. |
| How do I run it? | Setup and reproduction commands are visible from the README. |
| What should happen? | Expected outputs, metrics, report paths, or screenshots are documented. |
| What is proven? | Claims are tied to artifacts rather than vague demos. |
| Where does it fail? | Known limitations and next experiments are explicit. |

## Technical Vector

**Core languages:** Python, TypeScript, SQL, C++, CUDA, Swift, C#  
**Model systems:** PyTorch, Transformers, LoRA/QLoRA, vLLM, lm-eval, Triton  
**LLM applications:** RAG, retrieval evaluation, tool use, citation verification, structured generation  
**Infrastructure:** FastAPI, SQLite, Docker, GitHub Actions, Make, CLI tooling, PostGIS, Redis, Kafka  
**Research direction:** post-training, process supervision, agent evaluation, scientific reproducibility, AI4S infrastructure

## Contact

[Portfolio](https://kevin-li-2025.github.io/) | [GitHub](https://github.com/Kevin-Li-2025)

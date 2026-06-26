# Yin Li

**LLM systems engineer building reproducible evaluation, post-training, retrieval, and traceable agent infrastructure.**

[Portfolio](https://kevin-li-2025.github.io/) | [Selected repositories](https://github.com/Kevin-Li-2025?tab=repositories)

I work on the engineering layer around model behavior: data pipelines, benchmark harnesses, retrieval diagnostics, verifier-guided inference, trace capture, and regression tests that make LLM systems measurable instead of anecdotal.

## Upstream Open Source

- [Triton PR #10411](https://github.com/triton-lang/triton/pull/10411): merged runtime cache-group integrity fix that treats incomplete cache groups as misses.
- [Triton PR #10413](https://github.com/triton-lang/triton/pull/10413): merged benchmarking reliability fix for single pruned autotune configs.
- [PyTorch TorchTitan PR #3456](https://github.com/pytorch/torchtitan/pull/3456): merged LoRA freezing fix for non-linear modules.
- [Apache TVM PR #19818](https://github.com/apache/tvm/pull/19818): merged ONNX frontend correctness fix preserving BatchNormalization inference mode.
- [ONNX Runtime PR #29140](https://github.com/microsoft/onnxruntime/pull/29140): merged CUDA/FMHA kernel initialization fix for large-head variants.
- [PyTorch issue #188023](https://github.com/pytorch/pytorch/issues/188023): reported a negative-stride DLPack crash in `torch.from_dlpack`, triaged as a crash/error-checking/numpy/dlpack bug with a follow-up fix PR opened.

## Operating Thesis

- Treat every model claim as an artifact-backed systems claim: data version, command, hardware, metric, and failure boundary.
- Build evaluation loops that survive refactors: golden sets, deterministic runners, CI checks, and report provenance.
- Keep agent behavior inspectable: tool calls, retrieved sources, validators, retries, and escalation paths should be first-class data.
- Optimize for reproducible learning velocity: small models, single-GPU runs, tight ablations, and clear error analysis before scale.

## System Map

| Surface | What I build | Representative repos |
| --- | --- | --- |
| Post-training and verifier-guided inference | SFT/DPO-style pipelines, executable checks, reward-labeled traces, benchmark exports | [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge), [repro-llm-stack](https://github.com/Kevin-Li-2025/repro-llm-stack) |
| Retrieval and ranking evaluation | Query planning, citation checks, recall/MRR regression tests, reranker snapshots | [signal-rag](https://github.com/Kevin-Li-2025/signal-rag), [retrieval-eval](https://github.com/Kevin-Li-2025/retrieval-eval), [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota), [coreb-retrieval-sota](https://github.com/Kevin-Li-2025/coreb-retrieval-sota) |
| Structured generation benchmarks | NL2SQL, ordering reliability, multi-path inference, cost and robustness reporting | [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark), [arabic-small-qa-sota](https://github.com/Kevin-Li-2025/arabic-small-qa-sota), [order-delta-bench](https://github.com/Kevin-Li-2025/order-delta-bench) |
| Agent trace infrastructure | Scientific workflows, semantic judges, deterministic validators, trace review | [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl), [CodeGraph](https://github.com/Kevin-Li-2025/CodeGraph) |
| Efficient model systems | Quantization experiments, serving benchmarks, GPU instrumentation, compiler/runtime fixes | [Triton PR #10411](https://github.com/triton-lang/triton/pull/10411), [Triton PR #10413](https://github.com/triton-lang/triton/pull/10413), [TorchTitan PR #3456](https://github.com/pytorch/torchtitan/pull/3456), [ONNX Runtime PR #29140](https://github.com/microsoft/onnxruntime/pull/29140), [TVM PR #19818](https://github.com/apache/tvm/pull/19818), [PyTorch issue #188023](https://github.com/pytorch/pytorch/issues/188023), [l20-stack](https://github.com/Kevin-Li-2025/l20-stack), [llm-quant-bench](https://github.com/Kevin-Li-2025/llm-quant-bench), [l20-edu-135m-pretrain](https://github.com/Kevin-Li-2025/l20-edu-135m-pretrain) |

## Selected Systems

| Project | Signal | Evidence surface |
| --- | --- | --- |
| [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge) | Single-L20 post-training and verifier-guided inference for executable code benchmarks | Reproduction scripts, artifact hashes, result boundaries |
| [l20-stack](https://github.com/Kevin-Li-2025/l20-stack) | Single-L20 infra reference stack for kernels, dispatch policy, serving, and QLoRA smoke runs | Triton RMSNorm/RoPE+KV kernels, L20 benchmark reports, CUDA telemetry |
| [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark) | Text-to-SQL fine-tuning and multi-path inference with Qwen2.5-Coder-7B | Spider/BIRD-style evaluation, cost curves, export paths |
| [arabic-small-qa-sota](https://github.com/Kevin-Li-2025/arabic-small-qa-sota) | ARCD same-protocol SOTA: AraELECTRA v11 reaches 71.98 F1 / 40.77 EM, with v12 seed repeat support | Kaggle T4 runs, v1-v12 metrics, public comparison, research-readiness gaps |
| [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota) | FinanceMTEB Chinese reranking snapshot with Qwen3-Reranker-8B | Public report, CI checks, leaderboard snapshot context |
| [signal-rag](https://github.com/Kevin-Li-2025/signal-rag) | Retrieval workbench with query planning, citation checks, and extractive fallback | Recall evaluation, source-trust tiers, benchmark examples |
| [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl) | Trace, validation, and reward infrastructure for scientific agents | Adversarial cases, semantic judge, deterministic validators |
| [coreb-retrieval-sota](https://github.com/Kevin-Li-2025/coreb-retrieval-sota) | Reproducible CoREB retrieval benchmark snapshot | CI-backed artifacts, result provenance, and [upstream submission issue](https://github.com/hq-bench/coreb/issues/1) |
| [Upstream model-system PRs and reports](https://github.com/search?q=author%3AKevin-Li-2025+is%3Apr+is%3Amerged&type=pullrequests) | Merged fixes in Triton, PyTorch TorchTitan, Apache TVM, ONNX Runtime, plus a PyTorch crash report | Runtime/cache correctness, LoRA freezing behavior, benchmarking reliability, ONNX frontend behavior, CUDA/FMHA initialization, DLPack crash triage |

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

# Yin Li

**LLM systems engineer building reproducible evaluation, post-training, retrieval, and traceable agent infrastructure.**

[Portfolio](https://kevin-li-2025.github.io/) | [Selected repositories](https://github.com/Kevin-Li-2025?tab=repositories)

I work on the engineering layer around model behavior: data pipelines, benchmark harnesses, retrieval diagnostics, verifier-guided inference, trace capture, and regression tests that make LLM systems measurable instead of anecdotal.

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
| Structured generation benchmarks | NL2SQL, ordering reliability, multi-path inference, cost and robustness reporting | [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark), [order-delta-bench](https://github.com/Kevin-Li-2025/order-delta-bench) |
| Agent trace infrastructure | Scientific workflows, semantic judges, deterministic validators, graph memory | [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl), [multi-agent-memory-graphs](https://github.com/Kevin-Li-2025/multi-agent-memory-graphs) |
| Efficient model systems | Quantization experiments, serving benchmarks, GPU instrumentation, small-model pretraining | [bitnet-1p58b-experiments](https://github.com/Kevin-Li-2025/bitnet-1p58b-experiments), [llm-quant-bench](https://github.com/Kevin-Li-2025/llm-quant-bench), [l20-edu-135m-pretrain](https://github.com/Kevin-Li-2025/l20-edu-135m-pretrain) |

## Selected Systems

| Project | Signal | Evidence surface |
| --- | --- | --- |
| [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge) | Single-L20 post-training and verifier-guided inference for executable code benchmarks | Reproduction scripts, artifact hashes, result boundaries |
| [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark) | Text-to-SQL fine-tuning and multi-path inference with Qwen2.5-Coder-7B | Spider/BIRD-style evaluation, cost curves, export paths |
| [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota) | FinanceMTEB Chinese reranking snapshot with Qwen3-Reranker-8B | Public report, CI checks, leaderboard snapshot context |
| [signal-rag](https://github.com/Kevin-Li-2025/signal-rag) | Retrieval workbench with query planning, citation checks, and extractive fallback | Recall evaluation, source-trust tiers, benchmark examples |
| [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl) | Trace, validation, and reward infrastructure for scientific agents | Adversarial cases, semantic judge, deterministic validators |
| [coreb-retrieval-sota](https://github.com/Kevin-Li-2025/coreb-retrieval-sota) | Reproducible CoREB retrieval benchmark snapshot | CI-backed artifacts and result provenance |

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

**Core languages:** Python, TypeScript, SQL, Swift, C#  
**Model systems:** PyTorch, Transformers, LoRA/QLoRA, vLLM, lm-eval, Triton  
**LLM applications:** RAG, retrieval evaluation, tool use, citation verification, structured generation  
**Infrastructure:** FastAPI, SQLite, Docker, GitHub Actions, Make, CLI tooling, PostGIS, Redis, Kafka  
**Research direction:** post-training, process supervision, agent evaluation, scientific reproducibility, AI4S infrastructure

## Contact

[Portfolio](https://kevin-li-2025.github.io/) | [GitHub](https://github.com/Kevin-Li-2025)

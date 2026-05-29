# Yin Li

I build reproducible LLM systems where model behavior can be measured, traced, and improved.

[Personal site](https://kevin-li-2025.github.io/) · [GitHub](https://github.com/Kevin-Li-2025)

My work focuses on the engineering layer around large language models: post-training data, retrieval evaluation, tool-use traces, verifiers, and benchmark infrastructure.

## Current Direction

- LLM post-training: SFT, DPO/GRPO, process rewards, verifier-guided inference, and tool-use policy learning
- Retrieval and search: RAG evaluation, citation grounding, query planning, and regression testing
- Agent infrastructure: execution traces, validators, reward-labeled trajectories, and expert-escalation boundaries
- Efficient model systems: quantization, serving, GPU utilization, and reproducible benchmarking
- AI for Science infrastructure: scientific workflow verification, replay, and trace-to-reward learning

## Selected Systems

| Project | What it demonstrates | Evidence surface |
| --- | --- | --- |
| [L20-CodeForge](https://github.com/Kevin-Li-2025/L20-CodeForge) | Single-L20 post-training and verifier-guided inference for executable code benchmarks | Reproduction scripts, artifact hashes, result boundaries |
| [nl2sql-benchmark](https://github.com/Kevin-Li-2025/nl2sql-benchmark) | Text-to-SQL fine-tuning and multi-path inference with Qwen2.5-Coder-7B | Spider/BIRD-style benchmark runs, cost curves, official export paths |
| [finmteb-zh-reranker-sota](https://github.com/Kevin-Li-2025/finmteb-zh-reranker-sota) | FinanceMTEB Chinese reranking snapshot with Qwen3-Reranker-8B | Reported 0.9978 MAP run, CI checks, leaderboard snapshot |
| [signal-rag](https://github.com/Kevin-Li-2025/signal-rag) | Retrieval workbench with query planning, citation checks, and extractive fallback | Recall evaluation, source-trust tiers, benchmark examples |
| [scitrace-rl](https://github.com/Kevin-Li-2025/scitrace-rl) | Trace, validation, and reward infrastructure for scientific agents | Adversarial cases, semantic judge, deterministic validators |
| [accessible-route-planner](https://github.com/Kevin-Li-2025/accessible-route-planner) | Accessibility-aware urban routing across API, graph workers, and mobile client | .NET/PostGIS/Redis/Kafka stack, profiling, Kubernetes path |

## Engineering Standards

- Every serious project should expose setup, reproduce, expected output, and known limitations.
- Claims should be tied to commit-stable artifacts, data versions, hardware notes, and evaluation commands.
- Agent and RAG systems should preserve evidence: tool calls, retrieved sources, validators, failures, and escalation points.
- Benchmarks should be useful for regression testing, not just one-off reporting.

## Technical Stack

**Languages:** Python, TypeScript, SQL, Swift, C#  
**ML systems:** PyTorch, Transformers, LoRA/QLoRA, vLLM, lm-eval, Triton  
**LLM applications:** RAG, retrieval evaluation, tool use, citation verification, structured generation  
**Infrastructure:** FastAPI, SQLite, Docker, GitHub Actions, Make, CLI tooling, PostGIS, Redis/Kafka  
**Research interests:** post-training, process supervision, agent evaluation, scientific reproducibility, AI4S infrastructure

## Contact

- Website: [kevin-li-2025.github.io](https://kevin-li-2025.github.io/)
- Interests: LLM systems, AI agents, post-training, evaluation, AI for Science

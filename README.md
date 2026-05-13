# Hi, I'm Kevin

I am a second-year Artificial Intelligence student in the School of Computer Science at the University of Birmingham, with a 4.0 GPA. I build and study large language model systems, with a focus on post-training, evaluation, retrieval, tool use, and trustworthy agent infrastructure.

My current work sits between engineering and research: turning model behavior into measurable systems, building reproducible evaluation pipelines, and designing infrastructure that makes agentic workflows traceable, verifiable, and useful for further training.

## Current Focus

- Large language model post-training: SFT, DPO/GRPO, process rewards, and tool-use policy learning
- Retrieval and search systems: RAG evaluation, citation grounding, query planning, and regression testing
- Agent infrastructure: execution traces, validators, reward-labeled trajectories, and expert-escalation policies
- Efficient inference and model systems: quantization, serving, GPU utilization, and reproducible benchmarking
- AI for Science infrastructure: scientific workflow verification, reproducibility, and trace-to-reward learning

## Selected Projects

### SciTrace-RL
Trace, validation, and reward infrastructure for scientific agents.  
The system records tool calls, artifacts, citations, validation results, and failure modes, then converts execution traces into training-ready feedback data.

- 15-case adversarial evaluation suite
- DeepSeek/OpenAI-compatible semantic judge
- deterministic validators for citation integrity, replay, constraints, and claim-evidence alignment
- expert-required boundary cases for high-fidelity simulation or wet-lab validation

### NL2SQL
Reproducible text-to-SQL fine-tuning and multi-path inference benchmark using Qwen2.5-Coder-7B on Spider/BIRD-style tasks.

### repro-llm-stack
Reproducible post-training pipeline for 7B-class language models, including data manifests, SFT/DPO preparation, data quality checks, and lm-eval integration.

### SignalRAG
Search and retrieval workbench with query planning, multi-source retrieval, citation checking, corrective retrieval, and extractive fallback when model APIs are unavailable.

### CodeGraph
AST-driven GraphRAG for codebases, using deterministic program structure rather than plain text chunks for architectural reasoning.

## Technical Stack

**Languages:** Python, TypeScript, SQL, Swift  
**ML Systems:** PyTorch, Transformers, LoRA/QLoRA, vLLM, lm-eval, Triton  
**LLM Applications:** RAG, retrieval evaluation, tool use, citation verification, structured generation  
**Infra:** FastAPI, SQLite, Docker, GitHub Actions, Make, CLI tooling  
**Research Interests:** post-training, process supervision, agent evaluation, scientific reproducibility, AI4S infrastructure

## What I Care About

I am interested in systems where model outputs are not treated as the final product. I care about the execution layer around models: what evidence was used, which tools were called, whether the result can be reproduced, how failures are labeled, and how those traces can improve the next model or agent.

## Contact

- GitHub: [Kevin-Li-2025](https://github.com/Kevin-Li-2025)
- University: University of Birmingham, School of Computer Science
- Interests: LLM systems, AI agents, post-training, evaluation, AI for Science

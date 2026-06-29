---
title: Client-server interfaces enable efficient agent-driven variant calling
title_zh: 客户端-服务器接口实现高效的智能体驱动变异检测
authors: "Yu, X., Zheng, Z., CHEN, L., QIn, Z., Guo, X., He, M., Luo, R."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734665v1.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 变体检测的代理接口改进
tldr: 大语言模型代理自动化生物信息分析时，现有工具为人类设计导致低效。本文通过将Clair3重构为客户端-服务器系统Clair3-Connect，客户端处理基因组数据并暴露schema定义的代理工具，服务器仅运行推理。在APOE分型中，代理调用令牌减少6.8-14倍，时间缩短3/4，稳定性提升。结果表明，为代理设计专属接口比第三方包装更高效可靠，应成为工具开发的一等目标。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生物信息工具为人类专家使用设计，LLM代理调用时因需推理安装配置等，导致令牌和轮次开销大、可靠性低。
method: 将Clair3重构为客户端-服务器系统，客户端处理基因组学、持有可识别数据并暴露schema定义的工具接口，服务器仅运行神经网络推理，客户端仅传输特征张量。
result: "APOE分型任务中全部正确，令牌使用12K（3轮），比shell基线（81K-163K）减少6.8-14倍，时间约1/4，令牌波动4% vs 35%。去除pileup/phasing阶段后SNP F1与标准Clair3相差0.1-0.3。"
conclusion: 将已有算法重新设计为开发者构建的、带安全边界的agentic工具，比第三方包装更高效可靠；agentic接口应作为生物信息工具开发的一等交付物。
---

## 摘要
背景：大型语言模型智能体日益自动化生物信息学分析，但大多数现有生物信息学工具是为人类专家独立使用而构建的。驱动此类工具的智能体必须从人类文档中推理其安装、配置和执行，每个结果需要多次交互、大量令牌和工具调用。因此，方法对智能体的暴露方式与方法本身同等重要。通过为这些工具设计智能体接口，智能体可以减少此类开销并提高智能体驱动分析的可靠性。发现：为测试这一设计，我们重构了广泛使用的基于深度学习的长读长变异检测器Clair3，将其转变为客户端-服务器系统Clair3-Connect。客户端执行所有基因组学相关处理并持有可识别数据。服务器仅运行神经网络推理，客户端仅向服务器发送特征张量，而样本标识符和基因组上下文保留在客户端。客户端暴露基于模式定义的面向智能体的工具，智能体通过单一结构化调用调用这些工具。在APOE单倍型分型任务中，所有60次智能体运行均正确。智能体工具在3次交互中使用了1.2万令牌，比基于Shell的基线（8.1万-16.3万令牌）少6.8到14倍，用时约为其四分之一，且稳定性更高（令牌使用变异率4%对比35%）。为保持客户端轻量化而省略了堆积和定相阶段，使得SNP F1在50倍覆盖度下与标准Clair3相差0.1-0.3个百分点，而双向TLS和AES-256-GCM加密使端到端运行时间增加了7.2%。结论：将既定算法重塑为开发者构建的、置于安全客户端-服务器边界之后的智能体工具，使其对LLM智能体而言比第三方封装更高效、可靠且易于部署，因为第三方封装无法恢复只有其开发者才知道的默认值和惯例。智能体接口应成为生物信息学工具开发的一级交付物。

## Abstract
Background: Large language model (LLM) agents increasingly automate bioinformatics analyses, but most existing bioinformatics tools were built for standalone use by human experts. An agent driving such a tool must reason about its installation, configuration, and execution from documentation for human, spending many turns, tokens, and tool calls per result. How a method is exposed to an agent can therefore matter as much as the method itself. By designing agentic interfaces for these tools, agent can reduce such overhead and improve the reliability of agent-driven analyses. Findings: To test this design, we re-architected Clair3, a widely used deep-learning-based long-read variant caller, into a client-server system, Clair3-Connect. The client performs all genomics related processing and holds the identifiable data. The server runs only neural-network inference, and the client sends only feature tensors to the server, while sample identifiers and genomic context remain on the client. The client exposes schema-defined agent-facing tools that an agent invokes through single structured calls. On an APOE diplotyping task, all 60 agent runs were correct. The agentic tools used 12K tokens in 3 turns, 6.8 to 14 times fewer tokens than the shell-driven baselines (81K-163K tokens), at about a quarter the wall-clock time and far more stably (4% versus 35% token usage variation). Dropping the pileup and phasing stages to keep the client light left SNP F1 within 0.1-0.3 points of standard Clair3 by 50x coverage, while mutual TLS and AES-256-GCM encryption added 7.2% to end-to-end runtime. Conclusions: Recasting an established algorithm as developer-built, agentic tools behind a secure client-server boundary makes it more efficient, reliable, and easier to deploy for an LLM agent than a third-party wrapper, which cannot recover the defaults and conventions only its developers know. Agentic interfaces should be a first-class deliverable of bioinformatics tool development.
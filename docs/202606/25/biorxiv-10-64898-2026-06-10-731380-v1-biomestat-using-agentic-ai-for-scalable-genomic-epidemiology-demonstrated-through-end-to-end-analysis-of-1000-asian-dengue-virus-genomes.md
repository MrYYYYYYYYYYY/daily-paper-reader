---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用智能体AI实现可扩展基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析进行示范
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 通过确定性编排解决生物领域生成AI的幻觉问题
tldr: "基因组流行病学工作流通常依赖专家手动组合多个工具、调参和异构计算资源，标准生成式AI易在复杂生物学领域产生幻觉。本文提出biomeStat，一个自主AI代理，通过自动编写代码执行既定生物信息学工具并动态分配CPU/GPU资源，保证可重复性。在1,000个亚洲登革病毒基因组的全自动分析中，24小时内完成了系统发育重建、贝叶斯系统动力学、选择压力分析及结构映射，揭示了内源性稳定和大量免疫逃逸位点，并确认了抗病毒药物靶标残基的高度保守性。该平台将数周专家工作压缩为单次分析，同时保持方法论透明，弥合了自然语言意图与确定性计算执行间的鸿沟。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组流行病学工作流依赖专家手动操作多个工具和异构计算资源，耗时长且易出错，亟需可扩展的自主分析框架。
method: biomeStat作为确定性编排器，自动编写代码调用IQ-TREE、BEAST2、HyPhy等工具，在沙盒环境中动态分配CPU/GPU并保证可重复性。
result: "完成1,000个DENV基因组的24小时全自动分析，发现R_e≈1，鉴定1,869个候选免疫逃逸位点结构共定位于B/T细胞表位，并确认176个药物靶点残基在四种血清型中绝对保守。"
conclusion: biomeStat通过自然语言驱动的确定性计算执行，将数周专家工作缩减为单次可复现分析，为基因组流行病学提供了可扩展的AI解决方案。
---

## 摘要
基因组流行病学工作流程通常需要专家对多种专业工具进行管理、大量的手动参数调整以及访问异构计算基础设施。尽管标准的生成式AI模型在复杂的生物学领域常常出现幻觉，但我们引入了biomeStat：一个自主AI代理，它作为一个严格的确定性编排器。通过在沙盒环境中自动编写代码来执行成熟的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU）并保证可重复性，使其即使对于不熟悉命令行的科学家也能立即使用。

为了展示该平台，我们对2000年至2025年间从16个亚洲国家采集的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该代理无缝地编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU的BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在不到24小时的墙上时钟时间内完成，揭示了地方性稳定性（R_e ≈ 1.0），并识别了1869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该代理验证了病毒复制复合体中176个高度保守的药物靶点残基，确认新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专家工作减少为单次分析，同时保持完全的方法透明度。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.
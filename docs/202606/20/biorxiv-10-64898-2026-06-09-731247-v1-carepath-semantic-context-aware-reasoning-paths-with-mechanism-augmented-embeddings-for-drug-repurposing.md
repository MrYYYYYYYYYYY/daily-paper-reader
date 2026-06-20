---
title: "CAREPath: Semantic Context-Aware Reasoning Paths with Mechanism-Augmented Embeddings for Drug Repurposing"
title_zh: CAREPath：基于机制增强嵌入的语义上下文感知推理路径用于药物重定位
authors: "song, h., bang, d., koo, b., Kim, S., lee, s."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.731247v1.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 提出了一种新颖的KG-LLM推理框架，具有算法创新
tldr: "生物医学知识图谱通过多跳路径连接药物与疾病，但长路径存在组合爆炸和无关基因噪音问题。本文提出CAREPath框架，融合类似深度优先搜索的短路径语义编码和类似广度优先搜索的一跳基因邻域机制上下文增强嵌入。在五个知识图谱上，AUPRC优于18个基线，最高提升3.8%。该框架实现可解释、机制感知且可扩展的药物重定位。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有知识图谱路径推理在药物重定位中因长路径组合爆炸和hub基因噪音而效果不佳，过约束路径又丢失生物上下文。
method: CAREPath采用DFS-like约束短路径生成语义嵌入，并用BFS-like构建基因邻域机制上下文嵌入，通过药理相似药物和基因签名相似疾病进行增强。
result: "在五个生物医学知识图谱上，CAREPath在18个基线中取得最佳AUPRC，最高提升3.8%，短路径编码贡献最大。"
conclusion: CAREPath是一种可解释、机制感知的药物重定位框架，平衡了特异性、可扩展性与上下文恢复，并通过案例和FDA批准验证了实用性。
---

## 摘要
包含药物、基因和疾病的生物医学知识图谱通过基因介导的多跳路径将药物与疾病连接起来，从而支持药物重定位，并实现作用机制推理。然而，更深的遍历并不一定能改善机制推理：长路径的组合增长且频繁经过枢纽基因，产生无关的基因调控信号，而过度约束或稀疏的路径可能遗漏更广泛的生物学背景。我们提出CAREPath，一种受深度优先搜索和广度优先搜索推理启发的KG-LLM框架，以平衡机制特异性、可扩展性和上下文恢复。DFS类模块将遍历限制在短疾病-基因-药物路径上，将每条路径转换为结构化提示，并用生物医学语言模型编码生成语义路径嵌入。作为补充，BFS类模块从一跳基因邻域构建实体级机制上下文嵌入，并通过使用药理学相关药物和基因特征相似疾病的相似性引导增强来丰富嵌入。在五个生物医学知识图谱上，CAREPath在18个基线中达到了最佳整体AUPRC，性能提升高达3.8%。进一步分析表明，语义短路径编码对性能贡献最大，而机制上下文增强提高了稀疏证据下的鲁棒性，并加强了基因本体功能一致性。案例研究和最近FDA批准的适应症进一步证明了其实用性，将CAREPath定位为可解释的框架，用于可扩展且机制感知的药物重定位。源代码可在https://github.com/hamppy-song/CAREPath获取。

## Abstract
Biomedical knowledge graphs (BKGs) that include drugs, genes, and diseases support drug repurposing by connecting drugs to diseases through gene-mediated multi-hop paths, thereby enabling mechanism-of-action reasoning. However, deeper traversal does not necessarily improve mechanistic reasoning: long paths grow combinatorially and frequently pass through hub genes, producing irrelevant gene regulatory signals, whereas overly constrained or sparse paths may miss broader biological context. We propose CAREPath, a KG-LLM framework inspired by depth-first search (DFS)-like and breadth-first search (BFS)-like reasoning to balance mechanistic specificity, scalability, and context recovery. The DFS-like module constrains traversal to short disease-gene-drug paths, converts each path into a structured prompt, and encodes it with a biomedical language model to generate semantic path embeddings. Complementarily, the BFS-like module constructs entity-level mechanism-context embeddings from one-hop gene neighborhoods and enriches them through similarity-guided augmentation using pharmacologically related drugs and gene-signature-similar diseases. Across five biomedical KGs, CAREPath achieves the best overall AUPRC among 18 baselines, improving performance by up to 3.8%. Additional analyses show that semantic short-path encoding contributes most to performance, while mechanism-context augmentation improves robustness under sparse evidence and strengthens Gene Ontology functional agreement. Case studies and recently FDA-approved indications further demonstrate its practical relevance, positioning CAREPath as an interpretable framework for scalable and mechanism-aware drug repurposing. Source code is available at https://github.com/hamppy-song/CAREPath.
---
title: "APOSM: Pairwise preference learning improves generative small-molecule design"
title_zh: APOSM：成对偏好学习改进小分子生成设计
authors: "Dreisler, M. W., Michael, R., Hatzakis, N. S., Boomsma, W."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.06.730554v1.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 成对偏好学习用于分子设计中的代理模型
tldr: 小分子先导化合物优化受限于候选物合成与测试的高成本，依赖代理模型进行排序。传统点回归模型受限于噪声和稀疏数据。本文提出APOSM，利用成对偏好学习训练代理，结合片段生成器、成对消息传递图神经网络和概率排序，在主动学习循环中批量采样。在分子优化基准和GPCR配体重发现任务中，APOSM在目标达成和采样效率上优于多种基线方法，尤其在绝对分数校准困难的任务上提升显著。
source: biorxiv
selection_source: fresh_fetch
motivation: 点回归代理模型在噪声和稀疏的筛选测量下可靠性有限，需要更鲁棒的分子排序方法。
method: 提出APOSM算法，包含片段生成器、成对消息传递图神经网络代理和概率排序，通过成对比较训练代理并在批量采集循环中进行主动学习。
result: 在Practical Molecular Optimization基准和GPCR配体重发现任务中，APOSM比未引导的片段优化、Graph-GA遗传算法和点回归消融方法在目标达成和采样效率上更优。
conclusion: 成对偏好学习能显著提升主动小分子设计的代理模型可靠性，尤其适用于绝对分数难以校准的场景。
---

## 摘要
小分子先导化合物的优化受到合成和测试候选物成本的限制，因此，对实验测试的化合物进行优先排序的代理模型在设计过程中至关重要。这类代理模型的可靠性受到筛选测量噪声和稀疏性的限制。我们证明，在候选分子之间进行成对比较（而非绝对预测分数）的训练方式，能够在该场景下为主动候选选择提供更可靠的信号。我们开发了APOSM，一种主动学习算法，它结合了基于片段的生成器、成对消息传递图神经网络代理以及批量获取循环中的概率排名。在实用分子优化基准和GPCR配体重发现任务中，APOSM在目标达成和采样效率上优于无引导的基于片段的优化、Graph-GA遗传算法以及逐点回归消融方法，在绝对分数最难校准的任务中提升最为显著。

## Abstract
Small-molecule lead refinement is constrained by the cost of synthesizing and assaying candidates, making the surrogate models that prioritize compounds for experimental testing central to the design process. The reliability of such surrogates is limited by the noise and sparsity of screening measurements. We show that training the surrogate on pairwise comparisons between candidate molecules, rather than on absolute predicted scores, yields a substantially more reliable signal for active candidate selection in this regime. We develop APOSM, an active-learning algorithm that combines a fragment-based generator, a pairwise message-passing graph neural network surrogate, and probabilistic ranking inside a batched acquisition loop. On the Practical Molecular Optimization benchmark and a GPCR ligand rediscovery task, APOSM improves target attainment and sampling efficiency over unguided fragment-based optimization, the Graph-GA genetic algorithm, and a pointwise-regression ablation, with the largest gains on tasks where absolute scores are hardest to calibrate.
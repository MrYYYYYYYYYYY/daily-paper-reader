---
title: "AutoZyme: An Autonomous Agentic Framework to Optimize Bioinformatics Software"
title_zh: AutoZyme：一个用于优化生物信息学软件的自主代理框架
authors: "Xie, E., Cheng, L., Cai, Y., Shireman, J., Kendziorski, C."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731250v1.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 生物信息学算法改进的自主框架
tldr: "生物信息学软件性能瓶颈随数据增长而加剧，传统专家手动优化难以扩展。为此提出AutoZyme，一种自主智能体框架，能够自动构建基准测试、识别瓶颈并迭代优化代码，仅保留提升运行时的修改。在45个函数上评估，超过95%的情况下运行时显著改善且内存开销基本不变；针对Seurat、Scanpy等基因组学工具的38个函数，中位数加速8.52倍，最高达676倍。优化后的函数作为即插即用替换发布，框架本身可重用，为科学软件优化提供自动化解决方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 生物信息学软件性能瓶颈依赖专家手动优化，难以规模化应对数据增长。
method: AutoZyme通过智能体框架自动构建基准、识别瓶颈、迭代测试代码更改并保留有效优化。
result: "在45个函数中超95%提升运行时，38个基因组学函数中位数加速8.52倍，最大676倍。"
conclusion: AutoZyme是可重用框架，优化函数可即插即用，推动科学软件自动优化。
---

## 摘要
广泛使用的基因组学和生物信息学软件中的性能瓶颈带来了巨大且日益增长的负担，因为生物数据集在大小和数量上持续增加。缓解这些瓶颈主要依赖专家手动优化，因此难以扩展。本文介绍了AutoZyme，一个用于科学软件优化的代理框架。给定一个目标函数，AutoZyme构建基准测试、识别瓶颈并迭代测试代码更改，仅保留那些改善运行时间且保持输出不变的更改。我们在45个函数上评估了AutoZyme，在超过95%的案例中，在不显著增加内存的情况下改善了运行时间。对于来自Seurat、Scanpy以及基因组学和生物信息学相关包的38个函数，AutoZyme将运行时间中位数减少了8.52倍，最大减少超过676倍。优化后的函数通过AutoZyme-Library分发，作为现有分析管道的直接替换。我们还发布了AutoZyme作为一个可复用框架，用于优化用户指定的其他包和函数。

## Abstract
Performance bottlenecks in widely used genomics and bioinformatics software present a substantial and growing burden as biological datasets continue to increase in size and number. Relieving these bottlenecks relies largely on expert manual optimization and therefore remains difficult to scale. Here we present AutoZyme, an agentic framework for scientific software optimization. Given a target function, AutoZyme builds benchmarks, identifies bottlenecks, and iteratively tests code changes, retaining only those that improve runtime while preserving output. We evaluated AutoZyme on 45 functions, improving runtime without substantial memory increases in over 95% of cases considered. Across 38 functions from Seurat, Scanpy and related packages in genomics and bioinformatics, AutoZyme reduced runtime by a median of 8.52-fold, with the largest reductions exceeding 676-fold. The optimized functions are distributed through AutoZyme-Library as drop-in replacements for existing analysis pipelines. We also release AutoZyme as a reusable framework for optimizing additional user-specified packages and functions.
---
title: Spatial synaptic regularization stabilizes learning across biological and artificial neural networks
title_zh: 空间突触正则化在生物与人工神经网络中稳定学习
authors: "Zhu, H., Chen, Y., Zhao, P., Xiong, Z., Peng, H., Wu, F., Zhang, R."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735142v1.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 空间突触正则化作为稳定LLM学习的算法改进
tldr: 突触的空间组织如何稳定学习是神经科学的关键问题。利用人颞叶皮层H01电镜连接组，发现树突棘形态聚类且权重呈中心高、周围抑制的排布，据此提出空间突触正则化(SSR)。SSR通过保留高秩低重叠表示，在持续学习、大语言模型知识编辑和视觉语言模型适应等任务中有效减少遗忘并稳定学习。该发现揭示空间突触组织是稳定学习的新维度，表明结构连接组学可启发实用的AI方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究突触空间组织对学习稳定性的影响，并从中提取可应用于人工神经网络的正则化原理。
method: 基于H01电镜连接组发现突触权重空间模式，形式化为正则化Hebbian模型，进而提出空间突触正则化(SSR)。
result: SSR在持续视觉学习、LLM知识编辑及VLM参数高效适应中减少遗忘，稳定学习，并保持高秩低重叠表征。
conclusion: 空间突触组织是稳定学习的关键结构基础，结构连接组学可指导AI算法设计。
---

## 摘要
突触的空间组织如何促进学习的稳定仍是神经科学的一个基本问题。利用人类颞叶皮层的H01电子显微镜连接组，我们发现树突棘在形态上聚类，而突触权重沿树突呈中心升高、周围抑制的排列。一个正则化的赫布模型形式化了这一空间特征，表明强突触降低了相邻突触达到高权重状态的概率。将该原则转化为空间突触正则化（SSR），通过保留高秩、低重叠的表征，减少了不同人工网络和任务中的遗忘并稳定了学习，包括持续视觉学习、大型语言模型知识编辑以及视觉-语言模型的参数高效适应。这些发现将空间突触组织确定为稳定学习的一个未被认识的维度，并表明结构连接组学可以产生可操作的人工智能方法。

## Abstract
How the spatial organization of synapses contributes to stable learning remains a fundamental question in neuroscience. Using the H01 electron microscopy connectome of human temporal cortex, we found that dendritic spines clustered morphologically, whereas synaptic weights followed a center-elevated, surround-suppressed arrangement along dendrites. A regularized Hebbian model formalized this spatial signature, showing that strong synapses lower the probability that neighboring synapses reach high-weight states. Translating this principle into Spatial Synaptic Regularization (SSR) reduced forgetting and stabilized learning across diverse artificial networks and tasks, including continual visual learning, large language-model knowledge editing, and parameter-efficient adaptation of vision-language models, by preserving high-rank, low-overlap representations. These findings identify spatial synaptic organization as an unrecognized dimension for stabilizing learning and show that structural connectomics can yield actionable AI methods.
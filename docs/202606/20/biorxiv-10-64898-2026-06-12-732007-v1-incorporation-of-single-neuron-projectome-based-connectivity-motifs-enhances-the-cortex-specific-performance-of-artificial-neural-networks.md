---
title: Incorporation of single-neuron projectome-based connectivity motifs enhances the cortex-specific performance of artificial neural networks
title_zh: 基于单神经元投射组连接模式的人工神经网络皮层特异性性能增强
authors: "Sun, Y., Yao, W., Zhang, J., Song, W., Zhao, X., Hao, C., Chen, X., Zeng, S., Jia, S., Yang, Y., Xiao, X., Poo, M.-m., Xu, B., Zhang, T."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.732007v1.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 创新的生物启发连接模体提升人工神经网络包括大语言模型的性能
tldr: 该研究从小鼠单神经元连接组中提取不同皮层的三节点连接基序，开发CINA算法将其融入RNN和Transformer。平均皮层基序提升了抗噪分类和运动学习性能，而皮层特定基序进一步增强相关任务表现，且增大基序偏向可强化效果。图论分析表明自然基序诱导了模块化和小世界属性。工作验证了连接组启发的ANN优化及皮层特异性基序的功能意义。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索自然神经网络的皮层特异性连接基序，以启发人工神经网络的架构优化。
method: 分析小鼠单神经元连接组的基序特征，将自然基序嵌入RNN和Transformer架构。
result: 皮层特定基序提升相关任务性能，增强偏向可强化效果，并催生模块化与小世界拓扑。
conclusion: 证实了皮层特异性连接基序的功能重要性，为脑启发ANN设计提供新途径。
---

## 摘要
自然神经网络的组织原则可为人工神经网络（ANNs）的新架构设计提供灵感。对小鼠大脑单神经元连接组的分析揭示了不同皮层区域和海马结构中三节点连接模式的独特特征。我们开发了一种连接组信息神经网络算法（"CINA"），将自然连接模式融入以循环神经网络（RNN）和基于Transformer的大语言模型（LLM）为代表的人工神经网络算法中。研究发现，与随机连接的RNN相比，融入皮层连接模式的平均特征可提升RNN在抗噪声分类和运动学习基准任务中的表现。值得注意的是，融入皮层特异性连接模式进一步增强了RNN在皮层相关任务中的性能，且这种效应可通过人为增加连接模式偏置得到强化。在基于Motif-Transformer的LLM上进行的自然语言问答和脑信号解码任务中验证了相似的实验结果。图论分析表明，融入自然连接模式促使人工神经网络涌现出模块化和小世界特性。综上，我们不仅展示了连接组启发的神经网络架构优化，还揭示了特定连接模式在不同皮层中的功能重要性。

## Abstract
The organizational principles of natural neural networks could inspire the new architecture design of artificial neural networks (ANNs). Analysis of single-neuron connectomes of mouse brains revealed distinct profiles of three-node connectivity motifs in various cortical areas and hippocampal formation. A connectome-informed neural network algorithm ("CINA") was developed to incorporate natural connectivity motifs into ANN algorithms represented by recurrent neural network (RNN) and transformer-based large language model (LLM). We found that incorporation of the average profile of cortical motifs improved the RNNs performance in noise-resistant categorization and motor learning benchmark tasks, as compared with RNNs with random connectivity. Notably, incorporating cortex-specific motifs further elevated the RNNs performance in tasks related to the cortical function, and this effect was enhanced by artificially increasing the bias in the motif profile. Similar experimental results were verified on an LLM using Motif-Transformer for natural language question answering and brain-signal decoding tasks. Graph-theoretic analyses showed that incorporating natural motifs drove the emergence of modular and small-world properties in ANNs. Together, we demonstrated not only connectome-inspired optimization of ANN architecture but also functional significance of specific motif profiles in various cortices.
---
title: Transitive reasoning as linear classification
title_zh: 传递推理作为线性分类
authors: "Ferrera, V. P., Lippl, S., Kay, K., Munoz, F., Jin, Y., Jensen, G., Terrace, H."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734346v2.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 将传递推理形式化为线性分类，使用最小二乘估计
tldr: 传递推理依赖有序项的线性表示，但传统观点认为其需要复杂认知机制。本文用最小二乘估计构建线性分类器，无需显式传递假设，即可在序列学习任务中重现泛化能力和符号距离效应。分类器产生内部排序表示，通过差分操作选择正确项。结果表明传递推理可简化为线性分类问题，挑战传统认知假设。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1156, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1702, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1696, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1059, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1023, \"height\": 698, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 989, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-734346-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 828, \"height\": 877, \"label\": \"Figure\"}]"
motivation: 探索传递推理的计算机制，挑战传统认知假设。
method: 利用最小二乘估计学习线性分类器，对序列学习任务进行建模。
result: 线性分类器重现了传递推理的泛化能力和符号距离效应，产生内部排序表示。
conclusion: 传递推理本质上是一个线性分类问题，无需复杂认知机制。
---

## 摘要
传递推理（TI）是指在一组有序项目中推理传递关系的能力（例如，若A>B且B>C，则A>C）。普遍认为TI依赖于对这些项目序列（等级）顺序的线性表征。在学习过程中，这种排序是通过何种计算机制构建的，又是如何用于做出符合传递性的选择的？在此，我们采取一种极简主义方法，将最小二乘估计（LSE）应用于常用于测试人类和动物TI的序列学习任务。在这种表述中，LSE计算一个线性分类器，将任务条件映射到行为结果。该算法没有对传递性或序列顺序做出任何明确假设，但它再现了TI的关键经验特征；即超越训练集进行泛化的能力，以及正确率中的符号距离效应（SDE）。将该分类器应用于单个项目，会产生一个内部有序的等级表征，泛化和SDE自然从中涌现。该方法还提供了一种决策机制，以差分操作的形式，从任意一对项目中选择正确的项目。这些发现将TI重新定义为线性分类问题，挑战了关于传递推理所需认知机制的传统假设。

## Abstract
Transitive inference (TI) is the ability to reason about transitive relationships in an ordered set of items (e.g., if A>B and B>C, then A>C). TI is widely held to depend on a linear representation of the serial (rank) order of those items. By what computational mechanism is such an ordering constructed during learning, and how is it used to make choices that obey transitivity? Here we take a minimalist approach, applying least-squares estimation (LSE) to a serial learning task commonly used to test TI in humans and animals. In this formulation, LSE computes a linear classifier that maps task conditions onto behavioral outcomes. This algorithm makes no explicit assumptions about transitivity or serial order, yet it reproduces key empirical features of TI; namely, the ability to generalize beyond the training set, and a symbolic distance effect (SDE) in performance accuracy. Applying the classifier to individual items produces an internally ordered representation of rank from which both generalization and the SDE naturally emerge. The approach also yields a decision mechanism, in the form of a differencing operation, for selecting the correct item from any pair. These findings reframe TI as a linear classification problem, challenging conventional assumptions about the cognitive mechanisms required for transitive reasoning.
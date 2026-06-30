---
title: Inverse reinforcement learning reveals action-oriented value signals in naturalistic decision making
title_zh: 逆强化学习揭示自然决策中的行动导向价值信号
authors: "Lee, S. H., Chung, C., Oh, M.-h., Ahn, W.-Y."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.733779v1.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 逆强化学习用于奖励推断
tldr: 自然情境下的决策价值计算是认知神经科学的难题。本文采用逆强化学习从真实驾驶行为中推断潜在奖励轨迹，并将其与fMRI脑活动关联。结果发现该奖励主要映射到背侧纹状体，并分布到认知控制等脑区。这表明逆强化学习可提供行为驱动的、时间精细的动作导向价值信号。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有决策计算模型难以适用于自然情境实时行为，需要一种从观测行为推断潜在价值的框架，并验证其神经基础。
method: 在fMRI扫描中执行实时驾驶任务，用逆强化学习从行为数据推断逐时刻奖励轨迹，并与脑活动进行回归分析。
result: 逆强化学习奖励与背侧纹状体活动最显著相关，并与认知控制、感觉运动等分布式区域有关。
conclusion: 逆强化学习奖励可作为自然决策中动作导向价值的可靠代理，反映价值与多过程的交互。
---

## 摘要
认知神经科学的一个主要挑战是解释目标导向行为的价值如何在复杂和自然环境中被计算。标准的决策计算模型在受控的、基于试次的范式中取得了巨大成功，但它们往往不适用于自然范式中实时展开的行为。逆强化学习提供了一种从自然环境中观察到的行为推断潜在评价状态的方法，但其神经可解释性在很大程度上仍然未知。在此，我们研究了在执行功能磁共振成像扫描期间进行的实时驾驶任务中，从逆强化学习导出的逐时刻奖励轨迹是否映射到大脑中的价值信号。逆强化学习导出的奖励轨迹与背侧纹状体的活动相关性最强，该区域通常与价值导向的行动选择相关。它们还与支持额外过程（包括认知控制和感觉运动处理）的分布区域显示出关联。这种模式表明逆强化学习奖励捕获了以奖励回路为中心的分布式神经活动，可能反映了评价如何与其他过程相互作用。总之，这些发现表明，在自然决策过程中，逆强化学习奖励为行动导向评价提供了一个基于行为、时间分辨的代理指标。

## Abstract
A major challenge for cognitive neuroscience is to explain how value of a goal-directed behavior is computed in complex and naturalistic environments. Standard computational models of decision making have been highly successful in controlled, trial-based paradigms, but they are often ill-suited to real-time behavior unfolding in naturalistic paradigms. Inverse reinforcement learning (IRL) offers a way to infer latent evaluative state from observed behavior in naturalistic environments, but its neural interpretability remains largely unknown. Here, we investigated whether moment-to-moment reward trajectories derived from IRL map onto value signals in the brain during a real-time driving task performed during fMRI scanning. IRL-derived reward trajectories were most robustly associated with activity in the dorsal striatum, a region often linked to value-guided action selection. They also showed associations with distributed regions supporting additional processes, including cognitive control and sensorimotor processing. This pattern suggests that IRL reward captures distributed neural activity centered on the reward circuitry, potentially reflecting how valuation interacts with other processes. Together, these findings suggest that IRL reward provides a behaviorally grounded, temporally resolved proxy for action-oriented valuation during naturalistic decision making.
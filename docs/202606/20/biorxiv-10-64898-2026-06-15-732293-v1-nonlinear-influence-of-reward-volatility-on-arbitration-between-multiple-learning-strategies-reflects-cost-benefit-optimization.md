---
title: Nonlinear influence of reward volatility on arbitration between multiple learning strategies reflects cost-benefit optimization
title_zh: 奖励波动性对多种学习策略间仲裁的非线性影响反映成本效益优化
authors: "Yamada, T., Samejima, K."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732293v1.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 研究奖励波动下强化学习策略的选择
tldr: 行为选择依赖模型自由和模型基础两种策略。本研究通过两步决策任务发现奖励波动性对策略仲裁呈倒U形非线性影响：中等波动时模型基础策略最强，且仅在学习过渡结构的个体中显现；时间压力增加则偏向模型自由策略。结果表明人类在不确定环境中并非始终使用模型基础策略，支持成本效益优化。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究奖励波动性如何调节模型自由与模型基础学习策略的仲裁，以理解动态不确定环境中决策的优化机制。
method: 采用两个修正的两步决策任务，系统操纵奖励波动性和时间压力，结合模型无关分析和分层贝叶斯模型拟合。
result: 奖励波动性对策略仲裁呈倒U形非线性影响，中等波动时模型基础策略驱动最强，且仅在学习过渡结构的个体中出现；时间压力增加则偏向模型自由策略。
conclusion: 人类在动态环境中并不始终使用模型基础策略，即使了解任务结构，其选择符合成本效益优化原则。
---

## 摘要
行动选择涉及两个系统：无模型强化学习策略，依赖于行动-结果对的体验；以及基于模型的强化学习策略，通过使用对环境不变结构的推理实现更灵活的行为。尽管环境变化需要更灵活的行为，但波动性（一种捕捉环境变化速度或频率的高阶统计量）系统调节这些策略的能力仍不清楚。我们使用两种修改后的两步决策任务，研究了奖励波动性对无模型和基于模型强化学习策略之间仲裁的影响。在实验1中，参与者在不同奖励波动性和时间压力水平下执行任务。在实验2中，我们在更广范围内系统操纵奖励波动性，以评估波动性与学习策略之间的关系。行为数据通过模型无关的单试次和多试次回溯分析、强化学习模拟以及分层贝叶斯模型拟合进行分析。跨实验发现，奖励波动性对无模型和基于模型强化学习策略之间的仲裁呈倒U形非线性效应，即在中等奖励波动性水平下，基于模型的学习策略被强烈驱动。这些调节效应仅在已学会任务中转换结构的个体中观察到，而尚未学会转换结构的个体无论奖励波动性如何，都依赖无模型学习策略。强化学习模拟显示，基于模型学习策略相对于无模型学习策略的相对优势在中等奖励波动性水平达到峰值。此外，时间压力增加使行为转向无模型学习策略。这些结果表明，在不确定和动态环境中，人类即使意识到任务结构，也并非总是使用基于模型的强化学习策略，支持了成本效益优化。

## Abstract
Action selection involves two systems: a model-free reinforcement learning strategy, which relies on experience with action-outcome pairs, and a model-based reinforcement learning strategy, which enables more flexible behavior via inference using a model of the invariant environmental structure. Although environmental change requires more flexible behavior, the ability of volatility, a higher-order statistic that captures how rapidly or frequently the environment changes, to systematically modulate these strategies remains unclear. We examined the effects of reward volatility on arbitration between model-free and model-based reinforcement learning strategies using two modified two-step decision tasks. In Experiment 1, participants performed tasks with different levels of reward volatility and time pressure. In Experiment 2, we systematically manipulated reward volatility across a broader range to assess the relationship between volatility and learning strategy. Behavioral data were analyzed using model-agnostic one-trial and multitrial back analyses, reinforcement learning simulations, and hierarchical Bayesian model fitting. Across experiments, reward volatility exerted an inverse U-shaped nonlinear effect on the arbitration between model-free and model-based reinforcement learning strategies, as the model-based learning strategy was strongly driven at intermediate levels of reward volatility. These modulation effects were observed only in individuals who had learned the transition structure in the task, whereas those who had not learned the transition structure relied on the model-free learning strategy regardless of reward volatility. Reinforcement learning simulations revealed that the relative advantage of the model-based learning strategy over the model-free learning strategy peaked at intermediate levels of reward volatility. Additionally, increased time pressure shifted behavior toward the model-free learning strategy. These results demonstrated that, humans do not always use the model-based reinforcement learning strategy in uncertain and dynamic environments, even when they are aware of the task structure, supporting cost-benefit optimization.
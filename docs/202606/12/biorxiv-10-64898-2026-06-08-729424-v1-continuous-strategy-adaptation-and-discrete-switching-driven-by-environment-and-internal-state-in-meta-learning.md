---
title: Continuous Strategy Adaptation and Discrete Switching Driven by Environment and Internal State in Meta-Learning
title_zh: 元学习中环境和内部状态驱动的连续策略适应与离散切换
authors: "Chen, J., Taira, M., Doya, K."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.729424v1.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 使用时变元参数的强化学习模型分析行为
tldr: 研究环境与内部状态如何驱动元学习中的策略适应。通过多种模型分析小鼠决策行为，发现学习进步促进基于模型的策略和选择坚持性，不确定环境导致探索。元参数动态反映连续策略变化，有限状态模型捕捉离散策略切换，揭示了多时间尺度适应机制。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索大脑如何根据环境和内部状态灵活调节策略，实现元学习中的连续与离散适应。
method: 结合stay-switch概率分析、广义线性混合模型、时变参数强化学习粒子滤波和有限内部状态模型分析小鼠两步决策任务。
result: 学习进展增强模型基策略和坚持性；不确定性引发探索；元参数显示学习加速；离散状态切换存在于最优与次优策略间。
conclusion: 连续元参数动态和离散状态切换共同驱动策略适应，为元学习机制提供新见解。
---

## 摘要
行为策略可响应环境和内部状态而逐渐或突然变化，从而实现灵活适应。这种策略调节是元学习（学习如何学习）能力的核心。以往研究通过假设连续或离散变化的模型与理论分析了时间或条件依赖的策略变化。本文采用四种不同方法分析小鼠在两步决策任务中的行为：停留-切换选择概率分析；基于前序任务事件的选择与反应时间的广义线性混合模型；通过新型多步粒子滤波方法拟合具有时变元参数的强化学习模型；以及拟合基于离散状态转移产生选择与反应时间的有限内态模型。综合停留概率和广义线性混合模型分析表明，学习进展促使向基于模型、基于价值的学习策略转变，伴随选择坚持性增强。更不确定或变化的奖励设置导致随机探索行为。元参数动态显示：随学习进展，学习速度加快，基于模型策略参与度增加，选择随机性增高，选择坚持性发展更快但对最终决策贡献减小。面对不确定或变化的奖励设置时的探索行为，源于更慢的遗忘和更大的基于模型贡献。有限内态模型发现试次级别在最优基于价值学习状态和次优自我重复状态之间切换。元参数动态反映连续策略变化，而状态转移捕捉突然的离散策略切换。在中间时间尺度，当奖励设置变化时，两个过程相互作用：小鼠坚持自我重复状态，导致尝试基于模型策略但适应不完全。

## Abstract
Behavioral strategies can change in response to environmental and internal states, either gradually or abruptly, enabling flexible adaptation. Such strategy regulation is central to meta-learning, the ability to learn to learn. Previous studies analyzed temporal or condition-dependent strategy change using models and theories that assume continuous or discrete changes. Here, we analyze the mice's behavior in a two-step decision task using four different approaches: stay-switch choice probability analysis; generalized linear mixed model (GLMM) of choice and reaction time (RT) given preceding task events; fitting a reinforcement learning (RL) model with time-varying meta-parameter by a novel multiple-step particle filtering method; and fitting a finite internal state (FIS) model that produces choice and RT depending on discrete state transition. Together, the stay probability and GLMM analyses reveal that learning progress encourages a shift toward a model-based, value-based learning strategy, accompanied by elevated choice perseveration. More uncertain reward settings or changes in them lead to random, exploratory behavior. Meta-parameter dynamics show faster learning, greater involvement of a model-based strategy, higher choice stochasticity, and more rapid development of choice perseveration with less contribution to the final decision as learning progresses. Exploratory behavior in the face of uncertain reward settings or changes in those settings is underpinned by slower forgetting and greater model-based contribution. FIS modeling discovered a trial-level switch between an optimal value-based learning state and a suboptimal self-repeating state. Meta-parameter dynamics reflect continuous strategy changes, while state transitions capture abrupt, discrete strategy switches. At an intermediate timescale, when reward settings change, two processes interact: mice persist in a self-repeating state, leading to attempts at model-based strategy with incomplete adaptation.
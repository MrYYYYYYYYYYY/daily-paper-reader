---
title: Co-adaptation of dynamic human-machine interfaces
title_zh: 动态人机界面的共同适应
authors: "Chou, A. H. Y., Yamagami, M., Madduri, M., Chasnov, B. J., Hutchison, F., Peterson, L. N., Burden, S. A."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2023.07.14.549053v2.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 基于优化的协同适应，性能与努力权衡
tldr: 针对动态机器场景下人与智能界面的协同适应问题，现有理论存在局限性。通过人类实验发现人和界面在性能与信号能量之间权衡，并提出一个简约模型来模拟人类适应策略。计算仿真与实验吻合，表明人类旨在最小化误差与努力之和。该工作揭示了协同适应对行为的塑造，并提供建模框架以系统性设计交互结果。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有理论不足以解释动态机器场景下人机协同适应的行为表现与性能权衡。
method: 设计动态界面实验收集人类行为数据，构建基于误差与努力最小化的简约适应模型，并通过仿真验证。
result: 人类与界面在协同适应中表现出性能与信号能量的权衡，仿真结果与实验数据一致。
conclusion: 人类适应策略符合误差与努力的联合最小化，该建模框架可用于指导交互结果设计。
---

## 摘要
尽管学习算法在日常生活中日益普及，但分析和综合这些系统与人类交互的方法仍有限。我们研究了在存在动态机器的情况下与人类共同适应的基于优化的算法，发现当前理论的局限性促使我们进行了一项实验，其中人类受试者通过动态界面与具有复杂动态的机器进行交互。实验结果提供了共同适应的证据，以及性能与人类和界面的“努力”（定义为它们输出信号的范数）之间的权衡。我们开发了一个在我们实验中观察到的人类适应策略的简约模型，并使用该模型进行了仿真研究。我们的计算结果与实验结果相匹配，表明我们的人类受试者适应以最小化误差和努力的组合。这些结果展示了人类与智能界面之间的共同适应如何塑造行为和性能，并引入了一个建模框架，可用于未来的工作以系统设计交互结果。

## Abstract
Despite the growing prevalence of learning algorithms in daily life, methods for analysis and synthesis of how these systems interact with people are limited. We studied optimization-based algorithms that co-adapt with people in the presence of dynamic machines, finding limitations on current theory that motivated us to conduct an experiment where human subjects interact through a dynamic interface with a machine that has complex dynamics. Experimental results provided evidence of co-adaptation and a trade-off between performance and the "effort" of the human and interface, defined as the norm of their output signals. We developed a parsimonious model of the human adaptation strategy observed in our experiments and conducted a simulation study using this model. Our computational results matched the empirical results, suggesting our human subjects adapted to minimize a combination of error and effort. These results demonstrate how co-adaptation between humans and intelligent interfaces shapes behavior and performance, and introduces a modeling framework that can be used in future work to systematically design interaction outcomes.
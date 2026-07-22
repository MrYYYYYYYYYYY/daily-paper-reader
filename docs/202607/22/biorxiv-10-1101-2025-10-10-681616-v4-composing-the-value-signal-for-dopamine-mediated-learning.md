---
title: Composing the value signal for dopamine-mediated learning
title_zh: 构成多巴胺介导学习的价值信号
authors: "Mahajan, P., Seymour, B."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.10.681616v4.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 使用熵正则化强化学习框架组合奖励值
tldr: 传统多巴胺奖励预测误差理论在多奖励学习、效率及纹状体异质性方面面临挑战。本文提出熵正则化强化学习框架，将价值函数与偏离默认行为策略的惩罚相结合。模拟实验表明，该离策略方法能组合多重奖励值，避免目标切换时的干扰，并适应非平稳环境。该统一框架解释了纹状体内外的多巴胺异质性，并预测了厌恶与动作预测误差共存的现象。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1681, \"height\": 934, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1681, \"height\": 1217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1663, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1643, \"height\": 1679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1694, \"height\": 1429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1623, \"height\": 1196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1606, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1671, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-10-681616-v4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1665, \"height\": 879, \"label\": \"Figure\"}]"
motivation: 解决经典多巴胺奖励预测误差理论在多重奖励学习、离策略效率及纹状体反应异质性上的不足。
method: 采用熵正则化强化学习，将奖励价值函数与偏离默认策略的惩罚项相结合，实现可组合的离策略学习。
result: 模拟显示该方法能组合多重奖励，避免干扰和意外遗忘，且在非平稳环境中更高效，并统一解释纹状体多巴胺异质性。
conclusion: 多巴胺介导的学习可能由可组合的熵正则化价值函数预测误差驱动，而非单一广播预测误差。
---

## 摘要
多巴胺的经典奖赏预测误差理论取得了巨大成功，但仍面临若干关键挑战。最显著的问题包括难以同时学习多种奖赏、低效的在策略学习，以及如何解释纹状体目标之间和内部观察到的异质性纹状体反应。在此，我们通过一个规范化的熵正则化强化学习框架来解决这些问题。我们提出，多巴胺优化的不仅是累积奖赏，而是一个由偏离默认行为策略的惩罚所增强的奖赏价值函数。在模拟中，这种离策略公式为组合多种奖赏价值提供了原则性解决方案，避免了多目标在策略方法在优先级变化时出现的干扰和非预期性遗忘，并在具有非平稳奖赏的环境中比标准替代方案更有效地适应。更广泛地说，该框架为纹状体目标之间和内部的异质性多巴胺响应提供了统一解释，包括规范性地理解为何厌恶性预测误差和动作预测误差可能在纹状体尾部共存。这些结果表明，多巴胺介导的学习可能更好地被可组合的、熵正则化的价值函数中的预测误差所捕捉，而非单一广播预测误差，并为未来实验提供了可检验的预测。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWThe seminal reward prediction error account of dopamine has been highly successful, but faces several key challenges. Most notable are the difficulty of learning multiple rewards simultaneously, inefficient on-policy learning, and accounting for the heterogeneous striatal responses observed across and within striatal targets. Here we address these issues with a normative entropy-regularised reinforcement-learning framework. We propose that dopamine optimises not just cumulative rewards, but a reward value function augmented by a penalty for deviating from a default behavioural policy. In simulations, this off-policy formulation provides a principled solution to composing multiple reward values, avoids the interference and unintended unlearning seen in multi-objective on-policy methods when priorities change, and adapts more efficiently than standard alternatives in environments with non-stationary rewards. More broadly, the framework offers a unified account of dopamine heterogeneity between and within striatal targets, including a normative way to understand why aversive and action prediction errors may coexist in the tail of the striatum. Together, these results suggest that dopamine-mediated learning may be better captured by prediction errors in composable, entropy-regularised value functions than by a single broadcast prediction error, and offer testable predictions for future experiments.
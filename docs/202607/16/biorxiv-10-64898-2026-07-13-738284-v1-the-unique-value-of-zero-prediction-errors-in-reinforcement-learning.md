---
title: The unique value of zero prediction errors in reinforcement learning
title_zh: 强化学习中零预测误差的独特价值
authors: "Lloyd, B., Kikumoto, A., Wurm, F., Vives, M.-L."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.13.738284v1.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 研究人类强化学习中的零预测误差，直接为奖励建模提供见解
tldr: 强化学习中预测误差通常驱动学习，但零预测误差（结果与预期完全一致）是否具有独特价值尚不明确。本研究通过操纵试次结果完美匹配被试预测，结合计算建模和脑电实验，发现零预测误差能产生最高即时幸福感，并在行为上诱导一种独特的潜在信念状态，影响后续更新，尤其在高不确定性和高不确定性不耐受个体中更显著。脑电结果揭示了零预测误差诱发独特的P3样神经响应，且其残留神经活动能预测后续更新减弱。这些发现表明完美预测不是中性事件，而是主动塑造情感、行为和神经反馈的信息事件。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738284-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738284-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738284-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1677, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738284-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1664, \"height\": 721, \"label\": \"Figure\"}]"
motivation: 探究零预测误差在强化学习中是否具有独特的心理与计算意义，而非仅仅视为无信息的中性事件。
method: 通过操纵奖励预测任务中的试次结果使其完美匹配被试预测，结合计算建模和EEG记录，分析情感、行为更新及神经响应。
result: 零预测误差产生最高即时幸福感；计算建模显示其诱导独特信念状态，在高不确定性下更显著；EEG中诱发独特P3样响应，残留神经活动预测后续更新减弱。
conclusion: 完美预测不是中性，而是主动塑造情感、行为更新和神经反馈过程的信息事件。
---

## 摘要
学习通常被理解为一种由预测误差驱动的过程，即当结果与预期不同时。然而，完全匹配预期的结果是否具有心理和计算上的意义仍不清楚。在此，我们测试了零预测误差是否影响人类强化学习中的情感、信念更新和神经反馈处理。参与者在不确定性不同的环境中反复预测奖励，其中一部分试验的结果被操纵以完全匹配他们的预测。零预测误差产生了最高的瞬时幸福感，计算建模表明，行为最好由一种模型解释，其中零预测误差诱导一个独特的潜在信念状态，指导后续更新，尤其是在更高不确定性和对不确定性更不容忍的个体中。事件锁定脑电图分析进一步显示，零预测误差引发了独特的P3样反应，残余神经活动预测了零预测误差后更新的减弱，但标准预测误差后更新的增强。这些发现表明，完美预测并非中性，而是主动塑造情感、行为和神经反馈处理的信息性事件。

## Abstract
Learning is typically understood as a process driven by prediction errors, when outcomes differ from expectations. Yet it remains unclear whether outcomes that perfectly match expectations are psychologically and computationally meaningful. Here, we tested whether zero prediction errors shape affect, belief updating, and neural feedback processing in human reinforcement learning. Participants repeatedly predicted rewards in environments varying in uncertainty, with a subset of trial outcomes manipulated to exactly match their predictions. Zero prediction errors produced the highest momentary happiness, and computational modeling showed that behavior was best explained by a model in which zero prediction errors induce a distinct latent belief state that guides subsequent updating, particularly under higher uncertainty and in individuals with greater intolerance of uncertainty. Outcome-locked EEG analyses further showed that zero prediction errors elicited distinct P3-like responses, with residual neural activity predicting attenuated updating after zero prediction errors but enhanced updating after standard prediction errors. These findings suggest that perfect predictions are not neutral, but informative events that actively shape affect, behavior, and neural feedback processing.
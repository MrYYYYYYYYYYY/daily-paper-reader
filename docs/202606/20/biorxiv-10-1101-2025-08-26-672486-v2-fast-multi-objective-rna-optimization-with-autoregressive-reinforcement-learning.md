---
title: Fast Multi-objective RNA Optimization with Autoregressive Reinforcement Learning
title_zh: 基于自回归强化学习的快速多目标RNA优化
authors: "Huang, J., Feng, N., Bai, H., Fang, Y., Liu, X., Wang, S., Yan, J., Shen, H.-B., Qiu, Z., Yuan, Y., Hu, R., Pan, X."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.26.672486v2.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 强化学习应用于RNA优化
tldr: 针对传统密码子优化工具在mRNA疫苗设计中计算效率低、序列多样性差和通用性不足的问题，提出RNAJog框架，结合自回归生成与强化学习，无需标注数据即可同时优化最小自由能、密码子适应指数和GC含量。在长RNA序列上比传统算法LinearDesign快两个数量级；流感病毒HA mRNA疫苗设计中，小鼠抗体滴度比野生型提升约10倍；且支持生物学约束如最小化m6A修饰基序。该工作显著提升了mRNA疫苗设计的效率和效果。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有密码子优化工具在mRNA疫苗设计中面临计算效率低、序列多样性差和通用性不足的挑战。
method: 开发RNAJog框架，采用自回归生成与强化学习联合优化MFE、CAI和GC含量，无需标注训练数据，并支持生物学约束。
result: 长RNA序列优化速度比LinearDesign快两个数量级；流感疫苗设计中小鼠抗体滴度提升约10倍；细胞实验验证最小化m6A基序增强翻译效率和RNA稳定性。
conclusion: RNAJog提供了一种高效、多样且通用的多目标RNA优化方法，加速mRNA疫苗和RNA治疗药物开发。
---

## 摘要
密码子优化在mRNA疫苗开发中至关重要，而现有工具在计算效率、序列多样性和通用性方面存在局限性。为解决这些挑战，我们开发了RNAJog（基于自回归生成模型的RNA联合优化），该框架将自回归生成与强化学习相结合，以优化密码子序列的最小自由能（MFE）、密码子适应指数（CAI）和GC含量，甚至能够在无需注释训练数据的情况下进行序列设计。在计算机模拟和湿实验中的评估均证实了RNAJog的有效性和效率，对于长RNA序列，其速度比传统算法（LinearDesign）快两个数量级，在针对流感病毒血凝素（HA）mRNA疫苗设计的小鼠实验中，抗体滴度比野生型mRNA提高约10倍。RNAJog还支持序列优化的生物学约束。利用这一特性，我们在Bmp2编码序列中最小化了m6A修饰基序，以提高翻译效率和RNA稳定性，并在基于细胞的实验中得到了验证。

## Abstract
Codon optimization is essential in mRNA vaccine development, while existing tools face limitations in the computational efficiency, sequence diversity and universality. To address these challenges, we develop RNAJog (RNA Joint Optimization with autoregressive Generative model), a framework integrating autoregressive generation with reinforcement learning to optimize codon sequences for minimum free energy (MFE), codon adaptation index (CAI) and GC content, even enabling sequence design without requiring annotated training data. Evaluations in both in silico and wet-lab experiments have confirmed RNAJog's effectiveness and efficiency, with two orders of magnitude faster than traditional algorithm (LinearDesign) for long RNA sequence and about a 10-fold increase in antibody titer compared to the wild-type mRNA for Influenza virus hemagglutinin (HA) mRNA vaccine design in mouse. RNAJog also supports biological constraints for sequence optimization. Using this feature, we minimized m6A modification motifs in Bmp2 coding sequence for enhancing the translational efficiency and RNA stability, which are validated in cell-based experiments.
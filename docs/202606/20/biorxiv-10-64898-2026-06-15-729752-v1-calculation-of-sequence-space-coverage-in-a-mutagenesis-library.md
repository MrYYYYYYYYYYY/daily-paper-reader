---
title: Calculation of sequence space coverage in a mutagenesis library
title_zh: 诱变库中序列空间覆盖度的计算
authors: "Florez Prada, A., Uguzzoni, G., Hart, D. J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.729752v1.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 提出具有精确数学公式的可扩展算法框架计算发现概率
tldr: 在定向进化文库筛选中，准确计算所需文库大小是一大难题，现有计算方法随序列复杂度扩展性差。本文提出可扩展算法框架，通过将变体聚合为组合对数求和分布，并在随机化块上应用对数空间卷积，无需显式序列枚举即可精确计算饱和诱变文库的发现概率。该框架还可逆向推导实验设计的绝对数学上限，为权衡统计覆盖与多样性提供定量工具。最终实现为开源Web应用SSCC，支持异质文库设计并计算采样深度、覆盖概率等关键指标。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型低估文库复杂度，计算方法扩展性差，亟需精确且可扩展的工具用于计算诱变文库序列空间覆盖。
method: 提出算法框架，通过变体聚合为组合对数求和分布，结合对数空间卷积跨随机化块计算，避免显式枚举。
result: 无需枚举即可精确计算发现概率，并反向推导实验设计的绝对数学上限，支持混合密码子方案。
conclusion: 该框架作为开源Web应用SSCC，可平衡统计覆盖与多样性，辅助高效文库设计与筛选。
---

## 摘要
定向进化需要筛选大型诱变库，但准确计算发现功能变异所需库大小仍具挑战性。现有模型提供基线估计，但当前寻找最佳变体的计算方法随库复杂度扩展性差。在此，我们引入一种可扩展的算法框架，用于计算饱和诱变库中的精确发现概率，无需显式序列枚举。通过将变体聚合成组成对数求和分布，并在随机化模块间应用对数空间卷积，可将此方法扩展至大规模序列空间和混合密码子方案。通过逆向计算，为实验设计建立了绝对数学上限。最终，该框架提供了一个快速、定量的工具，以在实验室筛选的限制内平衡统计覆盖度-多样性权衡。最后，我们将其实现为一个开源Web应用程序（SSCC），使研究人员能够构建异质库设计并计算所需采样深度、覆盖概率和绝对随机化限制。

## Abstract
Directed evolution requires screening of large mutagenesis libraries, but accurate calculation of library sizes needed to discover functional variants remains challenging. Existing models provide baseline estimates, yet current computational approaches for finding the best variants scale poorly with library complexity. Here, we introduce a scalable algorithmic framework to compute exact discovery probabilities in saturation mutagenesis libraries with no requirement for explicit sequence enumeration. By aggregating variants into a composition log-sum distribution and applying log-space convolution across randomisation blocks, it is possible to extend this to massive sequence spaces and mixed codon schemes.

By inverting these calculations, absolute mathematical ceilings for experimental design are established. Ultimately, this framework provides a rapid, quantitative tool to balance the statistical coverage-diversity trade-off within the limitations of laboratory screening.

Finally, this is implemented as an open-source web application (SSCC) that allows researchers to construct heterogeneous library designs and compute required sampling depths, coverage probabilities, and absolute randomisation limits.
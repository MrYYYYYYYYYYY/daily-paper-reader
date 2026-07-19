---
title: "PathoBench: an open community-driven benchmark registry for pathogen bioinformatics tools"
title_zh: PathoBench：一个开放的社区驱动的病原体生物信息学工具基准注册库
authors: "Dong, Y., Li, N., Chiribau, C. B., Mitchell, M., Liu, X., Perkins, A."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739016v1.full.pdf"
tags: ["query:lpt"]
score: 6.0
evidence: 病原体工具开放基准注册平台
tldr: 病原体生物信息学工具和流程数量快速增长，但社区缺乏标准化的比较基准，自我报告性能、临时数据集和不一致指标导致研究者难以选择合适的工具。PathoBench开放平台通过三个协同机制解决这一问题：收录10种病原体的26个标准基准数据集、要求提交者报告统一的病原体特异性评估指标、以及构建包含数据集认证、ORCID归属、公开评论和管理员验证的可信度框架。案例研究中，该平台成功区分了四个已发表的结核分枝杆菌耐药性流程的性能差异。PathoBench对所有病原体开放社区贡献，旨在推动病原体生物信息学工具评估的规范化和标准化。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 551, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1661, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 630, \"height\": 142, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1708, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1714, \"height\": 1622, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 627, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 629, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 628, \"height\": 194, \"label\": \"Table\"}]"
motivation: 现有病原体生物信息学工具性能评估缺乏统一标准，自我报告结果不一致，导致临床和公共卫生研究人员难以进行公平比较和选择。
method: PathoBench通过三项机制实现：提供10种病原体的26个标准基准数据集、强制要求报告病原体特异性评估指标、以及构建包含数据集认证、归属和同行评议的可信度框架。
result: 对四个已发表的结核分枝杆菌耐药性流程进行对比评估，验证了该框架区分不同工具性能的有效性。
conclusion: PathoBench作为开放社区驱动的基准注册平台，促进病原体生物信息学工具评估的标准化，具有重要实用价值。
---

## 摘要
病原体生物信息学流程的激增已超出了社区在共同基础上进行比较的能力。自我报告的性能数据、临时评估数据集以及不一致的指标使得临床和公共卫生研究人员难以选择流程。我们提出了PathoBench，一个开放的Web平台，通过三个协调机制解决了这一差距：（i）一个包含26个标准基准数据集的精选注册库，涵盖10种人类病原体，每个数据集都有持久标识符和直接下载链接；（ii）病原体特异性评估指标，提交者必须报告这些指标，允许在同一数据集上进行直接头对头比较；以及（iii）一个可信度框架，结合了强制性的数据集认证、ORCID关联署名、公开同行评论和管理员验证。作为案例研究，四个已发表的结核分枝杆菌耐药性流程根据WHO结核突变目录进行了评估，展示了该框架的区分能力。PathoBench对所有十种支持病原体的社区贡献开放。

## Abstract
The proliferation of pathogen bioinformatics pipelines has outpaced the community ability to compare them on common ground. Self-reported performance numbers, ad-hoc evaluation datasets, and inconsistent metrics make pipeline selection difficult for clinical and public-health researchers. We present PathoBench, an open web platform that addresses this gap through three coordinated mechanisms: (i) a curated registry of 26 standard benchmark datasets across 10 human pathogens, each with persistent identifiers and direct download links; (ii) pathogen-specific evaluation metrics that submissions must report, allowing direct head-to-head comparison only on the same dataset; and (iii) a credibility framework combining mandatory dataset attestation, ORCID-linked attribution, public peer comments, and administrator verification. As a case study, four published Mycobacterium tuberculosis drug-resistance pipelines were evaluated against the WHO TB mutation catalogue, demonstrating the framework discriminating power. PathoBench is open for community contributions across all ten supported pathogens.
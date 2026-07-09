---
title: "Structured Schemas for Provenance-Rich, LLM-Assisted QSP Model Calibration"
title_zh: 用于富含来源、LLM辅助的QSP模型校准的结构化模式
authors: "Eliason, J., Popel, A. S."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.05.709623v2.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 提出结构化验证模式捕捉LLM在文献提取中的幻觉
tldr: QSP模型校准需从文献提取数据，但手动整理不一致，LLM提取可能产生幻觉。MAPLE框架使用结构化验证模式，分离数据提取与建模决策，记录每个值的来源和引文。在胰腺癌模型中提取82个目标，验证器触发50次自动重试，11/19参数有多个独立来源。该框架以可复现形式记录建模者推理，防止团队更替时信息丢失。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-05-709623-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1664, \"height\": 1080, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-05-709623-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1211, \"height\": 1067, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-05-709623-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 597, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-05-709623-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1018, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-05-709623-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1140, \"height\": 335, \"label\": \"Table\"}]"
motivation: 解决QSP模型校准中手动整理不一致和LLM提取幻觉问题，需要结构化协作接口来记录完整来源和建模决策。
method: 提出MAPLE，包含SubmodelTarget和CalibrationTarget两种结构化模式，结合验证器自动匹配源片段、解析DOI并触发重试。
result: 在胰腺癌QSP模型中提取37个SubmodelTargets和45个CalibrationTargets，50次自动重试后所有值均有直接引文，11/19参数有多来源支持。
conclusion: MAPLE以可复现、可独立检查的形式记录建模者推理，确保建模决策不因团队更替而丢失。
---

## 摘要
定量系统药理学（QSP）模型需要从文献中获取校准数据，但手动整理记录不一致，且大型语言模型（LLM）提取可能出现数值幻觉和虚假引用。我们提出了MAPLE（基于文献证据的模型感知参数化），它使用结构化验证模式作为LLM与建模者之间的协作界面。两种模式涵盖两个尺度：SubmodelTarget模式用于约束单个参数的孤立实验，CalibrationTarget模式用于约束完整模型的临床和体内终点。两者都将数据提取与建模决策分离，记录每个值及其完整来源。针对性的验证器通过将值与源片段匹配、解析DOI和执行代码来捕捉典型的LLM错误。对于胰腺导管腺癌QSP模型，我们使用MAPLE提取并整理了37个SubmodelTarget和45个CalibrationTarget。在任何人工审查之前，验证器触发了50次自动重试；每个值都带有来源的直接引用和经过验证的引用；19个参数中有11个得到多个独立来源的支持。LLM根据上下文起草了可用的前向模型和代码，而建模者提供了其无法推断的上下文和科学判断，在65%的SubmodelTarget中修正了前向模型选择，46%中修正了先验，所有文件中修正了来源相关性。该评估由一个团队覆盖一个疾病领域的一个模型，因此它描述了框架的特征，而非确立其泛化广度。MAPLE以可重新运行和独立检查的形式记录建模者的推理，因此当建模团队变更时，这些信息不会丢失。

## Abstract
Quantitative systems pharmacology (QSP) models require calibration data from literature, yet manual curation is inconsistently documented and large language model (LLM) extraction can hallucinate values and fabricate citations. We present MAPLE (Model-Aware Parameterization from Literature Evidence), which uses structured validation schemas as a collaboration interface between LLMs and modelers. Two schemas span two scales: the SubmodelTarget schema for isolated experiments constraining individual parameters, and the CalibrationTarget schema for clinical and in vivo endpoints constraining the full model. Both separate data extraction from modeling decisions, recording every value with full provenance. Targeted validators catch characteristic LLM errors by matching values to source snippets, resolving DOIs, and executing code. For a pancreatic ductal adenocarcinoma QSP model, we used MAPLE to extract and curate 37 SubmodelTargets and 45 CalibrationTargets. Before any human review, the validators triggered 50 automated retries; every value carries a direct quote from its source and a verified citation; and 11 of 19 parameters are supported by more than one independent source.The LLM drafted usable forward models and code from context, while the modeler supplied the context and scientific judgment it cannot infer, revising forward-model choices in 65% of SubmodelTargets, priors in 46%, and source relevance in all files. This evaluation covers one model in one disease area, by a single group, so it characterizes the framework rather than establishing how broadly it generalizes. MAPLE records the modelers reasoning in a form that can be re-run and independently checked, so it is not lost when the modeling team changes.
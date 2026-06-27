---
title: Agentic AI for Structural Elucidation and Discovery of Drug Metabolites from Mass Spectrometry Data
title_zh: 用于从质谱数据中进行结构解析和药物代谢物发现的智能体AI
authors: "Wang, X., Patan, A., Zhao, H. N., Charron-Lamoureux, V., Shin, Y., Petras, D., Hong, Y., Bowen, B. P., Northen, T. R., Dorrestein, P. C., Wang, M."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734138v1.full.pdf"
tags: ["query:lpt"]
score: 9.0
evidence: 通过领域工具约束LLM幻觉进行药物代谢物发现
tldr: 公共代谢组学数据中大量化学信号未被鉴定。本文利用大语言模型的生成能力，结合谱图比对、分子式推断、规则结构枚举和机器学习谱图预测，构建了GNPS2智能体系统，自动生成可验证的结构假说。系统成功从公共数据中发现了磷酸化羟嗪、对乙酰氨基酚-对香豆酸酯等新代谢物，并经实验确认。该方法展示了LLM驱动推理与领域专业知识结合在未知代谢物发现中的巨大潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 大多数代谢组学数据中的化学信号结构未知，需利用LLM生成能力产生假设并约束幻觉。
method: 构建GNPS2智能体系统，整合LC-MS/MS谱图比对、分子式推断、规则枚举、ML谱图预测及专家自然语言假设。
result: 发现并实验确认了磷酸化羟嗪、对乙酰氨基酚-对香豆酸酯及两种新氧化布洛芬-肉碱缀合物。
conclusion: LLM驱动推理与领域工具结合能有效产生可验证的未知代谢物结构假说。
---

## 摘要
公共代谢组学数据库中检测到的大多数化学信号仍未在结构上得到定义。大型语言模型（LLM）是概率系统，其生成超出训练数据的能力（可能导致幻觉）也使其可能适用于假设从未被描述过的分子结构。我们旨在构建一个系统，能够利用LLM的生成能力，结合领域特定的工具/框架，以约束幻觉并产生经过验证的发现。我们开发了一个GNPS2智能体AI系统，通过集成光谱比对、分子式推断、基于规则的结构枚举、基于机器学习的谱图预测，并将领域专家的自然语言假设转化为动态生成的分析工作流，来解读LC-MS/MS数据。我们展示了基于化学假设从公共数据中注释未知药物代谢物的过程。该智能体预测了磷酸化的羟嗪、对乙酰氨基酚-对香豆酸酯，并且我们在实验中确认了这些物质，同时从公共数据库中识别出了两种新的氧化布洛芬-肉碱结合物。这些结果表明，当将LLM驱动的智能体推理与领域专业知识相结合时，确实可以利用整个仓库的数据为先前未表征的代谢物生成可实验验证的结构假设。

## Abstract
The majority of chemical signals detected in public metabolomics repositories remain structurally undefined. Large language models (LLMs) are probabilistic systems whose capacity to generate outputs beyond their training data, which can cause hallucinations, makes them also potentially suited to hypothesize structures for molecules that have never been described. We aimed to build a system that could harness this LLM generative capacity combined with domain specific tools/framework to constrain hallucination and produce validated discoveries. We developed a GNPS2 agentic AI system that interprets LC-MS/MS data by integrating spectral alignment, molecular formula inference, rule-based structural enumeration, machine learning-based spectrum prediction, and translates natural language hypotheses from domain experts into dynamically generated analytical workflows. We demonstrate the annotation of unknown drug metabolites from public data guided by chemical hypotheses. The agent predicted, and we experimentally confirmed, a phosphorylated hydroxyzine, an acetaminophen-p-coumaric acid ester, and identified two new oxidative ibuprofen-carnitine conjugates from public repositories. These results demonstrate that LLM-driven agentic reasoning, when combined with domain expertise, can indeed generate experimentally testable structural hypotheses for previously uncharacterized metabolites leveraging pan repository data.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：公共代谢组学数据库中检测到的大量化学信号（LC-MS/MS 谱图）仍未被结构定义，存在大量“未知代谢物”。传统注释方法依赖数据库匹配，无法发现全新分子结构。
- **研究动机**：大型语言模型（LLM）具有生成超出训练数据内容的能力（即“幻觉”能力），这恰好可用于假设从未被描述过的分子结构。但直接使用 LLM 会产生不可靠的假说，需要结合领域专业知识来约束幻觉。
- **整体含义**：构建一个将 LLM 驱动推理与领域特定工具（谱图比对、分子式推断、规则结构枚举、机器学习谱图预测）集成的智能体系统，能够自动生成可实验验证的结构假说，从而从公共数据中发现新的药物代谢物。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用 LLM 的生成能力提出结构假说，同时通过一系列领域工具（约束）对幻觉进行校验和修正，最终输出可信的结构注释。
- **系统名称**：GNPS2 智能体 AI 系统。
- **关键技术细节**（工作流）：
  1. **光谱比对**：将 LC-MS/MS 谱图与公共数据库（如 GNPS）进行比对，获取候选相似谱。
  2. **分子式推断**：基于精确质量和同位素模式推断可能的分子式。
  3. **基于规则的结构枚举**：根据药物结构、已知代谢规则（如氧化、葡萄糖醛酸化、磷酸化等）枚举可能的结构变体。
  4. **基于机器学习的谱图预测**：使用 ML 模型（如 SIRIUS、MS²PIP 等）预测候选结构的理论碎片谱，与实验谱图匹配验证。
  5. **专家自然语言假设转化为动态工作流**：领域专家可以用自然语言描述化学假设（如“该代谢物可能是羟嗪的磷酸化产物”），系统自动将其转化为可执行的分析流程，结合上述工具进行验证。
- **流程示例**：输入未知谱图 → 智能体推理 → 提出假设结构 → 工具验证 → 输出可测试的结构假说。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：来源于公共代谢组学仓库（如 GNPS/MassIVE）中的 LC-MS/MS 数据，具体针对药物代谢物场景。
- **场景**：
  - 发现三种新代谢物：磷酸化羟嗪、对乙酰氨基酚-对香豆酸酯、两种新的氧化布洛芬-肉碱缀合物。
- **Benchmark**：未明确提及标准 benchmark 数据集。验证方式为实验合成/纯化后再次分析确认（实验确认）。
- **对比方法**：未公开与其他方法（如传统数据库搜索、从头测序、其他机器学习方法）进行系统比较。论文主要展示系统能力，而非在标准数据集上进行定量对比。

## 4. 资源与算力

- **文中未明确说明**：未提及 GPU 型号、数量、训练时长等算力资源。系统可能依赖 LLM API 和本地工具（如 GNPS 云平台），但具体硬件需求未知。

## 5. 实验数量与充分性

- **实验数量**：仅展示了 4 个具体案例（磷酸化羟嗪、对乙酰氨基酚-对香豆酸酯、两种布洛芬-肉碱缀合物），每个案例均经过实验确认。
- **充分性评价**：
  - **不足**：实验规模较小，仅针对药物代谢物这一特定子类，未在其他代谢物类型（如植物代谢物、微生物代谢物）上评估。缺乏大规模筛选实验或消融研究（如分析不同工具对结果准确性的贡献）。
  - **客观性**：实验确认采用合成标准品，结果可靠。但未采用交叉验证、盲测或与现有数据库注释的召回率对比，公平性有限。

## 6. 论文的主要结论与发现

- LLM 驱动的智能体推理与领域专业知识结合，能够生成可实验验证的新代谢物结构假说。
- 成功从公共数据中发现并实验确认了三种先前未表征的药物代谢物：
  - 磷酸化羟嗪（一种抗组胺药的新型代谢物）
  - 对乙酰氨基酚-对香豆酸酯（对乙酰氨基酚的共轭产物）
  - 两种氧化布洛芬-肉碱结合物
- 证明了利用全球公共仓库中的聚合数据（pan-repository data），配合智能体系统，可以系统地发现未知代谢物。

## 7. 优点

- **创新范式**：将 LLM 的生成能力（常被视为缺点“幻觉”）转化为优势，用于假设全新结构，并通过领域工具约束使其可信。
- **自动化程度高**：专家仅需提供自然语言假设，系统自动转化为分析工作流，降低了使用门槛。
- **可验证性**：输出结构假说可实验验证，避免了纯计算预测的不可靠性。
- **开放数据利用**：充分利用公共代谢组学数据仓库，具有大规模应用潜力。

## 8. 不足与局限

- **实验覆盖有限**：仅针对少数药物代谢物，未在更广泛的代谢物类别（如内源性代谢物、环境污染物）上验证泛化能力。
- **缺乏系统性评估**：未报告在标准数据集上的准确性、召回率、错误发现率等量化指标，也未与现有工具（如 SIRIUS、ISDB、MetFrag）进行定量对比。
- **依赖专家假设**：启动过程需要领域专家提供自然语言假设，若专家假设错误，可能导致错误导向。系统本身不具备自主发现完全未知结构类别的能力。
- **幻觉风险未完全消除**：尽管有约束，但 LLM 仍可能提出假阳性结构，且实验验证成本较高，无法大规模应用。
- **算力资源未说明**：缺乏对计算成本的讨论，可能限制可重复性。
- **对比方法缺失**：没有消融实验分析每个组件（如谱图预测、规则枚举）对最终结果的具体贡献。

（完）

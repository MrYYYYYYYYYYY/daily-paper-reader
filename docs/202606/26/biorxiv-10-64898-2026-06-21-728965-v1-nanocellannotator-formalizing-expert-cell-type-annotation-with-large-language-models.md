---
title: "NanoCellAnnotator: Formalizing Expert Cell Type Annotation with Large Language Models"
title_zh: NanoCellAnnotator：利用大型语言模型规范化专家细胞类型注释
authors: "Mahmud, M. I., Kochat, V., Anzum, H., Satpati, S., Dwarampudi, J. M. R., Rai, K., Banerjee, T."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.21.728965v1.full.pdf"
tags: ["query:lpt"]
score: 9.0
evidence: 在大语言模型注释中抑制幻觉细胞类型
tldr: 空间转录组学细胞注释面临稀疏基因面板、空间异质性和参考图谱缺失等挑战。NanoCellAnnotator通过混合空间正则化非负矩阵分解识别聚类，结合基因本体富集和GO-slim投影构建生物学证据，再利用轻量级大语言模型在限定标签空间中进行约束推断。在胆管癌和乳腺癌Xenium数据上，该方法高置信度恢复经典细胞类型，并明确标记异质性或过渡区域。框架将专家知识形式化，兼顾生物合理性、置信度评估和隐私友好部署。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有大语言模型在细胞注释中可能产生生物不支持预测或幻觉，且依赖云端模型限制可重复性和隐私。
method: 提出NanoCellAnnotator，解耦空间聚类、标记基因到本体功能程序的映射、以及基于轻量语言模型的约束标签选择，并独立评估置信度。
result: 在胆管癌和乳腺癌空间转录组数据中，该方法以高准确性和调整兰德指数恢复典型细胞群，并成功识别异质性区域。
conclusion: NanoCellAnnotator实现了生物约束与语言模型推理的融合，为空间转录组学提供可信且可部署的自动注释。
---

## 摘要
动机：空间转录组学中的细胞类型注释面临挑战，原因包括稀疏基因面板、空间异质性以及组织匹配参考图谱的有限可用性。最近的方法探索了使用大型语言模型（LLM）在注释过程中整合生物学知识，但无约束的推理可能产生生物学上无支持的预测和幻觉细胞类型。此外，许多基于LLM的流程依赖于大型云托管模型，这限制了在隐私敏感环境中的可重复性和部署。结果：我们引入了NanoCellAnnotator，这是一个生物约束且具有置信度感知的框架，用于空间转录组学中的自动化细胞类型注释。该框架解耦了空间结构发现、确定性生物学证据构建和基于语言模型的语义推断。使用混合空间正则化非负矩阵分解（hSNMF）识别空间聚类，之后通过基因本体论富集和GO-slim投影将聚类级别的标记基因抽象为源自本体的功能程序。一个轻量级的本地可执行语言模型在从PanglaoDB和CellMarker衍生的精心策划的可允许标签空间内执行约束标签选择。使用标记支持强度和谱系分离独立估计注释置信度，从而能够明确标记模糊或异质性的聚类。我们在肝内胆管癌的Xenium空间转录组学数据和独立的乳腺癌空间转录组学数据集上评估了NanoCellAnnotator。该框架以高置信度恢复典型细胞群体，同时将异质性或过渡性空间域识别为模糊。使用准确性和调整后的Rand指数评估与手动注释的一致性。可用性：代码可在https://github.com/ishtyaqmahmud/NanoCellAnnotator获取。

## Abstract
Motivation: Cell-type annotation in spatial transcriptomics is challenging due to sparse gene panels, spatial heterogeneity, and limited availability of tissue-matched reference atlases. Recent approaches have explored large language models (LLMs) for integrating biological knowledge during annotation, but unconstrained inference can produce biologically unsupported predictions and hallucinated cell types. In addition, many LLM-based pipelines rely on large cloud-hosted models that limit reproducibility and deployment in privacy-sensitive environments. Results: We introduce NanoCellAnnotator, a biologically constrained and confidence-aware framework for automated cell-type annotation in spatial transcriptomics. The framework de-couples spatial structure discovery, deterministic biological evidence construction, and language model-based semantic inference. Spatial clusters are identified using hybrid spatially regularized non-negative matrix factorization (hSNMF), after which cluster-level marker genes are abstracted into ontology-derived functional programs using Gene Ontology enrichment and GO-slim projection. A lightweight locally executable language model performs constrained label selection within a curated admissible label space derived from PanglaoDB and CellMarker. Annotation confidence is estimated independently using marker support strength and lineage separation, enabling ambiguous or heterogeneous clusters to be explicitly flagged. We evaluate NanoCellAnnotator on Xenium spatial transcriptomics data from intrahepatic cholangiocarci-noma and an independent breast cancer spatial transcriptomics dataset. The framework recovers canonical cell populations with high confidence while identifying heterogeneous or transitional spatial domains as ambiguous. Agreement with manual annotations was evaluated using accuracy and adjusted Rand index. Availability: Code available at https://github.com/ishtyaqmahmud/NanoCellAnnotator.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：空间转录组学中的细胞类型注释面临三大挑战：① 基因面板稀疏，② 空间异质性导致细胞状态多样，③ 缺乏与组织匹配的完整参考图谱。虽然已有工作尝试利用大型语言模型（LLM）整合生物学知识进行注释，但**无约束的推理**可能产生生物学不支持的预测甚至“幻觉”细胞类型（即生成真实组织中不存在的类型）。此外，现有基于LLM的流程多依赖云端大模型，在隐私敏感环境中难以重复和部署。
- **研究动机**：设计一种**生物约束、置信度感知**的自动化注释框架，将专家知识形式化，同时避免幻觉，并支持本地轻量部署。
- **整体含义**：提出NanoCellAnnotator，通过解耦空间聚类、生物学证据构建和基于轻量LLM的语义推断，在限定标签空间内实现可靠、可解释的细胞类型注释。

## 2. 论文提出的方法论

- **核心思想**：将注释过程分解为三个独立模块，每个模块使用确定性或强约束方法，最后通过轻量LLM进行受限推理，从而抑制幻觉并提升生物学合理性。
- **关键技术细节**：
  1. **空间聚类**：采用**混合空间正则化非负矩阵分解（hSNMF）** 识别空间聚类（即空间域），融合空间坐标信息和基因表达模式。
  2. **生物学证据构建**：对每个聚类，提取标记基因，进行**基因本体（GO）富集分析**，并通过**GO-slim投影**将基因集抽象为高层级的功能程序（ontology-derived functional programs），获得生物学语义。
  3. **约束标签选择**：从PanglaoDB和CellMarker等权威数据库中构建一个**可允许的标签空间**（curated admissible label space）；使用一个**轻量级本地可执行语言模型**（如小型模型，可在本地CPU/GPU运行）在该受限空间内进行标签匹配，避免生成不在列表中的幻觉类型。
  4. **置信度评估**：独立估计两个指标——**标记支持强度**（marker support strength）和**谱系分离**（lineage separation），并据此将聚类标记为**高置信度、低置信度或模糊**（heterogeneous/transitional regions）。
- **算法流程**：输入空间转录组数据 → hSNMF聚类 → 标记基因提取 → GO富集和GO-slim映射 → 轻量LLM在可允许标签空间中选择标签 → 输出注释及置信度。

## 3. 实验设计

- **数据集**：
  - **肝内胆管癌（ICC）** 的Xenium空间转录组数据（主数据集）。
  - **独立乳腺癌（breast cancer）** 空间转录组数据集（验证泛化性）。
- **评估指标**：与手动注释的一致性，使用**准确率（accuracy）** 和**调整后的Rand指数（Adjusted Rand Index, ARI）**。
- **对比方法**：文中未明确列出与其他方法的定量对比。仅呈现NanoCellAnnotator本身的注释结果（如高置信度恢复典型细胞群，识别异质性区域为模糊）。缺乏与Seurat、CellTypist、scArches、或其它LLM-based注释方法的直接比较。

## 4. 资源与算力

- **文中未明确说明**使用了何种GPU型号、数量、训练时长等具体算力信息。仅提及“轻量级本地可执行语言模型”，暗示模型较小，可以在消费级GPU或CPU上运行，但无量化数据。需要指出：论文未提供算力细节。

## 5. 实验数量与充分性

- **实验数量**：两个不同组织类型（胆管癌、乳腺癌）的数据集。未提及消融实验、不同聚类数影响、置信度阈值敏感性分析等。未在多个公开基准数据集（如MERFISH、Slide-seq等）上测试。
- **充分性与客观性**：
  - **充分性一般**：数据集覆盖一种癌症的两种场景，代表性有限；缺乏与现有方法的公平比较（如控制相同数据集和指标）。
  - **客观性**：使用标准指标（ARI、准确率），但未对比其他方法，难以判断相对优势。置信度评估依赖于自主定义的指标，缺乏外部验证。

## 6. 论文的主要结论与发现

- NanoCellAnnotator**以高置信度恢复了胆管癌和乳腺癌中的典型细胞群体**（如上皮细胞、免疫细胞、成纤维细胞等）。
- 能够**明确识别异质性或过渡性空间域**，并将其标记为“模糊”（ambiguous），避免了强制分配虚假标签。
- 与手动注释的一致性良好（在摘要中报告了高准确率和ARI，但未给出具体数值）。
- 该方法将**专家知识形式化**为生物约束+轻量LLM推断，兼顾了生物合理性、隐私友好和可重复性。

## 7. 优点

- **生物约束设计**：通过GO-slim功能程序和受限标签空间，有效抑制LLM的幻觉，提高注释的可信度。
- **置信度感知**：独立评估的支持强度和谱系分离允许用户明确区分高置信区域和模糊区域，避免过度解释。
- **本地轻量部署**：使用轻量LLM而非云端大模型，保护数据隐私，便于在资源有限的环境中复制。
- **模块化解耦**：聚类、证据构建、语言推理相互独立，便于替换或升级各模块。
- **代码开源**：提供GitHub仓库，促进可重复性和社区扩展。

## 8. 不足与局限

- **实验覆盖不足**：仅测试了两个数据集（同一组织来源？均为癌症数据），缺乏在正常组织、更多物种、不同技术平台（如MERFISH、Seq-FISH）上的验证。
- **缺乏对比基准**：未与现有主流注释方法（如基于参考图谱的scArches、基于标记的CellTypist/Seurat、以及基于LLM的GenePT等）进行系统性比较，难以评估其相对性能。
- **消融实验缺失**：没有分析各模块（如GO-slim投影、标签空间限制、置信度指标）的贡献，无法确认设计决策的必要性。
- **依赖先验知识库**：可允许标签空间依赖于PanglaoDB和CellMarker，可能遗漏新发现的细胞类型或亚型，对罕见细胞注释存在盲区。
- **置信度阈值主观**：未说明如何设定“高置信度”和“模糊”的阈值，可能影响不同数据的可比性。
- **局限性声明**：未讨论在强噪声、低分辨率、或细胞类型高度混合场景下的鲁棒性。

（完）

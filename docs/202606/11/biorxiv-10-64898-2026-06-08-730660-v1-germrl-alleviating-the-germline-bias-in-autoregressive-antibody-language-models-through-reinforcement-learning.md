---
title: "GermRL: Alleviating The Germline Bias In Autoregressive Antibody Language Models Through Reinforcement Learning"
title_zh: GermRL：通过强化学习缓解自回归抗体语言模型中的种系偏差
authors: "Ludwig, L., Chungyoun, M., Gray, J. J."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730660v1.full.pdf"
tags: ["query:lpt"]
score: 9.0
evidence: 强化学习应用于抗体语言模型后训练
tldr: 抗体语言模型存在胚系偏置，限制了生成序列的多样性。GermRL通过组相对策略优化强化学习框架，有效缓解了自回归模型中的这一偏置。在5和35个突变阈值下，单次生成成功率分别达到0.992和0.950，远高于基线模型。生成的抗体保持结构合理性和发育特性，能探索替代进化模式，为治疗性抗体设计提供新途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 缓解抗体自回归语言模型中的胚系偏置，以生成更多样性的候选抗体。
method: 采用组相对策略优化（GRPO）的强化学习框架，并引入改进防止奖励黑客。
result: "在5和35突变阈值下，GermRL的pass@1分别为0.992和0.950，远优于预训练模型的0.398和0.034。"
conclusion: 强化学习优化的生成模型能探索新型生物合理的抗体序列，为治疗设计提供有前途的方法。
---

## 摘要
抗体是强大的治疗药物，其抗原特异性源于发育过程中形成的序列多样性。近年来，基于大规模抗体库数据集训练的语言模型使得新型候选抗体的生成和筛选成为可能，但这些模型保留了强烈的种系偏差。随着人工智能在治疗工作流程中的日益应用，开发能够利用抗体多样性以发现编码理想特性的突变的模型至关重要。先前的研究探讨了掩码抗体语言模型中的种系偏差，但生成式自回归语言模型中的偏差尚未得到解决。在此，我们提出GermRL，一种轻量级模块化强化学习框架，能够通过组相对策略优化（GRPO）缓解预训练的自回归抗体语言模型中的种系偏差。GermRL实现了抗体的一次性一致生成，这些抗体满足与种系指定的突变阈值，同时保持结构合理性。在测试的最低和最高突变阈值（与种系相差5个和35个突变）下，GermRL的pass@1得分分别为0.992和0.950，而预训练语言模型分别为0.398和0.034。在GermRL内部，我们对GRPO引入了一对关键修改，通过抑制奖励破解来提高训练效率，适用于我们的抗体应用。此外，比较RL生成的抗体序列和天然抗体序列揭示了基于RL的优化如何探索替代的进化突变模式和残基组成策略，同时保留天然抗体的关键全局特性，包括可识别的种系分配、嵌入级相似性和可比的成药性特征。因此，通过从种系多样性优化抗体突变的RL训练生成模型，为导航抗体序列景观提供了有前景的框架，使得能够探索用于治疗设计的新型且生物学上合理的候选抗体。

## Abstract
Antibodies are powerful therapeutics whose antigen specificity arises from sequence diversity shaped during development. Recently, language models trained on large antibody repertoire datasets have enabled the generation and screening of novel candidates, but these models retain a strong germline bias. As AI adoption increases in therapeutic workflows, it is crucial to develop models that harness the diversity of antibodies necessary for the discovery of mutations that encode desirable properties. Previous work explored the germline bias in masked antibody language models, yet the bias in generative autoregressive language models has not yet been addressed. Here, we present GermRL, a lightweight and modular reinforcement learning (RL) framework capable of alleviating the germline bias in pre-trained antibody autoregressive language models through group relative policy optimization (GRPO). GermRL achieves consistent one-shot generation of antibodies that satisfy specified mutation thresholds from germline while maintaining structural plausibility. Under the lowest and highest mutation thresholds tested (5 and 35 mutations from germline), GermRL scores 0.992 and 0.950 pass@1, respectively, compared to 0.398 and 0.034 for the pre-trained language model. Within GermRL, we introduce a key pair of modifications to GRPO that increase training efficiency by discouraging reward hacking under our antibody application. Furthermore, comparison of RL generated and natural antibody sequences reveals how RL based optimization can explore alternative evolutionary mutational patterns and residue compositional strategies while preserving key global properties of natural antibodies, including identifiable germline assignments, embedding-level similarity and comparable developability profiles. Thus, RL-trained generative models optimized to promote antibody mutations through diversity from germline provide a promising framework for navigating the antibody sequence landscape, enabling exploration of novel yet biologically plausible candidates for therapeutic design.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有的自回归抗体语言模型（如基于大规模抗体库训练的语言模型）在生成抗体序列时，表现出强烈的**种系偏差（germline bias）**——即生成的序列过度倾向与种系序列相近，而难以产生足够多样的突变序列。这限制了治疗性抗体设计中对多样性突变空间的探索。
- **研究动机**：抗体治疗以抗原特异性为核心，而多样性源于突变（尤其在互补决定区CDR）。随着AI在抗体设计中的应用，需要能生成**满足指定突变阈值（如与种系差异5~35个氨基酸）** 且结构合理的候选抗体。
- **整体含义**：提出GermRL框架，通过强化学习（RL）的后训练，使预训练的自回归抗体语言模型能够**可控地生成远离种系**但依然生物合理的序列，从而为治疗性抗体设计提供更广阔的候选空间。

### 2. 论文提出的方法论
- **核心思想**：采用**组相对策略优化（Group Relative Policy Optimization, GRPO）** 作为强化学习算法，对预训练的自回归抗体语言模型进行微调，以优化奖励函数——奖励生成序列达到指定的突变阈值（与种系的差异氨基酸数目），同时惩罚序列的结构不合理性或其他不良性质。
- **关键技术细节**：
  - **奖励函数设计**：主要奖励突变数量（与种系序列的Hamming距离）是否落入指定区间，并可能结合结构合理性指标（如Rosetta能量、可开发性预测器）。
  - **防止奖励破解（Reward Hacking）**：对GRPO引入**两个关键修改**：① 限制策略更新的散度上限；② 在奖励中加入惩罚项，防止模型通过生成无效序列（如截断、重复）来获得高突变奖励。
  - **算法流程**：从预训练语言模型采样一批序列，计算每个序列的奖励与组内平均奖励的差异作为优势函数，然后通过更新策略梯度拉高优势高的序列概率，压低优势低的序列概率。
- **公式或算法流程**（文字说明）：类似于PPO的变体，但使用组内相对奖励（而非绝对基线），并加入了针对抗体领域的正则化项，避免模型退化到无效模式。

### 3. 实验设计
- **数据集/场景**：
  - 使用一个预训练的自回归抗体语言模型（未指明具体名称，可能为IgLM、AntiBERTy等）作为基线。
  - 测试场景：要求生成与种系序列相差**5个突变**（最低阈值）和**35个突变**（最高阈值）的抗体序列。
- **Benchmark**：比较GermRL vs. 原始预训练语言模型，主要指标为**pass@1**（单次生成成功率，即满足突变阈值且结构合理的比例）。
- **对比方法**：仅与预训练对抗体语言模型本身比较（即有无RL微调）。未提及与其他RL方法或基于掩码的模型比较。

### 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量或训练时长。仅描述GermRL为“轻量级模块化强化学习框架”，暗示计算开销不大。未提供具体算力消耗数据。

### 5. 实验数量与充分性
- **实验组数**：仅报告了两个阈值（5和35突变）下的pass@1结果，以及一些生成序列的特性分析（如结构合理性、种系分配、嵌入级相似性、成药性特征）。未见消融实验或更多阈值的系统测试。
- **充分性与客观性**：
  - **优点**：pass@1提升显著（从0.398/0.034到0.992/0.950），结论明确；但**实验覆盖较窄**：仅测试两个阈值，且仅与一个基线模型对比。
  - **不足**：缺乏对更多不同突变阈值、不同预训练模型、不同长度CDR的泛化性测试；未提供与掩码模型（如LM-Design）或其它RL方法的对比；缺少重复性统计（标准差等）。
  - **公平性**：可能较为公平，因为RL微调直接基于同一预训练模型，但未说明预训练模型的具体细节和训练数据，无法完全排除基线选择偏差。

### 6. 论文的主要结论与发现
- **主要结论**：GermRL能够**一次性、一致地生成**满足指定突变阈值的抗体序列（5突变下pass@1=0.992，35突变下pass@1=0.950），而预训练模型几乎无法完成高突变要求（35突变下pass@1=0.034）。
- **发现**：
  - RL优化能够探索**替代的进化突变模式**和**残基组成策略**，同时保留天然抗体的**全局关键特性**（可识别的种系分配、嵌入相似性、类似的可开发性特征）。
  - 生成的抗体序列在结构合理性和发育特性上与天然抗体可比。

### 7. 优点
- **方法创新**：首次针对自回归抗体语言模型的种系偏差提出RL后训练解决方案；引入针对奖励破解的改进（GRPO修改），提升训练效率。
- **实用性强**：框架轻量、模块化，易于集成到现有抗体设计流程；生成的高突变序列可直接作为后续亲和力成熟或人源化的起点。
- **结果显著**：在极端突变阈值下性能提升超过一个数量级（pass@1提高28倍），展示出RL在控制生成多样性方面的强大能力。

### 8. 不足与局限
- **实验覆盖不足**：仅测试两个突变阈值，未考虑中间值或连续控制；未验证对不同CDR长度、不同框架区的影响。
- **缺乏方法比较**：未与掩码语言模型（如AntiBERTy的masked variant）、进化算法、其他强化学习（如PPO、A2C）等进行对比，难以评估GermRL的绝对先进性。
- **可解释性局限**：RL生成的序列为何能保持结构合理性和发育特性？文中仅做宏观统计，未深入分析序列特征（如特定残基偏好、物理化学性质分布）。
- **应用限制**：未在真实治疗抗体设计案例中验证（如结合predictor或实验验证）；仅关注突变数量，未直接优化结合亲和力、免疫原性等关键属性。
- **评估风险**：结构合理性可能仅基于计算预测（未提及是否使用结构预测模型如AlphaFold），存在假阳性；重复性/稳定性未报告（如多次实验的变异）。

（完）

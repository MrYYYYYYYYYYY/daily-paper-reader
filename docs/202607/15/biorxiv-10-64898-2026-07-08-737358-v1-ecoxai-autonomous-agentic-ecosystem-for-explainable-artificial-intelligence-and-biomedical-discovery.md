---
title: "EcoXAI: Autonomous Agentic Ecosystem for Explainable Artificial Intelligence and Biomedical Discovery"
title_zh: EcoXAI：面向可解释人工智能和生物医学发现的自主代理生态系统
authors: "Matsumoto, N., Choi, H., Freda, P. J., Hernandez, M. E., Wang, Z. P., Moore, J. H."
date: 2026-07-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737358v1.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 旨在避免生物医学分析中出现幻觉的多智能体系统
tldr: 生物医学数据集和知识图谱日益复杂，传统AI易产生幻觉或不可靠结果。EcoXAI提出模块化、可定制的多智能体系统，将分析分解为明确执行阶段，并显式集成知识图谱，提升推理透明性与可验证性。在阿尔茨海默病药物重定位应用中，系统评估103个候选药物，发现79个新候选，其中Maraviroc的假设得到文献支持，展示出知识图谱引导的AI智能体加速假设驱动研究的潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737358-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 773, \"label\": \"Figure\"}]"
motivation: 生物医学数据规模和复杂性激增，研究者需自主、可靠的AI分析工具以避免幻觉和碎片化结果。
method: 构建模块化多智能体系统，通过显式管道执行阶段和知识图谱集成实现透明可解释推理。
result: 在阿尔茨海默病药物重定位中评估103个候选，发现79个新候选，包括文献支持的CCR5拮抗剂Maraviroc。
conclusion: EcoXAI提供透明可验证的AI框架，有效加速生物医学假设发现与验证。
---

## 摘要
动机：随着生物医学数据集和知识图谱在规模、复杂性和异质性上持续增长，研究人员从这些数据中导航和提取可操作见解面临重大瓶颈。亟需能够利用代理人工智能（如代理利用和循环工程）最新进展的自主分析解决方案，且不引入幻觉或工作流碎片化。无论技术背景如何，研究人员都需要能够简化复杂数据分析、并提供基于数据和已有生物医学知识的有意义、可操作见解的工具。EcoXAI通过引入模块化、可定制、容器化的多代理系统来解决这一问题，该系统将分析结构化为明确的流水线执行阶段，降低了临床和转化研究人员的计算门槛。

结果：EcoXAI用自主执行驱动的框架取代了单一的人工智能文本界面，该框架具有专门的生物信息学代理，能够提供基于已有生物知识的主动、数据驱动的见解。与纯LLM驱动或集成度较低、容易产生幻觉或生物学上不合理结果的AI解决方案不同，EcoXAI的多代理框架利用了现代代理管理和显式知识图谱集成，在其推理中提供了更高的透明度和可验证性。在以阿尔茨海默病药物重定位为用例的场景中，EcoXAI评估了103种候选药物，并识别出79种新型候选药物，其预测模型超过了随机基线，包括CCR5拮抗剂Maraviroc，其生成的假设后来得到了文献支持。这些结果证明了基于知识图谱的AI代理在加速假设驱动生物医学研究方面的潜力。

可用性和实现：EcoXAI可在GitHub上获取：https://github.com/EpistasisLab/EcoXAI。

联系方式：jason.moore@csmc.edu

## Abstract
MotivationAs biomedical datasets and knowledge graphs continue to grow in size, complexity, and heterogeneity, navigating and extracting actionable insights from them presents a major bottleneck for researchers. There is a clear need for autonomous analytical solutions that can utilize recent advancements in agentic AI such as agent harnessing and loop engineering without introducing hallucination or workflow fragmentation. Researchers, regardless of technical expertise, need tools that streamline complex data analysis and deliver meaningful, actionable insights grounded in both data and established biomedical knowledge. EcoXAI addresses this by introducing a modular, customizable, containerized multi-agent system that structures analysis into explicit pipeline execution stages, lowering the computational barrier for clinical and translational researchers.

ResultEcoXAI replaces monolithic AI text interfaces with an autonomous execution-driven framework with specialized bioinformatics agents for delivering proactive, data-driven insights grounded in established biological knowledge. Unlike purely LLM-driven or less integrated AI solutions prone to hallucinations or biologically implausible outcomes, EcoXAIs multi-agent framework, which leverages modern agentic management and explicit knowledge graph integration, provides greater transparency and verifiability in its reasoning. In our use case in drug repurposing for Alzheimers Disease, EcoXAI evaluated 103 drug candidates and identified 79 novel candidates whose predictive models exceeded a randomized baseline, including the CCR5 antagonist Maraviroc, whose generated hypothesis was subsequently supported by the literature. These results demonstrate the potential of knowledge graph-grounded AI agents to accelerate hypothesis-driven biomedical research.

Availability and implementationEcoXAI is available on GitHub at: https://github.com/EpistasisLab/EcoXAI.

Contactjason.moore@csmc.edu
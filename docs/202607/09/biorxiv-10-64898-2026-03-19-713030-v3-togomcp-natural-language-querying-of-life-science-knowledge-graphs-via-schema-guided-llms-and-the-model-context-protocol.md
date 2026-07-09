---
title: "TogoMCP: Natural Language Querying of Life-Science Knowledge Graphs via Schema-Guided LLMs and the Model Context Protocol"
title_zh: "TogoMCP: 通过模式引导的大语言模型和模型上下文协议对生命科学知识图谱进行自然语言查询"
authors: "Kinjo, A. R., Yamamoto, Y., Bustamante-Larriet, S., Labra-Gayo, J. E., Fujisawa, T."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.713030v3.full.pdf"
tags: ["query:lpt"]
score: 7.0
evidence: 通过模式引导减少LLM在SPARQL生成中的幻觉
tldr: "生命科学知识图谱RDF Portal集成约60个数据库，但查询需精通SPARQL和特定schema，多数研究者难以使用。TogoMCP基于MCP协议，通过MIE文件动态提供数据库结构语义，并采用实体解析与SPARQL生成两阶段流程。在50个生物问题基准测试中，相比无辅助基线显著提升（Cohen's d=1.82），准确可验证问题胜率超80%。研究表明简洁的动态schema上下文对平均分提升最有效，过程指导则降低风险。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 1488, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 790, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 773, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 885, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-713030-v3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1158, \"height\": 253, \"label\": \"Table\"}]"
motivation: LLM在缺乏schema上下文时常虚构谓词或无法解析实体至数据库标识符。
method: 通过MIE文件动态提供各数据库结构语义，采用两阶段工作流：先实体解析再schema引导SPARQL生成。
result: "在50个生物问题上平均分提升显著（Cohen's d=1.82），准确可验证问题胜率超80%。"
conclusion: 简洁动态schema上下文比复杂编排更重要，过程指导互补降低方差。
---

## 摘要
查询由DBCLS维护的RDF Portal知识图谱（该图谱整合了约60个生命科学数据库）需要精通SPARQL和特定于数据库的RDF模式，这使得大多数研究人员无法利用这一资源。大语言模型（LLM）原则上可以将自然语言问题转化为可执行的SPARQL，但若缺乏模式级上下文，它们常常捏造不存在的谓词，或无法将实体名称解析为特定于数据库的标识符。我们提出TogoMCP，该系统将LLM重新定义为一种协议驱动的推理引擎，通过模型上下文协议（MCP）协调专门的工具。其设计包含两个关键机制：(i) MIE（元数据-互操作性-交换）文件，一种简洁的YAML文档，在查询时动态地向LLM提供每个目标数据库的结构和语义上下文；(ii) 一个两阶段工作流，将外部REST API的实体解析与模式引导的SPARQL生成分离开来。在一个涵盖5种类型和23个数据库的50个生物学基础问题的基准测试中，TogoMCP相比无辅助基线取得了大幅提升（Cohen's d = 1.82, Wilcoxon p < 0.001），对于具有精确可验证答案的问题类型，获胜率超过80%。消融研究表明，所有组件配置都带来了显著改进，其中MIE模式文件在平均每问题得分上提供了最大的边际贡献（相对于无MIE条件，Δ = +0.50，双侧Wilcoxon p = 0.067；90%自助法置信区间[+0.04, +0.94]排除零）；加载相关MIE文件的一行指令可恢复与完整程序化协议相同的平均改进，而协议还额外降低了风险（损失率1.6% vs. 4.8%，Fisher p = 0.036）。这些结果表明了一个通用设计原则：对于平均得分性能，简洁、动态提供的模式上下文比复杂的编排逻辑更有价值，而程序化指导在缩小方差方面起补充作用。

数据库URL：https://togomcp.rdfportal.org/

## Abstract
Querying the RDF Portal knowledge graph maintained by DBCLS--which aggregates approximately 60 life-science databases--requires proficiency in both SPARQL and database-specific RDF schemas, placing this resource beyond the reach of most researchers. Large Language Models (LLMs) can, in principle, translate natural-language questions into executable SPARQL, but without schema-level context, they frequently fabricate non-existent predicates or fail to resolve entity names to database-specific identifiers. We present TogoMCP, a system that recasts the LLM as a protocol-driven inference engine orchestrating specialized tools via the Model Context Protocol (MCP). Two mechanisms are essential to its design: (i) the MIE (Metadata-Interoperability-Exchange) file, a concise YAML document that dynamically supplies the LLM with each target databases structural and semantic context at query time; and (ii) a two-stage workflow separating entity resolution via external REST APIs from schema-guided SPARQL generation. On a benchmark of 50 biologically grounded questions spanning five types and 23 databases, TogoMCP achieved a large improvement over an unaided baseline (Cohens d = 1.82, Wilcoxon p < 0.001), with win rates exceeding 80% for question types with precise, verifiable answers. An ablation study shows that all component configurations deliver significant improvements, with MIE schema files providing the largest marginal contribution on mean per-question score ({Delta} = +0.50 relative to a no-MIE condition, two-sided Wilcoxon p = 0.067; 90% bootstrap CI [+0.04, +0.94] excludes zero); a one-line instruction to load the relevant MIE file recovers the same mean improvement as a full procedural protocol, while the protocol additionally reduces downside risk (loss rate 1.6% vs. 4.8%, Fisher p = 0.036). These results suggest a general design principle: concise, dynamically delivered schema context is more valuable than complex orchestration logic for mean-score performance, while procedural guidance plays a complementary role in narrowing variance.

Database URL: https://togomcp.rdfportal.org/
---
title: "Systematic evaluation and benchmarking of text summarization methods for biomedical literature: From word-frequency methods to language models"
title_zh: 生物医学文献文本摘要方法的系统评估与基准测试：从词频方法到语言模型
authors: "Baumgärtel, F., Bono, E., Fillinger, L., Galou, L., Keska-Izworska, K., Walter, S., Andorfer, P., Kratochwill, K., Perco, P., Ley, M."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.09.697335v4.full.pdf"
tags: ["query:lpt"]
score: 8.0
evidence: 对62种文本摘要方法的系统评估与基准测试，包含大语言模型
tldr: 生物医学文献的激增需要可靠的自动摘要工具。本研究对62种摘要方法进行了系统基准测试，涵盖从词频、TextRank到编码器-解码器模型和大语言模型。在1000篇生物医学摘要上使用多种词汇、语义和事实性指标评估，发现通用大语言模型（如Mistral、GPT、Llama）性能最优，而领域特定模型和经典抽取式方法表现较弱。结果表明，广泛预训练比窄领域适应更有效，为工具选择提供了参考。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1604, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1555, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1292, \"height\": 2110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1578, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1576, \"height\": 2143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1732, \"height\": 1197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1043, \"height\": 1955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1475, \"height\": 1663, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1840, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1843, \"height\": 1602, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1839, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1544, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1157, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 801, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 794, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-09-697335-v4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1816, \"height\": 2171, \"label\": \"Table\"}]"
motivation: 评估和比较现有文本摘要方法在生物医学文献上的表现，为研究者选择自动摘要工具提供系统依据。
method: 对62种方法在1000篇生物医学摘要上进行基准测试，使用ROUGE、BLEU、METEOR、嵌入相似度和事实性评分等指标，以作者撰写的高亮为参考。
result: 通用大语言模型在词汇和语义维度表现最佳，中型模型优于大型模型，领域特定模型和经典方法表现较差。
conclusion: 广泛预训练的通用模型比窄领域适应的模型更有效，建议优先选用通用大语言模型进行生物医学摘要。
---

## 摘要
生物医学文献的快速增长要求自动化摘要工具能够可靠地将研究文章浓缩为简洁准确的摘要。我们在来自ScienceDirect和Cell Press的20种期刊的1000篇生物医学摘要上，以作者撰写的亮点作为参考摘要，对62种摘要方法进行了基准测试，涵盖基于词频和TextRank的抽取式方法、编码器-解码器模型（EDMs）以及大型语言模型（LLMs）。使用包含词法、语义和事实性指标的复合评估套件进行评估，包括ROUGE、BLEU、METEOR、基于嵌入的相似度和事实性分数。通用型模型（例如Mistral、GPT、Llama）在词法和语义维度上取得了最高整体性能，优于面向推理的模型（例如DeepSeek、Magistral）和领域特定模型（例如BioGPT、BioMistral）。值得注意的是，中等规模模型表现优于大规模模型，表明模型容量与效率之间存在最佳平衡，而经典的抽取式方法落后于神经方法。这些发现为选择生物医学摘要工具提供了系统参考，并强调广泛的预训练优于狭窄的领域适应。

## Abstract
The rapid expansion of biomedical literature demands automated summarization tools that reliably condense research articles into concise, accurate summaries. We benchmarked 62 summarization methods, ranging from frequency-based and TextRank extractors to encoder-decoder models (EDMs) and large language models (LLMs), on 1,000 biomedical abstracts from 20 journals across ScienceDirect and Cell Press, using author-written highlights as reference summaries. Models were evaluated with a composite suite of lexical, semantic, and factual metrics, including ROUGE, BLEU, METEOR, embedding-based similarity, and factuality scores. General-purpose models (e.g., Mistral, GPT, Llama) achieved the highest overall performance across lexical and semantic dimensions, outperforming reasoning-oriented (e.g., DeepSeek, Magistral) and domain-specific (e.g., BioGPT, BioMistral) models. Notably, medium-sized models outperformed large-scale models, suggesting an optimal balance between model capacity and efficiency, while classical extractive methods lagged behind neural approaches. These findings provide a systematic reference for selecting biomedical summarization tools and highlight that broad pretraining outperforms narrow domain adaptation.

---

## 论文详细总结（自动生成）

# 论文总结：生物医学文献文本摘要方法的系统评估与基准测试

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：生物医学文献呈指数级增长，研究者难以高效筛选和解读海量论文。自动文本摘要（ATS）工具能帮助浓缩研究文章，但缺乏对从传统方法到最新大语言模型（LLM）的系统比较。
- **背景**：已有评估多局限于少数模型或使用摘要本身作为参考，而对作者撰写的高亮摘要（highlights）作为黄金标准、全面覆盖多种方法的系统性基准尚属空白。
- **整体意义**：为生物医学研究者选择摘要工具提供实证依据，并揭示“广泛预训练的通用模型” vs “领域专精模型”的效果差异。

## 2. 方法论
- **核心思想**：固定输入（标题+摘要），要求模型生成15–100词的简洁摘要，并以作者撰写的高亮为参考，从多个维度（词法、语义、事实性）量化评估。最终通过标准化聚合得到“总体性能分数”（Overall Performance Score, OPS）进行排名。
- **关键技术细节**：
  - **输入**：同一提示模板（含长度限制、要求聚焦主要发现、排除背景方法，若无可摘要则返回INSUFFICIENT_FINDINGS）。
  - **评估指标体系**：
    - **词法维度**（5个指标）：ROUGE-1/2/L、BLEU、METEOR。
    - **语义维度**（3个指标）：BERTScore（RoBERTa & DeBERTa）、all-mpnet-base-v2（句子级嵌入相似度）。
    - **事实维度**（4个指标）：AlignScore、SummaC、MiniCheck-FT5、MiniCheck-7B（比较生成摘要与原始摘要的一致性）。
  - **聚合方法**：对每个维度内的指标取平均，再对三个维度的平均值进行z-score标准化，最后取三个标准化分数的均值作为OPS。
  - **统计比较**：使用Welch ANOVA和Games-Howell事后检验比较模型类别和模型家族间的差异。
  - **数据泄漏分析**：通过检查模型训练截止日期与文章出版日期的重叠，以及对高重叠模型进行“摘要完成探查”（abstract completion probe，比较前后截止日期的ROUGE-L差异）。
  - **专家评估**：8位专家对4个模型（2个最佳+2个最差）按SummEval四维度（连贯性、流畅性、相关性、一致性）进行5分制盲评。
  - **LLM-as-a-judge**：3个来自不同提供商的中档模型构成陪审团，评分后取中位数。

## 3. 实验设计
- **数据集**：
  - 1000篇生物医学论文，分别来自ScienceDirect和Cell Press的20种期刊（每种50篇），时间跨度2015–2025年，95%为2024年后出版。
  - 使用**作者撰写的高亮**（highlights）作为参考摘要（黄金标准），标题+摘要作为输入。
- **基准模型**：共62种，分为5大类：
  - 传统模型（2个）：frequency, textrank
  - 通用EDMs（4个）：bart-base, pegasus-large, t5-base, t5-large
  - 领域特定EDMs（8个）：mT5 XLSum, bart-large-cnn, bigbird-pegasus-pubmed, pegasus-pubmed等
  - 通用SLMs & LLMs（分别多个）：包括Mistral家族、GPT家族、Llama家族、Gemma、Granite等
  - 推理型SLMs & LLMs（多个）：deepseek-r1系列、qwen3、claude-opus、gpt-5等
  - 领域特定SLMs & LLMs（6个）：BioGPT, OpenBioLLM, BioMistral, medllama2, SciLitLLM等
- **对比方式**：所有模型使用相同提示，在完全相同的数据集上生成摘要，通过自动指标统一打分，最终按OPS排名。

## 4. 资源与算力
- 论文中仅提及**本地LLM推理**使用单张 **NVIDIA RTX A4000 GPU（16GB VRAM）**，配合Ollama和transformers库。
- **未明确说明**总计算量（GPU小时数）、训练时长（因本研究为评估而非训练）。闭源模型通过API访问，算力由提供商提供，无法量化。
- 可以认为相对轻量（单GPU+API调用），适合学术实验室复现。

## 5. 实验数量与充分性
- **数量**：
  - 62种模型 × 1000篇文档 = **62,000个生成摘要**，每个摘要均计算12个指标。
  - 专家评估：8位评估者 × 4个模型 × 20篇文章 = **640份评分**（每个维度160份）。
  - LLM-as-a-judge：3个法官 × 20篇文章 × 62个模型（仅部分维度） = 约111,600个评分。
  - 数据泄漏分析：对8个高重叠模型进行摘要完成探查。
- **充分性**：
  - **全面性**：覆盖从传统到最新LLM的广泛方法，指标涵盖三种互补维度，统计方法严谨。
  - **公平性**：统一提示、统一评估、盲评专家、独立LLM陪审团。但存在固定提示可能对某些模型不利的偏差（论文已承认）。
  - **限制**：仅测试单一任务（从摘要生成摘要），未涉及全文摘要、多文档摘要、或面向不同受众的摘要。数据集仅来自两家出版商20种期刊，可能无法代表整个生物医学领域。

## 6. 主要结论与发现
1. **通用LLM表现最佳**：Mistral家族（mistral-small3.2:24b、mistral-small-2506等）在所有维度上排名靠前，GPT、Llama紧随其后。
2. **中等规模模型优于大规模**：中等参数模型（如Mistral-small）胜过更大规模的专有模型（如claude-opus、gpt-5），表明存在容量-效率最优平衡。
3. **通用模型 > 领域特定模型**：领域微调模型（BioGPT、BioMistral等）和推理型模型（DeepSeek、Magistral）表现不如通用LLM，表明广泛预训练比窄领域适应更有效。
4. **传统抽取式方法最差**：frequency和textrank在词法和语义维度排名靠后，仅在事实性维度领先（因严格遵循源文本）。
5. **专家评估与自动指标一致**：两个最佳模型显著优于两个最差模型，吻合自动排名。
6. **LLM-as-a-judge有效但存在自偏好**：陪审团与专家高度相关（ρ=0.87），但Anthropic法官表现出自偏好（+0.30分），取中位数可缓解。
7. **数据泄漏影响可忽略**：即使有潜在重叠，摘要完成探查未发现记忆效应。
8. **事实性维度特殊性**：抽取式方法因复制源文本而获高分，表明事实性指标更偏好忠实原文而非抽象概括。

## 7. 优点
- **系统性与全面性**：首次将62种方法从传统到最新LLM纳入统一框架，覆盖5大类、多种指标。
- **多维评估**：词法、语义、事实性三管齐下，避免单一指标偏差；使用z-score标准化确保维度平衡。
- **高质量参考标准**：采用作者撰写的高亮（而非摘要本身），更反映论文的“关键信息”。
- **严谨的统计比较**：Welch ANOVA + Games-Howell专门处理异质性方差和不等样本，结果可靠。
- **消融分析**：数据泄漏分析和专家评估验证自动指标的有效性。
- **可复现性**：开源代码、数据集和结果，使用常用硬件（单GPU）即可复现。
- **LLM-as-a-judge创新**：采用三个不同提供商的法官组成陪审团，减少单模型偏差；并验证了与专家的一致性。

## 8. 不足与局限
- **任务局限性**：仅测试“从摘要生成摘要”的单任务场景，不覆盖全文摘要、临床报告摘要、或面向外行的总结。
- **提示固定**：所有模型使用同一提示，可能对某些模型不利（如推理模型可能需要特定指令才能最大发挥）。未进行每模型调优。
- **数据集代表性不足**：仅来自两家出版商（ScienceDirect、Cell Press）的20种英文期刊，可能偏向分子科学领域，不能完全代表整个生物医学。
- **参考主观性**：作者高亮虽权威，但本质上是主观选择，不同作者或不同论文可能有不同侧重点。
- **LLM-as-a-judge局限**：三个法官误差并非独立，统计上有效投票数远少于3；自偏好偏差（尤其是Anthropic）可能影响排名。
- **不可控变量**：闭源模型API可能有中间层处理，参数控制不完全标准化（如GPT-5不支持temperature）。
- **时效性**：结果仅反映论文写作时的模型快照；LLM领域快速迭代，排名可能很快变化。
- **事实性指标偏向**：事实性指标天然奖励忠实原文，导致抽取式方法得分虚高，而抽象型模型可能因创造性重述被扣分，需结合人类判断。

（完）

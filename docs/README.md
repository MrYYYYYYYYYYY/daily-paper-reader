<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-07-02
- 运行时间：2026-07-02 20:14:08 UTC
- 运行状态：成功
- 本次总论文数：14
- 精读区：6
- 速读区：8

### 今日简报（AI）
今日14篇推荐中聚焦LLM强化学习优化，6篇精读围绕rollout数据筛选与流水线训练。最值得关注两篇9分工作：《GEOALIGN》的几何rollout精选提升鲁棒性，《RolloutPipe》实现解耦在线RL中rollout与训练重叠流水线。建议读者深入探究强化学习数据质量与训练效率的融合策略，例如在较小模型上实验rollout缓存机制以平衡开销。
- 详情：[/202607/02/README](/202607/02/README)

### 精读区论文标签
1. [GEOALIGN: Geometric Rollout Curation for Robust LLM Reinforcement Learning](/202607/02/2606.26917v1-geoalign-geometric-rollout-curation-for-robust-llm-reinforcement-learning)  
   标签：评分：9.0/10、query:lpt
   evidence：通过几何方法筛选生成轨迹来处理噪声奖励，提升RL训练鲁棒性
2. [RolloutPipe: Overlapping Pipelined Rollout and Training in Disaggregated On-Policy LLM Reinforcement Learning](/202607/02/2606.26997v1-rolloutpipe-overlapping-pipelined-rollout-and-training-in-disaggregated-on-policy-llm-reinforcement-learning)  
   标签：评分：9.0/10、query:lpt
   evidence：针对LLM强化学习训练管线的算法改进
3. [Designing Reward Signals for Portable Query Generation: A Case Study in Industrial Semantic Job Search](/202607/02/2606.27291v1-designing-reward-signals-for-portable-query-generation-a-case-study-in-industrial-semantic-job-search)  
   标签：评分：9.0/10、query:lpt
   evidence：使用RLAIF和奖励建模进行查询生成，直接匹配奖励建模需求
4. [The Longevity of Innovation](/202607/02/2606.29777v1-the-longevity-of-innovation)  
   标签：评分：9.0/10、query:lpt
   evidence：研究创新的持久性与科学通才/专才
5. [MOPD: Multi-Teacher On-Policy Distillation for Capability Integration in LLM Post-Training](/202607/02/2606.30406v1-mopd-multi-teacher-on-policy-distillation-for-capability-integration-in-llm-post-training)  
   标签：评分：9.0/10、query:lpt
   evidence：用于LLM后训练的多教师强化学习蒸馏方法来整合能力
6. [Experience Augmented Policy Optimization for LLM Reasoning](/202607/02/2606.30420v1-experience-augmented-policy-optimization-for-llm-reasoning)  
   标签：评分：9.0/10、query:lpt
   evidence：提出基于可验证奖励的LLM推理经验增强策略优化，直接涉及奖励建模。

### 速读区论文标签
1. [Building Multi-Task Agentic LLMs via Two-Phase Distillation](/202607/02/2606.30044v1-building-multi-task-agentic-llms-via-two-phase-distillation)  
   标签：评分：8.0/10、query:lpt
   evidence：提出两阶段蒸馏构建多任务LLM，属于后训练算法改进。
2. [Test-Time Verification for Text-to-SQL via Outcome Reward Models](/202607/02/2606.30851v1-test-time-verification-for-text-to-sql-via-outcome-reward-models)  
   标签：评分：8.0/10、query:lpt
   evidence：使用结果奖励模型进行测试时验证，是一种奖励建模形式
3. [Internalizing the Future: A Unified Agentic Training Paradigm for World Model Planning](/202607/02/2606.27483v1-internalizing-the-future-a-unified-agentic-training-paradigm-for-world-model-planning)  
   标签：评分：7.0/10、query:lpt
   evidence：提出LLM智能体世界模型规划的统一训练范式，属于后训练算法改进。
4. [Yuvion LLM: An Adversarially-Aware Large Language Model for Content And AI Safety](/202607/02/2606.27632v1-yuvion-llm-an-adversarially-aware-large-language-model-for-content-and-ai-safety)  
   标签：评分：7.0/10、query:lpt
   evidence：面向LLM安全的对抗鲁棒性方法，与减少有害输出（幻觉）相关
5. [GenPage: Towards End-to-End Generative Homepage Construction at Netflix](/202607/02/2606.31031v1-genpage-towards-end-to-end-generative-homepage-construction-at-netflix)  
   标签：评分：7.0/10、query:lpt
   evidence：使用LLM后训练（RL/WBC）构建生成式主页，展示后训练在推荐中的应用
6. [When RAG Meets Query Planning: Logical Query Trees for Resolving Exploratory Reasoning Problems](/202607/02/2607.00508v1-when-rag-meets-query-planning-logical-query-trees-for-resolving-exploratory-reasoning-problems)  
   标签：评分：7.0/10、query:lpt
   evidence：通过查询规划和逻辑查询树减少RAG中的检索噪声和错误累积，抑制幻觉
7. [One Retrieval to Cover Them All: Co-occurrence-Aware Knowledge Base Reorganization for Session-Level RAG](/202607/02/2606.31156v1-one-retrieval-to-cover-them-all-co-occurrence-aware-knowledge-base-reorganization-for-session-level-rag)  
   标签：评分：6.0/10、query:lpt
   evidence：会话级RAG方法，通过共现感知聚类重组知识库，提升检索覆盖，有助于减轻幻觉
8. [Query-Centric Optimization of AI Workflows via Approximate Query Processing and Proxy Models](/202607/02/2607.00254v1-query-centric-optimization-of-ai-workflows-via-approximate-query-processing-and-proxy-models)  
   标签：评分：6.0/10、query:lpt
   evidence：通过近似查询处理和代理模型优化LLM后训练流程


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>

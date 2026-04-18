# AI 系统化学习课程体系

本文档定义了面向滑铁卢CS Co-op学生的AI学习路径分层结构、每阶段的学习目标、核心知识点与学习方法建议。具体课程资源见 courses.json。

## 学习模式

本课程体系支持三种学习模式，学生在首次使用时可自由选择：

### 模式A：系统路线（Bottom-Up）
从ML基础开始，按 Phase 1 → 2 → 3 → 4 逐步推进。适合喜欢扎实理论基础、偏学术研究方向的学习者。

### 模式B：项目驱动（Top-Down）
选一个想做的项目（如"搭建一个RAG聊天机器人"），边做边学，按需拉取知识。适合想快速出活、靠动手驱动学习的人。灵感来自 fast.ai Jeremy Howard 的教学哲学和 Harvard David Perkins 的"Making Learning Whole"理论。详见 [top_down_projects.md](top_down_projects.md)。

### 模式C：混合模式（Spiral，推荐）
先用项目驱动入门建立信心和上下文，再螺旋式回填理论基础。这是 fast.ai 推荐的方式，也是多数实践者的最优路径。

**混合模式典型路径：**
```
月1-3：Top-Down入门 → 用API搭一个能跑的AI应用（获得全局视角）
月4-9：Bottom-Up回填 → 系统学ML/DL理论（此时有项目经验做锚点，理论不再抽象）
月10-18：Top-Down深入 → 搭建RAG/Agent/微调等进阶项目
月19-24：Bottom-Up收尾 → 补全工程化能力，形成完整知识体系
```

课程体系中每门课标注了 `learning_mode` 字段（`bottom_up` / `top_down`），Agent 会根据学生选择的模式筛选和推荐课程。

---

## 学习路径总览（Bottom-Up模式）

```
Phase 1: 地基 (4-6月)  →  Phase 2: 核心 (6-9月)  →  Phase 3: 前沿 (6-9月)  →  Phase 4: 工程化 (3-6月)
     ↑                          ↑                          ↑                          ↑
  ML基础+数学             深度学习专项              GenAI/LLM/Agent/MCP       MLOps+生产部署
```

总预计时长：18-30个月（取决于Co-op周期和每周可用时间）。

---

## Phase 1：地基 (Foundations)

### 目标
建立扎实的编程与机器学习理论基础。完成此阶段后，学生能够独立使用Python进行数据处理，理解ML核心算法的数学原理，并能用Scikit-learn完成基础的分类/回归任务。

### 知识模块

**1.1 Python数据科学基础**
- Python语法、数据结构、函数、OOP
- NumPy：向量化运算、广播机制
- Pandas：DataFrame操作、数据清洗
- Matplotlib/Seaborn：数据可视化
- 预计学时：20-30小时
- 对应课程类别：`python_ds`

**1.2 机器学习基础**
- 监督学习：线性回归、逻辑回归、决策树、SVM、KNN
- 无监督学习：K-Means、PCA、层次聚类
- 模型评估：交叉验证、偏差-方差权衡、过拟合/欠拟合
- 特征工程基础
- 预计学时：40-60小时
- 对应课程类别：`ml_basics`

**1.3 数学基础（并行学习）**
- 线性代数：向量、矩阵运算、特征分解、SVD
- 微积分：偏导数、梯度、链式求导（反向传播的数学基础）
- 概率论：贝叶斯定理、常见分布、最大似然估计
- 预计学时：30-40小时（可在Study Term内与ML课程交替学习）
- 对应课程类别：`math_foundations`

### 学习方法建议
- **Bottom-Up模式**：此阶段"禁用AI辅助编码"。亲手写每一行NumPy和Pandas代码，建立肌肉记忆
- **Top-Down模式**：可跳过此阶段大部分内容，直接进入项目。遇到数据处理需求时再回来按需学习Pandas/NumPy
- 用"对抗式费曼法"验证理解：让AI扮演刁难的5岁小孩追问你"为什么"
- Kaggle入门竞赛是最佳实战场景（Titanic、House Prices）

### Co-op周期适配
- Study Term：每周5-8小时，系统推进理论+实战
- Co-op Term：每周2-3小时，重点巩固Python，利用通勤时间看3Blue1Brown数学视频

---

## Phase 2：深度学习核心 (Deep Learning Core)

### 目标
掌握现代深度学习的核心架构与训练方法。完成此阶段后，学生能独立搭建和训练CNN/RNN模型，理解Transformer架构的工作原理，并能阅读主流DL论文。

### 知识模块

**2.1 深度学习专项**
- 神经网络基础：前向传播、反向传播、激活函数
- 深层网络优化：Batch Normalization、Dropout、Adam/SGD
- 超参数调优策略
- 预计学时：60-80小时
- 对应课程类别：`dl_core`
- **2025新增**：Stanford CS336（从零手搓LLM）覆盖了从tokenization到训练到RLHF的完整链路，适合想深入理解底层的学生

**2.2 卷积神经网络 (CNN)**
- 卷积层、池化层、经典架构（LeNet → ResNet → EfficientNet）
- 迁移学习与微调
- 图像分类、目标检测基础
- 预计学时：30-40小时
- 对应课程类别：`cv_basics`

**2.3 序列模型与注意力机制**
- RNN/LSTM/GRU
- Seq2Seq架构
- 注意力机制（从Bahdanau到Self-Attention）
- Transformer架构详解（编码器-解码器、多头注意力、位置编码）
- 预计学时：30-40小时
- 对应课程类别：`nlp_basics`

### 学习方法建议
- **Bottom-Up模式**：此阶段可开始使用AI辅助（Cursor/Copilot加速实验代码编写），但架构设计必须自己做
- **Top-Down模式**：推荐从 fast.ai (DL-002) 开始，先跑通完整DL应用再回填理论。或直接跳到Phase 3做LLM应用项目，遇到Transformer理解需求时再回来
- "从破译开始"：让AI生成一个完整的图像分类项目，然后你的任务是逐行理解它
- 必做项目：至少完成一个端到端的DL项目（如Kaggle图像分类竞赛）

### Co-op周期适配
- Study Term：每周6-10小时，理论+代码实战交替
- Co-op Term：每周2-4小时，利用Co-op项目场景实践DL（如工作中有数据分析需求）

---

## Phase 3：生成式AI与LLM前沿 (GenAI, LLMs, Agents & MCP)

### 目标
掌握当前最前沿的生成式AI技术。完成此阶段后，学生能理解LLM的训练与推理原理，具备Prompt Engineering能力，能设计和实现AI Agent，能搭建RAG系统，并能使用MCP协议构建可扩展的AI应用。

**2025-2026关键变化：Agent和MCP已成为AI应用开发的核心能力，本阶段进行了大幅扩充。**

### 知识模块

**3.1 LLM基础**
- GPT架构演进：GPT-1/2/3/4
- LLM训练流程：预训练、SFT、RLHF/DPO/GRPO
- Token化、Embedding、位置编码
- 上下文窗口、KV Cache、推理优化
- LLM微调：LoRA、QLoRA、全参微调
- 预计学时：40-60小时
- 对应课程类别：`llm_fundamentals`
- **新增课程**：Hugging Face LLM Course (LLM-003)、freeCodeCamp LLM Fine-Tuning (LLM-004)、DeepLearning.AI GRPO (AGENT-008)

**3.2 Prompt Engineering**
- Prompt设计模式：Zero-shot、Few-shot、Chain-of-Thought
- 系统级Prompt工程（System Prompt设计）
- Prompt评估与迭代方法
- 预计学时：15-20小时
- 对应课程类别：`prompt_engineering`

**3.3 RAG与AI应用开发**
- 向量数据库（Pinecone、Chroma、FAISS）
- 文档解析与分块策略
- 检索增强生成（RAG）架构
- Agentic RAG（RAG + Agent结合）
- LLM应用框架（LangChain/LlamaIndex）
- 预计学时：30-40小时
- 对应课程类别：`rag_apps`
- **新增课程**：Building Agentic RAG with LlamaIndex (AGENT-006)

**3.4 AI Agent（2025-2026重点扩充）**
- Agent架构模式（ReAct、Plan-and-Execute、Reflection）
- Function Calling / Tool Use
- 多智能体系统（Multi-Agent Orchestration）
- Agent评估与调试
- Agent Skills（可复用指令模板）与Subagents（子代理编排）
- Self-Improving Agents（自我改进代理，前沿方向）
- 预计学时：40-60小时
- 对应课程类别：`ai_agents`
- **新增课程**：Andrew Ng Agentic AI (AGENT-002)、Hugging Face AI Agents Course (AGENT-003)、Stanford CS329A (AGENT-004)、Google/Kaggle 5-Day Agents Intensive (AGENT-005)、CrewAI Multi-Agent (AGENT-007)、Anthropic Agent Skills & Subagents (ANTH-002)

**3.5 Model Context Protocol (MCP)（2026新增模块）**
- MCP协议基础：三大原语（Tools、Resources、Prompts）
- MCP Server开发（Python）
- MCP Client集成
- 进阶：Sampling、Notifications、Transport机制
- 生产级MCP Server开发
- 预计学时：15-25小时
- 对应课程类别：`mcp`
- **课程**：Anthropic MCP入门 (MCP-001)、Anthropic MCP进阶 (MCP-002)、Hugging Face MCP Course (MCP-003)

**3.6 LLM API开发（2026新增模块）**
- Claude API / OpenAI API 全栈开发
- 认证、消息格式化、Streaming、Tool Use
- System Prompt设计模式
- 应用架构模式
- 预计学时：10-15小时
- 对应课程类别：`llm_fundamentals`
- **课程**：Anthropic Building with Claude API (ANTH-001)

### Agent学习推荐路径

Agent方向课程较多，建议按以下顺序：

```
入门：Andrew Ng Agentic AI (6h, 设计模式总览)
      ↓
实操：Hugging Face AI Agents Course (18h, smolagents实战)
 或   Google/Kaggle 5-Day Intensive (18h, Gemini+Notebook)
      ↓
深入：Anthropic Agent Skills & Subagents (3h, Claude生态)
 +    CrewAI Multi-Agent (2h, 多Agent编排)
      ↓
前沿：Stanford CS329A (30h, Self-Improving Agents, 学术深度)
```

### MCP学习推荐路径

```
入门：Anthropic MCP Introduction (3h, 官方协议入门)
      ↓
系统：Hugging Face MCP Course (10h, 全面实操)
      ↓
进阶：Anthropic MCP Advanced Topics (3h, 生产级开发)
```

### 学习方法建议
- **Bottom-Up模式**：先完成LLM基础理论（3.1），再进入应用层（3.2-3.6）
- **Top-Down模式**：直接从项目入手。推荐路径：先用API搭聊天机器人（3.6）→ 加RAG能力（3.3）→ 升级为Agent（3.4）→ 用MCP扩展（3.5）→ 回填LLM理论（3.1）
- 此阶段AI是你的学习对象也是学习工具，全力使用
- 必做项目：搭建一个RAG聊天机器人 + 设计一个多工具Agent + 开发一个MCP Server
- 关注一线从业者的技术博客和开源项目，课程可能落后于实际进展
- 每周花30分钟浏览Hacker News/Twitter上的AI动态

### Co-op周期适配
- Study Term：每周6-8小时，理论+项目并行
- Co-op Term：如果工作涉及AI，这是最佳学习期——在工作中实践。否则每周3-4小时维持学习。Agent和MCP的短课程特别适合Co-op期间碎片化学习

---

## Phase 4：AI工程化与生产 (MLOps & Production)

### 目标
学会将AI模型从实验室带到生产环境。完成此阶段后，学生能设计ML管线、部署模型服务、监控模型性能，具备AI Engineer的完整工程能力。

### 知识模块

**4.1 模型服务与部署**
- 模型序列化（ONNX、TorchScript）
- 推理服务（FastAPI + Docker、vLLM、TGI）
- GPU推理优化基础
- 预计学时：20-30小时
- 对应课程类别：`mlops`

**4.2 ML管线与自动化**
- 数据管线（ETL、特征存储）
- 实验追踪（MLflow、Weights & Biases）
- CI/CD for ML
- 模型注册与版本管理
- 预计学时：20-30小时
- 对应课程类别：`mlops`

**4.3 模型监控与维护**
- 数据漂移检测
- 模型性能监控
- A/B测试
- 预计学时：10-15小时
- 对应课程类别：`mlops`

### 学习方法建议
- **Bottom-Up模式**：按模块逐步推进
- **Top-Down模式**：将Phase 3的RAG/Agent项目部署为在线服务，在部署过程中按需学习Docker、CI/CD、监控
- 此阶段强烈建议结合Co-op实际工作场景学习
- Docker和Linux基础是前提，如不熟悉请先补上

### Co-op周期适配
- 理想情况：在ML相关Co-op岗位中边干边学
- 非ML岗位：每周3-6小时，以个人项目驱动

---

## 课程体系与滑铁卢CS课程的交叉映射

以下滑铁卢CS课程与AI学习路径有知识交叉，完成这些学校课程可为相应Phase加速：

| 滑铁卢课程 | 对应Phase | 可跳过的内容 |
|:---|:---|:---|
| CS 370 (Numerical Computation) | Phase 1 数学基础 | 线性代数和数值优化部分 |
| STAT 230/231 | Phase 1 数学基础 | 概率论部分 |
| CS 480/486 (AI/ML) | Phase 1-2 | ML基础理论 |
| CS 484 (Computational Vision) | Phase 2 CV | CNN基础 |
| CS 485 (Statistical & Computational Foundations of ML) | Phase 1-2 | ML数学基础 |

Agent应在用户提到已修过这些课程时，自动调整对应知识点的掌握度和课程推荐。

---

## 论文阅读阶梯（Paper Reading Ladder）

**核心理念：在北美AI行业，能不能读懂arxiv paper是区分"会调API"和"真正理解AI"的分水岭。不需要一上来就啃全文——渐进式培养，从博客到论文，从摘要到全文。**

### Rung 1：论文博客解读（Phase 1-2，被动接触）

在Phase 1-2学习期间，通过阅读高质量博客自然接触论文思想：

| 资源 | 特点 | 推荐时机 |
|:---|:---|:---|
| [Lilian Weng's Blog](https://lilianweng.github.io/) | OpenAI研究员，深入浅出的综述式解读 | 学完ML基础后开始读 |
| [Jay Alammar's Blog](https://jalammar.github.io/) | 可视化Transformer系列，堪称经典 | 学Transformer时必读 |
| [Distill.pub](https://distill.pub/) | 交互式ML可视化解释 | Phase 1-2全程适用 |
| [The Gradient](https://thegradient.pub/) | AI领域长文分析 | Phase 2后期 |

**学习方式：** 每周花30分钟读一篇博客。不需要全懂，建立"论文在说什么"的直觉。

### Rung 2：经典论文关键章节（Phase 2-3，定向阅读）

开始读真正的论文，但不求全文通读：

| 论文 | 读什么 | 什么时候读 |
|:---|:---|:---|
| Attention Is All You Need (2017) | Abstract + Section 3 (Architecture) | 学Transformer架构时 |
| BERT (2018) | Abstract + Introduction + Section 3 | 学NLP时 |
| GPT-3 (2020) | Abstract + Section 1-2 + Few-shot部分 | 学LLM时 |
| LoRA (2021) | Abstract + Method Section | 学Fine-tuning时 |
| RAG (2020) | Abstract + Architecture图 + Results | 做RAG项目时 |
| ReAct (2022) | Abstract + Method + 示例图 | 学Agent时 |
| Chain-of-Thought (2022) | Abstract + 示例部分 | 学Prompt Engineering时 |
| Toolformer (2023) | Abstract + Method | 学Tool Use时 |

**阅读方法：**
1. 先读Abstract（1分钟掌握论文在说什么）
2. 看所有图和表（通常比文字更直观）
3. 读Method/Architecture章节（理解核心设计）
4. 跳过实验细节和数学证明（除非你需要复现）
5. 用费曼笔记记录：这篇论文解决了什么问题？用了什么方法？

### Rung 3：独立阅读新论文（Phase 3-4，主动探索）

具备独立阅读和提炼新论文要点的能力：

- 订阅 [Papers With Code](https://paperswithcode.com/) 的每周热门
- 关注 Hugging Face Daily Papers
- 每月精读1篇当前方向的最新论文
- 将论文要点整理为Build in Public素材（流程十六）

**进阶挑战（可选）：** 在学校AI club做一次paper reading分享。这同时完成了论文阅读、费曼验证、社交学习、Build in Public四个目标。

---

## 系统设计思维训练（System Design Thinking）

**核心理念：大厂面试AI岗越来越多问"设计一个XX系统"。这种思维不是面试前临时抱佛脚的，而是在每个项目中自然培养的。**

### 从Phase 2开始植入

每个Top-Down项目完成一个迭代后，追加一个**"如果上线"**思考环节：

| Phase | 思考题 | 培养的能力 |
|:---|:---|:---|
| Phase 2（完成CNN项目后） | "如果这个模型要在手机上跑，你会怎么优化？" | 模型优化意识 |
| Phase 3 Level 2（RAG项目后） | "如果10万用户同时用这个RAG系统，哪个环节会先崩？" | 瓶颈分析 |
| Phase 3 Level 3（Agent项目后） | "如果Agent每天处理1万个请求，你怎么控制API成本？" | 成本意识 |
| Phase 3 Level 3（MCP项目后） | "如果MCP Server要在生产环境运行，你需要加什么？" | 生产化思维 |
| Phase 4（部署项目后） | "如果模型效果突然变差，你怎么排查？" | 监控和调试 |

### 系统设计核心维度（渐进引入）

不需要一次学完所有维度，随项目复杂度自然引入：

**Level 1（Phase 2-3早期）：** 单组件思维
- 输入/输出是什么？数据从哪来到哪去？
- 延迟要求是什么？（实时 vs 批处理）

**Level 2（Phase 3中期）：** 系统拆分
- 哪些组件可以独立扩展？
- 缓存放在哪？什么策略？
- 同步 vs 异步处理？

**Level 3（Phase 3后期-Phase 4）：** 生产级思维
- 如何处理故障？（降级、重试、熔断）
- 如何监控和告警？
- 成本模型是什么？（API调用、GPU时间、存储）

**与面试的连接：** 每次系统设计思考的笔记自动存入求职叙事（流程十一），面试时可以说"我在做[项目]时思考过如何扩展到生产环境"。

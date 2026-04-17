# AI 系统化学习课程体系

本文档定义了面向滑铁卢CS Co-op学生的AI学习路径分层结构、每阶段的学习目标、核心知识点与学习方法建议。具体课程资源见 courses.json。

## 学习路径总览

```
Phase 1: 地基 (4-6月)  →  Phase 2: 核心 (6-9月)  →  Phase 3: 前沿 (6-9月)  →  Phase 4: 工程化 (3-6月)
     ↑                          ↑                          ↑                          ↑
  ML基础+数学             深度学习专项              GenAI/LLM/Agent           MLOps+生产部署
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
- 此阶段"禁用AI辅助编码"。亲手写每一行NumPy和Pandas代码，建立肌肉记忆
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
- 此阶段可开始使用AI辅助：用Cursor/Copilot加速实验代码编写，但架构设计必须自己做
- "从破译开始"：让AI生成一个完整的图像分类项目，然后你的任务是逐行理解它
- 必做项目：至少完成一个端到端的DL项目（如Kaggle图像分类竞赛）

### Co-op周期适配
- Study Term：每周6-10小时，理论+代码实战交替
- Co-op Term：每周2-4小时，利用Co-op项目场景实践DL（如工作中有数据分析需求）

---

## Phase 3：生成式AI与LLM前沿 (GenAI & LLMs)

### 目标
掌握当前最前沿的生成式AI技术。完成此阶段后，学生能理解LLM的训练与推理原理，具备Prompt Engineering能力，能设计和实现AI Agent，并能搭建RAG系统。

### 知识模块

**3.1 LLM基础**
- GPT架构演进：GPT-1/2/3/4
- LLM训练流程：预训练、SFT、RLHF/DPO
- Token化、Embedding、位置编码
- 上下文窗口、KV Cache、推理优化
- 预计学时：30-40小时
- 对应课程类别：`llm_fundamentals`

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
- LLM应用框架（LangChain/LlamaIndex）
- 预计学时：30-40小时
- 对应课程类别：`rag_apps`

**3.4 AI Agent**
- Agent架构模式（ReAct、Plan-and-Execute）
- Function Calling / Tool Use
- 多智能体系统
- Agent评估与调试
- 预计学时：20-30小时
- 对应课程类别：`ai_agents`

### 学习方法建议
- 此阶段AI是你的学习对象也是学习工具，全力使用
- 必做项目：搭建一个RAG聊天机器人 + 设计一个多工具Agent
- 关注一线从业者的技术博客和开源项目，课程可能落后于实际进展
- 每周花30分钟浏览Hacker News/Twitter上的AI动态

### Co-op周期适配
- Study Term：每周6-8小时，理论+项目并行
- Co-op Term：如果工作涉及AI，这是最佳学习期——在工作中实践。否则每周3-4小时维持学习

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
- 此阶段强烈建议结合Co-op实际工作场景学习
- 如果Co-op工作不涉及ML部署，可在个人项目中实践：将Phase 3的RAG项目部署为在线服务
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

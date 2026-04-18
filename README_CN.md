# Sloth-NorthStar-Eido

**面向滑铁卢大学 CS Co-op 学生的全人发展 Skill 家族，基于 QoderWork 构建。**

*Code wins arguments. Health wins life.*

[English](README.md) | 中文文档

---

## NorthStar 是什么？

NorthStar 是一套 QoderWork Skill 家族，专为滑铁卢大学计算机科学 Co-op 学生设计，帮助他们在四个维度实现可持续成长：**AI 学习、身体健康、心理韧性、职业发展。**

与通用效率工具不同，NorthStar 理解滑铁卢 Co-op 体系的独特节奏——Study Term 与 Co-op Term 的高强度交替、WaterlooWorks 求职的压力、以及漫长的加拿大冬季。它会根据你所处的 Co-op 周期阶段自动调整行为。

## Skill 家族成员

| Skill | 职责 | 状态 |
|:---|:---|:---|
| [sloth-northstar-learn](sloth-northstar-learn/) | AI 学习导航：课程体系、学习计划、进度追踪 | **v0.2.0** |
| [sloth-northstar-health](sloth-northstar-health/) | 身体健康守护：睡眠、锻炼、精力、维生素D | v0.1.0 |
| [sloth-northstar-mind](sloth-northstar-mind/) | 心理韧性支持：情绪追踪、专业资源、意义锚点 | v0.1.0 |
| [sloth-northstar-career](sloth-northstar-career/) | Co-op 求职助手：简历优化、面试准备、职业叙事 | v0.1.0 |
| [sloth-northstar-core](sloth-northstar-core/) | 用户画像管理与跨 Skill 协调 | v0.1.0 |

**每个 Skill 可独立运行。** 按需安装，不必全部安装。当多个 Skill 同时安装时，它们通过共享数据提供更完整的体验。

## 快速开始

### 安装

将任意 Skill 目录复制到 QoderWork skills 文件夹：

```bash
# 安装学习导航（推荐首先安装）
cp -r sloth-northstar-learn ~/.qoderwork/skills/

# 或安装全部家族成员
cp -r sloth-northstar-learn ~/.qoderwork/skills/
cp -r sloth-northstar-health ~/.qoderwork/skills/
cp -r sloth-northstar-mind ~/.qoderwork/skills/
cp -r sloth-northstar-career ~/.qoderwork/skills/
cp -r sloth-northstar-core ~/.qoderwork/skills/
```

### 首次使用

安装后，在 QoderWork 中正常对话即可。Skill 会在你提到相关话题时自动触发：

- *"我想系统学习AI"* → 触发 **learn**
- *"这周睡得很差"* → 触发 **health**
- *"Co-op压力好大"* → 触发 **mind**
- *"帮我改简历"* → 触发 **career**
- *"我现在整体情况怎么样？"* → 触发 **core**

首次使用时，Skill 只会问 2-3 个简短问题了解你的情况，没有冗长的设置流程。

## 架构设计

### 共享数据模型

所有 NorthStar Skill 通过共享目录协同：

```
~/.qoderwork/skills/sloth-northstar-data/
├── user_profile.json        # 共享用户画像（所有Skill可读，core/learn负责写入）
├── learning_progress.json   # 学习数据（learn Skill 专属）
├── health_log.json          # 健康数据（health Skill 专属）
├── mood_log.json            # 情绪数据（mind Skill 专属）
└── career_tracker.json      # 求职数据（career Skill 专属）
```

每个 Skill 拥有自己的数据文件写入权，可以读取（但不写入）其他 Skill 的数据以实现跨维度感知。

### Schema 版本管理

数据文件包含 `metadata.schema_version` 字段，支持向前兼容。learn Skill 支持从 v1.0.0 到 v1.3.0 的自动迁移，透明升级旧版数据文件，无需用户干预。

### Co-op 周期感知

NorthStar 的核心差异化能力是理解滑铁卢的 Co-op 节奏：

| 学期类型 | Learn | Health | Mind | Career |
|:---|:---|:---|:---|:---|
| **Study Term** | 全强度（6-8小时/周） | 常规监测 | 正常运行 | 休眠 |
| **Co-op Term** | 降低强度（2-4小时/周） | 适配工作时间表 | 关注环境适应压力 | 经历积累 |
| **求职季** | 暂停，切换面试准备 | 关注过劳 | 高度关注被拒压力 | 全面激活 |
| **考试周** | 完全暂停 | 最低限度保护睡眠/锻炼 | 压力感知 | 休眠 |

## AI 学习导航 (v0.2.0 亮点)

### 三种学习模式

**learn** Skill 支持三种学习方式——选择适合你风格的模式：

| 模式 | 理念 | 适合人群 |
|:---|:---|:---|
| **Bottom-Up（系统路线）** | 先打地基，再做应用 | 喜欢先理论后实践的学习者 |
| **Top-Down（项目驱动）** | 先做项目，遇到什么补什么 | 做中学、实战驱动的学习者 |
| **Hybrid Spiral（混合螺旋）** | 理论与项目交替推进 | 过了入门阶段的大多数学习者 |

### 课程体系概览

**Bottom-Up 路径（4阶段，18-30个月）：**

| 阶段 | 重点 | 时长 | 核心内容 |
|:---|:---|:---|:---|
| 1. 地基 | Python、ML基础、数学 | 4-6个月 | Scikit-learn、线性代数、概率论 |
| 2. 核心 | 深度学习 | 6-9个月 | CNN、RNN、Transformer、从零构建LLM |
| 3. 前沿 | 生成式AI与LLM | 6-9个月 | LLM原理、Prompt Engineering、RAG、Agent、MCP |
| 4. 工程化 | MLOps | 3-6个月 | 模型服务、ML CI/CD、监控 |

**Top-Down 路径（5级项目驱动）：**

| Level | 项目目标 | 预计时长 | 按需学习 |
|:---|:---|:---|:---|
| 1 | AI 聊天机器人 | 0-3个月 | API、Prompt Engineering |
| 2 | RAG 文档问答系统 | 3-6个月 | Embedding、向量检索、部署 |
| 3 | AI Agent + MCP | 6-9个月 | Tool Use、Agent编排、MCP协议 |
| 4 | LLM 微调/从零训练 | 9-12个月 | LoRA、Transformer底层 |
| 5 | 多Agent平台 | 12个月+ | 系统设计、MLOps、全栈工程 |

### 2025-2026 课程亮点

种子课程库包含 **35门免费课程**，特别关注新兴方向：

- **AI Agent**（7门）：Andrew Ng Agentic AI、HuggingFace Agents Course、Stanford CS329A、Google Agents Intensive、Microsoft Agent Academy
- **MCP**（3门）：Anthropic 官方入门+进阶、HuggingFace MCP Course
- **从零构建LLM**：Stanford CS336（Language Modeling from Scratch）
- **LLM微调**：freeCodeCamp Complete Fine-Tuning、DeepLearning.AI GRPO

### 18个工作流

learn Skill 包含18个工作流，分四层渐进式披露：

| 层级 | 包含流程 | 解锁条件 |
|:---|:---|:---|
| **核心**（1-6） | 首次使用、日常对话、计划生成、每周回顾、课程管理、Co-op周期切换 | 始终启用 |
| **每日**（7-10） | 今天学什么+时间轴、5分钟模式、知识闪回、学习Streak | 始终启用 |
| **成长**（11-15） | 求职叙事自动生成、学期交接备忘录、费曼教学、工作经历学习化、学习能量感知 | 完成首门课程后 |
| **高级**（16-18） | Build in Public、社交学习与Peer Network、成果闭环反馈 | 首次进入求职季 |

### 核心特性（v0.2.0 新增）

- **姓名个性化**：系统记住你的名字，建立学长型导师关系
- **自适应难度校准**：根据实际完成时间 vs 预估时间自动调整学习节奏
- **课程收集者防御**：活跃课程限制2门，检测到放弃模式时发出警告
- **知识雷达图**：ASCII可视化12+个AI领域的掌握程度
- **认知负荷管理**：新概念学习45分钟封顶，能量感知推荐
- **论文阅读阶梯**：3级台阶——博客解读→经典论文关键章节→独立读新论文
- **系统设计思维训练**：每个项目Level追加"如果上线到生产环境"思考题
- **Schema自动迁移**：跨版本数据格式自动升级（1.0 → 1.3）
- **课程健康检查**：季度链接有效性验证与内容时效性检查

## 重要声明

- **非医疗建议。** 健康建议为通识性内容，如有身体不适请咨询专业医疗人员。
- **非心理治疗。** Mind Skill 定位为"指路牌"而非"治疗师"，提供专业资源引荐而非临床干预。
- **非移民/法律建议。** 签证和工签问题请咨询学校的 Immigration Consultant。
- **课程信息可能过时。** 注册前请点击链接确认最新状态。

## 项目结构

```
Sloth-NorthStar-Eido/
├── README.md                          # 英文文档
├── README_CN.md                       # 本文件（中文文档）
├── LICENSE                            # MIT 许可证
├── CONTRIBUTING.md                    # 贡献指南（中英双语）
├── CHANGELOG.md                       # 版本历史
├── .gitignore
│
├── sloth-northstar-learn/             # AI 学习导航（v0.2.0）
│   ├── SKILL.md                       # 主技能定义（模块化架构，约320行）
│   ├── references/
│   │   ├── curriculum.md              # 四阶段课程体系 + 论文阶梯 + 系统设计
│   │   ├── courses.json               # 35门种子课程
│   │   ├── top_down_projects.md       # 5级项目驱动路径
│   │   └── workflows/
│   │       ├── workflows_core.md      # 流程一~六：核心流程
│   │       ├── workflows_daily.md     # 流程七~十：每日交互
│   │       ├── workflows_growth.md    # 流程十一~十五：成长加速
│   │       └── workflows_advanced.md  # 流程十六~十八：高级功能
│   └── templates/
│       ├── user_profile_template.json     # Schema v1.3.0
│       └── learning_progress_template.json # Schema v1.3.0
│
├── sloth-northstar-health/            # 身体健康守护
│   ├── SKILL.md
│   └── templates/
│       └── health_log_template.json
│
├── sloth-northstar-mind/              # 心理韧性支持
│   ├── SKILL.md
│   ├── references/
│   │   └── mental_health_resources.md # 专业心理健康资源目录
│   └── templates/
│       └── mood_log_template.json
│
├── sloth-northstar-career/            # Co-op 求职助手
│   ├── SKILL.md
│   └── templates/
│       └── career_tracker_template.json
│
└── sloth-northstar-core/              # 画像与协调中心
    ├── SKILL.md
    └── templates/
        └── user_profile_template.json
```

## 参与贡献

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md)。我们欢迎在课程数据库更新、资源目录维护和 Skill 改进方面的贡献。

## 许可证

[MIT](LICENSE)

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
| [sloth-northstar-learn](sloth-northstar-learn/) | AI 学习导航：课程体系、学习计划、进度追踪 | v0.1.0 |
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

### Co-op 周期感知

NorthStar 的核心差异化能力是理解滑铁卢的 Co-op 节奏：

| 学期类型 | Learn | Health | Mind | Career |
|:---|:---|:---|:---|:---|
| **Study Term** | 全强度（6-8小时/周） | 常规监测 | 正常运行 | 休眠 |
| **Co-op Term** | 降低强度（2-4小时/周） | 适配工作时间表 | 关注环境适应压力 | 经历积累 |
| **求职季** | 暂停，切换面试准备 | 关注过劳 | 高度关注被拒压力 | 全面激活 |
| **考试周** | 完全暂停 | 最低限度保护睡眠/锻炼 | 压力感知 | 休眠 |

## AI 学习课程体系

**learn** Skill 提供结构化的四阶段 AI 学习路径（18-30个月）：

| 阶段 | 重点 | 时长 | 核心内容 |
|:---|:---|:---|:---|
| 1. 地基 | Python、ML基础、数学 | 4-6个月 | Scikit-learn、线性代数、概率论 |
| 2. 核心 | 深度学习 | 6-9个月 | CNN、RNN、Transformer架构 |
| 3. 前沿 | 生成式AI与LLM | 6-9个月 | LLM原理、Prompt Engineering、RAG、Agent |
| 4. 工程化 | MLOps | 3-6个月 | 模型服务、ML CI/CD、监控 |

内含 19 门来自顶级平台的免费种子课程（DeepLearning.AI、Stanford、fast.ai、Microsoft 等）。

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
├── sloth-northstar-learn/             # AI 学习导航
│   ├── SKILL.md
│   ├── references/
│   │   ├── curriculum.md              # 四阶段课程体系详情
│   │   └── courses.json               # 19门种子课程
│   └── templates/
│       ├── user_profile_template.json
│       └── learning_progress_template.json
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
        （使用 learn/ 中的 user_profile_template）
```

## 参与贡献

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md)。我们欢迎在课程数据库更新、资源目录维护和 Skill 改进方面的贡献。

## 许可证

[MIT](LICENSE)

---
name: Sloth-NorthStar-Eido
version: 0.2.0
description: >-
  Holistic development skill family for University of Waterloo CS Co-op students —
  AI learning navigator, physical health companion, mental resilience support,
  and career development assistant, all aware of the Co-op cycle rhythm.
  Use when user mentions AI learning, study plan, health tracking, mental wellness,
  Co-op job search, resume, interview prep, or overall student life management.
description_zh: >-
  面向滑铁卢大学 CS Co-op 学生的全人发展技能家族：AI 学习导航、身体健康守护、
  心理韧性支持、求职职业助手，全部感知 Co-op 周期节奏。
author: sloth-lab
tags:
  - student-development
  - ai-learning
  - health-tracking
  - mental-resilience
  - career-development
  - waterloo-coop
---

# Sloth-NorthStar-Eido

> <p align="center"><img src="https://raw.githubusercontent.com/wangguobao0215/Sloth-NorthStar-Eido/main/assets/qrcode.jpg" width="80" /><br/><sub>扫码关注 <b>树懒老K</b> · 获取更多 AI 技能</sub><br/><i>慢一点，深一度</i></p>
>
> Code wins arguments. Health wins life.

## 概述

Sloth-NorthStar-Eido 是一个技能家族（Skill Family），不是单一技能。它由 5 个独立子技能组成，共同服务于滑铁卢大学 CS Co-op 学生的全人发展。

本 SKILL.md 作为家族总入口，负责路由和协调。每个子技能有自己独立的 SKILL.md。

## 子技能路由

根据用户意图，路由到对应子技能：

| 触发场景 | 路由目标 | 子技能路径 |
|----------|----------|-----------|
| AI 学习、课程、学习计划、进度 | Learn | `sloth-northstar-learn/SKILL.md` |
| 睡眠、锻炼、精力、维生素 D | Health | `sloth-northstar-health/SKILL.md` |
| 压力、焦虑、情绪、心理资源 | Mind | `sloth-northstar-mind/SKILL.md` |
| 简历、面试、Co-op 求职、职业叙事 | Career | `sloth-northstar-career/SKILL.md` |
| 整体状态、个人设置、学期切换 | Core | `sloth-northstar-core/SKILL.md` |

## 家族协作机制

所有子技能通过共享数据目录协同工作：

```
~/.qoderwork/skills/sloth-northstar-data/
├── user_profile.json        # 共享用户画像
├── learning_progress.json   # 学习数据（Learn 专属写入）
├── health_log.json          # 健康数据（Health 专属写入）
├── mood_log.json            # 情绪数据（Mind 专属写入）
└── career_tracker.json      # 求职数据（Career 专属写入）
```

每个子技能拥有自己数据文件的写入权，可以读取其他子技能的数据实现跨维度感知。

## Co-op 周期感知

核心差异化能力 — 根据学生所处的 Co-op 阶段自动调整各子技能的行为：

| 学期类型 | Learn | Health | Mind | Career |
|----------|-------|--------|------|--------|
| Study Term | 全强度 | 常规监测 | 正常 | 休眠 |
| Co-op Term | 降低强度 | 适配工作节奏 | 关注适应压力 | 经历积累 |
| 求职季 | 暂停，切换面试准备 | 关注过劳 | 高度关注被拒压力 | 全面激活 |
| 考试周 | 完全暂停 | 最低保护 | 压力感知 | 休眠 |

## 约束

- 各子技能可独立运行，按需安装
- 健康建议为通识性内容，非医疗建议
- 心理支持定位为"指路牌"，非心理治疗
- 课程信息可能过时，使用前需验证

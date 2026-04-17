# Contributing to Sloth-NorthStar-Eido

[中文版](#中文) | [English](#english)

---

<a name="english"></a>

## English

Thank you for your interest in contributing to Sloth-NorthStar-Eido! This project aims to support University of Waterloo CS Co-op students in achieving holistic development through AI-powered skills.

### How to Contribute

#### Reporting Issues
- Use GitHub Issues to report bugs or suggest features
- Include the skill name (e.g., `sloth-northstar-learn`) in the issue title
- Provide clear steps to reproduce for bugs

#### Submitting Changes

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes following the guidelines below
4. Commit with clear messages: `git commit -m "feat(learn): add new course to seed database"`
5. Push and create a Pull Request

#### Commit Message Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

Types: feat, fix, docs, refactor, test
Scopes: learn, health, mind, career, core, docs
```

### Skill Development Guidelines

#### SKILL.md Standards
- Keep SKILL.md under 500 lines
- Use YAML frontmatter with `name` (lowercase, hyphens, max 64 chars) and `description` (max 1024 chars)
- Reference files must be one level deep (no nested references)
- Write descriptions in third person
- Include both WHAT the skill does and WHEN to use it

#### Data Files
- All shared data goes to `~/.qoderwork/skills/sloth-northstar-data/`
- Each skill only writes to its own data files
- Use JSON format with `metadata.schema_version` for future migrations
- Always provide templates in `templates/` directory

#### Course Database (courses.json)
- All courses must be free or have a free audit option
- Include `last_verified` date
- Required fields: `course_id`, `title`, `provider`, `url`, `phase`, `category`, `estimated_hours`, `free`, `status`

#### Mental Health Content
- **Never** provide diagnostic or therapeutic content
- Always include professional resource references
- Use "signpost" approach: acknowledge, normalize, direct to action/resources
- Append disclaimer to all mental health related outputs

### Code of Conduct

- Be respectful and constructive
- Focus on the wellbeing of end users (students)
- When in doubt about mental health content, err on the side of caution

---

<a name="中文"></a>

## 中文

感谢你对 Sloth-NorthStar-Eido 项目的关注！本项目旨在通过AI驱动的Skill帮助滑铁卢大学CS Co-op学生实现全人发展。

### 如何贡献

#### 报告问题
- 使用 GitHub Issues 报告Bug或建议功能
- 在Issue标题中包含Skill名称（如 `sloth-northstar-learn`）
- Bug报告请提供清晰的复现步骤

#### 提交更改

1. Fork 仓库
2. 创建功能分支：`git checkout -b feature/你的功能名`
3. 按照以下规范进行修改
4. 使用清晰的提交信息：`git commit -m "feat(learn): 添加新课程到种子数据库"`
5. Push 并创建 Pull Request

#### 提交信息规范

遵循 [Conventional Commits](https://www.conventionalcommits.org/)：

```
<类型>(<范围>): <描述>

类型: feat(新功能), fix(修复), docs(文档), refactor(重构), test(测试)
范围: learn, health, mind, career, core, docs
```

### Skill 开发规范

#### SKILL.md 标准
- SKILL.md 保持在 500 行以内
- 使用 YAML frontmatter，包含 `name`（小写+连字符，最长64字符）和 `description`（最长1024字符）
- 引用文件仅一层深度（不嵌套引用）
- description 使用第三人称
- 同时说明 Skill 做什么（WHAT）和何时使用（WHEN）

#### 数据文件
- 共享数据统一存放至 `~/.qoderwork/skills/sloth-northstar-data/`
- 每个Skill只写入自己负责的数据文件
- 使用JSON格式，包含 `metadata.schema_version` 以支持未来迁移
- 在 `templates/` 目录中提供数据模板

#### 课程数据库 (courses.json)
- 所有课程必须免费或支持免费旁听
- 包含 `last_verified` 日期
- 必填字段：`course_id`、`title`、`provider`、`url`、`phase`、`category`、`estimated_hours`、`free`、`status`

#### 心理健康内容
- **绝不**提供诊断或治疗性内容
- 始终附带专业资源引用
- 使用"指路牌"策略：承认、正常化、引导行动/资源
- 所有心理健康相关输出末尾附加免责声明

### 行为准则

- 保持尊重与建设性
- 以终端用户（学生）的福祉为优先
- 对心理健康内容有疑问时，选择更谨慎的方案

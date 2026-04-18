# 高级流程（流程十六~十八）

> 本文件包含高级学习机制：Build in Public、社交学习、成果闭环反馈。
> 这些流程在用户达到特定里程碑后渐进式引入（详见SKILL.md渐进式功能披露规则）。

### 流程十六：Build in Public（公开输出机制）

**核心理念：在北美AI行业，你的public presence和你的技术能力一样重要。闷头学100门课不如公开写10篇技术博客。GitHub活跃度、技术写作、开源贡献——这些才是hiring manager真正会看的东西。**

**触发条件：**
- 用户完成一个课程模块或项目迭代
- 每月自动检查一次：如有可输出的内容但用户未输出，温和提醒
- 用户主动说"我想写个博客"或"我想整理一下学的东西"

**公开输出类型（由易到难）：**

1. **Level 1 - 学习笔记（最低门槛）**
   - 把费曼笔记整理成一篇简短的技术笔记
   - 平台：Notion公开页、个人博客、GitHub Gist
   - 模板："今天学了[X]，核心概念是[Y]，我理解的类比是[Z]"
   - 预计时间：15-30分钟

2. **Level 2 - 技术博客**
   - 将一个知识模块的学习过程写成教程式文章
   - 平台：Medium、Dev.to、个人博客、公众号
   - 模板：问题引入 → 我学到了什么 → 代码示例 → 踩坑经验
   - 预计时间：1-2小时

3. **Level 3 - 项目README + Demo**
   - 将项目写成规范的GitHub repo：README、代码、截图/GIF
   - 必须包含：项目描述、技术栈、如何运行、学到了什么
   - 预计时间：2-3小时

4. **Level 4 - 技术分享 / Lightning Talk**
   - 在学校AI club或线上社区做5-10分钟的分享
   - 内容来源：费曼笔记 + 项目demo
   - 预计时间：准备2-3小时

**输出引导逻辑：**

当用户完成一个课程模块时：
```
🌐 Build in Public 建议：
[名字]，你刚学完 [知识点]。要不要花15分钟把你的理解写下来？

📝 最简版：写一条200字的学习笔记发到GitHub Gist
📝 标准版：整理成一篇技术博客（费曼笔记已经帮你打好了草稿）
📝 进阶版：如果这是一个项目，把它推到GitHub并写好README

你的费曼笔记可以直接作为素材：
"[引用用户之前的费曼解释]"
```

**与费曼笔记联动（流程十三）：** 费曼笔记是公开输出的天然草稿。系统自动将高质量的费曼笔记标记为"可发布素材"。

**数据存储：** 存储在 learning_progress.json 的 `public_outputs` 数组中：
```json
{
  "public_outputs": [
    {
      "date": "2026-04-18",
      "type": "blog_post",
      "title": "RAG入门：我是怎么搭文档问答系统的",
      "platform": "Medium",
      "url": "https://...",
      "knowledge_nodes": ["RAG", "Embedding"],
      "source_feynman_notes": ["note_id_1"]
    }
  ]
}
```

### 流程十七：社交学习与Peer Network

**核心理念：滑铁卢最大的资产不是课程，是人。你的同学里有未来的Google Staff Engineer和YC创始人。独学而无友，则孤陋而寡闻。**

**触发条件：**
- 首次使用后第2-3次对话中，自然引入社交学习概念
- 用户完成一个里程碑时建议分享
- 用户表达学习孤独感时（"一个人学好无聊"、"没人讨论"）

**社交学习维度：**

1. **学习搭子（Study Buddy）**
   - 在每月回顾时建议："[名字]，找一个也在学AI的朋友做互相的费曼验证搭子，效果会好很多。"
   - 推荐方式：在CS课上找、UW AI club、Waterloo Tech社群
   - 记录搭子信息（可选），在生成复习内容时可以加一句"这个可以跟你搭子互相考一下"

2. **社区参与**
   - 推荐参加：UW Data Science Club、UW AI Society、Kaggle competitions
   - Co-op期间：参加公司内部Tech Talk、Lunch & Learn
   - 线上：在Discord/Reddit/Stack Overflow上回答AI相关问题
   - 每回答一个别人的问题 → 等同于一次费曼验证，knowledge_map中相关节点 +0.05

3. **Lightning Talk挑战**
   - 每完成一个Phase，挑战一次5分钟lightning talk
   - 可以在学校club、朋友面前、甚至录个视频发到YouTube
   - 这是Build in Public的最高形式，也是面试presentation能力的最佳训练

**社交学习记录格式：**
```
👥 社交学习记录：
[名字]在 [场景] 中 [做了什么]

📌 效果：[对学习的促进作用]
📈 知识加成：[相关节点] +0.05（教别人/回答问题的加成）
```

**数据存储：** 存储在 learning_progress.json 的 `peer_activities` 数组中：
```json
{
  "peer_activities": [
    {
      "date": "2026-04-18",
      "type": "answered_question",
      "context": "Reddit r/MachineLearning",
      "topic": "RAG vs Fine-tuning选择",
      "knowledge_nodes_reinforced": ["RAG", "Fine_Tuning"],
      "mastery_boost": 0.05
    }
  ]
}
```

**不施压原则：** 社交学习是加分项，不是必修。有些人就是喜欢独自学习，那也完全OK。只建议，不强推。

### 流程十八：成果闭环反馈

**核心理念：开环系统会让你越走越偏。学了什么有用、什么没用，只有面试和工作能告诉你。让真实结果回流，让系统越来越聪明。**

**触发条件：**
- 用户进入求职季（学期切换到 job_search）
- 用户说"我拿到offer了"或"面试完了"
- 每个Co-op term结束时主动触发一次

**反馈收集流程：**

1. **面试复盘**（每次面试后）：
```
🎯 面试复盘：
[名字]，面试怎么样？聊几个问题帮你下次更好准备：

1. 面试中有问到AI/ML相关的问题吗？具体问了什么？
2. 你的AI学习经历在面试中有被提到吗？面试官的反应怎么样？
3. 有没有哪个知识点你觉得"要是当时学了就好了"？
```

2. **Offer复盘**（拿到/没拿到结果后）：
   - 拿到offer → "恭喜！这个岗位和你学的哪些AI技能最相关？"
   - 没拿到 → "没关系。你觉得技术面中哪个环节最需要加强？"

3. **Co-op工作期中复盘**（Co-op第4周自动触发）：
   - "工作一个月了，你觉得之前学的AI知识哪些用上了？哪些完全没用到？"

**反馈回流机制：**

收集到的反馈自动调整系统行为：
- **面试高频考点** → 在 knowledge_map 中标记为 `interview_hot`，优先推荐相关课程
- **"要是学了就好了"的知识点** → 自动加入下个学期的学习计划
- **实际工作用到的技能** → 掌握度加成 + 标记为 `practical_value: high`
- **学了但没用到的内容** → 不删除，但在排优先级时降权

**数据存储：** 存储在 learning_progress.json 的 `outcome_feedback` 数组中：
```json
{
  "outcome_feedback": [
    {
      "date": "2026-04-18",
      "type": "interview_debrief",
      "company": "匿名",
      "role": "AI/ML Intern",
      "ai_questions_asked": ["System Design: design a RAG system", "Explain Transformer attention"],
      "knowledge_gaps_identified": ["System_Design", "Distributed_Systems"],
      "learning_narrative_mentioned": true,
      "interviewer_reaction": "positive",
      "outcome": "pending"
    }
  ]
}
```

**长期价值：** 随着反馈积累，系统会逐渐学会"什么对这个特定学生最有价值"。这不是通用推荐，而是基于真实求职市场信号的个性化优化。

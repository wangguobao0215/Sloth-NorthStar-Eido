# Sloth-NorthStar-Eido

**A holistic development skill family for University of Waterloo CS Co-op students, powered by QoderWork.**

*Code wins arguments. Health wins life.*

[中文文档](README.md) | English

---

## What is NorthStar?

NorthStar is a family of QoderWork Skills designed to help University of Waterloo CS Co-op students achieve sustainable growth across four dimensions: **AI learning, physical health, mental resilience, and career development.**

Unlike generic productivity tools, NorthStar understands the unique rhythm of Waterloo's Co-op system — the intense alternation between study terms and work terms, the pressure of WaterlooWorks job searches, and the long Canadian winters. It adapts its behavior based on what phase of the Co-op cycle you're in.

## Skill Family

| Skill | Purpose | Status |
|:---|:---|:---|
| [sloth-northstar-learn](sloth-northstar-learn/) | AI learning navigator: curriculum, study plans, progress tracking | **v0.2.0** |
| [sloth-northstar-health](sloth-northstar-health/) | Physical health companion: sleep, exercise, energy, Vitamin D | v0.1.0 |
| [sloth-northstar-mind](sloth-northstar-mind/) | Mental resilience support: mood tracking, resources, meaning anchors | v0.1.0 |
| [sloth-northstar-career](sloth-northstar-career/) | Co-op career assistant: resume, interviews, career narrative | v0.1.0 |
| [sloth-northstar-core](sloth-northstar-core/) | User profile management and cross-skill coordination | v0.1.0 |

**Each skill works independently.** Install only what you need. When multiple skills are installed, they share data to provide a more integrated experience.

## Quick Start

### Installation

Copy any skill directory to your QoderWork skills folder:

```bash
# Install the learning navigator (recommended to start with)
cp -r sloth-northstar-learn ~/.qoderwork/skills/

# Or install the entire family
cp -r sloth-northstar-learn ~/.qoderwork/skills/
cp -r sloth-northstar-health ~/.qoderwork/skills/
cp -r sloth-northstar-mind ~/.qoderwork/skills/
cp -r sloth-northstar-career ~/.qoderwork/skills/
cp -r sloth-northstar-core ~/.qoderwork/skills/
```

### First Use

Once installed, simply start a conversation in QoderWork. The skill will be triggered automatically when you mention relevant topics:

- *"I want to start learning AI systematically"* → triggers **learn**
- *"I've been sleeping terribly this week"* → triggers **health**
- *"I feel so stressed about Co-op"* → triggers **mind**
- *"Help me polish my resume"* → triggers **career**
- *"What's my overall status?"* → triggers **core**

On first use, the skill will ask 2-3 quick questions to understand your situation — no lengthy setup wizards.

## Architecture

### Shared Data Model

All NorthStar skills share data through a common directory:

```
~/.qoderwork/skills/sloth-northstar-data/
├── user_profile.json        # Shared user profile (all skills read, core/learn write)
├── learning_progress.json   # Learning data (learn skill)
├── health_log.json          # Health data (health skill)
├── mood_log.json            # Mood data (mind skill)
└── career_tracker.json      # Career data (career skill)
```

Each skill owns its data file and can read (but not write) other skills' data for cross-dimensional awareness.

### Schema Versioning

Data files include `metadata.schema_version` for forward compatibility. The learn skill supports automatic migration from v1.0.0 through v1.3.0, transparently upgrading older data files without user intervention.

### Co-op Cycle Awareness

The core differentiator of NorthStar is its understanding of Waterloo's Co-op rhythm:

| Term Type | Learn | Health | Mind | Career |
|:---|:---|:---|:---|:---|
| **Study Term** | Full intensity (6-8 hrs/week) | Standard monitoring | Normal | Dormant |
| **Co-op Term** | Reduced (2-4 hrs/week) | Adapt to work schedule | Watch for adjustment stress | Experience accumulation |
| **Job Search** | Paused, switch to interview prep | Watch for burnout | High alert for rejection stress | Full activation |
| **Exam Period** | Suspended entirely | Minimum sleep/exercise protection | Stress awareness | Dormant |

## AI Learning Navigator (v0.2.0 Highlights)

### Three Learning Modes

The **learn** skill supports three approaches — choose the one that fits your style:

| Mode | Philosophy | Best For |
|:---|:---|:---|
| **Bottom-Up** | Build foundations first, then apply | Learners who prefer solid theory before practice |
| **Top-Down** | Start with a project, backfill knowledge gaps | Learners who are motivated by building things |
| **Hybrid Spiral** | Alternate between theory and projects | Most learners after the initial phase |

### Curriculum Overview

**Bottom-Up Path (4 phases, 18-30 months):**

| Phase | Focus | Duration | Key Topics |
|:---|:---|:---|:---|
| 1. Foundations | Python, ML basics, Math | 4-6 months | Scikit-learn, Linear Algebra, Probability |
| 2. Core | Deep Learning | 6-9 months | CNN, RNN, Transformer, Build LLM from Scratch |
| 3. Frontier | GenAI & LLMs | 6-9 months | LLM internals, Prompt Engineering, RAG, Agents, MCP |
| 4. Engineering | MLOps | 3-6 months | Model serving, CI/CD for ML, Monitoring |

**Top-Down Path (5 levels, project-driven):**

| Level | Project Goal | Duration | Learn As Needed |
|:---|:---|:---|:---|
| 1 | AI Chatbot | 0-3 months | API, Prompt Engineering |
| 2 | RAG Document QA | 3-6 months | Embeddings, Vector Search, Deployment |
| 3 | AI Agent + MCP | 6-9 months | Tool Use, Agent Orchestration, MCP Protocol |
| 4 | LLM Fine-tuning | 9-12 months | LoRA, Transformer Internals |
| 5 | Multi-Agent Platform | 12+ months | System Design, MLOps, Full-stack |

### 2025-2026 Course Highlights

The seed database includes **35 free courses** from top providers, with special focus on emerging directions:

- **AI Agents** (7 courses): Andrew Ng Agentic AI, HuggingFace Agents Course, Stanford CS329A, Google Agents Intensive, Microsoft Agent Academy
- **MCP** (3 courses): Anthropic official intro + advanced, HuggingFace MCP Course
- **LLM from Scratch**: Stanford CS336 (Language Modeling from Scratch)
- **LLM Fine-tuning**: freeCodeCamp Complete Fine-Tuning, DeepLearning.AI GRPO

### 18 Workflows

The learn skill includes 18 workflows organized into four tiers with progressive disclosure:

| Tier | Workflows | Unlocked |
|:---|:---|:---|
| **Core** (1-6) | First use, daily conversation, plan generation, weekly review, course management, Co-op cycle switch | Always |
| **Daily** (7-10) | "What to learn today" + timeline, 5-min mode, knowledge flashback, learning streak | Always |
| **Growth** (11-15) | Job narrative generation, semester handover memo, Feynman teaching, work experience integration, energy awareness | After completing first course |
| **Advanced** (16-18) | Build in Public, social learning & peer network, outcome feedback loop | After first job search season |

### Key Features (New in v0.2.0)

- **Name Personalization**: The system remembers your name and builds a mentor-student relationship
- **Adaptive Difficulty Calibration**: Automatically adjusts pace based on actual vs. estimated completion time
- **Course Collector Defense**: Limits active courses to 2, warns if abandonment pattern detected
- **Knowledge Radar Chart**: ASCII visualization of skill mastery across 12+ AI domains
- **Cognitive Load Management**: 45-minute cap on new concept learning, energy-aware recommendations
- **Paper Reading Ladder**: 3-rung progression from blog summaries to independent paper reading
- **System Design Thinking**: "What if deployed to production?" exercises at each project level
- **Schema Migration**: Automatic data format upgrades across versions (1.0 → 1.3)
- **Course Health Check**: Quarterly link validation and freshness verification

## Important Disclaimers

- **Not medical advice.** Health suggestions are general wellness tips. Consult a healthcare professional for medical concerns.
- **Not mental health treatment.** The mind skill is a "signpost," not a therapist. It provides professional resource referrals, not clinical intervention.
- **Not immigration/legal advice.** For visa and work permit questions, consult UW's Immigration Consultant.
- **Course information may be outdated.** Always verify links and availability before enrolling.

## Project Structure

```
Sloth-NorthStar-Eido/
├── SKILL.md                           # Family-level skill definition
├── README.md                          # Chinese documentation
├── README_EN.md                       # This file (English)
├── LICENSE                            # MIT License
├── CONTRIBUTING.md                    # Contribution guidelines (bilingual)
├── CHANGELOG.md                       # Version history
├── .gitignore
│
├── sloth-northstar-learn/             # AI Learning Navigator (v0.2.0)
│   ├── SKILL.md                       # Main skill definition (modular, ~320 lines)
│   ├── references/
│   │   ├── curriculum.md              # 4-phase curriculum + paper ladder + system design
│   │   ├── courses.json               # 35 seed courses
│   │   ├── top_down_projects.md       # 5-level project-driven path
│   │   └── workflows/
│   │       ├── workflows_core.md      # Workflows 1-6: core flows
│   │       ├── workflows_daily.md     # Workflows 7-10: daily interactions
│   │       ├── workflows_growth.md    # Workflows 11-15: growth acceleration
│   │       └── workflows_advanced.md  # Workflows 16-18: advanced features
│   └── templates/
│       ├── user_profile_template.json     # Schema v1.3.0
│       └── learning_progress_template.json # Schema v1.3.0
│
├── sloth-northstar-health/            # Physical Health Companion
│   ├── SKILL.md
│   └── templates/
│       └── health_log_template.json
│
├── sloth-northstar-mind/              # Mental Resilience Support
│   ├── SKILL.md
│   ├── references/
│   │   └── mental_health_resources.md # Professional resource directory
│   └── templates/
│       └── mood_log_template.json
│
├── sloth-northstar-career/            # Co-op Career Assistant
│   ├── SKILL.md
│   └── templates/
│       └── career_tracker_template.json
│
└── sloth-northstar-core/              # Profile & Coordination Center
    ├── SKILL.md
    └── templates/
        └── user_profile_template.json
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. We welcome contributions in course database updates, resource directory maintenance, and skill improvements.

## License

[MIT](LICENSE)

# Sloth-NorthStar-Eido

**A holistic development skill family for University of Waterloo CS Co-op students, powered by QoderWork.**

*Code wins arguments. Health wins life.*

[中文文档](README_CN.md) | English

---

## What is NorthStar?

NorthStar is a family of QoderWork Skills designed to help University of Waterloo CS Co-op students achieve sustainable growth across four dimensions: **AI learning, physical health, mental resilience, and career development.**

Unlike generic productivity tools, NorthStar understands the unique rhythm of Waterloo's Co-op system — the intense alternation between study terms and work terms, the pressure of WaterlooWorks job searches, and the long Canadian winters. It adapts its behavior based on what phase of the Co-op cycle you're in.

## Skill Family

| Skill | Purpose | Status |
|:---|:---|:---|
| [sloth-northstar-learn](sloth-northstar-learn/) | AI learning navigator: curriculum, study plans, progress tracking | v0.1.0 |
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

### Co-op Cycle Awareness

The core differentiator of NorthStar is its understanding of Waterloo's Co-op rhythm:

| Term Type | Learn | Health | Mind | Career |
|:---|:---|:---|:---|:---|
| **Study Term** | Full intensity (6-8 hrs/week) | Standard monitoring | Normal | Dormant |
| **Co-op Term** | Reduced (2-4 hrs/week) | Adapt to work schedule | Watch for adjustment stress | Experience accumulation |
| **Job Search** | Paused, switch to interview prep | Watch for burnout | High alert for rejection stress | Full activation |
| **Exam Period** | Suspended entirely | Minimum sleep/exercise protection | Stress awareness | Dormant |

## AI Learning Curriculum

The **learn** skill provides a structured 4-phase AI learning path (18-30 months):

| Phase | Focus | Duration | Key Topics |
|:---|:---|:---|:---|
| 1. Foundations | Python, ML basics, Math | 4-6 months | Scikit-learn, Linear Algebra, Probability |
| 2. Core | Deep Learning | 6-9 months | CNN, RNN, Transformer architecture |
| 3. Frontier | GenAI & LLMs | 6-9 months | LLM internals, Prompt Engineering, RAG, Agents |
| 4. Engineering | MLOps | 3-6 months | Model serving, CI/CD for ML, Monitoring |

Includes a seed database of 19 free courses from top providers (DeepLearning.AI, Stanford, fast.ai, Microsoft, etc.).

## Important Disclaimers

- **Not medical advice.** Health suggestions are general wellness tips. Consult a healthcare professional for medical concerns.
- **Not mental health treatment.** The mind skill is a "signpost," not a therapist. It provides professional resource referrals, not clinical intervention.
- **Not immigration/legal advice.** For visa and work permit questions, consult UW's Immigration Consultant.
- **Course information may be outdated.** Always verify links and availability before enrolling.

## Project Structure

```
Sloth-NorthStar-Eido/
├── README.md                          # This file (English)
├── README_CN.md                       # Chinese documentation
├── LICENSE                            # MIT License
├── CONTRIBUTING.md                    # Contribution guidelines (bilingual)
├── CHANGELOG.md                       # Version history
├── .gitignore
│
├── sloth-northstar-learn/             # AI Learning Navigator
│   ├── SKILL.md
│   ├── references/
│   │   ├── curriculum.md              # 4-phase curriculum details
│   │   └── courses.json               # 19 seed courses
│   └── templates/
│       ├── user_profile_template.json
│       └── learning_progress_template.json
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
        (uses user_profile_template from learn/)
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. We welcome contributions in course database updates, resource directory maintenance, and skill improvements.

## License

[MIT](LICENSE)

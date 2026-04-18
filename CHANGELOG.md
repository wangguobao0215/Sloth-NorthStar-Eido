# Changelog

All notable changes to Sloth-NorthStar-Eido will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2026-04-18

### Added (sloth-northstar-learn)

#### Course System
- Expanded seed course database from 19 to **35 courses**
- Added `learning_mode` field to all courses (`bottom_up` / `top_down`)
- New course categories: `mcp` (3 courses), `ai_agents` (7 courses)
- Key additions: Anthropic Academy series, Stanford CS329A/CS336, Andrew Ng Agentic AI, HuggingFace Agents/MCP courses, Google Agents Intensive, Microsoft Agent Academy
- Added course health check mechanism with quarterly validation schedule

#### Learning Methodology
- Three learning modes: Bottom-Up, Top-Down, Hybrid Spiral
- 5-level project-driven path (`top_down_projects.md`): AI Chatbot → RAG QA → AI Agent → LLM Fine-tuning → Multi-Agent Platform
- Paper reading ladder: 3-rung progression (blog summaries → key paper sections → independent reading)
- System Design thinking exercises at each project level

#### 18 Workflows (up from 6)
- **Core (1-6)**: First use, daily conversation, plan generation, weekly review, course management (with collector defense), Co-op cycle switch
- **Daily (7-10)**: "What to learn today" + daily timeline, 5-minute mode, knowledge flashback (spaced repetition), learning streak tracking with milestone celebrations
- **Growth (11-15)**: Job narrative auto-generation (STAR format), semester handover memo, Feynman teaching mechanism, Co-op work experience learning integration, learning energy awareness with cognitive load theory
- **Advanced (16-18)**: Build in Public guidance, social learning & peer network, outcome feedback loop

#### UX & Personalization
- Name personalization and mentor-student relationship building
- Adaptive difficulty calibration based on actual vs. estimated completion time
- Course collector defense: max 2 active courses, abandonment pattern warning
- Knowledge radar chart: ASCII visualization of skill mastery across 12+ domains
- Cognitive load management: 45-minute cap on new concept learning
- Progressive feature disclosure: Tier 1 (new users) → Tier 2 (after first course) → Tier 3 (job search season)

#### Architecture
- Refactored SKILL.md from ~939 lines to ~320 lines (modular architecture)
- Split 18 workflows into 4 categorized files under `references/workflows/`
- Schema versioning upgraded to v1.3.0 with automatic migration (1.0 → 1.1 → 1.2 → 1.3)
- Added `energy_pattern` to user profile template

### Changed (sloth-northstar-learn)
- Expanded `curriculum.md` with MCP module (Phase 3.5), LLM API module (Phase 3.6), paper reading ladder, and system design training
- Updated both template files to Schema v1.3.0 with 19 data fields

### Fixed
- Course count mismatch: SKILL.md referenced 34 courses but courses.json contained 35
- Field name inconsistency: unified `milestone_reached` to `milestones_reached` (plural)

### Changed (sloth-northstar-core)
- Updated `user_profile_template.json` to Schema v1.3.0

## [0.1.0] - 2026-04-17

### Added
- **sloth-northstar-learn**: AI learning navigator with 4-phase curriculum, 19 seed courses, progress tracking, and Co-op cycle awareness
- **sloth-northstar-health**: Physical health companion with sleep/exercise tracking, energy monitoring, winter mode, and Vitamin D reminders
- **sloth-northstar-mind**: Mental resilience support with mood tracking, meaning anchors, professional resource directory, and crisis signal response protocol
- **sloth-northstar-career**: Co-op career assistant with resume optimization (CAR framework), interview prep, career narrative builder, and WaterlooWorks strategy
- **sloth-northstar-core**: Unified user profile management, term type switching, fixed anchor configuration, and family status overview
- Shared data architecture via `~/.qoderwork/skills/sloth-northstar-data/`
- Bilingual documentation (English + Chinese)
- Data templates for all skills
- Seed course database (courses.json) with 19 free AI/ML courses
- Mental health professional resource directory for Waterloo region

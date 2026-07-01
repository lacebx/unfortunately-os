# unfortunately-os

The operating system for Unfortunately.

---

## Purpose

This repository is the single source of truth for everything Unfortunately knows, builds, and decides. It is not a code repository. It is the company's internal headquarters — a living document system that grows every day.

Every AI assistant (Comet, Claude, ChatGPT, Cursor, local models) should read from this repository before acting and append to it after learning.

---

## Repository Layout

```
/
├── README.md               # This file
├── MISSION.md              # Why Unfortunately exists
├── VALUES.md               # How we operate
├── STYLE.md                # Voice and tone guidelines
├── AGENTS.md               # Rules for all AI agents
├── CEO_BRIEF.md            # Daily executive summary (regenerated each morning)
├── TODAY.md                # Today's executable task list
├── ROADMAP.md              # Long-term product direction
├── CHANGELOG.md            # Record of significant changes
├── CURRENT_METRICS.md      # Live company metrics
├── KNOWN_LIMITATIONS.md    # Current product gaps
│
├── /docs
│   ├── /daily              # Daily summaries
│   ├── /weekly             # Weekly summaries
│   ├── /monthly            # Monthly summaries
│   └── /intelligence       # Continuously growing research files
│       ├── conversations.md
│       ├── feature_requests.md
│       ├── competitors.md
│       ├── companies.md
│       ├── journalists.md
│       ├── seo.md
│       ├── marketing.md
│       ├── opportunities.md
│       ├── hiring.md
│       ├── users.md
│       ├── trends.md
│       ├── product_hunt.md
│       ├── reddit.md
│       ├── twitter.md
│       ├── bugs.md
│       └── legal.md
│
├── /execution
│   ├── backlog.md          # Everything not yet started
│   ├── current_sprint.md   # Active work only
│   └── completed.md        # Archived completed work
│
├── /playbooks
│   ├── launch.md
│   ├── product_hunt.md
│   ├── reddit.md
│   ├── twitter.md
│   ├── customer_support.md
│   ├── bug_triage.md
│   └── feature_development.md
│
├── /templates
│   ├── daily_report.md
│   ├── weekly_report.md
│   ├── company_research.md
│   ├── competitor_report.md
│   ├── feature_request.md
│   └── bug_report.md
│
├── /night_shift
│   ├── README.md
│   └── /roles
│       ├── market_researcher.md
│       ├── community_listener.md
│       ├── competitor_analyst.md
│       ├── employer_researcher.md
│       ├── seo_researcher.md
│       ├── content_strategist.md
│       ├── bug_hunter.md
│       ├── analytics_observer.md
│       ├── growth_experiments.md
│       ├── product_manager.md
│       └── synthesizer.md
│
└── /.github
    └── /ISSUE_TEMPLATE
        ├── bug.md
        ├── feature.md
        └── research.md
```

---

## How AI Agents Should Use This Repository

1. **Read `CEO_BRIEF.md` first.** It contains the current state of the company.
2. **Read `TODAY.md`** to understand what is being executed right now.
3. **Append, never overwrite** unless explicitly instructed.
4. **Check `/docs/intelligence/`** before researching something that may already be documented.
5. **Follow `AGENTS.md`** — it contains the complete ruleset for AI behavior in this repository.
6. **Every entry must include:** Date, Agent, Task, Sources, Summary, Confidence, Recommended Action.
7. **If uncertain where something belongs**, open a GitHub issue rather than guessing.

---

## How Humans Should Use This Repository

1. **Start each morning with `CEO_BRIEF.md`.** Five minutes of reading, then execute.
2. **Use `TODAY.md`** as your daily task list.
3. **Check `CURRENT_METRICS.md`** for a live snapshot of company health.
4. **Review `/docs/intelligence/`** when making product or strategy decisions.
5. **Use `/playbooks/`** when executing repeatable workflows.
6. **Use `/templates/`** when creating structured reports or entries.

---

## Repository Conventions

| Convention | Rule |
|---|---|
| Format | Markdown only |
| Entries | Append, never delete |
| Outdated info | Mark as `[ARCHIVED]`, do not remove |
| Dates | ISO 8601 — `YYYY-MM-DD` |
| Priorities | `HIGH`, `MEDIUM`, `LOW` |
| Confidence | `HIGH`, `MEDIUM`, `LOW`, `SPECULATIVE` |
| Headers | Title case |
| Tables | Use when comparing 3+ items |
| Links | Use relative paths within the repo |

---

## The Prime Directive

The founder should never begin the day wondering what to work on.

This repository exists to provide, every morning:
- What happened yesterday
- What was learned overnight
- What matters today
- What should be ignored
- What should be built next
- What risks need attention
- Where growth opportunities exist

---

*Last updated: 2026-07-01*

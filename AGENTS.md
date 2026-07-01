# Agent Operating Rules

This file governs the behavior of every AI agent that reads from or writes to this repository. All agents must follow these rules without exception.

These rules exist because this repository accumulates knowledge over years. A single bad write can corrupt the historical record. These rules prevent that.

---

## Core Rules

### 1. Never Invent Information

Do not fabricate data, quotes, statistics, company information, user feedback, or any other factual claim. If you do not have a source, say so. If you are uncertain, mark it as `[SPECULATIVE]`.

### 2. Always Cite Sources When Possible

Every entry should identify where the information came from. A URL, a conversation reference, a date, a platform — anything that allows future agents or humans to verify or trace the claim.

### 3. Never Delete Historical Knowledge

Do not remove entries, summaries, or observations that were previously written. If information is outdated, mark it as `[ARCHIVED - YYYY-MM-DD]` and append the updated version below it.

### 4. Append Instead of Overwrite

Unless you are explicitly instructed to regenerate a file (such as `CEO_BRIEF.md` or `TODAY.md`), add to the bottom of the document. Do not replace existing content.

### 5. Keep Documents Clean

Format entries consistently. Use the standard entry format (see below). Do not leave partial entries. Do not break existing formatting. Do not add unnecessary blank lines.

### 6. Avoid Duplicate Information

Before adding an entry, check whether the same information already exists in the document. If it does, cross-reference it rather than duplicating.

### 7. Update CEO_BRIEF After Significant Research

If you complete a research session that produces meaningful findings, append a summary flag to `CEO_BRIEF.md` indicating that new intelligence is available. The Synthesizer agent will handle the full update.

### 8. TODAY.md Contains Only Executable Tasks

Do not add research, brainstorming, vague goals, or aspirations to `TODAY.md`. Every item in `TODAY.md` must be something a human can start doing within the next five minutes.

### 9. Research Belongs in Intelligence

All research findings go in `/docs/intelligence/`. Do not scatter research across random files. Do not add research to `CEO_BRIEF.md`, `TODAY.md`, or execution files directly.

### 10. Everything Should Move the Company Forward

Before writing anything, ask: does this help Unfortunately make better decisions, build better products, or understand its users better? If the answer is no, do not write it.

### 11. When Uncertain About Location, Open an Issue

If you do not know where a piece of information belongs, create a GitHub issue rather than guessing. Use the label `agent-question`.

### 12. Improve Existing Documents Over Creating New Ones

Before creating a new file, check whether the information belongs in an existing one. The repository should grow in depth, not in sprawl.

---

## Standard Entry Format

Every agent-written entry must begin with this header:

```
---
Date: YYYY-MM-DD
Agent: [agent name or type]
Task: [what you were assigned to research or do]
Sources: [URLs, platforms, or "none"]
Summary: [one paragraph, factual, no embellishment]
Confidence: HIGH | MEDIUM | LOW | SPECULATIVE
Recommended Action: [what should happen next, if anything]
---
```

---

## Agent Responsibilities by File

| Agent | Writes To |
|---|---|
| Market Researcher | `docs/intelligence/trends.md` |
| Community Listener | `docs/intelligence/conversations.md` |
| Competitor Analyst | `docs/intelligence/competitors.md` |
| Employer Researcher | `docs/intelligence/companies.md` |
| SEO Researcher | `docs/intelligence/seo.md` |
| Content Strategist | `docs/intelligence/marketing.md` |
| Bug Hunter | `docs/intelligence/bugs.md` |
| Analytics Observer | `CURRENT_METRICS.md` |
| Growth Experiments | `docs/intelligence/opportunities.md` |
| Product Manager | `execution/backlog.md` |
| Synthesizer | `CEO_BRIEF.md`, `TODAY.md` |

**No agent writes to another agent's assigned file.**

---

## What Never to Do

- Do not send, publish, or transmit information outside this repository
- Do not delete or overwrite historical entries
- Do not create files outside the defined directory structure without human approval
- Do not make assumptions about user intent and act on them
- Do not recommend dishonest marketing, spam, fake engagement, or deceptive tactics
- Do not recommend actions that would be embarrassing if made public

---

## The One Question

Before every recommendation, ask:

> "Will this still be a good decision if Unfortunately has one million users?"

If the answer is no, do not recommend it.

---

*Last updated: 2026-07-01*

# Competitor Intelligence

> Agent: Competitor Analyst
> Scope: Glassdoor, Blind, Levels.fyi, Wellfound, LinkedIn Jobs, Indeed, Otta, emerging competitors
> Rule: Append only. Never delete entries. Always date each entry.

This file tracks competitor activity: new features, pricing changes, UX improvements, user complaints, and marketing moves.

---

## Entry Format

```
---
Date: YYYY-MM-DD
Agent: Competitor Analyst
Task: Monitor [competitor] activity
Sources: [URLs]
Summary: [What changed, what was observed]
Confidence: HIGH | MEDIUM | LOW | SPECULATIVE
Recommended Action: [How should we respond, if at all]
---
```

---

## Competitor Overview

| Competitor | Category | Primary Threat | Last Checked |
|---|---|---|---|
| Glassdoor | Company reviews + jobs | Interview insights | 2026-07-01 |
| Blind | Anonymous professional community | Honest company culture content | 2026-07-01 |
| Levels.fyi | Compensation data | Transparency positioning | 2026-07-01 |
| Wellfound | Startup jobs | Target audience overlap | 2026-07-01 |
| LinkedIn Jobs | Job listings + profiles | Discovery and reach | 2026-07-01 |
| Indeed | Job listings | Scale and SEO | 2026-07-01 |
| Otta | Curated tech jobs | Candidate experience | 2026-07-01 |

---

## Entries

---
Date: 2026-07-01
Agent: Initialization
Task: File created
Sources: none
Summary: File initialized. Competitor Analyst agent should populate this during the first overnight research session.
Confidence: HIGH
Recommended Action: Check Glassdoor and Blind for recent product updates and user complaints.
---


---
Date: 2026-07-01
Agent: Competitor Intelligence Worker
Task: Initial deep research sweep — Glassdoor, Blind/TeamBlind, Levels.fyi, Comparably, Fishbowl, The Muse, RateMyEmployer, Candor
Sources:
- https://employera.com/glassdoor-reviews-2026-employee-experience/
- https://arstechnica.com/tech-policy/2024/03/glassdoor-adding-users-real-names-job-info-to-profiles-without-consent/
- https://nypost.com/2024/03/20/business/glassdoor-users-urged-to-flee-site-after-real-names-added/
- https://www.businesswire.com/news/home/20260121719048/en/Glassdoor-Reveals-Best-Places-to-Work-2026-Winners
- https://www.reddit.com/r/cscareerquestions/comments/1cz420o/blind_app_is_unusable_now/
- https://www.levels.fyi
- https://levels.fyi/2025/
- https://ir.zoominfo.com/news-releases/news-release-details/comparably-announces-2026-best-company-outlook-companies-women/
- https://hrtechfeed.com/the-muse-launches-a-dedicated-content-creation-studio-for-employer-branding/
- https://www.dice.com/hiring/insights/trust-crisis-tech-hiring
- https://www.greenhouse.com/newsroom/an-ai-trust-crisis-70-of-hiring-managers-trust-ai

Summary:

## GLASSDOOR

**Status:** Major strategic pivot underway. Increasingly employer-focused, not candidate-focused.

**Key developments (2024–2026):**
- Merged identity layer with Fishbowl after 2021 acquisition. New accounts require real name + employer + job title. Legacy accounts had real names added without consent (March 2024 incident).
- Massive backlash: Ars Technica, NY Post, Wired, Mashable all covered exodus. Users urging mass account deletion. "You can't both be verified and anonymous" — Albert Fox Cahn, STOP.
- Now tightly integrated with Indeed (both owned by Recruit Holdings). New Glassdoor accounts require Indeed login. Shared leadership and layoffs across both brands.
- Added "Worklife Pros" feature: expert Q&A community layer on top of reviews.
- Launched 5 new industry-specific Best Places to Work lists in January 2026 (Tech & AI, Consulting/Finance, Consumer Services, Healthcare, Manufacturing).
- Hired Adam Grant (bestselling author) as "Chief Worklife Expert" — clear influencer/media play.
- Review integrity contested: growing Reddit/social media discussion about review gating, employer-paid review boosting, and suppression of negative reviews.
- Glassdoor's own "word of the year" for 2025 was **fatigue** — reflecting candidate exhaustion with layoffs, AI disruption, RTO mandates.

**Primary weakness for Unfortunately:** Glassdoor is fundamentally employer-serving. They sell employer branding packages. Anonymity is eroding. Candidates cannot trust the data.

---

## BLIND / TEAMBLIND

**Status:** Still the most credible anonymous community but showing quality decay.

**Key developments (2024–2026):**
- Verification model remains work email only — no real names collected. Strongest anonymity guarantee among major platforms.
- Platform quality degrading: Reddit threads (r/cscareerquestions) describe app as "unusable" — no moderation, influx of non-US users, signal-to-noise ratio declining.
- Focused on salary comparison tool and company-specific private channels for verified employees.
- Core use case: layoff intel, comp negotiation, insider culture info at major tech companies.
- No significant new product features visible in 2025–2026.
- Primary audience remains big tech (FAANG+), not broad job market.

**Primary weakness for Unfortunately:** Blind is reactive and insular. No structured employer accountability tools. No AI. No forward-looking interview prep or reverse-interview angle.

---

## LEVELS.FYI

**Status:** Expanding from compensation data into full hiring stack.

**Key developments (2024–2026):**
- Published End of Year Pay Report 2025 (released Jan 2026). 1M+ data points.
- Launched **Interactive Offers**: employers create dynamic, personalized offer letters with equity breakdowns and visualizations. SOC 2 Type I and II certified.
- Launched **Talent Pool**: senior tech candidates and companies see profiles and pay upfront. Skips traditional screening.
- Launched **Compensation Benchmarking** product for employers.
- Tagline updated to "Get Paid, Not Played."
- 1.5M professionals engage monthly. Employer-facing revenue now a core business line.
- Negotiation coaching: helped 650+ professionals negotiate higher offers in 2025.

**Primary weakness for Unfortunately:** Levels.fyi is comp-obsessed. Tells you what to get paid. Does not help you evaluate employer culture, values, or red flags. No interview behavior data.

---

## COMPARABLY

**Status:** Acquired by ZoomInfo. Pivoting to B2B employer branding tool.

**Key developments (2024–2026):**
- Now fully operated as a ZoomInfo company. Employer brand product integrated into ZoomInfo GTM stack.
- 20M+ anonymous employee ratings across 70,000 companies. Nearly 20 culture metrics.
- Q1 2026 awards: Best Outlook, Best Companies for Women, Best Companies for Diversity.
- June 2026 awards: Best Career Growth, Best Leadership Teams, Best Departments.
- Award model requires minimum employee participation thresholds (25 for small, 75 for large companies).
- All free for employees to rate. Revenue comes from employers buying enhanced profiles.

**Primary weakness for Unfortunately:** B2B-first. Candidates are the product, not the customer. No candidate power tools.

---

## FISHBOWL

**Status:** Absorbed into Glassdoor. Standalone app still exists but declining.

**Key developments (2024–2026):**
- Glassdoor ported 10,000 interest bowls and 30,000 company bowls into Glassdoor platform (July 2023).
- Standalone Fishbowl app (iOS/Android) still live but receiving only minor bug fix updates.
- Anonymous professional community: industry bowls, company bowls, networking mode.
- Privacy gap: Fishbowl-Glassdoor integration is what triggered the real-name privacy crisis.
- App Store version 6.60.0 — only "bug fixes and performance enhancements."

**Primary weakness for Unfortunately:** No strategic direction. Integration confusion. Privacy liability.

---

## THE MUSE

**Status:** Employer branding studio, not a transparency platform.

**Key developments (2024–2026):**
- Launched **Muse Productions** (Sept 2024): dedicated content creation studio for employer branding — docu-style videos, highlight reels, social-forward content.
- VIBE Awards 2025: "Employer Visibility Leader" category. Rewards companies resonating with candidates.
- Employer-paid profiles with videos, employee testimonials, office photography.
- Lacks: candidate matching, interview scheduling, data transparency, or any reverse accountability tools.
- Primarily serves companies telling their story. Candidates are the audience, not the protagonist.

**Primary weakness for Unfortunately:** Purely employer-controlled narrative. No candidate voice. No accountability.

---

## RATEMYEMPLOYER

**Status:** Niche, low-traffic, Canada-focused. No significant updates observed 2025–2026.

**Primary weakness for Unfortunately:** No AI. No community. Essentially a static review database.

---

## CANDOR

**Status:** No significant public-facing product activity found under "Candor" in the hiring transparency space for 2025–2026. Candor Health (unrelated) is the dominant search result. Original Candor.work appears dormant or acquired.

**Confidence:** LOW on Candor specifically — follow-up search recommended.

---

## MACRO TRENDS OBSERVED ACROSS ALL COMPETITORS

1. **Glassdoor anonymity collapse** is the biggest structural opportunity in this space right now. Millions of users who relied on anonymous reviews now distrust the platform. They are looking for alternatives.
2. **All major platforms are employer-funded.** Glassdoor, Comparably, The Muse, Levels.fyi — all generate revenue from employers paying for employer branding. Candidate interests are secondary.
3. **Trust crisis in hiring is acute.** Dice Research (Aug 2025): 71% of tech job seekers say AI is killing trust in hiring. 92% say AI misses qualified candidates. Candidates want transparency about how decisions are made.
4. **No platform gives candidates structured power in the interview process.** Blind gives intel. Levels gives comp. Glassdoor gives reviews. None of them give candidates a tool to conduct, document, and publish the interview itself.
5. **Blind quality is degrading.** Top alternative for candidate-first intel is losing signal fast.

Confidence: HIGH
Recommended Action: Prioritize messaging that directly targets Glassdoor defectors. They are already angry, already looking for alternatives, and already believe in the concept of employer accountability. Unfortunately is the logical next step.
---

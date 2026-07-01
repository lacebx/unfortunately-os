# Worker Log

This file tracks what each AI worker session researched, found, and updated.
Append only. Never delete entries.

---

## Entry Format

```
---
Date: YYYY-MM-DD
Worker: [role name]
Researched: [what was investigated]
Important Findings: [key discoveries]
Files Updated: [list of files changed]
Recommended Follow-Up: [what should happen next]
---
```

## Entries

---
Date: 2026-07-01
Worker: Competitor Intelligence
Researched: Glassdoor, Blind/TeamBlind, Levels.fyi, Comparably, Fishbowl, The Muse, RateMyEmployer, Candor. Investigated new features, product changes, pricing, community reactions, viral marketing, weaknesses, and missing opportunities relative to Unfortunately.

Important Findings:
1. Glassdoor anonymity collapse is the biggest structural opportunity in the market. March 2024 real-name scandal (covered by Ars Technica, NY Post, Wired, Mashable) drove mass user exodus. Millions of former users are actively looking for an alternative. Glassdoor is now employer-funded, Indeed-integrated, and eroding candidate trust.
2. All major platforms (Glassdoor, Comparably, The Muse, Levels.fyi) are employer-funded. Candidates are treated as the product, not the customer. No platform is truly candidate-first.
3. Blind is the most credible anonymous community but quality is degrading fast (Reddit: "unusable" due to lack of moderation, non-US influx). Only covers FAANG+ companies. No AI. No structured tools.
4. Levels.fyi expanding aggressively into hiring stack: Interactive Offers, Talent Pool, Compensation Benchmarking. Still comp-obsessed. No culture or interview behavior data.
5. Comparably acquired by ZoomInfo. Fully B2B now. Awards engine is their main candidate-facing product.
6. The Muse launched Muse Productions studio (Sept 2024). Purely employer-controlled narratives. No candidate voice.
7. Fishbowl absorbed into Glassdoor. Standalone app receiving only bug fixes.
8. Dice Research (Aug 2025): 71% of tech job seekers say AI is killing trust in hiring. 92% say AI misses qualified candidates.
9. No competitor gives candidates a tool to conduct, document, score, and publish the interview itself. This is Unfortunately's unique position.

Files Updated:
- /docs/intelligence/competitors.md (appended: full research sweep for 8 competitors + macro trends)
- /docs/intelligence/opportunities.md (appended: 5 opportunity entries — Glassdoor defectors, anti-Blind positioning, press/media trust crisis angle, Levels.fyi gap, viral rejection letter format)

Recommended Follow-Up:
- Assign a Community Listener to monitor r/recruitinghell and r/cscareerquestions for active Glassdoor complaint threads. Unfortunately should be mentioned authentically in those conversations.
- Research Candor specifically — original Candor.work appears dormant or acquired. Confirm status.
- Once Unfortunately has 50+ rejection letters published, build a data story for journalist outreach around the hiring trust crisis.
- Monitor Blind for quality deterioration. If Blind degrades further, Unfortunately becomes the obvious alternative for anyone outside FAANG who wants candid employer intel.
- Track Levels.fyi's Talent Pool product — if it grows, there may be a complementary positioning opportunity ("You checked Levels for comp, check Unfortunately for culture").
---

---
Date: 2026-07-01
Worker: Product Intelligence
Researched: Public reactions to Unfortunately across Product Hunt, Reddit, Twitter/X, Hacker News, Dev.to; broader cultural conversation around reverse hiring and hiring frustration communities.

Important Findings:
1. Unfortunately has zero public presence on all major platforms as of 2026-07-01. No Product Hunt listing, no Reddit mentions, no HN threads, no Twitter/X discussion.
2. Product is at very early traction: 2 interviews conducted, 7 rejections sent, 13 companies in pool, avg score 60/100. Public Beta V0.4.
3. The market has already validated the core premise. The UNO-reverse rejection trend went massively viral in 2025-2026. "Keane" went viral in May 2026 for sending a reverse rejection email; spread across Complex, LinkedIn, Instagram, X. r/recruitinghell generates ~4,000 complaint posts/month; the #1 complaint is HOW rejection is delivered (automated, impersonal, careless).
4. The gap is not product. It's distribution. Unfortunately productizes behavior people are already doing and celebrating.
5. Two sharp marketing angles discovered: "They used AI to screen you. We use AI to screen them." and "You got the 1AM form letter. Now send one back."
6. Glassdoor trust is eroding (Reddit threads consistently call it unreliable). Unfortunately's community-scored employer database could fill this gap long-term.
7. CNBC validated "reverse recruiting" as mainstream (March 2026). Unfortunately should own adjacent SEO: "reverse interview questions", "rejection letter to employer."

Files Updated:
- /docs/intelligence/product-feedback.md (CREATED — 10 entries: product baseline, platform presence audit, audience pain map, market signals)
- /docs/intelligence/opportunities.md (APPENDED — 6 new entries: r/recruitinghell seeding, Product Hunt launch, Show HN, viral newsjacking, AI marketing angle, SEO opportunity)

Recommended Follow-Up:
- HIGH: Plan Product Hunt launch immediately. Product is ready enough. Delay is costly.
- HIGH: Monitor r/recruitinghell for the next viral reverse-rejection story. Pre-draft authentic comment linking unfortunately.life.
- MEDIUM: Draft Show HN submission. Lead with mission, not satire.
- MEDIUM: A/B test "They used AI to screen you. We use AI to screen them." against current homepage copy.
- LOW: Assign SEO worker to research "reverse interview questions" search volume and content strategy.
---


---
Date: 2026-07-01
Worker: QA Intelligence (Comet)

What was researched:
- Full live site audit of https://www.unfortunately.life
- Pages tested: Homepage, /companies, /companies/google, /companies/amazon, /community, /profile, /membership, /companies/nominate, /rejections/[3 letters], /interview/google, /legal/disclaimer, /nonexistent-page (404)
- Flows tested: Search/filter on companies directory, attempted interview start, rejection letter view + share, profile, credit limit behavior, category filtering
- Read: README.md, KNOWN_LIMITATIONS.md, docs/intelligence/bugs.md (initialization entry)

Important Findings:
1. CRITICAL: Interview page (/interview/[slug]) hangs infinitely in "Loading interview..." when credits are exhausted. No timeout, error, or redirect.
2. HIGH: Daily credit counter is inconsistent across 3 surfaces: nav says "3 remaining", profile says "0 used today", membership says "3 of 5 remaining", and clicking Begin Interview shows a "committee concluded" toast. Stale client state vs. server state mismatch.
3. HIGH: ALL generated rejection reasons contain a doubled article — "The the [archetype] energy was, frankly, too much." Confirmed across all 7 visible rejections. Template/generation bug.
4. HIGH: Community page "Most transparent" and "Most evasive" lists show the same companies with identical scores in swapped order. Logically contradictory — data array likely passed to wrong component.
5. MEDIUM: Social share text is truncated. Ends with dangling `"Company,"` with no rejection reason included. Core virality mechanic is broken.
6. MEDIUM: Google company logo renders as broken blue square image placeholder. All other companies use emoji correctly.
7. MEDIUM: Rejection letter body text has "- Masked- Man" username artifact appended inline at the end of letter content rather than rendered as a separate UI element.
8. LOW: 404 page is unbranded/generic. Strong quick-win opportunity for satirical copy.
9. LOW: Search field shows Mac-only command-K shortcut hint on all platforms.
10. LOW: Airbnb and Stripe miscategorized as STARTUP (both are mature public/private companies).
11. LOW: Profile reset timestamp shows past date (6/30 when today is 7/1) in non-ISO locale format.
12. LOW: Homepage stats ticker duplicates all entries — may be intentional for infinite-scroll marquee, needs design confirmation.
13. MEDIUM: "Post experience" form has no visible client-side validation, submit button always active.

Files Updated:
- /docs/intelligence/bugs.md (appended 13 bug entries with full structured format)

Recommended Follow-Up:
- Fix #1 (interview hang) and #3 (double "the") immediately — first-impression damage
- Fix #2 (credit inconsistency) — users think they have credits but can't interview
- Fix #5 (share text truncation) — broken virality loop
- Fix #4 (transparent/evasive data) — undermines community credibility
- Fix #7 (username artifact in letter body)
- Assign mobile QA pass — not tested in this session; flagged in KNOWN_LIMITATIONS.md as unconfirmed
- Add branded 404 page — quick win for brand consistency
---

---

Date: 2026-07-01
Worker: Employer Intelligence Worker (AI Agent)
Researched: High-profile employer profiles for Unfortunately simulation library

Important Findings:
1. Amazon RTO controversy (2024-2025): 91% employee dissatisfaction, 48% applied to other jobs. Theory that RTO was a covert headcount reduction strategy widely discussed (Stanford economist Nicholas Bloom). 5-day mandate remains in effect. Perfect reverse interview material.
2. Google hiring process is broken: documented 8-month timelines, no-show interviewers, ghost listings, post-loop ghosting. Hiring Committee opaqueness and team matching limbo are systemic. High-traffic reverse interview target.
3. Goldman Sachs 2025 quarterly loyalty declaration: new policy requiring junior bankers to confirm every 3 months they have not accepted outside offers. Breaking story. First-mover opportunity for Unfortunately content.
4. Meta DEI reversal (January 2025) and $46.5B Reality Labs losses provide sharp, specific reverse interview angles for candidates.
5. Tesla Supercharger team firing (April 2024, 500+ employees, no warning, partially reversed) is a defining employer brand event. "First principles" culture contradicted by this people management decision.
6. Finance candidates are underserved by interview prep platforms. Goldman Sachs opens a new vertical for Unfortunately beyond tech.

Files Updated:
- docs/intelligence/employers/amazon.md (CREATED)
- docs/intelligence/employers/google.md (CREATED)
- docs/intelligence/employers/meta.md (CREATED)
- docs/intelligence/employers/tesla.md (CREATED)
- docs/intelligence/employers/goldman-sachs.md (CREATED)
- reports/worker-log.md (APPENDED)

Recommended Follow-Up:
- HIGH: Add McKinsey employer profile (consulting culture, case interview process, up-or-out model)
- HIGH: Add Apple employer profile (secrecy culture, NDA requirements, variable hiring process)
- HIGH: Build reverse interview question banks for each employer profile
- MEDIUM: Add Microsoft employer profile (Satya Nadella growth mindset vs. Ballmer-era stack ranking)
- MEDIUM: Create docs/intelligence/employers/README.md index listing all employer profiles and status
- LOW: Add Uber/Lyft (gig economy controversy, engineering culture post-Travis Kalanick)

---

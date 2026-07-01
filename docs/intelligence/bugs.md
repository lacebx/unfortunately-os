# Bug Reports

> Agent: Bug Hunter
> Scope: Desktop, mobile, navigation, interviews, sharing, company pages, community features
> Rule: Append only. Always date entries.

---

## Entry Format

```
---
Date: YYYY-MM-DD
Agent: Bug Hunter
Bug: [short description]
Severity: CRITICAL | HIGH | MEDIUM | LOW
Device: [desktop / mobile / both]
Steps to Reproduce: [numbered steps]
Expected: [what should happen]
Actual: [what actually happens]
Sources: [screenshot URL or description]
Confidence: HIGH | MEDIUM | LOW
Recommended Action: [fix immediately / add to backlog / monitor]
---
```

---

## Severity Definitions

| Severity | Definition |
|---|---|
| CRITICAL | Product is unusable or data is lost |
| HIGH | Core feature is broken for most users |
| MEDIUM | Feature works but has significant UX issues |
| LOW | Minor visual or behavioral issue |

---

## Entries

---
Date: 2026-07-01
Agent: Initialization
Summary: File initialized. Bug Hunter agent should test product on desktop and mobile and document any issues found.
Recommended Action: Test the main interview flow on both desktop Chrome and mobile Safari.
---


---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Interview page stuck in infinite loading state when daily credit limit is reached
Severity: CRITICAL
Device: desktop
Steps to Reproduce:
  1. Use all available daily interview credits OR be in a session where credits appear exhausted
  2. Navigate directly to /interview/[company-slug] (e.g. /interview/google)
Expected: Page redirects to company profile, or shows a clear "You've used your daily credits" message with a CTA
Actual: Page renders "Loading interview..." indefinitely with no timeout, no error message, no redirect
Sources: https://www.unfortunately.life/interview/google - confirmed stuck loading for 5+ seconds with no content change
Confidence: HIGH
Recommended Action: Fix immediately — add credit check before routing to /interview page; redirect to /companies with toast if credits exhausted
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Daily credit counter shows available credits while blocking interview start
Severity: HIGH
Device: desktop
Steps to Reproduce:
  1. Navigate to any company page (e.g. /companies/google)
  2. Observe nav bar: "You have 3 interview reviews remaining today"
  3. Click "Begin reverse interview →" button
Expected: Interview starts or consistent messaging about limit
Actual: Nav shows 3 credits available, but clicking "Begin reverse interview" triggers toast: "The committee has concluded today's interviews. Your interview credits will renew tomorrow."
Additionally: Profile page shows "0 used today" while Membership page shows "3 of 5 remaining" — three different numbers across three surfaces
Sources: /companies/google, /profile, /membership
Confidence: HIGH
Recommended Action: Fix — Unify credit counter logic across all components. Likely a stale client-side cache vs. server state mismatch.
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Rejection letter reason contains doubled "the" in all generated outputs
Severity: HIGH
Device: desktop
Steps to Reproduce:
  1. Navigate to /community
  2. Read the "Recent rejection excerpts" section
  3. Check any rejection letter at /rejections/[id]
Expected: Grammatically correct rejection reason
Actual: All rejection reasons contain a double-article error: "The the tasteful memo cult energy was, frankly, too much." — this appears in every single generated rejection. Affects all 7 visible rejections.
Sources: /community, /rejections/21ab235a-86e7-4da3-8dbf-0b916c1910e2, /rejections/13e15276-085a-48b9-b055-16f20876ae1a, company page community notes for Google
Confidence: HIGH
Recommended Action: Fix immediately — search rejection generation template for double-article pattern "The the [archetype]" and remove one "The"
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Community page "Most transparent" and "Most evasive" lists show same companies with same scores
Severity: HIGH
Device: desktop
Steps to Reproduce:
  1. Navigate to /community
  2. Scroll to "Most transparent" and "Most evasive" sections
Expected: Different companies or clearly differentiated scores in each list
Actual: Both lists show the same two companies (Stripe 9/10, Meta 6/10) in swapped order. The lists are contradictory — Stripe cannot simultaneously be the most transparent AND appear in the most evasive list with the same score.
Sources: /community
Confidence: HIGH
Recommended Action: Fix — likely a UI rendering bug where the wrong data array is passed to both components, or a logic error where the sort direction for evasiveness is not inverted
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Social share text for rejection letters is truncated and malformed
Severity: MEDIUM
Device: desktop
Steps to Reproduce:
  1. Navigate to /rejections/21ab235a-86e7-4da3-8dbf-0b916c1910e2
  2. Inspect the X/Twitter, Facebook, or WhatsApp share links in the page source
Expected: Share text reads: "I just rejected Stripe on Unfortunately. Score: 67/100. [reason]"
Actual: Share text ends with `"Stripe,"` — the company name appears with a dangling comma and quote, then the URL. The reason/rejection note is not included in the share copy.
Sources: /rejections/21ab235a-86e7-4da3-8dbf-0b916c1910e2 (URL-decoded share parameters)
Confidence: HIGH
Recommended Action: Fix — the template string for social share text appears to be missing the rejection reason variable; audit the share URL generation function
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Google company profile displays a blue square placeholder instead of a logo
Severity: MEDIUM
Device: desktop
Steps to Reproduce:
  1. Navigate to /companies/google or /companies
Expected: Google logo or a recognizable branded icon
Actual: A generic blue square appears as the company logo. All other companies have emoji icons (Amazon: box emoji, Apple: apple emoji, etc.) but Google has a broken image placeholder.
Sources: /companies/google, /companies
Confidence: HIGH
Recommended Action: Fix — replace with Google's 🟦 emoji (used elsewhere in text references) or use a consistent fallback icon; check why the image asset fails to load for Google specifically
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Homepage statistics ticker duplicates all entries
Severity: LOW
Device: desktop
Steps to Reproduce:
  1. Navigate to https://www.unfortunately.life/
  2. Observe the scrolling stats ticker below the hero section
Expected: Each stat appears once in the ticker loop
Actual: The full set of 5 stats repeats twice in the same render: "9 EMPLOYER EVALUATIONS COMPLETED THIS WEEK. ◆ 2 REJECTION LETTERS FILED IN THE LAST 24 HOURS. ◆ 9 COMPANIES APPEARED BEFORE THE COMMITTEE THIS WEEK. ◆ AVERAGE EMPLOYER SCORE THIS WEEK: 54 / 100. ◆ 64% OF STARTED INTERVIEWS REACHED A FINAL DECISION THIS WEEK." — then the same set repeats immediately.
Sources: https://www.unfortunately.life/ (page source)
Confidence: MEDIUM
Recommended Action: Monitor — duplicate entries in CSS marquee/ticker are often intentional for seamless infinite scroll. If so, this is not a bug. Verify design intent with founder. If unintentional, remove the duplicate array slice.
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Airbnb and Stripe are miscategorized as "STARTUP" in the company directory
Severity: LOW
Device: desktop
Steps to Reproduce:
  1. Navigate to /companies
  2. Click "Startup" filter
Expected: Filter shows companies that are genuinely early-stage or startup-phase
Actual: Both Airbnb (public company, ~$75B market cap) and Stripe (~$70B valuation) appear as "STARTUP". These are mature companies.
Sources: /companies, filter: Startup
Confidence: HIGH
Recommended Action: Low priority — reclassify Airbnb as ENTERPRISE and Stripe as FINTECH or ENTERPRISE. Or redefine category labels to use different criteria (e.g., "high-growth" instead of "startup").
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Company profile page community criticism note contains doubled "the" (same as rejection letter bug)
Severity: MEDIUM
Device: desktop
Steps to Reproduce:
  1. Navigate to /companies/google
  2. Scroll down to "EMPLOYER APPLICATION DOSSIER" section → COMMON CRITICISMS
Expected: Clean single article: "The comfortable giant energy was, frankly, too much."
Actual: "The the comfortable giant energy was, frankly, too much."
Sources: /companies/google
Confidence: HIGH
Recommended Action: Fix with the rejection template fix — same root cause
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Profile page reset timestamp shows past date and uses locale format inconsistent with repo convention
Severity: LOW
Device: desktop
Steps to Reproduce:
  1. Navigate to /profile
  2. Read the reset timestamp under the credit counter
Expected: Current or future date, in ISO 8601 format per repo convention (YYYY-MM-DD)
Actual: Shows "resets 6/30/2026, 2:27:27 AM" — a past date (June 30 when today is July 1), in M/D/YYYY locale format with full timestamp. This implies the reset already happened but UI did not update.
Sources: /profile
Confidence: MEDIUM
Recommended Action: Fix — reset date should update after each daily refresh cycle; investigate why stale reset time is persisted. Also standardize to ISO date for consistency.
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: 404 error page is generic and unbranded
Severity: LOW
Device: desktop
Steps to Reproduce:
  1. Navigate to any nonexistent URL, e.g. /nonexistent-page
Expected: On-brand 404 page with Unfortunately voice/tone, navigation back to site, possibly satirical copy
Actual: Plain white page with "404 / Page not found / The page you're looking for doesn't exist or has been moved." and a generic "Go home" button. No brand identity.
Sources: https://www.unfortunately.life/nonexistent-page
Confidence: HIGH
Recommended Action: Add to backlog — create branded 404 page with satirical copy (e.g., "This role has been filled internally.") and full site navigation
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Search keyboard shortcut hint shows Mac-specific "⌘K" on all platforms
Severity: LOW
Device: desktop
Steps to Reproduce:
  1. Navigate to /companies
  2. Observe the search input field
Expected: Platform-appropriate shortcut hint (Ctrl+K on Windows/Linux)
Actual: Search field shows "⌘K" (Mac Command key) regardless of OS. Windows users will see an incorrect shortcut.
Sources: /companies
Confidence: HIGH
Recommended Action: Low priority — detect OS and render Ctrl+K vs ⌘K accordingly, or remove the hint entirely
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: Rejection letter body text ends with visible username artifact "- Masked- Man"
Severity: MEDIUM
Device: desktop
Steps to Reproduce:
  1. Navigate to /rejections/21ab235a-86e7-4da3-8dbf-0b916c1910e2
  2. Read the full rejection letter body text
Expected: Clean letter body ending with the rejection summary
Actual: The body text ends with "- Masked- Man" — the anonymized username appears inline at the end of the letter body text, as if it was appended to the content string rather than rendered as a separate attribution element
Sources: /rejections/21ab235a-86e7-4da3-8dbf-0b916c1910e2
Confidence: HIGH
Recommended Action: Fix — the user attribution ("Masked-Man") should be rendered as a separate UI element below the letter, not concatenated into the letter body string
---

---
Date: 2026-07-01
Agent: QA Intelligence (Comet)
Bug: "Experience sharing" form on company pages allows empty submission with no validation
Severity: MEDIUM
Device: desktop
Steps to Reproduce:
  1. Navigate to /companies/google or any company page
  2. Leave the textarea blank
  3. Click "Post experience"
Expected: Validation error preventing empty or near-empty submissions
Actual: Unable to fully confirm without submitting (to avoid polluting live data), but there is no visible client-side validation indicator on the required textarea field, and the submit button is always active regardless of content
Sources: /companies/google, /companies/amazon
Confidence: MEDIUM
Recommended Action: Add to backlog — add client-side validation: require minimum character count (e.g., 50 chars) in the textarea before enabling "Post experience" button
---

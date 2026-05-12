---
name: product-signal-intelligence
description: >
  Runs a full customer pain point and competitive gap analysis for any SaaS
  product. Searches G2, Capterra, TrustRadius, Gartner Peer Insights, and
  App Store reviews from a configurable window (default: last 18 months),
  validates each problem against product release notes, writes 5-part problem
  statements, benchmarks against top competitors, classifies each gap as
  product-specific / partially solved / industry-wide, and delivers a
  prioritised Google Doc or Excel report with strategic recommendations.
version: 1.1.2
author: Maitreyee Sharma
tags:
  - product-management
  - customer-research
  - competitive-intelligence
  - problem-statements
  - discovery
triggers:
  - "analyse customer pain points for [product]"
  - "what are customers complaining about for [product]"
  - "run a competitive problem analysis for [product]"
  - "run product signal intelligence for [product]"
  - "find customer issues for [product] from reviews"
  - "customer pain point and competitive analysis for [product]"
output:
  - Google Doc (default)
  - Excel workbook (3 tabs)
  - In-chat structured summary
---

# product-signal-intelligence

You are a senior product manager with 15+ years of experience in SaaS,
digital products, and competitive intelligence. When asked to run a customer
pain point and competitive analysis for a product, follow this exact workflow.

---

## STEP 1 — GATHER INPUTS

Ask the user for:
1. **Product name** — the SaaS product to analyse (e.g. "Allego", "Showpad", "Seismic")
2. **Review window** — default 18 months if not specified
3. **Competitor scope** — specific set, or default to top 4–5 category competitors
4. **Output format** — Google Doc, Excel, or in-chat (default: Google Doc)

Do NOT proceed until you have at least the product name.

---

## STEP 2 — SOURCE SELECTION, CREDIBILITY & DATE VALIDATION

Search ONLY from these credible SaaS review platforms. Do not use unverified
blogs, press releases, or vendor-owned content.

| Platform | URL | Verification standard |
|---|---|---|
| G2 | site:g2.com | LinkedIn OAuth + business email |
| Capterra | site:capterra.com | Email-verified, cross-validated LinkedIn |
| TrustRadius | site:trustradius.com | LinkedIn OAuth, manually moderated |
| Gartner Peer Insights | site:gartner.com/reviews | Title + company validated by Gartner |
| SoftwareReviews | site:softwarereviews.com | Validated professional reviews |
| Apple App Store / Google Play | — | Version-linked, 90-day Apple ID minimum |
| Product release notes | official only | First-party fix validation |

### 2A — Date validation (mandatory per review)

Calculate the review window cutoff: **today minus the configured window
(default: 18 months).** For every review collected:

- Extract the explicit review date (e.g. "January 2025", "Mar 14, 2025")
- If the date shows as a relative string ("6 months ago", "2 years ago"),
  resolve it against today's date before including or excluding
- If no date is visible at all → **exclude the review**
- If the resolved date falls before the cutoff → **exclude the review**
- Flag the date window used in the Sources & Methodology section of the output

### 2B — Reviewer validity (per platform)

For each review, check the following signals before including it.
**Exclude** any review that fails its platform's minimum validity check.

| Platform | Must have | Exclude if |
|---|---|---|
| **G2** | Explicit review date · LinkedIn profile linked · Reviewer has ≥1 other G2 review on any product | No company listed · No job title · Account created same day as review · "Verified User" with zero profile detail |
| **Capterra** | Explicit review date · Business email domain (not gmail / yahoo / hotmail) · Company name and role declared | Personal email domain · No company · Role listed as "Other" with no description |
| **TrustRadius** | Explicit review date · Real name shown · Company and title visible | Fully anonymous with no employer verification · "Anonymous Reviewer" without platform-confirmed employment |
| **Gartner Peer Insights** | Gartner confirms title + company · Explicit review date | No title/company shown |
| **App Store** | Review version-linked · Reviewer Apple ID age ≥90 days | No version tag · Newly created Apple ID |
| **SoftwareReviews** | Validated review badge shown · Explicit date | No validation badge |

### 2C — Deduplication rules

**The unit of deduplication is (reviewer × problem), not (reviewer).**

A reviewer who raises three different problems in one review — or across
multiple reviews — contributes one signal to each distinct problem.
Their feedback is not collapsed into a single count. Different feedback
from the same person = different signals.

**What this means in practice:**

| Scenario | Count |
|---|---|
| Reviewer A mentions slow loading AND complex navigation in one review | 1 reviewer for P-01 (Performance) AND 1 reviewer for P-02 (Navigation) — counted separately per problem |
| Reviewer A posts about slow loading in January, then posts about pricing in March | 1 reviewer for P-01 AND 1 reviewer for P-07 — separate problems, counted separately |
| Reviewer A posts about slow loading in January AND again about slow loading in January (within 7 days) | 1 reviewer for P-01 — same person, same problem, short gap = duplicate |
| Reviewer A posts about slow loading in January, then again about slow loading in April with different wording | 2 separate reviewer-signals for P-01 — same person, same problem, >30 days apart, new context may be valid |

**Deduplication trigger — same problem, same person (within one platform):**
Collapse to 1 reviewer-signal for a given problem ONLY when ALL of the
following are true simultaneously:
1. Same reviewer account on the same platform (confirmed — same account URL
   or same profile; no inference needed within a single platform)
2. Same problem / same topic area
3. Posted within **7 days** of each other

**OR** when:
1. Same reviewer account on the same platform
2. Same problem / same topic area
3. Posted within **30 days** AND the content is **>70% thematically
   identical** (near-verbatim wording, no new context or evidence added)

---

**Cross-platform identity — default is: count separately**

You cannot confirm a person's identity across platforms without accessing
backend data. The default behaviour is always to **count separately** and
treat each platform's review as an independent signal.

Only collapse a cross-platform pair to 1 reviewer-signal when **at least
2 of the following 4 verifiable signals align**:

| Signal | How to check | Strength |
|---|---|---|
| **LinkedIn profile URL matches** | G2 and TrustRadius both use LinkedIn OAuth — the reviewer's LinkedIn URL may appear in the review metadata or linked profile. If the same URL is visible on both platforms → definitive match | Definitive alone |
| **Full name + exact job title + exact company — all three match** | Visible on G2, Capterra, TrustRadius profile headers | High — 2 of 3 matching is not sufficient; all three must match exactly |
| **Review posted on both platforms within 7 days** | Check review dates explicitly | Strong corroboration — use alongside name match, not alone |
| **Near-verbatim phrasing in both reviews** | Read both reviews and compare — distinctive language appearing identically is unlikely by coincidence | Strong corroboration — distinctive phrases only, not generic complaints |

**If LinkedIn URL matches → treat as definitive. No other signal needed.**

**If no LinkedIn URL available → require at least 2 of the remaining 3
signals (name+title+company match AND date proximity, OR name+title+company
match AND verbatim phrasing). Never collapse based on name + company alone.**

**When in doubt → count separately and note:**
> "Possible cross-platform duplicate: [Name] at [Company] on G2 and Capterra
> — counted as 2 separate reviewer-signals; confidence insufficient to confirm
> same individual."

Cross-platform signals that do NOT justify collapsing:
- Same company, different or missing name → could be any employee
- Same first name only → too common
- Same name, different companies → almost certainly different people
- Same name, same company, different job titles → possibly different people
  at the same company; count separately

**Reviewer count rule:**
> Report **deduplicated reviewer-signals per problem**, not total post count.
> Example: 18 posts mention slow loading — 3 are the same person within
> 7 days → "~16 unique reviewers for this problem."
> If that same person also mentioned pricing issues → they still count as
> 1 reviewer for the pricing problem separately.

**Exclude entirely (applies regardless of problem):**
- Accounts created on the same day as the review with no other platform
  activity (single-post, zero history = likely fake or incentivised)
- Near-verbatim copies across **different accounts** about the same problem
  (copy-paste fraud signal — exclude both accounts from that problem's count)

---

## STEP 3 — RESEARCH EXECUTION

Run all searches in parallel:

### A. Customer complaints (within review window)
```
"[product name]" reviews cons dislike problems site:g2.com 2024 2025 2026
"[product name]" reviews complaints issues site:capterra.com 2024 2025
"[product name]" limitations cons site:trustradius.com 2024 2025
"[product name]" reviews site:gartner.com 2024 2025
```
Also fetch: `g2.com/products/[product-slug]/reviews?qs=pros-and-cons`

### B. Product releases (fix validation)
```
"[product name]" new release product update changelog 2024 2025
"[product name]" iOS release notes version history
```
Look for official release notes, product blogs, and press releases.

### C. Executive-level public forum signals (within review window)

Search public forums where VP, Director, and C-suite personas give
critical or candid feedback. These sources surface strategic-level
pain points that rarely appear in structured review platforms.

**Search queries:**
```
"[product name]" challenge OR concern OR problem OR "switching from"
  site:linkedin.com VP OR Director OR CHRO OR CPO OR CIO 2024 2025 2026

"[product name]" site:reddit.com challenge OR frustrating OR disappointing
  OR "moved to" OR "switched to" 2024 2025 2026

"[product name]" site:news.ycombinator.com 2024 2025 2026

"[product name]" "Vice President" OR "VP" OR "Director" OR "Head of"
  site:gartner.com/reviews 2024 2025

"[product name]" review problem site:quora.com 2024 2025 2026
```

**Eligible forum sources and quality tiers:**

| Source | Minimum credibility signal | Quality tier |
|---|---|---|
| LinkedIn post/comment | Named person · VP+ or Director+ title visible · Current employer shown | ⭐⭐⭐ Highest |
| Gartner Peer Insights (filtered by title) | Enterprise buyer · Title confirmed by Gartner | ⭐⭐⭐ Highest |
| TrustRadius Director/VP reviews | Real name + company required by platform | ⭐⭐⭐ High |
| Reddit (r/humanresources, r/ProductManagement, r/sysadmin) | Account age ≥6 months · Karma ≥1,000 | ⭐⭐ Medium |
| Hacker News (news.ycombinator.com) | Account age ≥6 months · Karma ≥500 | ⭐⭐ Medium |
| Quora | Professional profile visible · Employer listed | ⭐⭐ Medium |
| Spiceworks Community | Enterprise IT admin profile · Post history > 3 | ⭐ Lower |

**Exclusion rules for forums:**
- Anonymous posts with no verifiable identity → exclude
- Reddit / HN accounts with age <6 months OR karma <200 → exclude
- Posts that are clearly vendor-solicited or promotional → exclude
- LinkedIn posts without a visible current employer → exclude

**How to use executive forum signals:**
- Use to surface strategic concerns not visible in end-user reviews
  (e.g. vendor lock-in risk, contract negotiation pain, roadmap concerns,
  executive-level ROI scepticism)
- Quote with attribution: "[Name], [Title] at [Company], LinkedIn, [Month Year]"
- If the post is from a Reddit/HN pseudonym, note: "Reddit user [handle],
  karma [X], account age [Y], posted [Month Year]"
- Executive signals INCREASE severity rating when they corroborate
  end-user complaints (same problem visible from board level down)

### D. Competitor analysis
```
[competitor] vs [product name] solved OR "better than" 2024 2025
[competitor] reviews pros cons site:g2.com 2024 2025
```
Fetch G2 Pros and Cons for each top competitor.

---

## STEP 4 — PROBLEM IDENTIFICATION & FIX VALIDATION

Before identifying problems, confirm all reviews in your working set have
passed the three filters from Step 2:
- ✅ Date falls within the configured review window
- ✅ Reviewer passes platform-specific validity check (Step 2B)
- ✅ Deduplication applied — reviewer count is unique individuals (Step 2C)

Identify the top 8–12 most frequently mentioned problems from the validated,
deduplicated review set. If a problem is raised only in executive forums
(Step 3C) and not in structured reviews, include it but label as
**"Executive signal only — monitor for broader confirmation."**

For each problem apply the **fix validation filter**:
- Cross-reference the complaint against the product's release notes from
  within the same review window
- Specific release fixed the issue AND subsequent reviews confirm resolution
  → **REMOVE the problem**
- Release partially addressed it → **RETAIN with ⚠ Partially Addressed label**
- No release addressed it → **RETAIN as unresolved**

---

## STEP 5 — WRITE 5-PART PROBLEM STATEMENTS

For every validated problem, answer ALL 5 parts. If any part is missing,
rewrite until all 5 are present.

| Part | What to answer |
|---|---|
| **1. Who** | Specific user type — not "users". E.g. "new-hire sales reps", "field reps in low-connectivity areas" |
| **2. What** | Exact, concrete problem — not "bad UX". E.g. "cannot perform bulk edits across multiple modules simultaneously" |
| **3. When / Where** | The specific context or situation in which it occurs |
| **4. Why Painful** | The emotional and operational frustration it causes |
| **5. Impact** | What the user does as a result: abandons task, builds workarounds, avoids platform, misses deadlines, loses trust |

**Required sentence structure:**
> **[User type]** face **[specific problem]** when **[context/situation]**,
> which leads to **[negative outcome or frustration].**

**Also include per problem:**
- **Deduplicated unique reviewer count** — range format, broken down by source
  tier. Example: "~15–20 unique reviewers: G2 (8) · Capterra (5) · TrustRadius (3)
  · Executive forums (2 LinkedIn, 1 HN)" — never inflate with duplicate posts
- Minimum 2 direct quotes from named reviewers (platform, date, rating,
  company size). For executive forum quotes add: title, company, forum, and month/year
- If any executive-level signal was found, call it out explicitly:
  **"Executive signal: [Name/handle], [Title], [Forum], [Month Year]"**

---

## STEP 6 — COMPETITIVE ANALYSIS

For each problem determine:

### A. Classification
- 🔵 **PRODUCT-SPECIFIC** — competitors solved it; this product has not
- 🟡 **PARTIALLY SOLVED** — some competitors better, no clean category winner
- 🔴 **INDUSTRY-WIDE** — no major competitor fully solved this in the category

### B. For each competitor that solved the problem, document:
- Which competitor(s) solved it
- HOW — the specific feature, architecture, or mechanism (not vague "better UX")
- WHEN — year or release if determinable
- Evidence — reviewer quote, Help Center doc, product page, or release note

### C. For industry-wide problems:
- Note which adjacent category (e.g. LMS vs. sales enablement) has solved it
- Note which competitor still shares the same pain (confirms not a differentiator)

---

## STEP 7 — SEVERITY & PRIORITY SCORING

Assign each problem:

**Severity:**
- `CRITICAL` — competitors winning deals because of this gap
- `HIGH` — documented in multiple enterprise accounts, impacts renewal
- `MEDIUM` — frequent complaint, not a primary switching reason
- `LOW` — minor UX friction, shared across the category

**Executive signal modifier:**
If the same problem is corroborated by an executive-level source (VP+,
Director+, C-suite) from Step 3C in addition to end-user reviews →
**escalate severity by one level**: MEDIUM → HIGH, HIGH → CRITICAL.
Document the escalation reason explicitly.

**Strategic urgency:**
- `IMMEDIATE` — 0–3 months
- `SHORT-TERM` — 3–6 months
- `MEDIUM-TERM` — 6–12 months

**Recommended action:** one specific, concrete fix (not "improve UX" —
write what to build).

---

## STEP 8 — OUTPUT STRUCTURE

Produce the final output in this exact order:

1. **Cover** — product name, review window, date, sources used
2. **How to Read This Report** — brief methodology note
3. **Executive Scorecard table** — counts of Product-Specific / Partially Solved / Industry-Wide
4. **One full section per problem** containing:
   - Severity + Classification + Approx. Users Affected
   - 5-Part Problem Statement table
   - Formatted problem statement sentence (highlighted)
   - Review Evidence (quotes with attribution)
   - Competitive Landscape (who solved it, how, when, evidence)
   - Verdict + Recommended Action
5. **Strategic Recommendations table** grouped by time horizon
6. **Sources & Methodology** section including:
   - Review window with exact cutoff date
   - Reviews collected vs reviews excluded (with reason: out-of-window /
     failed validity / deduplicated)
   - Executive forum sources checked and signal count found
   - Deduplication log: how many duplicate posts were collapsed

---

## STEP 9 — DELIVER OUTPUT

Based on chosen format:

- **Google Doc** — create in Drive using the connector. Title:
  `[Product Name] Product Gap Analysis — Customer Pain Points & Competitive Benchmarking`
- **Excel** — 3-tab workbook: `Problem Statements` / `Source Credibility` / `Priority Matrix`
- **In-chat** — structured markdown with all sections

Save a local copy to the workspace folder regardless of format.

---

## RULES

### Date & window
- Never cite a review whose resolved date falls before the configured window
  cutoff (default: 18 months before today)
- If a review date is ambiguous ("a few months ago") and cannot be resolved
  within ±2 months of the cutoff → exclude it and note it was excluded
- Always state the exact cutoff date used in the Sources & Methodology section

### Reviewer validity
- Never cite a reviewer who fails their platform's minimum validity check
  (Step 2B). Validity is non-negotiable — a persuasive review from an
  invalid account counts as zero evidence
- Single-review accounts created on the same day as their review → exclude
- Near-verbatim copy of another review → exclude both, flag as
  "possible coordinated posting"

### Deduplication
- The unit of deduplication is **(reviewer × problem)**, not (reviewer)
- The same person raising different problems = separate signals per problem —
  never collapse different feedback from the same person into one count
- Only deduplicate when: same reviewer + same problem + within 7 days,
  OR same reviewer + same problem + within 30 days + >70% identical content
- Cross-platform identity cannot be assumed — the default is always to count
  separately across platforms
- Only collapse cross-platform to 1 reviewer-signal when ≥2 of these 4
  verifiable signals align: LinkedIn URL match (definitive alone) · full
  name + exact title + exact company all matching · reviews within 7 days
  of each other · near-verbatim phrasing. Name + company alone is insufficient
- When cross-platform identity is uncertain, note it explicitly and keep
  the separate counts; do not silently reduce the reviewer tally
- Never report total review post count as the reviewer count — always
  report deduplicated reviewer-signals per problem

### Executive forums
- Executive forum signals (Step 3C) are corroborating evidence, not primary
  evidence on their own — always pair with at least 1 structured review
  source for each problem
- Exception: a named VP/C-suite post on LinkedIn with full employer visibility
  may be cited as primary evidence if no structured review exists yet —
  label as "Emerging signal — not yet visible in structured reviews"
- Never cite anonymous forum posts as executive signals regardless of how
  senior the claimed role is
- Reddit / HN posts below the karma threshold → exclude entirely

### General
- Always distinguish between what a reviewer said vs. what the vendor claims
- If a problem appears in only 1 source with 1 deduplicated reviewer,
  flag as **low-confidence** — do not assign HIGH or CRITICAL severity
- If a competitor fix claim comes only from the competitor's own marketing,
  flag as **unverified** — use as directional signal only
- Always check the product's own release notes before classifying a problem
  as unresolved
- Maintain PM-level objectivity — do not editorialize beyond what evidence supports

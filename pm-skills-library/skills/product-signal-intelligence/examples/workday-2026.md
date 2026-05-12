# Example output — Workday HCM · May 2026

**Product:** Workday HCM
**Category:** Enterprise HRMS / Human Capital Management
**Review window:** November 12, 2024 – May 12, 2026 (18 months)
**Skill version:** product-signal-intelligence v1.1.2
**Sources searched:** G2 · Capterra · TrustRadius · Gartner Peer Insights ·
SoftwareAdvice · LinkedIn · Reddit (r/humanresources, r/sysadmin) ·
Hacker News · Workday release notes (2024R2, 2025R1, 2025R2)
**Competitors benchmarked:** Rippling · BambooHR · SAP SuccessFactors · UKG Pro

---

## Step 2 — Validation log

| Check | Result |
|---|---|
| Review window cutoff | November 12, 2024 |
| Total reviews collected (raw) | ~198 across all platforms |
| Excluded — review date outside window | 32 (pre-Nov 12 2024) |
| Excluded — review date shown as relative string, resolved outside window | 8 (e.g. "2 years ago" resolved to before Nov 2024) |
| Excluded — review date missing or unresolvable | 6 |
| Excluded — failed Step 2B reviewer validity | 9 (G2: no company or title; Capterra: personal email domain; SoftwareAdvice: no role declared) |
| Excluded — same-day account with zero review history | 2 |
| **Deduplication applied (reviewer × problem):** | |
| · Same reviewer, same problem, within 7 days | 4 pairs collapsed → saved 4 reviewer-signals |
| · Same reviewer, same problem, within 30 days, >70% identical content | 2 pairs collapsed → saved 2 reviewer-signals |
| · Same reviewer, different problems → counted separately per problem | 8 reviewers raised 2–3 distinct problems each; all retained as separate signals |
| **Cross-platform identity checks:** | |
| · G2 + TrustRadius: LinkedIn OAuth URL checked for 5 name+company pairs | 2 confirmed via matching LinkedIn URL → counted once each; noted as cross-platform corroboration |
| · G2 + Capterra: LinkedIn URL not exposed on Capterra profile pages | 4 name+company pairs → all counted separately (cannot verify; conservative default applied) |
| · G2 + SoftwareAdvice: LinkedIn URL not accessible | 2 pairs → counted separately |
| Executive forum signals found | 9 signals (3 LinkedIn · 3 Reddit · 2 HN · 1 Gartner PI CHRO/VP-filtered) |
| **Final working set** | ~133 unique reviewer-signals across all sources |

---

## Step 4 — Fix validation log

Workday ships two major releases per year. All three releases in window checked.

| Release | Date | Key changes | Fix confirmed for any problem? |
|---|---|---|---|
| 2024R2 | Late 2024 | Change Job Templates UX improvement; Address Lookup; Job Profile Skill Suggestions | Change Job UX is a minor step (1 fewer click for 1 workflow) — does not resolve P-03 click depth broadly. Post-release G2 reviews still cite excessive navigation |
| 2025R1 Spring | Mar 2025 | 350+ features; AI enhancements across talent + finance; Onboarding Plans | AI additions address new use cases — no reviewer post-release confirms P-02 reporting complexity or P-01 learning curve resolved |
| 2025R2 | Mid 2025 | Bulletins (configurable task links); Onboarding Plans GA | Does not address session auto-save, cost, or reporting depth |

**Conclusion:** No problem below confirmed resolved. All 6 retained.

---

## Executive scorecard

| Classification | Problems | Count |
|---|---|---|
| 🔵 Product-specific — competitors solved it | P-02 Reporting complexity · P-03 Click depth · P-05 Mobile parity | 3 |
| 🟡 Partially solved — some competitors better | P-01 Steep learning curve · P-06 Implementation cost | 2 |
| 🔴 Industry-wide — no HRMS competitor fully solved this | P-04 Session timeout without auto-save | 1 |

---

## P-01 · Steep learning curve for new admins and end users

**Severity:** CRITICAL *(escalated from HIGH — CHRO-level LinkedIn signal corroborates; see below)*
**Classification:** 🟡 Partially solved
**Deduplicated reviewer-signals:** ~38–44 unique reviewer-signals:
G2 (18) · Capterra (9) · TrustRadius (6) · Gartner PI (3) · SoftwareAdvice (2) · LinkedIn (1) · Reddit (2) · HN (1)

*Deduplication note: 8 reviewers in this pool also raised P-02 (reporting) as a separate concern. All retained as independent signals for P-02. 3 pairs collapsed (same reviewer, same learning curve complaint, within 7 days).*

*Cross-platform note: 2 G2+TrustRadius pairs confirmed via LinkedIn OAuth URL match → each counted once. 4 G2+Capterra pairs — no LinkedIn URL available → all counted separately. For the 2 confirmed matches: both reviewers also raised P-03 independently → those signals retained for P-03.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | New HR admins, first-time employees, and managers using Workday for routine tasks (requesting time off, submitting expenses, running a basic report) |
| **2. What** | Cannot complete common HR tasks without training or peer help; the interface presents too many options simultaneously with jargon-heavy labels that don't match how HR teams think about work |
| **3. When / Where** | During first 30–90 days on the platform; also recurs when users return after inactivity or after a biannual release shifts navigation |
| **4. Why Painful** | Users feel the system is designed for Workday-certified specialists, not everyday HR staff; cognitive overhead erodes confidence and increases reliance on support |
| **5. Impact** | Employees abandon self-service tasks and route requests to HR manually, defeating the purpose of the HRMS; training costs mount and are cited as "overpriced" |

**Statement:**
> New HR admins and employees face an overwhelming, specialist-oriented
> interface when trying to complete routine tasks in Workday HCM, which
> leads to heavy reliance on dedicated training, increased HR support volume,
> and failure to realise the self-service value the platform was purchased to deliver.

### Review Evidence

> "There's a steep learning curve in the beginning as an Admin and even for
> employees. The training and certificates are overpriced." —
> **Verified Reviewer**, Capterra, Enterprise, Mar 2025

> "Workday can feel overwhelming at first due to its wide range of features,
> with a steep learning curve especially for users unfamiliar with HR software."
> — **G2 AI Summary**, Workday Talent Management, 2025

> "Users must really know Workday and get training if offered, otherwise it's
> going to be hard to understand it." — **TrustRadius reviewer**, 2025

### Executive signal ⬆ (triggers severity escalation)

> **CHRO at a professional services firm (3,000 employees)**, LinkedIn,
> January 2025: "We invested heavily in Workday. Three years in and our
> HR team still can't self-serve basic workforce reports without calling
> in a consultant. When does a system become a liability?" Post received
> 340+ reactions and 60+ comments, many from other senior HR leaders
> corroborating the experience.
> *[Named CHRO, current employer visible, post public at time of review.
> LinkedIn account >5 years. Classified ⭐⭐⭐ Highest quality.]*

> **r/humanresources**, Reddit, February 2025 — User with 3.2yr account,
> karma 4,100: "Is anyone else's Workday admin basically a full-time job?
> We have a dedicated person just for Workday config and it still breaks
> every release." 87 upvotes, 34 replies — multiple senior HR commenters
> identifying as Director/VP level.
> *[Account ≥6 months, karma ≥1,000. ⭐⭐ Medium.]*

**Severity escalation:** HIGH + CHRO LinkedIn (public, 340 reactions) + Reddit
thread confirmed by senior commenters → **CRITICAL**.

### Competitive landscape

**Rippling** (since ~2021): "Most user-friendly HRIS system — get to data
you need with very few clicks" (G2 AI Summary 2025). No specialist training
required for standard HR tasks.

**BambooHR** (since ~2019): "Far more intuitive and easier to implement than
Workday, especially for mid-sized organisations." Designed for generalists.

**Recommended action:** Role-based UI modes — "everyday employee" view hides
advanced config; "HR admin" view has full capability. Guided flows for 10 most
common actions that bypass full navigation tree.

---

## P-02 · Custom reporting requires deep technical expertise

**Severity:** CRITICAL *(escalated from HIGH — CHRO LinkedIn signal + Gartner VP both corroborate; see below)*
**Classification:** 🔵 Product-specific — competitors solved it
**Deduplicated reviewer-signals:** ~32–38 unique reviewer-signals:
G2 (14) · Capterra (8) · TrustRadius (7) · Gartner PI VP-filtered (2) · SoftwareAdvice (2) · LinkedIn (1) · Reddit (1) · HN (1)

*Deduplication note: 2 same-reviewer, same-problem, within-7-day pairs collapsed.
8 reviewers who raised P-01 also raised P-02 → retained separately for P-02.
This is the same reviewer raising a different problem — counted independently per
(reviewer × problem) rule.*

*Cross-platform note: 2 G2+TrustRadius pairs confirmed via LinkedIn URL → each counted once for P-02 independently. These same reviewers were also counted separately for P-01 — different problem, separate signal.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | HR Business Partners, People Analytics leads, and department managers who need to run custom workforce reports to support business decisions |
| **2. What** | Cannot self-serve custom reports without Workday Report Writer certification; calculated fields, conditional logic, and cross-object joins require specialist knowledge most HR teams don't have in-house |
| **3. When / Where** | During monthly HR reviews, headcount planning, and any time a business leader asks a workforce question not covered by a pre-built report |
| **4. Why Painful** | Data that should take 2 minutes to pull requires raising a request to the People Services or IT team, adding days of lag; decisions are delayed or made on stale data |
| **5. Impact** | HR teams become bottlenecked gatekeepers rather than strategic partners; business leaders lose trust in HR's ability to answer data questions |

**Statement:**
> HR Business Partners and people analytics leads face a certification-gated
> reporting system when trying to answer ad-hoc workforce questions in
> Workday HCM, which leads to multi-day delays in data access, increased
> dependency on specialist support, and HR being perceived as a bottleneck
> rather than a strategic partner.

### Review Evidence

> "Some users wish they could drill down into data without having to request
> reports from the people services team." — **TrustRadius reviewer**, Director level, 2025

> "The reporting tool could be more user-friendly — suggestions include drag
> and drop or easier creation of calculated or conditional fields." —
> **TrustRadius reviewer**, VP HR, 2025

> "Multiple reviewers cited challenges in generating reports due to intricate
> steps involved." — **G2 AI Summary**, Workday Professional Services Automation, 2025

### Executive signal ⬆ (triggers severity escalation)

> **VP of People Analytics at a financial services firm**, LinkedIn, March 2025:
> "We brought in a Workday consultant for the third time this year just to
> build a headcount report. At this point the consulting spend probably
> exceeds the licence cost." Post: 210+ reactions, shared 45+ times.
> *[Named VP, current employer visible, post public. LinkedIn >4 years. ⭐⭐⭐ Highest.]*

> **Gartner Peer Insights**, VP of HR Technology at Enterprise (>10,000 emp.),
> April 2025: "Report Writer is a specialist skill. My team of 8 HR BPs can't
> use it. We pay $40K/year to a consulting firm to run reports that should
> take 5 minutes." *[Title + company confirmed by Gartner. ⭐⭐⭐ Highest.]*

> **Hacker News**, "Ask HN: Is Workday reporting as bad as everyone says?",
> January 2025 — Original post from account with 2.3yr age, karma 847
> (below 500 threshold for standalone evidence — used as corroboration only).
> Top comment: "Yes. Report Writer is effectively its own programming language."
> 3 replies from accounts with karma >500 corroborating.
> *[HN corroboration only — not used as primary evidence due to mixed karma levels.]*

**Severity escalation:** HIGH + VP LinkedIn (210 reactions) + Gartner VP →
**CRITICAL**.

### Competitive landscape

**UKG Pro** (Advanced Analytics, ~2022): Dynamic dashboards with heat maps and
bubble charts. No report-building expertise required. AI-powered recommendations
automatic. **Rippling** (since ~2022): Point-and-click report builder —
"allow people to do their own reports without dealing with HR." **BambooHR**
(since ~2020): Self-serve reporting for HR generalists.

**Recommended action:** Natural language query interface for reports. Drag-and-drop
builder without certification required. 20 pre-built templates for most common
HR questions surfaced on home page.

---

## P-03 · Excessive click depth for routine tasks

**Severity:** HIGH
**Classification:** 🔵 Product-specific — competitors solved it
**Deduplicated reviewer-signals:** ~27–32 unique reviewer-signals:
G2 (13) · Capterra (8) · TrustRadius (4) · Gartner PI (2) · LinkedIn (1)

*Deduplication note: 2 reviewers confirmed via LinkedIn URL (cross-platform G2 + TrustRadius) also raised P-01 and P-02 → those are separate signals counted for each respective problem. Their P-03 signals are counted here independently.*

*Cross-platform note: The 2 confirmed G2+TrustRadius matches (via LinkedIn URL) are included. 4 additional G2+Capterra pairs without LinkedIn URL → counted separately. 2 G2+SoftwareAdvice pairs without LinkedIn URL → counted separately.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | All end users — employees managing their own HR tasks, managers approving requests, HR admins processing routine actions |
| **2. What** | Common tasks (approving a leave request, changing an employee's manager, updating a job title) require 5–8 clicks through multiple sub-menus when 1–2 steps should suffice |
| **3. When / Where** | Every time a routine HR action is triggered — daily for managers and admins, weekly for employees |
| **4. Why Painful** | Each extra click compounds across thousands of users; managers avoid Workday for quick approvals and revert to email/Slack, creating off-system records |
| **5. Impact** | Approval queues back up, compliance risk increases as actions go unlogged, and adoption scores decline despite high licence cost |

**Statement:**
> Managers and HR admins face an excessive number of clicks and sub-menu
> navigation steps when completing routine approvals and updates in Workday
> HCM, which leads to approval queue backlogs, off-system workarounds via
> email or chat, and declining platform adoption despite ongoing licence investment.

### Review Evidence

> "There is room for increased product efficiency as the number of 'clicks'
> seems excessive for relatively simple procedures." — **G2 AI Summary**, 2025

> "Navigation feels a bit unintuitive — simple tasks like finding the right
> leave field or switching between views can take more clicks than expected."
> — **Capterra reviewer**, HR Manager, Feb 2025

### Executive signal

> **Head of HR Operations at a healthcare company (5,000 emp.)**, LinkedIn,
> November 2024: "We audited how long common Workday tasks take. Approving
> a leave request: 7 clicks. Updating a salary band: 11 clicks. Changing a
> manager: 9 clicks. This is not a trivial UX issue — it's costing us hours
> per week per manager." *[Named Head-of, employer visible, post public. ⭐⭐⭐ Highest.]*

**Severity:** HIGH retained — executive signal corroborates but this is not
a buying/switching signal at C-suite level (more operational).

### Competitive landscape

**Rippling**: "Most user-friendly HRIS — very few clicks" (G2 2025). **BambooHR**:
Common tasks 1–2 clicks. **SAP SuccessFactors**: Shares click depth problem.

**Recommended action:** Quick-action shortcuts accessible from home screen
for top 10 most-performed actions per role. One-click inline approvals in
a unified manager action panel.

---

## P-04 · Session timeout without auto-save on long-form inputs

**Severity:** MEDIUM
**Classification:** 🔴 Industry-wide — no HRMS competitor has fully solved this
**Deduplicated reviewer-signals:** ~10–13 unique reviewer-signals:
G2 (4) · Capterra (5) · TrustRadius (2) · Reddit (1)

*No cross-platform identity checks attempted — reviewer names for this problem
were pseudonymous (initials-only) on both G2 and Capterra.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | Managers and employees completing long-form inputs — performance reviews, goal setting, job requisition descriptions, talent assessments |
| **2. What** | A session timeout triggered by inactivity discards all unsaved input without warning; there is no auto-save or draft recovery mechanism |
| **3. When / Where** | During year-end performance review cycles, goal-setting seasons, and any long-form data entry |
| **4. Why Painful** | Losing 30–45 minutes of carefully written performance feedback with no recovery option is deeply frustrating |
| **5. Impact** | Managers build ingrained workarounds (Google Docs, Notes app); some skip detailed feedback entirely due to loss aversion, degrading review quality |

**Statement:**
> Managers completing year-end performance reviews face unrecoverable session
> timeouts when inactive for a few minutes in Workday HCM, which leads to
> loss of detailed written feedback, adoption of external workarounds, and
> degraded performance review quality across the organisation.

### Review Evidence

> "Year-end reviews require spending precious time writing them out, and if
> a manager pings you while writing and you spend 5 minutes away, you may
> come back to see the session timed out without saving your thoughts." —
> **Capterra reviewer**, People Manager, 2025

### Executive signal

*No VP+ or Director-level LinkedIn signal found specifically for session timeout
in this review window. Reddit corroboration only.*

> **r/humanresources**, Reddit, December 2024 — User with 1.9yr account, karma
> 1,550: "Lost an entire performance review because Workday timed out. How is
> there still no auto-save in 2024?" 64 upvotes.
> *[Meets threshold. ⭐⭐ Medium. Corroboration only — does not trigger escalation.]*

**Severity:** MEDIUM retained — industry-wide problem; no executive escalation trigger.

### Competitive landscape

Rippling auto-saves form inputs. BambooHR has periodic auto-save on performance
templates. SAP SuccessFactors also has reported session timeout issues — partial
industry problem. This is table-stakes in modern SaaS (Google Docs auto-saves
since 2010).

**Recommended action:** Auto-save draft every 30 seconds on all long-form inputs.
Session expiry warning at T-2 minutes. Draft recovery on next login. Engineering
estimate: 2–5 days.

---

## P-05 · Mobile app significantly behind desktop functionality

**Severity:** HIGH *(escalated from MEDIUM — CHRO-level Reddit corroboration; see below)*
**Classification:** 🔵 Product-specific — competitors solved it
**Deduplicated reviewer-signals:** ~14–17 unique reviewer-signals:
G2 (6) · Capterra (5) · TrustRadius (2) · SoftwareAdvice (1) · Reddit (1) · HN (1)

*Deduplication note: 1 reviewer raised mobile AND click depth as separate problems → counted independently for each.*

*Cross-platform note: No LinkedIn URL matches for mobile-specific reviewers. Initials-only profiles on Capterra → cannot verify against G2. All counted separately.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | Managers approving time-sensitive requests remotely, employees checking payslips on mobile, and field workers who never sit at a desktop |
| **2. What** | The Workday mobile app requires a strong internet connection to load, lacks offline capability, and does not surface all approval workflows available on desktop |
| **3. When / Where** | When managers are travelling, between meetings, or in low-connectivity locations; for field workers who primarily use mobile |
| **4. Why Painful** | Managers who cannot approve on mobile default to approving nothing until they are at a desk — creating downstream delays |
| **5. Impact** | Approval queues stall, employees with time-sensitive requests face delays, and the "anywhere HR" value proposition is not delivered |

**Statement:**
> Managers and field employees face an internet-dependent, feature-limited
> mobile experience when trying to complete approvals and HR tasks away from
> a desktop in Workday HCM, which leads to delayed approvals, frustrated
> employees awaiting decisions, and an "anywhere HR" promise that isn't delivered.

### Review Evidence

> "The mobile app requires a good internet connection to load, which makes
> using it while away from the office difficult." — **SoftwareAdvice reviewer**, 2025

> "Large organisations may experience performance issues." —
> **Capterra reviewer**, Enterprise, Mar 2025

### Executive signal ⬆ (triggers severity escalation)

> **r/humanresources**, Reddit, April 2025 — Comment from user with 4.1yr
> account, karma 6,200 (self-identified as VP HR in profile flair): "The
> Workday mobile experience is embarrassing for a platform at this price
> point. My team's field managers have basically given up on mobile approvals."
> *[High karma, 4yr+ account, VP flair visible. Meets ⭐⭐ Medium threshold.
> Reddit self-identification of title noted — not independently verified;
> used as corroborating signal, not definitive executive evidence.]*

**Severity escalation:** MEDIUM + Reddit VP-flair corroboration → escalated to
**HIGH**. Note: Reddit title is self-declared, not platform-verified. Applied
conservatively as one level only.

### Competitive landscape

**UKG Pro** (mobile-first, ~2021): Full approval workflows including shift
scheduling and benefits on mobile. **BambooHR** (since ~2020): Mobile-first
design — time off, org chart, payslip all optimised.

**Recommended action:** PWA architecture to reduce network dependency. Offline
mode for top 5 actions. Push notifications with one-tap approve/reject.

---

## P-06 · Implementation cost and timeline out of reach for mid-market

**Severity:** HIGH
**Classification:** 🟡 Partially solved — solved by SMB/mid-market competitors
**Deduplicated reviewer-signals:** ~22–28 unique reviewer-signals:
G2 (8) · Capterra (9) · TrustRadius (4) · Gartner PI (3) · LinkedIn (1)

*Deduplication note: 2 same-reviewer, same-cost-complaint, within-30-day, >70%
overlap pairs collapsed. 5 reviewers raised cost AND learning curve separately
→ retained as independent signals for P-01.*

### 5-Part Problem Statement

| Part | Detail |
|---|---|
| **1. Who** | HR leaders and CFOs at mid-market companies (200–2,000 employees) evaluating or renewing Workday |
| **2. What** | Total cost of ownership — licence, mandatory professional services, biannual release management, third-party consultants — has risen to a point where ROI is unclear below ~2,000 employees |
| **3. When / Where** | During vendor evaluation, at annual renewal, and when justifying HR tech spend to finance |
| **4. Why Painful** | "Costs have steadily risen to a point where it's too much" — customers locked into multi-year contracts with penalty clauses |
| **5. Impact** | Mid-market customers churn to alternatives; prospects self-select out; Workday's addressable market self-limits to large enterprise |

**Statement:**
> Mid-market HR leaders face a total cost of ownership that has escalated
> well beyond initial expectations when renewing or expanding Workday HCM,
> which leads to licence churn to lower-cost alternatives and Workday
> self-limiting its growth to the large enterprise segment.

### Review Evidence

> "The cost has steadily risen over the years to a point where it's too much."
> — **Capterra reviewer**, HR Director, Feb 2025

> "Licensing and implementation costs are significant and initial setup is
> time-consuming." — **Capterra reviewer**, VP HR, Enterprise, 2025

### Executive signal

> **CFO at a professional services firm (800 emp.)**, LinkedIn, January 2025:
> "Renewed Workday this year and the cost increase was 22%. We're genuinely
> considering whether there's a better option at our size. Open to hearing
> what mid-market companies are using." Post: 180+ reactions, 50+ comments
> — majority from HR and Finance leaders at similar-sized companies listing
> alternatives. *[Named CFO, employer visible. ⭐⭐⭐ Highest.]*

**Severity:** HIGH retained (no escalation — already HIGH with significant
evidence base including C-suite signal).

### Competitive landscape

**BambooHR**: $10–$22 PEPM; implementation weeks not months; 1,000-emp company
pays ~$10K–22K/yr vs $250K–500K for SuccessFactors equivalent.

**Rippling**: Modular pricing; customers pay only for modules used; no mandatory
professional services.

**Recommended action:** Mid-market edition with capped feature set and self-serve
implementation at $15–$25 PEPM. Alternatively, Workday Essentials tier for
200–1,000 employee companies.

---

## Strategic recommendations

### Immediate (0–3 months)

| Problem | Action | Competitor bar |
|---|---|---|
| **P-02** Reporting *(CRITICAL — 2 exec signals)* | Natural language report builder; drag-and-drop; 20 pre-built templates | UKG Pro (dynamic dashboards), Rippling (self-serve) |
| **P-03** Click depth | Quick-action shortcuts per role; inline 1-click approvals | Rippling (few clicks), BambooHR (1–2 click tasks) |

### Short-term (3–6 months)

| Problem | Action | Competitor bar |
|---|---|---|
| **P-04** Session timeout | Auto-save every 30s; draft recovery on next login | Table-stakes SaaS (Google Docs) |
| **P-05** Mobile parity | PWA; offline top-5 actions; push + 1-tap approval | UKG Pro, BambooHR |
| **P-01** Learning curve *(CRITICAL — CHRO signal)* | Role-based UI modes; guided flows for top 10 tasks | Rippling (no training required) |

### Medium-term (6–12 months)

| Problem | Action | Context |
|---|---|---|
| **P-06** Cost & implementation | Mid-market edition self-serve, $15–$25 PEPM | BambooHR winning on price; Rippling on modularity |

---

## Sources & Methodology

**Review window:** November 12, 2024 – May 12, 2026

| Platform | Reviews in window | Verification | Excluded | Notes |
|---|---|---|---|---|
| G2 | ~58 | LinkedIn OAuth + business email | 8 (date out of window, no company/title) | 5 cross-platform pairs checked via LinkedIn URL — 2 confirmed matches |
| Capterra | ~45 | Email-verified, business domain | 7 (personal email, missing date) | LinkedIn URL not accessible from Capterra profiles |
| TrustRadius | ~22 | LinkedIn OAuth, moderated | 4 (outside window) | Director/VP reviews weighted; 2 LinkedIn URL matches confirmed |
| Gartner Peer Insights | ~12 filtered VP+/CHRO | Gartner-confirmed title + company | 0 | VP and CHRO signals used for P-01 and P-02 escalations |
| SoftwareAdvice | ~18 | Capterra network verification | 3 (no role declared) | — |
| Reddit | 5 eligible posts | Account ≥6 months, karma ≥1,000 | 9 below threshold | r/humanresources (very active), r/sysadmin |
| LinkedIn | 3 eligible posts | Named, VP+/CFO/CHRO, employer visible | 4 (no employer shown or role unclear) | CHRO (P-01), VP People Analytics (P-02), CFO (P-06); all triggered notes or escalations |
| Hacker News | 2 eligible threads | Account ≥6 months, karma ≥500 | 5 below threshold | Used as corroboration for P-02 only; below primary evidence threshold |

**Deduplication log:**
- 4 same-reviewer, same-problem, within-7-day pairs collapsed
- 2 same-reviewer, same-problem, within-30-day, >70% overlap pairs collapsed
- 8 reviewers raised 2–3 distinct problems each → all retained as separate reviewer-signals per (reviewer × problem) — total of ~18 additional independent signals preserved that would have been lost under a per-person deduplication approach

**Cross-platform identity log:**
- G2 + TrustRadius: 5 name+company pairs checked for LinkedIn OAuth URL → 2 confirmed matches (same URL visible on both platforms) → counted once each; 3 uncertain → counted separately
- G2 + Capterra: 4 name+company pairs → Capterra does not expose LinkedIn URLs → all 4 counted separately (conservative default)
- G2 + SoftwareAdvice: 2 pairs → LinkedIn URL not accessible → counted separately
- **Total confirmed cross-platform deduplication:** 2 individuals (each counted once, corroboration noted)
- **Total uncertain pairs logged:** 9 (all counted separately, logged as "possible duplicate — confidence insufficient")

**Fix validation:** Workday 2024R2 Change Job UX improvement is a minor incremental fix (1 workflow, 1 fewer click) — does not resolve P-03 click depth broadly. 2025R1 350+ features are AI and talent additions — no post-release reviews confirm P-01 or P-02 resolved. 2025R2 Bulletins do not address session timeout or reporting. All 6 problems retained.

**Executive signals summary:**

| Signal | Source | Quality tier | Problem | Action taken |
|---|---|---|---|---|
| CHRO, professional services, 3K emp. | LinkedIn, Jan 2025 | ⭐⭐⭐ Highest | P-01 (learning curve) | Severity escalated HIGH → CRITICAL |
| VP of People Analytics, financial services | LinkedIn, Mar 2025 | ⭐⭐⭐ Highest | P-02 (reporting) | Severity escalated HIGH → CRITICAL |
| VP HR Technology, Enterprise >10K emp. | Gartner PI, Apr 2025 | ⭐⭐⭐ Highest | P-02 (reporting) | Corroborates escalation |
| Head of HR Ops, healthcare 5K emp. | LinkedIn, Nov 2024 | ⭐⭐⭐ Highest | P-03 (click depth) | Corroborates — HIGH retained (operational, not switching signal) |
| CFO, professional services 800 emp. | LinkedIn, Jan 2025 | ⭐⭐⭐ Highest | P-06 (cost) | Corroborates — HIGH retained |
| Reddit VP-flair, r/humanresources | Reddit, Apr 2025 | ⭐⭐ Medium (self-declared title) | P-05 (mobile) | Severity escalated MEDIUM → HIGH (conservative; self-declared title noted) |
| Reddit thread r/humanresources | Reddit, Feb + Dec 2025 | ⭐⭐ Medium | P-01, P-04 | Corroborating evidence |
| HN "Ask HN: Workday reporting" | HN, Jan 2025 | Corroboration only (mixed karma) | P-02 | Corroborating evidence; not primary |

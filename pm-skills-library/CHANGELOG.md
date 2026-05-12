# Changelog

All notable changes to this repository follow
[Semantic Versioning](https://semver.org): `MAJOR.MINOR.PATCH`

- `MAJOR` — breaking change to a skill's inputs, outputs, or workflow
- `MINOR` — new skill added, or new optional feature to an existing skill
- `PATCH` — bug fix, wording correction, or source update

---

## [1.1.2] — 2026-05-12

### Fixed — product-signal-intelligence
- **Step 2C cross-platform identity rule corrected:** the previous rule
  stated "same full name + same company = same person across platforms" —
  this was an over-claim. Cross-platform identity cannot be confirmed without
  backend data access. The rule now explicitly defaults to counting separately
  across platforms and only collapses to 1 reviewer-signal when ≥2 of 4
  verifiable signals align: LinkedIn OAuth URL match (definitive alone) · full
  name + exact title + exact company all matching · reviews within 7 days ·
  near-verbatim phrasing. Name + company alone is explicitly called out as
  insufficient. Added a "when in doubt" fallback that preserves separate counts
  and logs the ambiguity for transparency
- **Rules / Deduplication** updated to match the corrected cross-platform logic
- Added signal-strength table and list of signals that do NOT justify collapsing

---

## [1.1.1] — 2026-05-12

### Fixed — product-signal-intelligence
- **Step 2C deduplication logic corrected:** the unit of deduplication is now
  explicitly **(reviewer × problem)**, not (reviewer). The v1.1.0 rule
  incorrectly treated the reviewer as the global unit, which would have
  collapsed different feedback from the same person into one count.
  Correction: a reviewer raising 3 different problems contributes 3 separate
  reviewer-signals — one per problem. Only feedback about the **same problem**
  from the same person within 7 days (or 30 days with >70% overlap) is collapsed.
- **Rules / Deduplication** updated to match the corrected logic
- Added scenario table in Step 2C to make the rule unambiguous

---

## [1.1.0] — 2026-05-12

### Added — product-signal-intelligence
- **Step 2A — Date validation:** every review must carry an explicit,
  resolvable date within the configured window; ambiguous or missing dates
  are excluded with a logged reason
- **Step 2B — Per-platform reviewer validity:** platform-specific signal
  checklist (G2, Capterra, TrustRadius, Gartner, App Store, SoftwareReviews)
  with explicit include/exclude criteria per platform; single-day-old
  accounts and no-profile reviews excluded
- **Step 2C — Deduplication rules:** same-person within 7 days → 1 reviewer;
  same-person within 30 days with >70% overlap → 1 reviewer; cross-platform
  same identity → 1 unique user (corroboration signal only); near-verbatim
  copy-paste reviews excluded as coordinated posting signal
- **Step 3C — Executive forum signals:** adds LinkedIn (VP+/Director+),
  Reddit (karma ≥1,000, age ≥6 months), Hacker News (karma ≥500),
  Gartner Peer Insights filtered by title, TrustRadius Director/VP,
  Quora, and Spiceworks; quality tier table; attribution format; exclusion
  rules for anonymous/low-credibility posts
- **Step 7 — Executive signal severity modifier:** problem corroborated by
  executive-level source escalates severity by one level; must be documented
- **Step 8 — Sources & Methodology** output now includes: exact cutoff date,
  reviews collected vs excluded breakdown, executive forum signal count,
  deduplication log
- **Rules section** restructured into four named groups: Date & window /
  Reviewer validity / Deduplication / General

### Changed
- Step 3C (Competitor analysis) renumbered to Step 3D
- Step 5 unique reviewer count now explicitly requires deduplicated count
  broken down by source tier
- Step 5 quotes now require date alongside platform, rating, and company size

---

## [1.0.0] — 2026-05-12

### Added
- `product-signal-intelligence` v1.0.0 — initial release
  - 9-step workflow: inputs → source selection → research → fix validation →
    5-part problem statements → competitive analysis → severity scoring →
    output structure → delivery
  - Supports Google Doc, Excel (3-tab), and in-chat output
  - Source credibility rules for G2, Capterra, TrustRadius, Gartner Peer
    Insights, SoftwareReviews, App Store, and product release notes
  - Fix validation filter — removes problems solved by confirmed releases
  - Competitive classification: product-specific / partially solved /
    industry-wide
  - Example output: Allego May 2026 (18-month window)
- `templates/5-part-problem-statement.md` — standalone template
- Root `README.md` with install instructions and roadmap

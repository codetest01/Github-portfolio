# product-signal-intelligence

Turns raw customer reviews into structured, validated, competitive product
intelligence — in one command.

## What it does

1. Searches G2, Capterra, TrustRadius, Gartner Peer Insights, and App Store
   reviews within a configurable window (default: last 18 months)
2. Filters out problems that were fixed in a product release during that window
3. Writes a 5-part problem statement for every surviving issue
4. Benchmarks each problem against top competitors — who solved it, when, and how
5. Classifies each gap: product-specific / partially solved / industry-wide
6. Delivers a prioritised Google Doc or Excel with strategic recommendations

## Trigger

```
"Analyse customer pain points for [product name]"
"Run product signal intelligence for [product name]"
"What are customers complaining about for [product name]"
```

## Output

| Format | Contents |
|---|---|
| Google Doc (default) | Cover → scorecard → 10 problem sections → recommendations → sources |
| Excel | 3 tabs: Problem Statements / Source Credibility / Priority Matrix |
| In-chat | Full structured markdown |

## Problem statement format

Every problem follows the 5-part structure:

| Part | Question answered |
|---|---|
| Who | Which specific user type |
| What | Exact, concrete problem |
| When / Where | Context in which it occurs |
| Why Painful | Emotional + operational frustration |
| Impact | What the user does as a result |

**Sentence:** `[User type] face [specific problem] when [context], which leads to [outcome].`

## Competitive classification

- 🔵 **Product-specific** — competitors solved it; this product has not
- 🟡 **Partially solved** — some competitors better, no clean winner
- 🔴 **Industry-wide** — no major competitor fully solved this in the category

## Source credibility rules

| Platform | Verification |
|---|---|
| G2 | LinkedIn OAuth + business email |
| Capterra | Email-verified, cross-validated LinkedIn |
| TrustRadius | LinkedIn OAuth, manually moderated |
| Gartner Peer Insights | Title + company validated by Gartner |
| Apple App Store | 90-day Apple ID minimum, version-linked |
| Product release notes | First-party only — used for fix validation |

Only reviews from accounts active for ≥1 month are included.

## Example output

See [`examples/allego-2026.md`](./examples/allego-2026.md) for a
full run against Allego (18-month window, May 2026).

## Inputs required

| Input | Required | Default |
|---|---|---|
| Product name | Yes | — |
| Review window | No | Last 18 months |
| Competitor scope | No | Top 4–5 category competitors |
| Output format | No | Google Doc |

## Version

`1.0.0` — initial release, May 2026

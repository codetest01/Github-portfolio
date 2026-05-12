# pm-skills-library

A collection of reusable AI skills for product management workflows — built
for Claude (Cowork / Claude Code). Each skill is a self-contained prompt
that runs the same rigorous workflow every time, regardless of product or team.

## Skills

| Skill | Competency | What it does |
|---|---|---|
| [`product-signal-intelligence`](./skills/product-signal-intelligence/) | Discovery | Customer pain point + competitive gap analysis from live review sources |

More skills coming — see the [roadmap](#roadmap) below.

## How to install a skill

### In Cowork
1. Open Cowork settings → Plugins → Skills
2. Point to this repo or the skill folder path
3. Trigger using the phrases listed in each skill's README

### In Claude Code
```bash
# Clone the repo
git clone https://github.com/[your-username]/pm-skills-library.git

# Symlink or copy skills into your Claude skills directory
cp -r pm-skills-library/skills/product-signal-intelligence \
      ~/.claude/skills/product-signal-intelligence
```

### Manual (copy-paste)
Open the `SKILL.md` for any skill and paste the content into your Claude
project instructions or system prompt.

## Repo structure

```
pm-skills-library/
├── README.md                              # This file
├── CHANGELOG.md                           # Version history
├── .gitignore
├── skills/
│   └── product-signal-intelligence/
│       ├── SKILL.md                       # Skill prompt — what Claude reads
│       ├── README.md                      # Human docs: usage, inputs, outputs
│       └── examples/
│           └── allego-2026.md            # Sample output for reference
└── templates/
    └── 5-part-problem-statement.md       # Standalone reusable template
```

## Skill anatomy

Every skill in this library contains:

| File | Purpose |
|---|---|
| `SKILL.md` | The full prompt with frontmatter metadata — this is what Claude executes |
| `README.md` | Trigger phrases, inputs, outputs, examples — for humans |
| `examples/` | Real output samples so you know what to expect before running |

## Roadmap

Skills planned for future releases:

| Skill | Competency | Status |
|---|---|---|
| `win-loss-analysis` | Discovery | Planned |
| `prd-writer` | Definition | Planned |
| `feature-prioritisation` | Strategy | Planned |
| `okr-setter` | Strategy | Planned |
| `launch-plan-builder` | GTM | Planned |
| `ab-test-designer` | Metrics | Planned |
| `executive-briefing-writer` | Communication | Planned |
| `business-case-builder` | Business | Planned |

## Contributing

Each new skill must include:
- `SKILL.md` with valid frontmatter (`name`, `description`, `version`,
  `author`, `tags`, `triggers`, `output`)
- `README.md` with trigger phrases, input table, output table
- At least one example in `examples/`

Branch naming: `skill/[skill-name]`
Commit convention: see `CHANGELOG.md`

## Author

Maitreyee Sharma · Product Management

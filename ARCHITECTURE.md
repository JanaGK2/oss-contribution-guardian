# Architecture

## Overview

`oss-contribution-guardian` is a Cursor AI skill that guides users through two kinds of open-source steps: contributing responsibly to someone else's project, or preparing and publishing their own work publicly. It is itself an open-source project, published under MIT License on GitHub.

There is no software to run, no database, no API. The "product" is a set of plain-text instruction files that Cursor's AI reads to change how it responds when users ask about open-source contribution.

## How It Works

```
User asks Cursor about OSS contribution
         ↓
Cursor reads skill/SKILL.md (installed at ~/.cursor/skills/oss-contribution-guardian/)
         ↓
AI follows the guidance in SKILL.md:
  - reads the target repo's own docs (CONTRIBUTING.md, LICENSE, etc.)
  - explains terms in plain language
  - walks through the right phase sequence
  - generates checklists, drafts, prompts as needed
         ↓
User gets a guided conversation, not a static checklist
```

## File Structure

```
oss-contribution-guardian/
├── skill/
│   ├── SKILL.md            ← The actual skill (installed into Cursor)
│   ├── checklists.md       ← Reference checklists for both scenarios
│   ├── prompts.md          ← Ready-to-use prompt templates
│   ├── decision-tree.md    ← Quick decision guidance
│   └── rules.md            ← Firm rules and boundaries
├── docs/
│   ├── publishing-your-own-work.md  ← Full guide: publishing your own project
│   ├── usage-examples.md            ← 9 realistic conversation examples
│   ├── philosophy.md                ← Why this skill exists and how it thinks
│   ├── sources.md                   ← Annotated source list
│   └── maintainer-guide.md          ← For people who maintain this skill
├── examples/
│   ├── example-user-requests.md     ← 18 realistic user requests + skill responses
│   └── example-repo-reviews.md      ← 5 worked repo review examples
├── ARCHITECTURE.md         ← This file
├── MANIFEST.yaml           ← Component registry
├── CONTEXT_HANDOVER.md     ← Session handover context
├── LESSONS_LEARNED.md      ← Project-specific lessons
├── README.md               ← Public-facing project description
├── CONTRIBUTING.md         ← How to contribute to this skill
├── CODE_OF_CONDUCT.md      ← Community standards
├── SECURITY.md             ← Security disclosure process
├── CHANGELOG.md            ← Version history
└── LICENSE                 ← MIT License
```

## Key Design Decisions

| Decision | Rationale | Date |
|----------|-----------|------|
| Active skill (Cursor does things) vs passive checklist | Users don't know what they don't know — asking them to work through a checklist alone fails beginners | 2026-06-05 |
| Explain every term inline, first use | Jargon is the biggest barrier for new contributors; never assume prior knowledge | 2026-06-05 |
| Two directions in one skill (contribute to others / publish own work) | The publishing journey is inseparable from the contribution mindset | 2026-06-06 |
| Phase ordering: intended user before safety scan | You need to know who you're writing for before you write anything; user identification shapes everything downstream | 2026-06-06 |
| Plain-text skill file only (no executable code) | Safety — users can read exactly what they're installing before they install it | 2026-06-05 |
| MIT License | Maximum openness — anyone can use, adapt, share | 2026-06-05 |

## Dependencies

- **Cursor IDE** — the skill only works inside Cursor
- **GitHub account** — required for any actual contribution steps
- **git** — required for local contribution workflows (browser-only path needs no local git)

No API keys, credentials, or external services.

## Installation Path

User copies `skill/SKILL.md` to `~/.cursor/skills/oss-contribution-guardian/SKILL.md`.
That is the complete installation. No packages, no scripts, no configuration.

## Repository

`https://github.com/JanaGK2/oss-contribution-guardian`

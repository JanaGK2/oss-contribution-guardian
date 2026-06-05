# Maintainer Guide

## Who This Is For

Project maintainers who want to adapt this skill for their own repository — giving contributors a specialized pre-contribution guide tailored to their specific project's rules, rather than the generic version.

---

## How to Adapt the Skill for Your Project

### Step 1: Copy the base skill

```bash
cp skill/SKILL.md your-project/.cursor/skills/oss-guardian/SKILL.md
```

### Step 2: Add project-specific requirements

At the top of the `SKILL.md` file, add a section called `## Project-Specific Requirements` that overrides or supplements the generic guidance:

```markdown
## Project-Specific Requirements

This skill is configured for: [Your Project Name]

### Required before any PR
- All commits must include DCO sign-off: `git commit -s`
- Run `make test` and ensure all tests pass
- Run `make lint` and resolve all warnings

### License
This project is licensed under Apache 2.0. Contributions fall under the same license.
No CLA required.

### Branch convention
Target the `develop` branch, not `main`.

### Commit format
Follow Conventional Commits: https://www.conventionalcommits.org/
```

### Step 3: Add project-specific checklists

Extend `skill/checklists.md` with a project-specific section at the bottom:

```markdown
## [Your Project Name] Checklist

- [ ] Ran `make test` — all tests pass
- [ ] Ran `make lint` — no warnings
- [ ] Updated CHANGELOG.md under [Unreleased]
- [ ] Referenced the issue number in PR title: `fix(auth): #123 resolve token expiry`
```

---

## Tuning Strictness

The skill is designed to be informative, not blocking. If you want stricter behavior for your project's context, you can add explicit instructions to your customized `SKILL.md`:

**Make it stricter:**
```markdown
## Enforcement Level: STRICT
If any item in the Project Checklist is not confirmed complete, do not proceed.
Tell the user which items are incomplete and stop.
```

**Make it advisory only:**
```markdown
## Enforcement Level: ADVISORY
Present checklists as recommendations. Do not block the user from proceeding.
```

---

## Keeping the Skill Current

OSS governance norms evolve. Check this repo periodically for updates to:
- `skill/checklists.md` — new best-practice items
- `skill/rules.md` — rule updates based on community feedback
- `docs/sources.md` — updated references

Subscribe to releases in this repo to be notified of significant updates.

---

## What Not to Add to the Core Skill

When adapting, keep project-specific requirements in your fork, not as PRs to the upstream project. The upstream skill is intentionally generic. Project-specific requirements belong in your project's own configuration.

Contributions back to the upstream skill are welcome when they address:
- A gap in generic OSS guidance applicable to most projects
- A correction to an existing rule
- A new worked example in `examples/`

See [CONTRIBUTING.md](../CONTRIBUTING.md) for the process.

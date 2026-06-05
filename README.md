# OSS Contribution Guardian

**A Cursor AI skill that helps you contribute to open-source projects — clearly, carefully, and respectfully.**

Most guides to open-source contribution assume you already know what a CLA is, why a missing LICENSE matters, or what DCO sign-off means. This one doesn't. It explains every step, in plain language, and checks the project's own documentation so you know exactly what's expected from you — not what's generically expected from everyone.

---

## Why bother contributing?

The tools you use every day — your code editor, frameworks, libraries — exist because people gave back. You don't have to be a senior engineer. You can fix a typo in documentation, report a bug clearly, or improve a confusing explanation. Those contributions are real and genuinely appreciated.

This skill helps you do that without accidentally breaking norms, ignoring requirements, or creating work for a maintainer that doesn't help them.

---

## What it does

When you point it at a GitHub repository, it:

1. Reads the project's own rules (`CONTRIBUTING.md`, `LICENSE`, `SECURITY.md`, etc.)
2. Explains what each file means in plain language
3. Tells you what this specific project requires — not just general advice
4. Flags anything missing or ambiguous
5. Gives you a concrete checklist of what to do before you open a pull request

It handles:
| Area | What gets checked |
|---|---|
| **License** | Does it exist? What type? What does it mean for your contribution? |
| **Contribution rules** | What does the project explicitly require? |
| **Security** | Is there a safe way to report vulnerabilities? |
| **Sign-off requirements** | Does this project need a CLA or DCO? (Plain-English explanation included.) |
| **Attribution** | How does this project credit contributors? |
| **PR readiness** | Are you actually ready to open a pull request? |
| **Etiquette** | First-contribution expectations, communicating with maintainers |

---

## Quick Start

### Install the skill in Cursor

```bash
mkdir -p ~/.cursor/skills/oss-contribution-guardian
cp skill/SKILL.md ~/.cursor/skills/oss-contribution-guardian/SKILL.md
```

Then in any Cursor chat:

> *"I want to contribute to https://github.com/owner/repo — what do I need to know?"*

or

> *"Review this CONTRIBUTING.md before I open a PR."* [paste the file]

or

> *"Walk me through contributing to an open-source project for the first time."*

### Use the prompt templates

`skill/prompts.md` contains ready-to-use prompts for common situations — reviewing a repo, checking a license, understanding a CLA, preparing a first contribution, and responding to maintainer feedback.

### Use the checklists

`skill/checklists.md` has step-by-step checklists for: licenses, attribution, security, PR readiness, etiquette, and employer IP. Each item includes a plain-English explanation of why it matters.

---

## Limitations

**This skill reads documentation — it does not read code.** It cannot detect secrets in your diff, find vulnerable dependencies, or check license compliance in vendored code. For that, use dedicated tools like `git-secrets`, `trivy`, or `npm audit`.

**This is not legal advice.** For questions about employer IP agreements, license compatibility in commercial contexts, or CLA obligations, consult a qualified attorney. The skill will tell you when a question is in that territory.

**It can only work with what's in the repo.** If a project has no `CONTRIBUTING.md`, the skill will tell you that — it won't guess what the maintainer probably wants.

---

## Who maintains this

This project is community-maintained and welcomes contributions. See [CONTRIBUTING.md](CONTRIBUTING.md). If you find guidance that's wrong, outdated, or unclear — especially for beginners — please open an issue.

---

## Sources

This skill is grounded in:
- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/) — GitHub's Open Source Guides
- [The Legal Side of Open Source](https://opensource.guide/legal/) — Open Source Guides
- [New to open source? Here's everything you need to get started](https://github.blog/open-source/new-to-open-source-heres-everything-you-need-to-get-started/) — GitHub Blog
- [Developer Certificate of Origin](https://developercertificate.org/)
- [Choose a License](https://choosealicense.com/) — GitHub's license picker

See [docs/sources.md](docs/sources.md) for the full annotated list.

---

## License

[MIT](LICENSE) — use it, adapt it, share it.

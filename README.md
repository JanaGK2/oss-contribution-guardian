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

### The easy way — just tell Cursor

Open a Cursor chat and paste this:

> *"Please install this skill: https://github.com/JanaGK2/oss-contribution-guardian"*

Cursor will handle it. Once installed, you can use it immediately in the same chat or any new one.

### Then try one of these prompts

> *"I want to contribute to https://github.com/owner/repo — what do I need to know?"*

> *"Walk me through contributing to an open-source project for the first time."*

> *"Review this before I open a pull request."* [paste a CONTRIBUTING.md or LICENSE file]

That's it. The skill will guide you from there.

---

### If you prefer to install manually (optional)

If you're comfortable with a terminal, you can also copy the skill file directly:

```bash
mkdir -p ~/.cursor/skills/oss-contribution-guardian
cp skill/SKILL.md ~/.cursor/skills/oss-contribution-guardian/SKILL.md
```

### Prompt templates and checklists

`skill/prompts.md` has ready-to-copy prompts for every common situation — reviewing a repo, checking a license, understanding sign-off requirements, preparing a first contribution, responding to maintainer feedback, and more. Each one explains in plain language when to use it.

`skill/checklists.md` has step-by-step checklists for licenses, attribution, security, PR readiness, etiquette, and employer IP — with a plain-English explanation of why each item matters.

---

## Limitations

**This skill reads documentation — it does not read code.** It cannot detect secrets in your diff, find vulnerable dependencies, or check license compliance in vendored code. For that, use dedicated tools like `git-secrets`, `trivy`, or `npm audit`.

**This is not legal advice.** For questions about employer IP agreements, license compatibility in commercial contexts, or CLA obligations, consult a qualified attorney. The skill will tell you when a question is in that territory.

**It can only work with what's in the repo.** If a project has no `CONTRIBUTING.md`, the skill will tell you that — it won't guess what the maintainer probably wants.

---

## Who maintains this, and how to improve it

This project is community-maintained. If the skill gave you confusing advice, missed something, or explained something badly — that's exactly the kind of feedback that makes it better.

**The easiest way to contribute is to use the skill itself.** Once you've installed it, open a Cursor chat and say:

> *"I want to contribute an improvement to https://github.com/JanaGK2/oss-contribution-guardian — walk me through it."*

The skill will guide you through the whole process: figuring out what to suggest, whether to open an issue or a pull request, what to write, and how to do it step by step. You don't need to know how GitHub contributions work in advance — that's the point of the skill.

If you'd rather start with something simpler, go to [github.com/JanaGK2/oss-contribution-guardian/issues](https://github.com/JanaGK2/oss-contribution-guardian/issues) and click **New Issue**. Describe what confused you or what was wrong. That's a valid contribution too — you don't have to fix it yourself.

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

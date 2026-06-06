# OSS Contribution Guardian

**A Cursor AI skill for people who want to start contributing to open source — whether that means giving something back to a project you use, or sharing your own work with the world.**

No prior experience required. Every term explained. Every step guided.

---

## Open source is not a niche hobby

Before anything else: if you've ever thought "open source is for developers, not for me" — that framing is wrong, and it's worth correcting before we start.

Open source software is the shared foundation of modern technology. The operating system that powers most of the world's web servers (Linux) is open source. The platform that runs most cloud infrastructure at Google, Amazon, and Microsoft (Kubernetes) is open source. The JavaScript library behind many of the websites you use every day (React, built by Meta) is open source. The programming language used across data science, AI research, and automation worldwide (Python) is open source.

These aren't hobbyist side projects. They are the infrastructure that Fortune 500 companies depend on, that hospitals and governments run on, that banks and universities build with. Companies like Google, Microsoft, Red Hat, and IBM don't just *use* open source — they employ thousands of engineers whose primary job is contributing to it. It is, genuinely, how a large portion of the world's software gets built.

Open source works because people give back. When someone fixes a bug, improves documentation, or shares a tool they built — everyone benefits. That pool of shared knowledge grows. The [Open Source Initiative](https://opensource.org/about), which maintains the [Open Source Definition](https://opensource.org/osd), puts it directly: open source is about the freedom to use, study, modify, and distribute software for any purpose.

You can be part of that. Even as a beginner. Even if you've never written a line of code in public. Even if your first contribution is fixing a typo.

---

## What this skill does

This skill helps you take two kinds of steps into open source:

**1. Contributing to someone else's project**
You found a bug, spotted a documentation mistake, have an idea for an improvement, or just want to give back to a tool you use. This skill walks you through what you need to know before you propose your change: what the project allows, what it expects, what could go wrong if you skip a step, and how to communicate with the maintainers.

**2. Publishing your own project**
You built something — a script, a tool, a template, a skill file. You want to know if it's worth sharing, how to prepare it safely, and how to get it into a state where someone else could actually use it. This skill guides you through that whole process, including what happens after you publish.

In both cases: the skill explains every term it uses. It does not assume you already know what a pull request, a license, a fork, or a commit is.

---

## What it covers

### When contributing to someone else's project

| What gets checked | Why it matters |
|---|---|
| **Does the project have a license?** | Without one, the legal status of your contribution is genuinely unclear. The skill explains what to do if there isn't one. |
| **What does the license allow?** | Different licenses have different rules. Some require that your contribution stays open source. The skill explains this in plain language. |
| **What does this project specifically require?** | Many projects have a `CONTRIBUTING.md` file with their own rules. The skill reads it and tells you what it says. |
| **Does the project need a sign-off?** | Some projects require a CLA (Contributor License Agreement) or DCO (Developer Certificate of Origin). The skill explains what these are and how to handle them. |
| **How do you report a security issue safely?** | Posting a vulnerability as a public issue can cause harm. The skill tells you the right way. |
| **Are you ready to open a pull request?** | A checklist based on what *this specific project* requires, not generic advice. |
| **How do you talk to the maintainer?** | Tone, expectations, and what to do if you don't hear back. |

### When publishing your own project

| What the skill does | Why it matters |
|---|---|
| **Helps you decide if it's worth sharing** | Asks the right questions so you can articulate the value before you do any setup work. |
| **Identifies your intended user** | Helps you write documentation for the person who will actually use it, not a generic reader. |
| **Scans for things that shouldn't go public** | Credentials, internal company references, hardcoded paths, sensitive comments. Once something is on GitHub, it's very hard to fully remove. |
| **Generates the standard files** | README, LICENSE, .gitignore, CONTRIBUTING.md, SECURITY.md — drafted for you. |
| **Walks you through pushing to GitHub** | What `git add`, `git commit`, and `git push` mean, in plain English. |
| **Suggests where to share after publishing** | Matches your project to the platforms where your intended users actually spend time. |
| **Explains what being a maintainer means** | Stars, issues, pull requests, forks — what each one is and what (if anything) you need to do. |

---

## Quick Start

### The easy way — just tell Cursor

Open a Cursor chat and paste this:

> *"Please install this skill: https://github.com/JanaGK2/oss-contribution-guardian"*

Cursor will handle it. Once installed, you can use it immediately in the same chat or any new one.

### Then describe your situation

You don't need to memorize commands or learn a workflow first. Just say what you're trying to do:

> *"I want to contribute to https://github.com/owner/repo — what do I need to know?"*

> *"Walk me through contributing to an open-source project for the first time."*

> *"I built something and I'm wondering whether to publish it — help me think it through."*

> *"Scan my project for anything that shouldn't go in a public repository."*

> *"Someone opened an issue on my project. Help me understand it and draft a response."*

The skill will ask you questions, check the relevant files, and guide you step by step. You don't need to know the terminology in advance — it will explain everything as you go.

### Not sure what to try first? Start here.

If you're new to open source and want somewhere low-stakes to practice, this project itself is a good first contribution.

Why low-stakes? Because:
- The maintainer (the author) is also learning. There's no senior gatekeeper waiting to judge your contribution.
- The project is documentation — there's no risk of breaking production software.
- Every improvement that makes the skill clearer for beginners directly serves the project's purpose.
- Mistakes are easy to fix. GitHub keeps the full history — nothing is permanent or catastrophic.

**Things you could contribute right now:**
- Something that confused you — if a term wasn't explained or an explanation wasn't clear, that's a real gap
- A topic that's missing — a situation you ran into that the skill didn't cover
- A typo or unclear sentence — fix it and open a pull request; a one-line fix is a valid first PR
- A new usage example — a conversation with the skill that went well (or didn't)
- A platform missing from the sharing guide — a community where this content belongs

You don't need to know how any of this works first. Once the skill is installed, say:

> *"I want to make my first open-source contribution to https://github.com/JanaGK2/oss-contribution-guardian — walk me through it from the beginning."*

Or go straight to [github.com/JanaGK2/oss-contribution-guardian/issues](https://github.com/JanaGK2/oss-contribution-guardian/issues) and click **New Issue**. Describe what you ran into. That's a contribution.

### If you prefer to install manually (optional)

If you're comfortable with a terminal, you can copy the skill file directly:

```bash
mkdir -p ~/.cursor/skills/oss-contribution-guardian
cp skill/SKILL.md ~/.cursor/skills/oss-contribution-guardian/SKILL.md
```

---

## Who this is for

**Primarily: people who are new to open source.**

This skill was built by someone who is new to this space herself. Not a senior engineer with years of GitHub history. Someone who found the existing documentation confusing, jargon-heavy, and written for people who already knew what they were doing. Every explanation in this skill was written with that experience in mind.

If you're in that position — you use open-source tools, you've built things you want to share, but the standard GitHub documentation makes you feel like you're missing something obvious — this was built for you.

**Also: experienced open-source contributors who want to improve it.**

This skill is itself an open-source project, and it needs people who know this space well to make it better. If you've been contributing to open source for years and you see something that's wrong, incomplete, or could be explained more clearly — please improve it. The guidance on how to do that is directly below.

The author being new to this space is not a limitation — it's the point. The perspective of someone learning the process from scratch is exactly what was needed to write documentation that doesn't assume prior knowledge.

---

## Is it safe to install?

Short answer: yes — and here is exactly why, so you can judge for yourself.

**A skill is a plain text file.** Installing this skill copies one file — `SKILL.md` — to a folder on your computer (`~/.cursor/skills/oss-contribution-guardian/`). That file contains instructions written in plain English (specifically Markdown, a simple text format). You can read it before installing it: [skill/SKILL.md](skill/SKILL.md).

**It has no executable code.** Unlike installing software (`npm install`, `pip install`, downloading an app), a skill file runs nothing. There are no scripts, no dependencies, no network calls, nothing that executes on your machine. It is a text document that Cursor's AI reads to understand how to behave when you ask it questions.

**It cannot access your files or system on its own.** The skill influences how the AI responds in chat — that's all. It cannot open files, make network requests, or do anything to your computer without you explicitly asking Cursor to do something and approving it.

**What you should always do with any skill from anyone:**
- Read the `SKILL.md` file before installing — it is short and written in plain English
- Check that the instructions look reasonable and match what the skill claims to do
- If anything looks suspicious (instructions to ignore your safety settings, instructions to run commands without telling you), don't install it

This applies to this skill and any other skill you find online.

---

## Limitations

**This skill reads documentation — it does not read code.** It cannot detect secrets in your files, find vulnerable dependencies, or check license compliance in vendored code. For automated secret scanning, use dedicated tools like `git-secrets` or `trufflehog`. For dependency vulnerabilities, use `trivy` or `npm audit`.

**This is not legal advice.** For questions about employer IP agreements, license compatibility in commercial contexts, or CLA obligations, consult a qualified attorney. The skill will tell you when a question is in that territory.

**It can only work with what's in the repo.** If a project has no `CONTRIBUTING.md`, the skill will tell you that — it won't invent what the maintainer probably wants.

---

## How to improve this skill

If you've used the skill and have more substantive feedback — something that was wrong, a whole area that's missing, a checklist that needs rewriting — the same process applies.

**The easiest path:** Open a Cursor chat and say:

> *"I want to contribute an improvement to https://github.com/JanaGK2/oss-contribution-guardian — walk me through it."*

The skill will guide you: what to suggest, whether to open an issue or a pull request, what to write, and each step of the process. You don't need to know how GitHub contributions work first.

---

## Sources and further reading

This skill is grounded in:
- [Open Source Definition](https://opensource.org/osd) — Open Source Initiative
- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/) — GitHub's Open Source Guides
- [The Legal Side of Open Source](https://opensource.guide/legal/) — Open Source Guides
- [New to open source? Here's everything you need to get started](https://github.blog/open-source/new-to-open-source-heres-everything-you-need-to-get-started/) — GitHub Blog
- [Developer Certificate of Origin](https://developercertificate.org/)
- [Choose a License](https://choosealicense.com/) — GitHub's license picker

See [docs/sources.md](docs/sources.md) for the full annotated list.

---

## License

[MIT](LICENSE) — use it, adapt it, share it.

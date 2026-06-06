# Publishing Your Own Work

## The situation this covers

You built something — a script, a tool, a collection of templates, a skill file, a configuration. You use it yourself. You're wondering: is this worth sharing publicly? Could it help other people?

This guide walks you through that decision and everything that needs to happen before you publish.

---

## Phase 1: Is it worth sharing?

Most people skip this step and go straight to "how do I put it on GitHub." That's backwards. Publishing something nobody can find a reason to use creates maintenance work for you (people will file confusing issues) and noise for everyone else.

**Ask yourself:**

**What problem does this solve?**
If you struggle to answer this in one sentence, the project may not be ready to share — not because it's bad, but because you haven't articulated what it's for yet. A project without a clear "why" is hard for anyone else to understand.

**What would you have to do without it?**
This is often the clearest way to describe value. "Without this, I had to manually export the CSV, convert it in a spreadsheet, and upload the result. Now it's one command." That's a README.

**Who else encounters this same problem?**
You don't need to know thousands of people would use it. You need a reasonable answer to "would someone else in my situation find this useful?" If yes, it's worth sharing.

**Is there already something that does this?**
Search GitHub. Ask Cursor: *"Is there already an open-source tool that does [describe what yours does]?"* If something similar exists, that's not a reason not to publish — it's a reason to understand what makes yours different and say so clearly.

**In Cursor, say:**
> *"Help me figure out if my project is worth publishing. Here's what it does: [describe it]. Ask me questions and help me work out whether it would be useful to others and how to describe it."*

---

## Phase 2: Is it safe to share?

This is the most important phase and the one most people skip. Before a single file goes public, you need to check for things that must not be in a public repository.

**In Cursor, say:**
> *"Before I publish this project publicly, please scan it for anything that shouldn't be in a public repository — credentials, internal company references, hardcoded paths, or internal context in comments. Here's the project: [paste files or point to folder]"*

Cursor will actively look for:

**Credentials and secrets**
API keys, passwords, tokens, private keys. Common patterns: `sk-`, `AIza`, `Bearer `, `password =`, `api_key =`, long random strings assigned to variables. Fix: move to environment variables.

What is an environment variable? It's a value stored on your computer (or server) that your code reads at runtime, so the secret never lives in your files. Ask Cursor: *"How do I replace this hardcoded API key with an environment variable?"*

**Internal company references**
Internal domain names (anything like `*.internal.company.com`), internal tool names (Jira project codes, internal wiki URLs), VPN addresses, internal hostnames. Fix: remove or replace with generic placeholders.

**Hardcoded personal paths**
Things like `/Users/yourname/projects/company-stuff/` or `C:\Users\Jana\Documents\work\`. These paths only exist on your machine — they'll break for anyone else. Fix: make paths relative or configurable.

**TODO/FIXME comments with internal context**
Comments like `# TODO: ask Maria about the Salesforce rate limit` or `# FIXME: workaround for our broken internal proxy`. These reveal internal context and people. Fix: either remove the comment, or rewrite it as a generic technical note.

**Company-specific logic**
Business rules, customer names, internal product codes that have no meaning outside your organization. Fix: generalize or remove.

**After Cursor's scan:** fix everything it flags before creating the repository. Once something is published to GitHub, it's very hard to truly remove it from the internet — even if you delete the file, it may already be cached or forked.

---

## Phase 3: Does it have the right structure?

A project that is hard to understand from the outside will not get used, even if it's genuinely useful.

**In Cursor, say:**
> *"Help me create the standard documentation files for my open-source project. Here's what it does: [describe it]. Generate a draft README, and tell me what license to use."*

### The files you need

**README.md** (required)
The first thing anyone reads. It should explain:
- What the project does (one clear sentence)
- Why it exists (the problem it solves)
- How to install and use it
- A simple example showing what output looks like

Cursor can draft this from your description. The opener is the hardest part — see Phase 4.

**LICENSE** (required)
Without a license, your project is technically "all rights reserved" even if it's public. Nobody can legally use it.

For most tools and skills: **MIT License** — simplest, most permissive, lets anyone use it for anything.
If you want any modified version to stay open source: **GPL v3**.

Ask Cursor: *"What license should I use for my project and why?"*

**.gitignore** (required)
A list of files that git should never commit. Prevents you from accidentally publishing credentials, local config, or system files.

Ask Cursor: *"Generate a .gitignore for a [Python/JavaScript/general] project."*

**CONTRIBUTING.md** (recommended, can be short)
Two to three sentences is enough: what contributions are welcome, and how to propose them. Sets expectations for anyone who wants to help.

**SECURITY.md** (recommended, can be very short)
One paragraph: how to report a security issue privately. Most projects just say: "Please don't post security issues as public GitHub issues. Contact [method] instead."

**CODE_OF_CONDUCT.md** (recommended)
One line referencing the Contributor Covenant is fine: *"This project follows the Contributor Covenant v2.1."*

---

## Phase 4: Can you explain the why?

The README opening is the hardest writing you'll do. Most people write: *"This is a tool that does X."* That tells someone what it does but not why they should care.

**In Cursor, say:**
> *"Help me write the opening paragraph for my README. Ask me questions about why I built this and what problem it solves, then draft an opener from my answers."*

A good opener answers: "Why does this exist? What was painful enough that you built something?"

It sounds like:
> *"Every time I needed to [do the thing], I had to [describe the painful manual process]. This tool does it in [describe the simpler way]."*

or:

> *"I couldn't find a straightforward way to [do the thing], so I built one."*

Once you have that sentence, the rest of the README is just the details.

---

## When you're ready to publish

Once Phases 1–4 are done:

1. Create a new repository on GitHub (green button on github.com, or ask Cursor to do it)
2. Make sure it's set to **Public**
3. Add the license GitHub recommends (or let Cursor set it up for you)
4. Add GitHub topic tags so people can find it — things like the language, the problem domain, the tools it works with
5. Consider posting about it where your target audience is — a relevant subreddit, a Discord, a Slack group, a blog post

You don't need many users for a project to be worth publishing. One person finding it useful and not having to build it themselves is a success.

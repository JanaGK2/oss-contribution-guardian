---
name: oss-contribution-guardian
description: >-
  Helps you contribute to open-source projects responsibly. Reviews the target
  repository's own documentation and guides you step by step — from understanding
  why you're contributing to knowing exactly what the project expects from you.
  Explains every term. No prior GitHub experience assumed.
---

# OSS Contribution Guardian

## Why This Exists

Every tool you use daily — your browser, your code editor, the frameworks behind the websites you visit — was almost certainly built with open-source software. Open source works because people give back: they fix a bug they found, improve a confusing explanation, add a missing example. You don't have to be an expert. You just have to do it carefully and respectfully.

This skill helps you do that. It walks you through what to check before you contribute, explains what you're looking at, and tells you what the project itself expects from you — without making you feel like you need a law degree or 10 years of GitHub experience.

---

## When to Invoke This Skill

Use this skill when the user:
- Is preparing to contribute to an open-source project for the first time (or the first time to *this* project)
- Asks "what should I check before I contribute to X?"
- Wants to understand a project's license, rules, or requirements
- Wants help reviewing a specific file like `CONTRIBUTING.md` or `LICENSE`
- Found a bug they want to report or fix
- Is wondering if their change is appropriate to propose

---

## Start Here: What Is a Contribution?

Before checking anything, help the user understand that a contribution is not just code. Many valuable contributions have nothing to do with writing software:

- Fixing a typo in documentation
- Reporting a bug clearly and in detail
- Improving a confusing explanation in the README
- Translating documentation to another language
- Answering a question another user had

This matters because beginners often assume they need to write complex code to contribute. They don't. A clear, well-documented bug report is genuinely valuable. Start by asking what kind of contribution they're planning — then tailor the guidance.

---

## The Files You'll Look At (and What They Are)

When you review a repository for the user, look for these files and explain what each one means if the user hasn't encountered them before:

### `LICENSE`
**What it is:** A text file that specifies the legal terms under which the project's code can be used, modified, and shared.

**Why it matters:** Without a license, the code is legally "all rights reserved" — even if it's publicly visible on GitHub, you don't automatically have the right to use or modify it. A license is what makes software genuinely open source.

**Common types:**
- **MIT, Apache 2.0, BSD**: Permissive — you can use the code for almost anything, including commercial projects. Your contribution will be under the same terms.
- **GPL (General Public License), AGPL**: Copyleft — these licenses say "you can use this freely, but if you distribute your version, it must use the same license." This can have implications if you're contributing code you wrote at work.
- **No license**: This is a red flag. See the decision tree.

### `CONTRIBUTING.md`
**What it is:** The project's instruction manual for contributors. It explains the steps the maintainer wants you to follow before opening a pull request (PR).

**Why it matters:** Ignoring it is the single most common reason contributions get rejected. It might specify: which branch to target, how to format your commits, whether you need to write tests, and whether to open an issue first.

**A pull request (PR)** is how you propose changes on GitHub. You make a copy of the project (called a "fork"), make your changes in your copy, then open a pull request asking the maintainer to bring your changes into the main project.

### `CODE_OF_CONDUCT.md`
**What it is:** A document that describes how people in this community are expected to treat each other.

**Why it matters:** Most projects adopt the Contributor Covenant — a standard that says, roughly: be respectful, no harassment, focus on the work. If you encounter a problem with another contributor or maintainer, the Code of Conduct tells you who to contact and how.

### `SECURITY.md`
**What it is:** Instructions for what to do if you discover a security vulnerability in the project.

**Why it matters:** Security issues should *never* be reported as public GitHub issues. A public report tells attackers about the vulnerability before the maintainer can fix it. `SECURITY.md` tells you the safe way to report it — usually a private email or GitHub's private reporting feature.

### `CLA` and `DCO` (often referenced in `CONTRIBUTING.md`)
**What a CLA is:** A Contributor License Agreement — a document some projects require you to sign before they'll accept your changes. It confirms you have the right to contribute the code and you're okay with the project using it. Big foundation-backed projects (like Kubernetes or Apache projects) often require this. Most small projects don't.

**What a DCO is:** Developer Certificate of Origin — a simpler alternative. You add one line to your git commit message: `Signed-off-by: Your Name <you@example.com>`. You do this by running `git commit -s` instead of `git commit`. It's just a statement that you wrote the code and have the right to contribute it.

**If neither is mentioned:** The project probably just relies on the license itself, which is the norm for most open-source projects.

### PR template (`.github/PULL_REQUEST_TEMPLATE.md`)
**What it is:** A pre-filled form that appears when you open a pull request. It usually asks you to describe your change, how you tested it, and which issue it addresses.

**Why it matters:** Filling it out completely signals to the maintainer that you've done the work carefully.

---

## What to Do When Given a Repository

### Step 1: Ask what kind of contribution the user is planning
Understanding this shapes everything else. A bug report has different requirements than a code change.

### Step 2: Find and read these files in order
```
LICENSE
CONTRIBUTING.md
SECURITY.md
CODE_OF_CONDUCT.md
README.md (for anything CONTRIBUTING.md doesn't cover)
.github/PULL_REQUEST_TEMPLATE.md
.github/ISSUE_TEMPLATE/
Any mention of CLA, DCO, or sign-off
```

For each file found: note what it explicitly requires.
For each file missing: say it is missing. Do not invent rules.

### Step 3: Produce a structured report in four sections

**1. What this repository explicitly requires**
Quote or paraphrase the repo's own docs. Only state things you can point to.

**2. General best practice** (where the repo is silent)
Label these clearly as recommendations, not requirements.

**3. Open questions / things to ask the maintainer**
Anything ambiguous, missing, or where you couldn't find an answer.

**4. Action checklist**
A short, concrete list of what the user needs to do before contributing.

---

## The Giving-Back Mindset

When the user seems nervous or uncertain, remind them: maintainers were once exactly where they are. The best contributions come from users who genuinely use the software and notice something that could be better. You don't need to be impressive — you need to be clear, careful, and respectful.

If your first PR doesn't get merged, that's not failure. It's how you learn the project's specific expectations. Most maintainers appreciate the effort even when they can't accept the change.

---

## Always End With a Next Step

After delivering a repo review or checklist, never stop there. Always close with something like:

> "That's what the project expects. What would you like to do next? I can help you:
> - **Define your contribution** — figure out exactly what you want to add or change
> - **Walk through the steps** — forking, editing, committing, and opening a pull request, one step at a time
> - **Answer questions first** — like whether you need a GitHub account, whether this is reversible, or what 'commit' and 'push' actually mean"

Match the offer to what the user seems ready for. A nervous first-timer needs option 3 first. Someone who says "I already have a fork" needs option 2.

## The Guided Journey (be ready to walk through all of this)

When a user wants to be walked through the process, cover these steps in order. Explain each one before asking them to do it. Answer the safety questions proactively — most beginners are wondering "will I break something?" and won't ask directly.

### Step 1: Do you need a GitHub account?

Yes. You need a free account at github.com. If the user doesn't have one, that's the first step. Sign up, verify your email, done.

### Step 2: What exactly do you want to contribute?

Help the user get specific before they touch anything. "I want to improve it" is not enough. Ask:
- Is it a bug fix? A documentation improvement? A new feature? A typo?
- Do you know which file needs changing?
- Has anyone else reported this? (Check the project's Issues tab)

A clear, specific contribution is much more likely to be accepted than a vague one.

### Step 3: The two ways to contribute — browser vs. local

Explain both options and recommend the right one:

**Browser method (easiest for beginners, works for documentation and small changes):**
No software to install. Everything happens on GitHub.com in your browser.
1. Go to the repository on GitHub
2. Click the **Fork** button (top right) — this makes your own personal copy of the project
3. In your fork, navigate to the file you want to change
4. Click the pencil icon ✏️ to edit it
5. Make your change
6. Click "Commit changes" — give it a short description of what you changed
7. GitHub will offer to open a pull request — accept it and fill in the description

**Local method (needed for code changes, adding new files, or anything complex):**
Requires git installed on your computer and GitHub authentication set up.
Walk through this only when the browser method isn't sufficient.

### Step 4: What is a commit? What is pushing?

**Commit:** Saving a version of your change with a label. Like "Save As" but with a message attached: "Fixed typo in README." It's a checkpoint. You can always go back to any previous commit.

**Push:** Sending your local commits up to GitHub so they're visible online. Your changes live on your computer until you push — after that they're on GitHub in your fork.

**Is this reversible?** Yes. At every stage:
- You can close your own pull request at any time — it just disappears
- The maintainer can decline your pull request — nothing changes in the main project
- A fork is your copy — you can delete it with no effect on the original
- A commit can be undone
- The maintainer's project is completely unaffected until they explicitly choose to accept your pull request

**Is it safe?** Yes. A pull request is a *proposal*. Nothing happens to the original project until the maintainer accepts it. You cannot accidentally break someone else's project by opening a pull request.

### Step 5: What to write in the pull request

The pull request description is your cover letter. Help the user write it. It should include:
- **What changed:** One or two sentences describing what you did
- **Why:** Why is this an improvement?
- **How you tested it:** Did you check that it works? How?
- **Related issue:** If there's an issue number, write "Fixes #42" or "Related to #42"

Keep it short. Maintainers are busy. One paragraph is usually enough.

### Step 6: What happens after you open it?

Set expectations:
- The maintainer will see it (usually via email notification)
- They may respond quickly or it may take days or weeks — this is normal
- They may ask for changes — this is also normal and not a rejection
- They may close it without merging — this happens, especially for changes that don't fit the project direction
- They may merge it — your contribution becomes part of the project

Do not send follow-up messages asking for a faster review within the first two weeks.

---

## Firm Boundaries

- **Do not provide legal advice.** When questions about license compatibility or employer IP arise, give the factual context and recommend they consult a lawyer or their company's legal team. Say explicitly: "This is not legal advice."
- **Do not invent maintainer intent.** If the docs don't say it, say "not stated in the repo documentation."
- **Do not claim to detect secrets or bugs in code.** This skill reads documentation. Recommend dedicated tools (`git-secrets`, `trufflehog`, `npm audit`) for that work.
- **Do not assume all repos are mature.** Many repos have no `CONTRIBUTING.md` — that's information, not a failure.

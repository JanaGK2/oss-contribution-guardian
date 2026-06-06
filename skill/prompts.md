# Prompt Templates

These are ready-to-use prompts. Copy one, fill in the blanks, and paste it into Cursor with the OSS Contribution Guardian skill active.

Each prompt includes a plain-English description of when to use it and what you'll get back.

---

## "I'm new to this — just walk me through it"

**When to use:** You've never contributed to open source before, or you're contributing to this particular project for the first time and want to understand what you're walking into before doing anything.

```
I want to contribute to this open-source project for the first time: [paste the URL]

I don't have much experience with open-source contributions. Please:
1. Tell me what this project expects from contributors, based on its own documentation
2. Explain any terms or requirements I might not be familiar with
3. Tell me if there's anything that would block my contribution before I even start
4. Give me a simple checklist of what to do before I open my first pull request

Please explain things in plain language — I may not know what a CLA, DCO, or copyleft license is.
```

---

## "Check this repo before I contribute"

**When to use:** You've found something you want to fix or improve and want a quick safety check — does the project have any requirements you need to know about first?

```
Please review this repository before I contribute to it: [paste the URL]

I want to know:
1. Does this project have a license? What does it mean for contributions?
2. Are there rules I need to follow (in CONTRIBUTING.md or similar)?
3. Do I need to sign anything or add special text to my commits before my changes can be accepted?
4. Is there anything missing or worrying that I should sort out before I start?

Please tell me what the project's own documentation says, not just general advice.
If any term needs explaining, please explain it.
```

---

## "Am I ready to open a pull request?"

**When to use:** You've already made your change and you're about to propose it to the project. A "pull request" is how you do that on GitHub — you're asking the project maintainer to "pull in" your changes.

```
I'm about to propose my change to this project: [paste the URL or project name]

Here's what my change does: [describe it in 1-2 sentences]

Please:
1. Read the project's CONTRIBUTING.md (if it exists) and tell me what it requires before I open a pull request
2. Tell me if there's a form or template I need to fill out when I open my pull request
3. Help me write my pull request description
4. Tell me if I'm missing anything obvious

Walk me through it — don't just give me a checklist to do alone.
```

---

## "What does this license mean for me?"

**When to use:** You want to understand the project's license before contributing — especially if you wrote the code at work, or you're not sure what the license type means in practice.

A "license" is the legal document that says who can use the code and how. It also determines what happens to the code you contribute.

```
Please explain the license for this project: [paste the URL, or paste the contents of the LICENSE file]

I want to understand:
1. What type of license is this, in plain terms?
2. What does it mean for the code I contribute?
3. Is there anything I should check with my employer before contributing?

Note: I'm not looking for legal advice — I just want to understand what the license actually says.
```

---

## "What are the rules here?"

**When to use:** You want a plain-English summary of what this project's maintainer expects from contributors — things like how to write your commit messages, whether to open an issue first, and what format the pull request should be in.

A "maintainer" is the person (or team) who owns and manages the project. They set the rules in a file called `CONTRIBUTING.md`.

```
Please summarize what the maintainer of this project expects from contributors: [paste the URL, or paste the contents of CONTRIBUTING.md and/or README.md]

I want to know:
- What steps do I need to follow before opening a pull request?
- Are there formatting rules for commits or pull request descriptions?
- Do I need to write tests?
- Is there anything the maintainer has said they don't want?

Please explain any technical terms I might not know.
```

---

## "Help me make my first contribution"

**When to use:** You've found a project you want to contribute to and you want a guided walkthrough — finding where to start, understanding the culture, and making sure your first attempt is likely to go well.

```
I want to make my first open-source contribution to this project: [paste the URL]

I'm new to contributing to open source. Please help me:
1. Understand what kind of contributions this project is looking for
2. Find a good starting point (is there a "good first issue" label, or a list of beginner-friendly tasks?)
3. Know what the maintainer expects from new contributors
4. Avoid common mistakes that first-timers make with this kind of project

Please keep explanations simple — I may not be familiar with standard open-source practices yet.
```

---

## "Do I need to sign anything?"

**When to use:** You've heard that some projects require you to sign a legal document (called a CLA) or add a special line to your commits (called DCO sign-off) before they'll accept your contribution. You want to know if this project requires either one.

```
Does this project require me to sign anything or add special text to my commits before my contribution can be accepted?
Project: [paste the URL]

Specifically, I want to know:
- Is there a CLA (Contributor License Agreement) — a document I need to sign?
  Please explain what that is if yes.
- Is there a DCO sign-off — a line I need to add to my commits?
  Please explain how to do it if yes.
- If my code was written for my employer, does my employer need to sign anything?

Please explain any terms I might not know.
```

---

## "I wrote this at work — is it okay to contribute?"

**When to use:** The code or content you want to contribute was written during work hours or using work tools. You want to understand whether that creates any issues.

```
I want to contribute to [project URL], but the code I want to contribute was written [at work / during work hours / using a work computer — describe your situation].

Help me think through:
- What questions should I ask my employer before contributing?
- Does this project's license or contribution agreement say anything about employer-owned contributions?
- What is the general guidance for this situation?

I understand you can't give legal advice — I just want to know what questions to ask.
```

---

## "The maintainer gave me feedback — help me respond"

**When to use:** You opened a pull request and the maintainer left comments. You want help understanding what they're asking for and how to respond professionally.

A pull request review is normal — most contributions go through at least one round of feedback before being accepted. This is not rejection. It's the process.

```
I opened a pull request to [project name] and the maintainer left this feedback:

[paste the feedback here]

Please help me:
1. Understand what the maintainer is asking for, in plain terms
2. Tell me which comments I need to address versus which are just suggestions
3. Help me draft a polite response to any feedback I think might be a misunderstanding
4. Tell me what to address first if there are multiple comments
```

---

## "Walk me through it step by step"

**When to use:** You've done the repo review and you're ready to actually do the contribution — but you want someone to guide you through each step without assuming you know what "fork", "commit", or "push" means.

```
I've reviewed what this project expects and I'm ready to contribute.
Please walk me through the process step by step.

Here's where I am: [describe your situation, e.g. "I have a GitHub account but I've never made a pull request before" or "I just want to fix a typo in the README"]

Please:
1. Tell me the simplest way to make this contribution (browser vs. working locally on my computer)
2. Walk me through each step one at a time, waiting for me to confirm I've done it before moving to the next
3. Explain what "commit" and "push" mean when we get there
4. Tell me: is this reversible? Will I break anything?
```

---

## "I think I found a security issue"

---

## "Should I publish my own project?"

**When to use:** You've built something and you're wondering whether it's worth sharing publicly. Use this before you do any setup work — it helps you figure out if the project is ready, who it's for, and whether you can explain why it exists.

```
I built something and I'm wondering whether to publish it publicly.

Here's what it does: [describe it in a few sentences]

Please:
1. Ask me questions to help figure out if this is worth sharing — who it's for, what problem it solves, whether something like it already exists
2. Based on my answers, give me an honest assessment: is this ready to share, does it need more work, or is the value unclear?
3. If it looks worth sharing, help me write a one-sentence description that explains it to someone who's never heard of it before

Don't just tell me yes or no — help me think it through.
```

---

## "Scan my project before I publish it"

**When to use:** You've decided to publish a project and want to make sure nothing sensitive or private goes out. This is the most important check before you make anything public.

**What "sensitive" means:** credentials (passwords, API keys), internal company references, hardcoded paths that only work on your machine, or comments that reveal internal context.

```
I'm about to publish this project publicly and I need you to scan it for anything that shouldn't be in a public repository.

[Paste your files, or describe the folder path]

Please look for:
1. Credentials or secrets — API keys, passwords, tokens, anything that looks like a long random string assigned to a variable
2. Internal company references — internal URLs, domain names, tool names, project codes that only make sense inside an organization
3. Hardcoded personal or machine-specific paths
4. TODO or FIXME comments that mention internal context, people's names, or company-specific systems
5. Anything else that looks like it should stay private

For each thing you find: tell me exactly where it is, why it's a problem, and what to do about it.
```

---

## "Help me create the standard files for my open-source project"

**When to use:** You've confirmed the project is worth sharing and you've cleaned it up. Now you need the standard files that every public project should have.

```
I'm publishing my project publicly. It's called [name] and it does [describe it].

Please help me create the following files. Draft each one from scratch — don't just describe what it should contain, write it:

1. README.md — what it does, why it exists, how to install and use it, a simple example
2. LICENSE — suggest which license makes sense for this project and why, then draft it
3. .gitignore — appropriate for [the type of project / language]
4. CONTRIBUTING.md — even a short one is fine
5. SECURITY.md — one paragraph on how to report security issues

For the README opener specifically: ask me questions about why I built this and what problem it solves before you write it, so it reflects what's actually true.
```

---

## "Help me write the README opening"

**When to use:** You have most of the README written but you're stuck on the first paragraph — the part that explains why the project exists and who should care.

```
I need help writing the opening paragraph for my README for a project called [name].

Please ask me:
1. What problem was I trying to solve when I built this?
2. What did I have to do before I had this tool?
3. Who else is likely to encounter this same problem?

Then draft an opening paragraph from my answers. It should explain why this project exists, not just what it does. Keep it short — two to four sentences.
```

---

## "I found a security vulnerability" A security vulnerability is a bug that could let someone do something harmful — access data they shouldn't, crash a service, etc.

**Important:** Do not post security issues as public GitHub issues. This prompt helps you figure out what to do instead.

```
While preparing my contribution to [project URL], I found what I think might be a security vulnerability.

Please tell me:
1. Does this project have a documented process for reporting security issues? (Check for SECURITY.md)
2. If yes, what is the process?
3. If no, what is the safest way to contact the maintainer about this privately?

I understand I should not post this as a public GitHub issue.
```

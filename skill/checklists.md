# Contribution Checklists

This file covers two situations:

1. **Publishing your own project** — checklists to work through before making something public for the first time
2. **Contributing to someone else's project** — license, attribution, security, PR readiness, etiquette, CLA/DCO, and employer IP

Each item includes a plain-English explanation of why it matters.

**Tip:** You don't have to work through these manually. In Cursor, you can say: *"Walk me through the contribution checklist for [this project / my own project]"* and it will guide you through each item step by step.

---

## Before You Publish Your Own Project

Use this checklist when you're making something you built public for the first time. Work through it in order — each phase depends on the previous one being done.

**In Cursor, say:** *"Help me work through the 'before you publish' checklist for my project."*

### Phase 1: Value — is it worth sharing?

- [ ] **I can describe what the project does in one sentence.**
  *If you can't, the project may not be ready to share yet — not because it's bad, but because the purpose isn't clear enough for someone else to understand.*

- [ ] **I can describe what problem it solves.**
  *"Without this, I had to [manual painful process]" is a complete answer. If you can say this, you have a README opener.*

- [ ] **I've checked whether something similar already exists.**
  *Ask Cursor: "Is there already an open-source tool that does [describe it]?" If yes, understand what makes yours different before you publish.*

### Phase 2: Who is your intended user?

- [ ] **I can name a specific type of person this is for — not just "developers."**
  *Example: "People who use Cursor and work with Google Sheets for reporting." The more specific you are, the clearer your README will be.*

- [ ] **I've thought about what they already know and what they'd need explained.**
  *Are they comfortable with the command line? Do they know what a CSV is? What about git? Write your README for what they know, not what you know.*

- [ ] **I've asked Cursor to check my README from their point of view.**
  *"My intended user is [describe them]. Read my README and tell me: would this person know how to get started? Is anything unclear or missing?"*

### Phase 3: Safety — is it safe to share?

This is the most important phase. Once something is public on GitHub, it is very difficult to truly remove it from the internet.

- [ ] **Cursor has scanned the project for credentials and secrets.**
  *API keys, passwords, tokens, private keys. Ask Cursor to scan before you create the repository.*

- [ ] **There are no internal company references.**
  *Internal domain names, internal URLs, Jira project codes, company-specific tool names. Replace with generic placeholders or remove entirely.*

- [ ] **There are no hardcoded personal or machine-specific paths.**
  *Paths like `/Users/yourname/` or `C:\Users\yourname\` only work on your machine. Make paths relative or configurable.*

- [ ] **TODO/FIXME comments contain no internal context.**
  *Remove or rewrite any comment that mentions a person's name, internal system, or company-specific workaround.*

- [ ] **A `.gitignore` file exists and covers sensitive files.**
  *`.gitignore` tells git which files to never commit — things like `.env` (where secrets live), local config files, and system files. Ask Cursor to generate one if it doesn't exist.*

### Phase 4: Structure — does it have the right files?

- [ ] **`README.md` exists and has a clear opener, installation instructions, and a usage example written for my intended user.**

- [ ] **A `LICENSE` file exists.**
  *Without a license, the project is technically "all rights reserved" even if it's public. For most tools: MIT. Ask Cursor: "What license should I use and why?"*

- [ ] **`CONTRIBUTING.md` exists (even if short).**
  *Even two sentences saying what contributions are welcome sets useful expectations.*

- [ ] **`SECURITY.md` exists.**
  *One paragraph saying how to report security issues privately. Prevents people from posting vulnerabilities as public issues.*

### Phase 5: The "why" — can you explain it?

- [ ] **The README opening answers "why does this exist?" not just "what does it do?"**
  *"This is a tool that does X" tells someone what it does. "Every time I needed to X, I had to [painful process]" tells someone why they should care.*

- [ ] **The README is written for my specific intended user, not for a generic reader.**
  *The tone, vocabulary, and level of explanation should match the person from Phase 2.*

### Phase 6: After publishing — did I tell people about it?

- [ ] **I've identified where my intended users spend time online.**
  *A subreddit, a Discord, LinkedIn, dev.to — somewhere the right people will actually see it.*

- [ ] **I've shared the project with a short post explaining why it exists, not just a link.**
  *Ask Cursor: "Help me draft a post for [platform] announcing my project."*

### Phase 7: Maintenance — am I ready to be a maintainer?

- [ ] **I understand what a star, an issue, a fork, and a pull request are.**
  *See the guide at `docs/publishing-your-own-work.md` for plain-English explanations of each.*

- [ ] **I've thought about how quickly I can respond to issues.**
  *No rule requires you to be fast, but a short acknowledgment ("I saw this, will look into it soon") goes a long way.*

- [ ] **My README says something about the project's current status.**
  *Even "actively maintained" or "maintained occasionally" helps people know what to expect.*

---

## License Checklist

The license is the legal document that says who can use the project and how. Without one, the code is technically "all rights reserved" even if it's public on GitHub.

- [ ] **The repository has a `LICENSE` file.**
  *If there is no LICENSE file, stop here. See below.*

- [ ] **I have a basic sense of what the license allows.**
  *You don't need to read every word. The main question is: permissive or copyleft? Permissive (MIT, Apache 2.0) = use it for almost anything. Copyleft (GPL, AGPL) = your contribution must stay under the same open-source license. If you're not sure which type a license is, paste its name into Cursor and ask: "What type of license is [name] and what does it mean for my contribution?"*

- [ ] **I understand that my contribution will be subject to this license.**
  *Whatever rights the project gives to others, your contribution will be under the same terms.*

- [ ] **If this is a copyleft license (GPL, AGPL), I've thought about whether my employer has any restrictions on this.**
  *Some companies have policies about this. If you're unsure, ask HR or your manager — it usually takes one email.*

- [ ] **If I'm bringing in code from another project, I've confirmed the licenses are compatible.**
  *Copying code from a project with a different license can create a conflict. Not sure if they're compatible? Ask any AI tool — including Cursor: "Is it okay to include code from a [License A] project into a [License B] project?" AI handles this factual question well. That said, treat the answer as a starting point, not as legal advice.*

> **No license found?** Ask the maintainer to add one before you contribute.
>
> **How:** Go to the repository on GitHub → click the **Issues** tab → click **New Issue** → write something like: *"I'd love to contribute — would you consider adding an open-source license? choosealicense.com makes it easy to pick one."*
>
> An "issue" on GitHub is just a message to the project — like a public note. It's visible to everyone, which is normal. Wait for a license to be added before contributing.

---

## Attribution and Credit Checklist

"Attribution" means giving credit to the people whose work you're building on.

- [ ] **I've checked how this project credits contributors.**
  *Some projects have a `CONTRIBUTORS` or `AUTHORS` file. Others list contributors in the README. Many just use the git commit history. There's no single standard — have a look and follow whatever pattern is already there.*

- [ ] **If I'm adapting code from another source, I've noted it in my pull request description.**
  *A pull request is how you propose your change on GitHub — you're asking the project owner to "pull in" your changes. When you open one, there's a text box where you write what you changed and why. That's the "pull request description." If your change is based on something you found elsewhere, mention it there: "The approach here is based on the pattern from [link]." This isn't always required, but it's good practice.*

- [ ] **I have not removed existing copyright notices from any file I modified.**
  *If a file starts with `// Copyright 2024 Some Person`, leave it there even if you change every line of code below it.*

- [ ] **I'm comfortable with my name appearing in the commit history and contributor list.**
  *Your GitHub username (or configured git name) becomes part of the permanent record. This is how open source attribution works.*

---

## Security Checklist

- [ ] **My contribution does not contain passwords, API keys, tokens, or private credentials.**

  A password or API key is a secret string that gives access to a service. Accidentally publishing one means anyone who reads your code can use it.

  **The easiest way to check — ask Cursor:**
  > *"Please scan my changes and tell me if there are any hardcoded passwords, API keys, or credentials that shouldn't be in a public repository."*

  If Cursor finds something, ask it to suggest a fix:
  > *"How should I store this API key safely instead of hardcoding it?"*

  The usual answer is to use an environment variable — a value stored on your computer that the code reads at runtime, so the secret never ends up in your files. Cursor can help you set that up.

  **If you're editing in the GitHub browser:** Before clicking "Commit changes", scroll through your edits and confirm you haven't pasted in anything sensitive.

- [ ] **If I found a security vulnerability while preparing this contribution, I will report it privately — not via a public GitHub issue.**

  Public issues are visible to everyone immediately, including people who might exploit the vulnerability. Check `SECURITY.md` for how the project wants you to report it.

  **If there's no SECURITY.md and no obvious way to contact the maintainer privately:**
  Go to their GitHub profile (click their username anywhere in the repo) — some maintainers list an email there. If not, use [GitHub's private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) if the repo has it enabled (look under the Security tab). As a last resort, reply to an existing open issue in the repo — that sends them a notification without creating a new public post about the vulnerability.

- [ ] **I have read `SECURITY.md` if it exists.**
  *Even if your contribution isn't security-sensitive, knowing the disclosure process is useful.*

---

## PR Readiness — Let Cursor Guide You

A "pull request" (PR) is how you propose your changes to the project.

**Start here — don't work through a generic checklist alone:**

The most important thing is to let Cursor read the project's `CONTRIBUTING.md` and walk you through what *this specific project* requires. Every project is different.

In Cursor, say:
> *"Please read the CONTRIBUTING.md for [project URL or paste the file] and walk me through exactly what I need to do before opening a pull request."*

Cursor will tell you the specific steps *this project* asks for — which branch to target, whether tests are required, what format the commit message should be in, and whether you need to open an issue first.

If Cursor finds no CONTRIBUTING.md, ask:
> *"There's no CONTRIBUTING.md — what are the standard best practices I should follow before opening a pull request?"*

---

### What CONTRIBUTING.md usually asks for

These are the most common requirements across open-source projects. They're what Cursor will likely surface when it reads a project's contribution guide:

- **One change per pull request** — fix one bug, add one feature, update one document. Don't combine unrelated changes. Smaller PRs are easier to review and more likely to be accepted.

- **Tests pass** — many projects ask you to run their test suite before submitting. Ask Cursor: *"How do I run the tests for this project and what do I do if they fail?"* Cursor can read the project's documentation and walk you through it.

- **Documentation updated** — if you changed how something works, update any written explanation of it. This might be the README, a docs folder, or a comment in the code. If you're unsure what needs updating, mention it in your PR description and ask.

- **PR description explains the why** — "Fixed the bug" is less useful than "Fixed the bug — when users clicked X, Y happened because of Z." The maintainer needs to understand your reasoning, not just what you changed.

- **Related issue referenced** — if there's an issue number this PR addresses, write "Fixes #42" or "Related to #42" in your description. GitHub will automatically link them.

- **Commit message format** — some projects require a specific format (e.g., `fix: correct typo in README` or `[BUGFIX] login flow`). Check the existing commits in the repo to see the pattern, or ask Cursor: *"What commit message format does this project use?"*

- **Be ready for feedback** — maintainer feedback is normal, not rejection. Most PRs go through at least one round of requested changes before being accepted.

---

## Etiquette Checklist

Open source is a community. How you behave matters as much as what you contribute.

- [ ] **I've searched existing issues and PRs to confirm this isn't already reported or in progress.**
  *Opening a duplicate creates work for everyone. Search first. In Cursor: "Check if there's already an open issue about [describe your issue] in this project."*

- [ ] **For any non-trivial change, I opened an issue to discuss it before building it.**
  *This is especially important for new features. Spending a week building something the maintainer doesn't want is frustrating. A 2-minute issue first can prevent that.*

- [ ] **My first contribution to this project is small.**
  *A bug fix or documentation improvement is a good first contribution. A major refactor is not. Build trust first.*

- [ ] **My tone in all comments and messages is professional and kind.**
  *Assume good intent. Maintainers are often volunteers. "This is broken" lands differently than "I noticed X behavior — is this expected?"*

- [ ] **I will not pressure the maintainer for a faster review.**
  *Give it at least 2 weeks before any follow-up. One follow-up, politely worded, is acceptable after that.*

- [ ] **I accept that the maintainer may decline this PR.**
  *"No" is a valid answer. It doesn't mean your work was bad — it may mean the change doesn't fit the project's direction. Respect it.*

---

## CLA / DCO Checklist

**CLA = Contributor License Agreement.** A document some projects require you to sign before they accept your contribution. It confirms you have the right to contribute and you're granting the project permission to use it. Most small projects don't require this. Large foundation-backed projects (Kubernetes, Apache projects) often do.

**DCO = Developer Certificate of Origin.** A simpler alternative. You add one line to your commit message: `Signed-off-by: Your Name <you@example.com>`. You do this automatically with `git commit -s` instead of `git commit`.

- [ ] **I've checked whether this project requires a CLA or DCO.**
  *Ask Cursor: "Does this project require a CLA or DCO sign-off?" and point it at the CONTRIBUTING.md or project URL.*

- [ ] **If a CLA is required, I've signed it before opening a PR.**
  *A bot will block your PR until this is done. Better to do it first.*

- [ ] **If DCO is required, I'm adding `-s` to my commits: `git commit -s`.**

- [ ] **If I'm contributing on behalf of an employer, I've checked whether a corporate CLA is needed.**
  *Some projects require your employer to sign separately. Check CONTRIBUTING.md or ask Cursor.*

---

## Employer / IP Ownership Checklist

This is the one most people skip — and the one that can occasionally matter.

- [ ] **I know whether I wrote this code on personal time or work time.**
  *Personal time on personal equipment: you almost certainly own it. Work time or work equipment: read your employment agreement or ask HR.*

- [ ] **If I work for a company, I know whether my employment agreement assigns IP to my employer.**
  *Many tech employment agreements include language like "anything you create related to the company's business is owned by the company." If unsure, ask.*

- [ ] **If there's any doubt, I've asked my employer before contributing.**
  *Most employers say yes quickly. One email to HR or your manager is worth it.*

> This checklist does not substitute for legal advice. If the contribution is significant or the IP situation is complex, consult a lawyer.

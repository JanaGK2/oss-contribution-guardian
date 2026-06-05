# Contribution Checklists

Use these before contributing to any open-source project. Each item includes a plain-English explanation of why it matters. Most items take under a minute to verify.

---

## License Checklist

The license is the legal document that says who can use the project and how. Without one, the code is technically "all rights reserved" even if it's public on GitHub.

- [ ] **The repository has a `LICENSE` file.**
  *If there is no LICENSE file, stop here. See the decision tree — this is a significant issue.*

- [ ] **I have read the license (or at least the first few paragraphs) and have a basic sense of what it allows.**
  *You don't need to understand every word. The main question is: permissive or copyleft? Permissive (MIT, Apache 2.0) = use it for almost anything. Copyleft (GPL, AGPL) = your contribution must stay under the same license.*

- [ ] **I understand that my contribution will be subject to this license.**
  *Whatever rights the project gives to others, your contribution will be under the same terms.*

- [ ] **If this is a copyleft license (GPL, AGPL), I've thought about whether my employer has any restrictions on this.**
  *Some companies have policies about contributing to copyleft-licensed projects. If you're unsure, ask. This is not common, but it's worth 5 minutes to check.*

- [ ] **If I'm bringing in code from another project, I've confirmed the licenses are compatible.**
  *Copying 10 lines from a GPL project into an MIT project creates a license conflict. If in doubt, write the code yourself or ask the maintainer.*

> **No license found?** Ask the maintainer to add one before you contribute.
> 
> **How to ask:** Go to the repository on GitHub. Click the **Issues** tab (it's near the top of the page). Click **New Issue**. Write something like: *"I'd love to contribute — would you consider adding an open-source license? choosealicense.com makes it really easy to pick one."*
> 
> An "issue" on GitHub is just a message to the project maintainer — like sending them a note. It's visible to everyone, which is normal. Most maintainers will respond within a few days. Wait for a license to be added before contributing.

---

## Attribution and Credit Checklist

"Attribution" means giving credit to the people whose work you're building on.

- [ ] **I've checked how this project credits contributors.**
  *Some projects have a `CONTRIBUTORS` or `AUTHORS` file. Others list contributors in the README. Many just use the git commit history. There's no single standard.*

- [ ] **If I'm adapting code from another source, I've noted that in my pull request description.**
  *A pull request is how you propose your change on GitHub — you're asking the project owner to "pull in" your changes. When you open one, there's a text box where you write what you changed and why. That's the "pull request description." If your change is based on something you found elsewhere, mention it there: "The approach here is based on the pattern from [link]." This isn't always required, but it's good practice and shows you're being transparent.*

- [ ] **I have not removed existing copyright notices from any file I modified.**
  *If a file starts with `// Copyright 2024 Some Person`, leave it there even if you change every line of code below it.*

- [ ] **I'm comfortable with my name appearing in the commit history and contributor list.**
  *Your GitHub username (or configured git name) becomes part of the permanent record. This is a good thing — it's how open source attribution works.*

---

## Security Checklist

Before contributing, check that your change doesn't accidentally introduce a problem — and that you know what to do if you found a problem.

- [ ] **My contribution does not contain passwords, API keys, tokens, or private credentials.**

  A password or API key is a secret string that gives access to a service — like a password to a database, or a key that lets code talk to Google or OpenAI. Accidentally publishing one means anyone who reads your code could use it.

  **If you're contributing via the GitHub browser (editing files on GitHub.com):**
  Before you click "Commit changes", scroll through your edits and confirm you haven't accidentally included any secret strings, especially if you copied code from your own project.

  **If you're working locally (on your computer):**
  Before committing, review your changes by looking at the files you edited. Pay particular attention to any configuration files (especially files named `.env`, `config.json`, `settings.py`, or similar) — these often contain secrets and should almost never be committed to a public project.

  A `.env` file is a common way developers store secrets locally. It should never be shared or committed. If a project has a `.gitignore` file (a list of files git should ignore), `.env` is usually listed there for this reason.

- [ ] **If I found a security vulnerability while preparing this contribution, I will report it privately — not via a public GitHub issue.**
  *Public issues are visible to everyone, including attackers. Check `SECURITY.md` for the project's preferred reporting method. If there isn't one, contact the maintainer directly via GitHub.*

- [ ] **I have read `SECURITY.md` if it exists.**
  *Even if your contribution isn't security-sensitive, knowing the project's security disclosure process is useful.*

---

## PR Readiness Checklist

A "pull request" (PR) is how you propose your changes to the project. This checklist helps you make sure you're actually ready.

- [ ] **I have read `CONTRIBUTING.md` and followed every step it specifies.**
  *This is the most important item on this entire list. Maintainers are busy. A PR that ignores the contribution guide creates extra work for them.*

- [ ] **My change is narrowly scoped — one thing per PR.**
  *Don't fix a bug AND refactor the code AND add a new feature in the same PR. Split it up. Smaller PRs are easier to review and more likely to be accepted.*

- [ ] **I have run the project's tests locally and they pass.**
  *Check `CONTRIBUTING.md` or the README for how to run tests. If there are no tests, note that in your PR.*

- [ ] **If my change affects how users interact with the software, I have updated the documentation.**
  *If you changed how something works, update any written explanation of how it works. This might be the README, a docs folder, or a comment in the code explaining what a function does. If you're not sure what needs updating, mention it in your pull request description and ask.*

- [ ] **I have reviewed my own diff before opening the PR.**
  *Read through your changes as if you're the maintainer seeing them for the first time. Is it clear what changed and why?*

- [ ] **My PR description explains the *why*, not just the *what*.**
  *"Fixed the login bug" is less useful than "Fixed the login bug — when users clicked 'remember me', the session token was being overwritten on page reload (see issue #42)."*

- [ ] **I have referenced the related issue in my PR (if one exists).**
  *Add "Fixes #42" or "Related to #42" in your PR description. GitHub will automatically link them.*

- [ ] **I am prepared to iterate on this PR based on feedback.**
  *Maintainer feedback is normal, not a rejection. Most PRs go through at least one round of changes.*

---

## Etiquette Checklist

Open source is a community. How you behave matters as much as what you contribute.

- [ ] **I have searched existing issues and PRs to confirm this isn't already reported or in progress.**
  *Opening a duplicate issue or PR creates work for everyone. Search first.*

- [ ] **For any non-trivial change, I opened an issue to discuss it before building it.**
  *This is especially important for new features. Spending a week building something the maintainer doesn't want is frustrating for everyone. A 2-minute issue first can prevent that.*

- [ ] **My first contribution to this project is small.**
  *A bug fix or documentation improvement is a good first contribution. A major architectural refactor is not. Build trust first.*

- [ ] **My tone in all comments and messages is professional and kind.**
  *Assume good intent. Maintainers are often volunteers. "This is broken" lands differently than "I noticed X behavior — is this expected?"*

- [ ] **I will not pressure the maintainer for a faster review.**
  *Maintainers have jobs, families, and other projects. "Just checking in" messages every few days are exhausting to receive. Give it at least 2 weeks.*

- [ ] **I accept that the maintainer may decline this PR.**
  *"No" is a valid answer. It doesn't mean your work was bad — it may mean the change doesn't fit the project's direction. Respect it.*

---

## CLA / DCO Checklist

**CLA = Contributor License Agreement.** A document some projects require you to sign before they accept your contribution. It's a legal confirmation that you have the right to contribute the code and you're granting the project permission to use it.

**DCO = Developer Certificate of Origin.** A simpler, lighter-weight alternative. You add one line to your commit message: `Signed-off-by: Your Name <you@example.com>`. You do this automatically by running `git commit -s` instead of `git commit`. It's a statement that you wrote the code and have the right to contribute it.

Most small projects require neither. Large foundation-backed projects (Kubernetes, Linux kernel, Apache projects) often require one or both.

- [ ] **I have checked whether this project requires a CLA.**
  *Search `CONTRIBUTING.md` and the README for "CLA", "Contributor License Agreement", or "sign". Also look for a CLA bot comment on existing PRs.*

- [ ] **If a CLA is required, I have signed it before opening a PR.**
  *The CLA bot will block your PR from being merged until this is done. Better to do it first.*

- [ ] **I have checked whether this project requires DCO sign-off.**
  *Search for "DCO", "sign-off", or "Signed-off-by" in `CONTRIBUTING.md`.*

- [ ] **If DCO is required, I'm adding `-s` to my commits: `git commit -s`.**

- [ ] **If I'm contributing on behalf of an employer, I've checked whether the project needs a corporate CLA.**
  *When code is written on work time or using work resources, some projects require your employer to sign a corporate version of the CLA, not just you individually. Check `CONTRIBUTING.md` or the project's CLA page.*

---

## Employer / IP Ownership Checklist

This is the one most people skip — and the one that can occasionally matter a lot.

- [ ] **I know whether I wrote this code on personal time or work time.**
  *If it was personal time on personal equipment: you almost certainly own it. If it was work time or work equipment: read your employment agreement or ask HR.*

- [ ] **If I work for a company, I know whether my employment agreement assigns IP to my employer.**
  *Many technology employment agreements include language like "any work related to the company's business is owned by the company." If you're not sure, the safe move is to ask.*

- [ ] **If there's any doubt, I've asked my employer before contributing.**
  *This sounds bureaucratic, but most employers will say yes quickly. It takes 5 minutes to send an email and avoid a problem later.*

> This checklist does not substitute for legal advice. If the contribution is significant or the IP situation is complex, consult a lawyer.

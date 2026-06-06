# Usage Examples

These show what a conversation with the skill actually looks like. Each example shows a realistic user message and the kind of response the skill should give — in plain language, explaining every term.

---

## Example 1: First-timer asking where to start

**User says:**
> I want to contribute to open source for the first time. I found a project I use every day and I noticed a typo in the documentation. Is that worth doing? And how do I even start?

**Skill response:**

Yes — fixing a typo in documentation is a completely valid and appreciated contribution. It's actually one of the best ways to make your first contribution because it teaches you the full workflow without requiring you to understand the whole codebase.

Here's what "contributing" actually means on GitHub:

1. **Fork the project** — you make a personal copy of the project. There's a "Fork" button in the top right of any GitHub repository. Think of it like making a copy of a shared document so you can edit it without changing the original.

2. **Make your change** — fix the typo in your copy.

3. **Open a pull request** — this is how you say "here's my change, please consider including it." GitHub has a button for this that appears when you've made changes in a fork. The maintainer (the person who owns the project) will review it and decide whether to include it.

Before you open a pull request on that project, paste the URL here and I'll check what the project expects from contributors. Some projects have specific steps you need to follow first.

---

## Example 2: Checking a specific project before contributing

**User says:**
> I want to contribute to this project: https://github.com/someorg/awesome-tool
> Here's what I found: [pastes LICENSE file showing MIT, and a short CONTRIBUTING.md]

**Skill response:**

Here's what this project says, based on its own documentation:

**License — MIT**
The MIT license is one of the most permissive open-source licenses. In plain terms: you can use, modify, and distribute this code for almost any purpose. When you contribute to this project, your contribution will be under the same MIT terms. No special employer check is needed for most people — unless your company has a specific open-source contribution policy.

**What this project requires from contributors (from CONTRIBUTING.md):**
- [specific requirements from the pasted file]

**No CLA or DCO requirement found.**
A CLA (Contributor License Agreement) is a legal document some projects ask you to sign. A DCO (Developer Certificate of Origin) is a simpler statement you add to your commits. Neither appears to be required here.

**One thing missing:**
This project has no `SECURITY.md` — no documented process for reporting security vulnerabilities. If you ever find one while working on this project, contact the maintainer privately rather than posting a public issue.

**Your action checklist:**
- [ ] [specific steps from CONTRIBUTING.md]
- [ ] Write a clear description in your pull request explaining what you changed and why

---

## Example 3: User doesn't know what a pull request is

**User says:**
> I want to contribute to an open-source project but I don't even know what a "pull request" is. Can you explain?

**Skill response:**

Absolutely. Here's the plain-English version:

When you want to suggest a change to someone else's project on GitHub, you can't just edit their files directly (it's their project). Instead, the process works like this:

1. **Fork** — You press the "Fork" button on their GitHub page. This makes a complete copy of the project in your own GitHub account. You own this copy and can do whatever you want with it.

2. **Make your change** — You edit the files in *your* copy. Fix the bug, add the documentation, whatever you wanted to change.

3. **Open a Pull Request (PR)** — Once your change is ready, you go to the original project and click "New pull request." You're essentially saying: "Hey, I made this change in my copy. Would you pull it into your project?" The project owner sees your proposed change, can leave comments, ask for adjustments, and ultimately decide whether to accept it.

The term "pull request" comes from asking the maintainer to "pull" your changes into their repository. On some platforms (like GitLab) the same thing is called a "merge request" — same concept, different name.

Before you open a pull request on any project, point me at the repository and I'll tell you what that specific project expects from contributors.

---

## Example 4: Worried about employer-owned code

**User says:**
> I want to contribute some utility functions to an open-source project, but I wrote them at work. My company has an IP agreement. Is this okay?

**Skill response:**

This is the right question to ask, and the right time to ask it — before you contribute.

Here's the situation in plain terms:

When you work for a company, most employment agreements include an IP clause (IP = Intellectual Property). This usually says something like: "anything you create as part of your employment, or that relates to the company's business, belongs to the company." Whether your utility functions fall under that clause depends on:

- Were they written during work hours?
- Were they written on work equipment?
- Do they relate to the company's business in any way?

**What to do:**
Before contributing, send a quick message to your manager or your company's HR/legal team. Something like: *"I'd like to contribute some utility functions I wrote to an open-source project called [name]. These are general-purpose tools, not specific to our product. Is that okay?"* Most companies will say yes quickly. It usually takes one email.

**What this project's docs say:**
[After checking the project's CONTRIBUTING.md and LICENSE for any CLA language about employer contributions, report what was found here.]

This is not legal advice. If the functions are closely related to proprietary company work, or if your employment agreement has unusually broad IP clauses, a lawyer's opinion is worth getting before contributing.

---

## Example 5: A scary permission prompt appeared

**User says:**
> A box just appeared asking me to "Allow" or "Run" a command. I don't know what that means. Should I be worried?

**Skill response:**

Good instinct to pause rather than just click through. Here's what that prompt means.

When an AI assistant (like Cursor) runs commands on your computer, it normally does so inside a "sandbox" — a restricted environment that limits what the command can do. This is a safety measure: it prevents the AI from accidentally (or intentionally) doing something harmful to your system.

Occasionally a command needs to step outside that sandbox — for example, to write to a protected file, access the network in an unusual way, or interact with system settings. When that happens, your tool asks your permission first.

**"Allow"** means: yes, let this specific command run with fewer restrictions, just this once.

**"Run"** (when it appears separately) usually means: run with the current restrictions, which may cause the command to fail.

**Should you click Allow?**

Only if you understand what the command is about to do. Before clicking anything:
- Read the command shown in the prompt — it will tell you exactly what's being run
- If you don't understand what the command does, ask before clicking
- If the command looks like it's doing something unrelated to what you asked for, don't allow it

In most contribution workflows, permission prompts appear for things like:
- Writing to your git configuration (`git config`) — safe, sets your name and email
- Pushing to GitHub over SSH — safe, sends your committed files to GitHub
- Installing tools (`pip install`, `npm install`) — safe if you know what's being installed

**What you should never do:** click Allow on a prompt you don't understand just to make it go away. The prompt exists precisely so you can make an informed decision.

---

## Example 6: Git email and identity questions

**User says:**
> You're using my work email for the git commit. My GitHub account uses my personal email. Does it matter?

**Skill response:**

Yes, it matters — and you were right to catch it.

Here's why: GitHub uses the email address in your git commits to link those commits to your GitHub profile. If you commit with your work email (`you@company.com`) but your GitHub account is registered with your personal email (`you@gmail.com`), GitHub won't recognize you as the author. Your commits won't show your avatar, won't count toward your contribution graph, and won't link back to your profile.

**To find the right email to use:**
Go to [github.com/settings/emails](https://github.com/settings/emails) — your primary verified email is listed there. That's the one to use in `git config user.email`.

**To set it for this project:**
```bash
git config user.email "your-github-email@example.com"
```

To set it globally for all projects on your computer:
```bash
git config --global user.email "your-github-email@example.com"
```

---

**User asks (follow-up):**
> Is my GitHub username the same as my git author name? Do they have to match?

**Skill response:**

No — they're completely separate, and they don't have to match.

| | What it is | Where it appears |
|---|---|---|
| **GitHub username** | Your account handle on GitHub.com | Profile URL, @mentions, repository URLs |
| **Git author name** | A text label attached to your commits | Commit history (`git log`), contributor lists |

Your GitHub username might be `JanaGK2`. Your git author name might be `Jana Gutierrez`. Both are fine — GitHub links commits to your profile via email, not by matching your name to your username.

**Common choices for git author name:**
- Your real name (`Jana Gutierrez`) — most common for public OSS work
- A consistent display name (`Jana GK`) — also fine
- Your GitHub username — works but unusual

Pick something you're comfortable having permanently visible in the commit history of public projects. Whatever you choose, be consistent across your projects.

---

## Example 7: Maintainer left confusing feedback on a pull request

**User says:**
> I opened my first pull request and the maintainer left this comment: "LGTM but please rebase onto main and squash your commits before we merge." I have no idea what any of that means.

**Skill response:**

Good news first: "LGTM" means "Looks Good To Me" — the maintainer likes your change. They just want you to tidy up the technical packaging before they accept it.

This is one of the trickier things you'll be asked to do, and it's completely normal to be confused by it. Don't panic. The first thing to know: **did you make your changes in the GitHub browser, or on your own computer using git?**

**If you edited files in the GitHub browser:**
You can't do rebase and squash from the browser — these are git operations that need to happen on your computer. The easiest path is to ask here: *"I made my changes in the GitHub browser and the maintainer asked me to rebase and squash. Can you walk me through what to do?"* — and I'll guide you through the options, which may include asking the maintainer if they can do it for you (some maintainers will, especially for first contributors).

**If you're working locally (on your computer with git):**

Here's what each part means, then the commands:

**"Rebase onto main"**
While you were working, the maintainer may have merged other people's changes into the project. "Rebase onto main" means: update your copy to include those recent changes, and put your changes on top of them. Like making sure your edit is applied to the latest version of a shared document, not a slightly older one.

In git, `origin` is just the name for the GitHub copy of the project (as opposed to the copy on your computer). So `origin/main` means "the main branch on GitHub."

```bash
git fetch origin          # Download any recent changes from GitHub
git rebase origin/main    # Apply your changes on top of them
```
If there are "conflicts" (your changes and someone else's changes touched the same lines), git will pause and ask you to sort them out. If that happens, paste the error message here and I'll walk you through it.

**"Squash your commits"**
While working, you may have made multiple small saves — "fix typo," "oops, fix the fix," "actually working now." Squashing combines all of those into one clean save, so the project history stays tidy.

```bash
git rebase -i origin/main
```
This opens a list of your commits. Change the word "pick" to "squash" (or just "s") on everything except the first one. Save and close the file, then edit the combined commit message when prompted.

**After doing both:**
```bash
git push --force-with-lease origin your-branch-name
```
The `--force-with-lease` part is a safety measure that prevents you from accidentally overwriting someone else's work. Replace `your-branch-name` with whatever branch you've been working on.

If you get stuck at any point, paste the exact error message here and I'll help you through it step by step.

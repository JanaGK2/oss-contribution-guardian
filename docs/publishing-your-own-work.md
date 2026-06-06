# Publishing Your Own Work

## The situation this covers

You built something — a script, a tool, a collection of templates, a skill file, a configuration. You use it yourself. You're wondering: is this worth sharing publicly? Could it help other people?

This guide walks you through that decision, the preparation work, how to tell people about it after you publish, and what being a project maintainer actually involves day-to-day.

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

## Phase 2: Who is your intended user?

This is the question most people never ask before publishing — and it's why most READMEs are impossible to follow.

Your project will be found by real people who have never spoken to you, have no idea what you were thinking when you built this, and will spend about 30 seconds deciding whether to try it or close the tab. The only way to keep their attention is to speak directly to them, in their terms, at their level.

**Be specific about who they are.**

"Developers" is not an audience. "People who use Python" is not an audience. The more specific you can get, the clearer your README will be.

Good examples:
- "People who use Cursor and work with Google Sheets for reporting"
- "Data analysts who need to pull Salesforce data without a developer's help"
- "New open-source contributors who don't yet know git"

Bad examples:
- "Developers"
- "Anyone who works with data"
- "Open-source users"

If you're struggling to be specific, ask yourself: *Who would I send this to right now, and what would I say when I sent it?* The person you're imagining is your intended user.

**Think about what they already know — and what they don't.**

Once you've named your audience, think about what they know:
- What tools do they already use?
- What words are familiar to them, and which would need explaining?
- Are they comfortable with the command line, or do they do everything through a browser?

This shapes everything: how you write the installation instructions, what examples you include, what you don't need to explain.

**Then write (and check) your README for them.**

Once the README is drafted, test it. Ask Cursor:
> *"My intended user is [describe them]. Read my README and tell me: would this person know how to get started? Is there anything that assumes knowledge they might not have? Is there anything confusing or missing?"*

This is the same thing a good editor does — checking that what you meant to say is what someone else actually reads.

---

## Phase 3: Is it safe to share?

This is the most important phase and the one most people skip. Before a single file goes public, you need to check for things that must not be in a public repository.

**Why this matters so much:** Once something is published to GitHub, it is very difficult to truly remove it from the internet. Even if you delete the file an hour after publishing, automated bots and search engines may have already copied it. Treat this check as mandatory, not optional.

**In Cursor, say:**
> *"Before I publish this project publicly, please scan it for anything that shouldn't be in a public repository — credentials, internal company references, hardcoded paths, or internal context in comments. Here's the project: [paste files or point to folder]"*

Cursor will actively look for:

**Credentials and secrets**
API keys, passwords, tokens, private keys. These are things that give you access to a service — if someone else gets them, they can use that access as if they were you.

Common patterns Cursor will look for: strings starting with `sk-`, `AIza`, `Bearer `, assignments like `password =`, `api_key =`, or any long random string assigned to a variable.

Fix: move them to environment variables. An environment variable is a value stored on your computer (or server) that your code reads at runtime — so the secret never lives in your files at all. Ask Cursor: *"How do I replace this hardcoded API key with an environment variable?"*

**Internal company references**
Internal domain names (anything like `internal.yourcompany.com`), internal tool names (Jira project codes that only exist in your company, internal wiki URLs), VPN addresses, internal hostnames.

Fix: remove or replace with generic placeholders. Example: replace `https://jira.internal.yourcompany.com/PROJECT-1234` with a comment like `# see your team's issue tracker`.

**Hardcoded personal or machine-specific paths**
Things like `/Users/Jana/Documents/work/project/` or `C:\Users\Jana\`. These paths only exist on your machine. Someone else running your code will get an immediate error.

Fix: make paths relative (starting with `./` instead of a full path), or configurable via a setting they can change.

**TODO/FIXME comments with internal context**
Comments like `# TODO: ask Maria about the Salesforce rate limit` or `# FIXME: workaround for our broken internal proxy`. These reveal your workplace, internal people, and internal systems.

Fix: remove the comment entirely, or rewrite it as a generic technical note: `# TODO: handle rate limiting` is fine publicly.

**Company-specific logic**
Business rules, customer names, internal product codes that have no meaning outside your organization.

Fix: generalize, remove, or replace with a clearly labeled example.

---

## Phase 4: Does it have the right structure?

A project that is hard to understand from the outside will not get used, even if it's genuinely useful. These are the files every public project should have.

**In Cursor, say:**
> *"Help me create the standard documentation files for my open-source project. Here's what it does: [describe it], and my intended users are [describe them]. Generate a draft README, and tell me what license to use."*

### The files you need

**README.md** (required)
The first thing anyone reads. It should explain:
- What the project does (one clear sentence)
- Why it exists (the problem it solves)
- Who it's for (your intended user, from Phase 2)
- How to install and use it (step by step, at the level of your intended user)
- A simple example showing what it looks like in practice

Cursor can draft this from your description. The opener is the hardest part — see Phase 5.

**LICENSE** (required)
Without a license, your project is technically "all rights reserved" even if it's public. That means nobody can legally use it, modify it, or share it.

A license is a short legal document that gives people permission. For most tools and skills: **MIT License** — simplest, most permissive, lets anyone use it for anything, including commercial use.
If you want any modified version to stay open source: **GPL v3** — people can use and modify it, but they must also share their changes publicly.

Ask Cursor: *"What license should I use for my project and why?"* — it will ask you a couple of questions and recommend one.

**.gitignore** (required)
A list of files that git should never commit. Prevents you from accidentally publishing credentials, local config, or system files.

Git is the version control system that tracks your project's history (what changed, when, and why). A `.gitignore` file tells git: "These files exist on my machine, but never include them in what you track or share."

Ask Cursor: *"Generate a .gitignore for a [Python / JavaScript / general] project."*

**CONTRIBUTING.md** (recommended, can be short)
Two to three sentences is enough: what contributions are welcome, and how to propose them. Sets expectations for anyone who finds the project and wants to help.

**SECURITY.md** (recommended, can be very short)
One paragraph saying how to report a security issue privately. This prevents people from accidentally posting vulnerabilities (bugs that could let someone do harm) as public GitHub issues where anyone can read them.

**CODE_OF_CONDUCT.md** (recommended)
One line referencing the Contributor Covenant is fine: *"This project follows the [Contributor Covenant v2.1](https://www.contributor-covenant.org/version/2/1/code_of_conduct/)."* The Contributor Covenant is a widely-used standard document that sets basic expectations for respectful collaboration in open-source projects.

---

## Phase 5: Can you explain the why?

The README opening is the hardest writing you'll do. Most people write: *"This is a tool that does X."* That tells someone what it does but not why they should care.

Remember your intended user from Phase 2. Write the opener as if you're explaining it to that specific person, in the way you'd explain it in a message to a friend in the same situation as them.

**In Cursor, say:**
> *"Help me write the opening paragraph for my README. My intended user is [describe them]. Ask me questions about why I built this and what problem it solves, then draft an opener from my answers. Write it as if talking directly to my intended user."*

A good opener answers "why does this exist?" immediately:

> *"Every time I needed to [do the thing], I had to [describe the painful manual process]. This does it in [describe the simpler way]."*

or:

> *"I couldn't find a straightforward way to [do the thing], so I built one."*

Once you have that sentence, the rest of the README is just the details.

---

## Phase 6: Creating the repository and pushing your files

Once Phases 1–5 are done, you need to get your files from your computer to GitHub. Here's how that works.

### Step 1: Create the repository on GitHub

A repository (often called a "repo") is a project's home on GitHub — a folder that stores all the files and their full history of changes.

Create one at [github.com](https://github.com) (green "New" button, top left), or ask Cursor: *"Create a new public GitHub repository called [name] and push my project to it."*

When creating it: set it to **Public**, and don't tick any of the "Initialize with..." options if your project already has files. You'll push those yourself.

### Step 2: Does Cursor need to be connected to GitHub?

No — there is no separate "connect Cursor to GitHub" step. Cursor uses git, which is the underlying tool that talks to GitHub. If you've successfully run `git push` before in this workspace (which you have — we've done it in this project), everything is already set up.

What actually handles the connection is one of two things:
- **GitHub CLI** (`gh`): A command-line tool that logs you into GitHub. If you installed it and ran `gh auth login` at some point, that's what's been authenticating you. You can check: in Cursor's terminal, type `gh auth status` and it will tell you who you're logged in as.
- **SSH keys**: A cryptographic pair of files that GitHub uses to recognize your computer. More technical to set up, but doesn't require typing a password.

If you've been successfully pushing to GitHub (as we have), you don't need to do anything.

### Step 3: Push your files

Pushing means sending your local changes from your computer to GitHub. The process is always three steps, in this order:

**Step 3a — Stage your changes (`git add`)**
"Staging" means telling git which changed files you want to include in your next save. Think of it as putting items in a box before sealing and sending it.

```bash
git add .
```
The `.` means "all changed files in this folder." You can also specify individual files instead.

**Step 3b — Commit (`git commit`)**
A commit is a saved snapshot of your project at a specific moment, with a short description of what changed and why. It's like pressing Save in a word processor, except it keeps every previous save and you can go back to any of them.

```bash
git commit -m "Add README and initial skill files"
```
The message after `-m` (short for "message") is yours to write. A good commit message describes *what changed* in plain language. "Update README" is fine. "Fix typo in Phase 3 checklist" is fine.

**Step 3c — Push (`git push`)**
Push sends your committed changes from your computer to GitHub.

```bash
git push origin main
```
`origin` is the name git uses to refer to the GitHub copy of your project (the remote). `main` is the name of the branch you're pushing to. A branch is a parallel version of the project — `main` is the default one where finished work lives.

Or just:
```bash
git push
```
If your branch is already set up to track a remote branch (which it will be after the first push), git will know where to send it.

### Step 4: Add topic tags and a description

On your repository page on GitHub, click the gear icon next to "About" on the right side. Add:
- A short description (the one-sentence summary from Phase 5)
- Topic tags (searchable labels like the language, the problem domain, tools it works with — e.g., `python`, `cursor`, `google-sheets`, `automation`)

These are how people discover your project without already knowing it exists.

---

## Day-to-day: pushing ongoing changes

Once your project is published, you'll continue making changes over time. The same three-step process always applies: `git add`, `git commit`, `git push`.

For skills and documentation projects like this one, the workflow looks like this in practice:

1. You edit a file in Cursor
2. When you're ready to save your work to GitHub, say: *"Commit and push my changes"*
3. Cursor will stage the changes, ask you for (or suggest) a commit message, and push

**Asking Cursor for a reminder:** You can also set Cursor to prompt you when a session ends if you have uncommitted local changes. Say: *"Remind me to commit and push before we finish this session."*

### The "always ask before pushing" rule

A global rule is installed that makes Cursor always show you a summary of what's about to be pushed and ask for your confirmation before running `git push`. This means:

- You'll never accidentally push something you didn't mean to
- You'll see a plain-English summary of what changes are going out
- You can say no and review further if something looks off

**If you want to remove this rule** (for example, because you find it interruptive), the rule file is at `~/.cursor/rules/git-push-confirmation.mdc`. You can delete it or open it in Cursor and say "disable this rule."

---

## Phase 7: Telling people about it

Publishing the repository is not the same as anyone knowing it exists. GitHub has millions of repositories. Yours won't be found unless you put it in front of the right people.

The key rule: **post where your intended user already spends time.** A Cursor skill for data analysts goes where data analysts are. A Python library goes where Python developers are. There is no single universal place.

Here are the options, with honest guidance on each:

---

### Reddit

Reddit is organized into communities called **subreddits** (each one starts with `r/`). The key is finding the right subreddit — the one where your intended user hangs out.

Examples:
- Built a Python tool? → [r/Python](https://www.reddit.com/r/Python/) or [r/learnpython](https://www.reddit.com/r/learnpython/)
- Built a Cursor skill? → [r/cursor](https://www.reddit.com/r/cursor/) or [r/AIAssistants](https://www.reddit.com/r/AIAssistants/)
- Built a productivity tool? → [r/productivity](https://www.reddit.com/r/productivity/)
- General dev tool? → [r/programming](https://www.reddit.com/r/programming/) or [r/github](https://www.reddit.com/r/github/)

**How to post on Reddit without it going badly:**
- Read the community rules before posting. Many subreddits have rules about self-promotion.
- Don't just paste a link. Tell the story: what problem you had, what you built, what it does. Then add the link.
- Be present to answer questions in the comments. A post with no replies to comments feels abandoned.

---

### LinkedIn

LinkedIn works best for tools that solve professional or workplace problems — productivity, data work, reporting automation, anything used in a job context.

**How to post on LinkedIn:**
Write a short post (3–5 paragraphs) telling the story of why you built it. End with the GitHub link. Stories that start with "I got tired of doing [thing] manually every week" consistently do better than posts that start with "I built a tool."

LinkedIn posts with images or a short screen recording tend to get significantly more views than text-only posts.

---

### dev.to

[dev.to](https://dev.to) is a developer-focused writing platform. It's explicitly welcoming to first posts and beginner-friendly projects. Unlike Hacker News (see below), the community here is not harsh.

**What to write:** A short article (500–1000 words) explaining what the project does, why you built it, and what you learned. You can embed code snippets and link to GitHub. Tag the article with relevant topics.

---

### Hacker News

[Hacker News](https://news.ycombinator.com) is a tech community with high traffic. Posts that do well there get seen by a lot of people. The "Show HN:" format (posts that start with "Show HN:") is specifically for sharing projects you've built.

**The honest caveat:** the community is technically sophisticated and direct. Comments can be critical. This is not a bad place to post — honest feedback is useful — but be prepared for it.

A "Show HN:" post needs a very strong one-liner. If your first sentence is unclear or the project seems too niche, it won't get traction.

---

### Product Hunt

[producthunt.com](https://www.producthunt.com) is built for announcing tools and apps. It works best for things with a visual interface — a web app, a dashboard, something you can show a screenshot of.

For command-line scripts or text-based tools, Product Hunt is less effective. For anything with a UI, it's worth considering.

---

### Discord and Slack communities

Many technology communities have Discord servers or Slack groups with channels specifically for sharing projects. These are often the highest-quality places to share — you're reaching people who are already using the technology your tool is built for.

To find them: search for "[your technology] Discord" or "[your technology] community" on Google. Or ask Cursor: *"Where do [type of user] communities hang out online? I'm looking for a Discord or Slack where I could share a project."*

---

### Twitter/X

Posting with the hashtag `#buildinpublic` reaches a community of people who share what they're building. Works best if you have some existing followers or if the project is genuinely interesting and you can explain it in a tweet.

Include a short description, a GitHub link, and — if possible — a short screen recording or screenshot of the tool in action.

---

### Substack or personal blog

If the project has an interesting backstory or you learned something unexpected while building it, consider writing about it. A "why I built this" blog post often travels further than a plain GitHub link because it gives people something to read and share.

If you don't have a blog: [Substack](https://substack.com) is free, [dev.to](https://dev.to) works without any setup, and [GitHub itself supports a blog through GitHub Pages](https://pages.github.com/) if you want to keep everything in one place.

---

**In Cursor, say:**
> *"My project is [describe it]. My intended user is [describe them]. Which of these platforms would be the best fit for sharing it, and can you help me draft a post for the top two?"*

---

## Phase 8: What being a maintainer actually means

When you publish a project publicly, you become its **maintainer** — the person responsible for keeping it alive and responding to the community that forms around it. This is not as scary as it sounds, but it's worth understanding before you publish.

---

### When someone stars your project

A **star** (the ⭐ icon on a GitHub repository) means someone bookmarked your project. They found it interesting or useful.

**What you need to do:** Nothing. No action is required. Stars are not requests. They're signals — a rough measure of how many people found the project worth saving. It's a good feeling. Enjoy it.

---

### When someone forks your project

A **fork** means someone created their own copy of your project in their GitHub account, usually because they want to modify it or use it as a starting point for something else.

**What you need to do:** Nothing, unless the fork is followed by a pull request (see below). Forks are a normal, positive thing. The MIT License (and most others) explicitly allows this.

---

### When someone opens an issue

An **issue** on GitHub is like a message someone sends to the project. It might be:
- A **bug report**: something isn't working as expected
- A **feature request**: something they wish the project did
- A **question**: they're confused about how to use it

**What to do when an issue arrives:**

1. **Acknowledge it.** Even a one-line "Thanks for reporting this, I'll take a look" makes a huge difference to the person who filed it. They don't know if anyone read it.

2. **Label it** (optional but helpful). GitHub lets you add labels like "bug," "enhancement," "question." Ask Cursor: *"How do I add labels to GitHub issues?"*

3. **Decide what to do:**
   - If it's a valid bug: confirm you can reproduce it and then fix it, or leave it open if you need time.
   - If it's a feature request: decide if you want to build it. It's completely fine to say "this is out of scope for this project" and close the issue.
   - If it's a question: answer it. If the same question comes up often, add the answer to the README.

4. **Close it when it's resolved.** An issue with no resolution comment just looks abandoned.

**How quickly do you need to respond?**
There's no rule. For a small personal project, even a few weeks is fine. But even a short acknowledgment ("I saw this, will look into it soon") prevents the person from thinking nobody maintains the project.

---

### When someone opens a pull request

A **pull request** (PR) is when someone has made a change to your project and is proposing you add it. They've done the work — now they're asking you to review it.

**What to do when a pull request arrives:**

1. **Acknowledge it.** "Thanks for this, I'll review it soon." Same principle as with issues.

2. **Read the change.** GitHub shows you exactly what they changed. You can see a line-by-line comparison between the original and the proposed version.

3. **Decide:**
   - If it looks good: click "Merge pull request." You're done. Their change is now part of your project.
   - If you have questions: leave a comment on the specific lines. GitHub lets you comment on individual lines of code. Ask for clarification, suggest an alternative, or explain why something needs to change.
   - If it's not what you want: explain why and close it politely. "Thanks for taking the time — this is out of scope for the direction I'm taking this project" is a complete and respectful response. You don't owe anyone a merge.

4. **Say thank you.** The person did work they didn't have to do. It costs nothing to acknowledge that.

**In Cursor, say:**
> *"Someone just opened a pull request on my GitHub project. Here's what they changed: [paste the description]. Help me understand what they did and how to respond."*

---

### When you don't have time anymore

Life changes. Projects you were excited about six months ago sometimes become things you no longer have time to maintain. This is completely normal and happens to almost every project eventually.

**You have options:**

**Option 1: Mark it as "unmaintained."**
Add a notice at the top of your README: *"This project is no longer actively maintained. It may still work, but issues and pull requests are not being reviewed."*

You can also add an "unmaintained" badge — a small image that signals project status visually. Ask Cursor: *"How do I add an unmaintained badge to my GitHub README?"*

**Option 2: Archive it.**
GitHub lets you "archive" a repository. Archived repositories become read-only — people can still view and fork them, but no new issues or PRs can be opened. On your repository page: Settings → scroll down to "Danger Zone" → Archive this repository.

This is a responsible thing to do. It honestly communicates the state of the project.

**Option 3: Transfer it to someone else.**
If someone is actively using the project and wants to take over maintenance, you can transfer ownership to them. GitHub Settings → Danger Zone → Transfer ownership.

---

### The honest picture of what low-maintenance looks like

Most small open-source projects have one maintainer (the person who built it) and receive only occasional activity — maybe a few issues a year, maybe a PR or two. You don't need to treat it like a job.

A realistic minimum:
- Respond to issues when you have time
- Keep the README accurate if something changes
- Be honest about the project's status in the README

That's it. Nobody expects you to work weekends on a free tool you built for yourself.

---

**In Cursor, say:**
> *"I just published my project and someone opened an issue / pull request. Here's what it says: [paste it]. Help me understand it and draft a response."*

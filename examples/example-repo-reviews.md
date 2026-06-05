# Example Repository Reviews

Five worked assessments showing how the skill should respond to different repository states. Each one shows the exact kind of response a beginner should expect.

---

## Example 1: Healthy, Well-Documented Repository

**User says:** *"I want to fix a typo I found in the documentation for this project: https://github.com/expressjs/express. What do I need to know?"*

**What the skill finds:**
- LICENSE: MIT ✓
- CONTRIBUTING.md: exists, covers tests, commit format, and branch conventions ✓
- CODE_OF_CONDUCT.md: exists ✓
- SECURITY.md: exists ✓
- PR template: exists ✓
- No CLA or DCO required

**Skill response:**

---
Good news — this is a well-organized project with clear contribution docs. Here's what you need to know for your documentation fix.

**What this project explicitly requires:**

The license is MIT — permissive, meaning your contribution will be under the same terms. No CLA or sign-off required.

The `CONTRIBUTING.md` specifies:
- Open a pull request targeting the `master` branch
- For documentation-only changes, you may not need to add tests, but check the PR template

The PR template will appear automatically when you open the PR. Fill it out — even for a typo fix, explain what you changed and why.

**What you should do:**

A typo fix is a great first contribution. Here's the sequence:
1. Fork the repository (GitHub has a "Fork" button in the top right)
2. Make your fix in your fork
3. Open a pull request targeting `master`
4. In your PR description: "Fixed typo in [filename]: 'recieve' → 'receive'"

**One thing to be aware of:**

The project has a `SECURITY.md`. You're not contributing security-sensitive code, but it's worth knowing it exists. If you ever find a security issue while browsing a project, that's the right place to learn how to report it.

**Open questions:** None — this is a well-documented project.

**Action checklist:**
- [ ] Fork the repo
- [ ] Make your fix
- [ ] Target the `master` branch in your PR
- [ ] Fill out the PR template
---

---

## Example 2: Missing Contribution Documentation

**User says:** *"I found a bug in this small Python library I use. There's no CONTRIBUTING.md. What do I do?"*

**What the skill finds:**
- LICENSE: MIT ✓
- CONTRIBUTING.md: missing
- CODE_OF_CONDUCT.md: missing
- SECURITY.md: missing
- Recent merged PRs: informal, short descriptions

**Skill response:**

---
This project has a license (MIT — permissive, low risk) but no formal contribution documentation. That's common for smaller or newer projects. It doesn't mean contributions aren't welcome — it just means there's no written process to follow.

**What this means practically:**

There are no documented requirements, so there's also nothing to violate. But a few things will help your contribution land well:

1. **Open an issue before you write any code.** Describe the bug: what you expected to happen, what actually happened, and how to reproduce it. This does two things: confirms the maintainer considers it a bug, and lets them tell you if they're already working on it.

2. **Look at recent merged PRs.** This shows you the informal conventions — how people write commit messages, how long PR descriptions usually are, whether tests are expected.

3. **Keep your first contribution small and focused.** A bug fix that does exactly one thing is much easier to review and accept than a bug fix that also reorganizes some code while it's at it.

**On the missing SECURITY.md:**
If you found a security vulnerability (not just a regular bug), don't open a public issue. Try GitHub's private reporting feature or contact the maintainer via their GitHub profile directly.

**Action checklist:**
- [ ] Open an issue describing the bug first
- [ ] Wait for the maintainer to confirm before building the fix
- [ ] Keep the PR narrowly scoped to the bug
- [ ] Write a clear PR description: what was broken, what you changed, how you tested it
---

---

## Example 3: License Concern — No LICENSE File

**User says:** *"I want to add a feature to this tool I use every day. It has 800 stars but I don't see a license file anywhere."*

**What the skill finds:**
- LICENSE: missing
- CONTRIBUTING.md: missing
- README: exists, no license mention
- Active project with recent commits

**Skill response:**

---
**There is no LICENSE file in this repository.**

This is worth understanding before you invest time in a contribution.

Under copyright law in most countries, when someone creates software, it is automatically "all rights reserved" — even if they put it on GitHub. A public repository is not the same as an open-source repository. Without a license, you don't have an explicit legal right to use, modify, or contribute to the code.

**What this means for you:**

Contributing to an unlicensed repository puts you in an ambiguous position. Your contribution would have no defined legal status. The maintainer could, in theory, change their mind about permissions at any time.

**What to do before contributing:**

Open an issue and ask the maintainer to add a license. Most people haven't thought about it and will add one quickly. A suggested message:

> "I love this tool and would like to contribute. Would you consider adding an open-source license? choosealicense.com makes it straightforward — for a project like this, MIT would probably make sense. Without a license, it's legally unclear what rights contributors have."

**Wait for a license to be added before opening any PR.** The time you'd invest in a contribution is not worth the legal ambiguity.

**Open questions:**
- Does the maintainer intend for this to be open source?
- Is this intentionally unlicensed, or just an oversight?

**Action checklist:**
- [ ] Open an issue asking the maintainer to add a license
- [ ] Wait for a license to be added
- [ ] Then proceed with your feature contribution
---

---

## Example 4: CLA Required — Enterprise Project

**User says:** *"I want to contribute to Kubernetes. I've never done this before. Where do I start?"*

**What the skill finds:**
- LICENSE: Apache 2.0 ✓
- CONTRIBUTING.md: extensive, references CLA requirement ✓
- CLA bot: active on PRs
- DCO: also required
- SECURITY.md: formal disclosure process ✓

**Skill response:**

---
**Important: You need to sign a CLA before your PR can be merged.** This is the first thing to sort out.

**What is a CLA?**
A Contributor License Agreement is a legal document you sign confirming you have the right to contribute the code and you're granting the Kubernetes project permission to use it. Kubernetes uses one managed by the Linux Foundation.

**Individual vs. Corporate CLA:**
- If you're contributing personal code written on your own time: sign the individual CLA at [link in CONTRIBUTING.md]
- If you're contributing code written at work or using work tools: your *employer* may need to sign a corporate CLA in addition to you signing the individual one. This is common for Kubernetes. Check with your employer's legal team — this can take a few days to a few weeks, so plan ahead.

**What is DCO?**
Kubernetes also requires DCO (Developer Certificate of Origin) sign-off on every commit. This is simpler than the CLA — you just add `-s` to your git commit command:
```
git commit -s -m "Your commit message"
```
This automatically adds: `Signed-off-by: Your Name <you@example.com>`
Make sure your git name and email are correct first: `git config user.name` and `git config user.email`.

**On security:**
Kubernetes uses a formal security disclosure process. Don't report security issues as public GitHub issues — the SECURITY.md has the right process.

**For a first contribution to Kubernetes specifically:**
Kubernetes is a large, complex project with extensive contribution requirements. Start with the Kubernetes contribution guide at https://www.kubernetes.dev/docs/guide/. Look for issues labeled `good first issue`. The community has a mentorship program for new contributors.

**Action checklist:**
- [ ] Sign the individual CLA (link in CONTRIBUTING.md)
- [ ] Confirm whether your employer needs to sign a corporate CLA
- [ ] Set your git name and email
- [ ] Add `-s` to all commits going forward
- [ ] Find a `good first issue` before attempting anything complex
---

---

## Example 5: Ambiguous License Terms

**User says:** *"I want to contribute to this project but the LICENSE says 'for educational use only.' Is that an open-source license?"*

**What the skill finds:**
- LICENSE: custom text, "for educational use only, commercial use prohibited"
- CONTRIBUTING.md: exists, covers code style
- No CLA or DCO

**Skill response:**

---
**This is not an open-source license.**

Open source licenses, as defined by the Open Source Initiative (OSI), grant you the right to use the software for any purpose — including commercial use. A license that says "commercial use prohibited" does not meet that definition.

**What this means:**
The project's code has a custom restrictive license. Contributing to it means your contribution would be under those same restrictive terms. Whether that's acceptable depends on what you plan to do with your contribution.

**Practical implications:**
- If you want to use this project or your contribution in commercial work, this license may prevent that
- If you're contributing code from your employer, your employer's legal team would likely view this as contributing to a proprietary-licensed project, not an open-source one

**What to do:**
Before contributing, ask the maintainer directly:
> "The LICENSE file restricts commercial use. Could you clarify what terms contributions will be under? I want to understand before I invest time in a PR."

If the maintainer can't or won't clarify, or if the terms are not compatible with your situation, this may not be the right project to contribute to.

**This is not legal advice.** If the license terms matter to you commercially or professionally, consult a qualified attorney.

**Action checklist:**
- [ ] Ask the maintainer for clarification on the license terms before contributing
- [ ] Do not assume "educational" restrictions won't affect you
- [ ] If you need certainty, consult a lawyer before proceeding
---

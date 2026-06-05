# Decision Tree

A structured decision flow for common contribution scenarios. Work through each branch in order. Plain-English explanations are included for every term.

---

## Branch 1: Does the repository have a license?

A `LICENSE` file is what makes software legally open source. Without it, the code is "all rights reserved" by default — even if it's publicly visible on GitHub.

```
Does the repo have a LICENSE file?
│
├── NO
│   → This is a significant issue. Tell the user:
│     "This repository has no LICENSE file. Under copyright law in most
│     countries, that means the code is 'all rights reserved' by default —
│     even though it's public on GitHub. You don't automatically have the
│     legal right to use, modify, or contribute to it.
│
│     The practical advice: open an issue and ask the maintainer to add a
│     license. Point them to choosealicense.com — it takes about 2 minutes.
│     Most maintainers simply haven't thought about it. Don't contribute
│     until a license is in place."
│
└── YES → What type of license?
          │
          ├── Permissive (MIT, Apache 2.0, BSD, ISC)
          │   → Low risk. Tell the user:
          │     "This project uses [license name] — a permissive license.
          │     That means you can use and modify the code freely, and your
          │     contribution will be under the same terms. No special
          │     employer check needed unless your company has specific
          │     open-source policies."
          │
          ├── Copyleft (GPL v2, GPL v3, AGPL, EUPL, LGPL)
          │   → Requires more care. Tell the user:
          │     "This project uses [license name] — a copyleft license. This
          │     means your contribution will also be under the same copyleft
          │     terms. In plain terms: the code must stay open source.
          │
          │     If you wrote this code at work, check whether your employer
          │     has policies about contributing to copyleft-licensed projects.
          │     Some do. If you're unsure, ask HR or your manager — it usually
          │     takes one email to get a yes."
          │
          ├── Dual license or unusual license
          │   → State the specific terms found. Tell the user:
          │     "This project uses [description of license]. I've noted what
          │     it says, but given the non-standard terms, I'd recommend
          │     reading it yourself and contacting the maintainer if anything
          │     is unclear. For significant IP questions, consult a lawyer —
          │     this is not legal advice."
          │
          └── No LICENSE file but mentions a license in the README
              → The README mention is not a substitute for an actual license
                file. Treat this the same as "no license" and flag it.
```

---

## Branch 2: Is there a CONTRIBUTING.md?

`CONTRIBUTING.md` is the project's instructions for contributors. It's the most important file to read before opening a pull request.

A **pull request** (PR) is how you propose changes on GitHub. You make a copy of the project, make changes in your copy, then ask the maintainer to bring those changes in.

```
Does the repo have a CONTRIBUTING.md?
│
├── NO
│   → Tell the user:
│     "This project has no CONTRIBUTING.md. There's no formal documented
│     process for contributions. This might mean the project is early-stage,
│     or the maintainer is flexible about how contributions arrive.
│
│     Recommended approach:
│     1. Open an issue describing your proposed change before doing the work.
│        This lets the maintainer weigh in early.
│     2. Look at how recent merged pull requests were structured — that
│        gives you informal conventions to follow.
│     3. Keep your first contribution small."
│
└── YES → Read it carefully and follow it precisely.
          │
          ├── Branch naming convention specified? → Use it.
          ├── Tests required? → Write tests.
          ├── Specific commit message format? → Use it.
          │     (Look for references to "Conventional Commits" — a format
          │     like: feat: add login button, or fix: correct typo in README)
          ├── Issue required before PR? → Open one first.
          └── Things the maintainer doesn't want?
              → Note these explicitly for the user. These are hard stops.
```

---

## Branch 3: Is a CLA or DCO required?

**CLA (Contributor License Agreement):** A legal document you sign confirming you have the right to contribute the code. Required by some large projects, uncommon in small ones.

**DCO (Developer Certificate of Origin):** A lightweight alternative. You add `Signed-off-by: Your Name <email>` to each commit message by running `git commit -s`.

```
Does the repo require a CLA or DCO?
│
├── Check: CONTRIBUTING.md, README.md, any CLA bot activity on existing PRs
│
├── CLA required
│   ├── Individual CLA
│   │   → Tell the user: "You need to sign the CLA before your PR can be
│   │     merged. The link should be in CONTRIBUTING.md. A bot will check
│   │     this automatically when you open the PR. Sign it first to avoid
│   │     delays."
│   │
│   └── Corporate CLA mentioned
│       → Tell the user: "This project may require your employer to sign a
│         corporate CLA, not just you individually. This is common in
│         foundation-backed projects like those under the Cloud Native
│         Computing Foundation (CNCF) or Apache Software Foundation.
│         Check CONTRIBUTING.md for details, then contact your employer's
│         legal team. This can take days to weeks — plan ahead."
│
├── DCO required
│   → Tell the user: "This project requires a DCO sign-off on your commits.
│     This is simple: instead of `git commit -m 'your message'`, run
│     `git commit -s -m 'your message'`
│     That adds a line to your commit:
│     Signed-off-by: Your Name <you@example.com>
│     It's just a statement that you wrote the code and have the right to
│     contribute it. Make sure your git name and email are set correctly:
│     git config user.name 'Your Name'
│     git config user.email 'you@example.com'"
│
└── Neither found
    → Tell the user: "No CLA or DCO requirement was found in the docs.
      This is normal for most small and medium open-source projects.
      Note this as an observation, not a guarantee — if a CLA bot comments
      on your PR, follow its instructions."
```

---

## Branch 4: Is there a security disclosure process?

A security vulnerability is a bug that could let someone do something harmful — access data they shouldn't, crash a service, etc.

```
Does the repo have a SECURITY.md?
│
├── YES
│   → Summarize the disclosure process for the user.
│     Always remind them: "If you find a security issue while preparing
│     your contribution, report it via this process — not as a public
│     GitHub issue. Public issues are visible to everyone immediately,
│     including people who might exploit the vulnerability."
│
└── NO
    → Tell the user: "This project has no SECURITY.md — no documented
      process for reporting security issues.
      If you find a security vulnerability:
      - Look for GitHub's private vulnerability reporting at:
        github.com/[owner]/[repo]/security/advisories/new
      - Or contact the maintainer directly via their GitHub profile.
      Do not post it as a public issue."
```

---

## Branch 5: Is there a PR template?

A PR template is a pre-filled form that appears when you open a pull request. It guides you through what information the maintainer needs.

```
Does the repo have .github/PULL_REQUEST_TEMPLATE.md?
│
├── YES
│   → List the required sections for the user.
│     Tell them: "Fill out each section in the template completely.
│     Leaving sections blank or writing 'N/A' everywhere signals you
│     didn't take the time. The template exists because the maintainer
│     needs that information to review your change."
│
└── NO
    → Tell the user: "No PR template found. In your PR description, include:
      - What you changed and why
      - How you tested the change
      - The issue number it addresses (if any): write 'Fixes #42'
      Keep it short and specific — one paragraph is usually enough."
```

---

## Branch 6: How confident are you in your conclusions?

```
For every conclusion you draw, ask: is this based on repo evidence or assumption?
│
├── Based on repo docs → State it clearly. Quote or paraphrase the source.
│
├── General best practice, not in this repo's docs
│   → Label it explicitly: "General OSS practice (not stated in this repo)"
│
└── Unknown / ambiguous / docs conflict
    → Put it in "Open questions."
      Tell the user: "I couldn't verify this from the available documentation.
      The safe move is to ask the maintainer directly before assuming."
```

---

## Branch 7: Employer / IP question

```
Did the user write this code at work or using work resources?
│
├── Yes, or unclear
│   → Raise this once: "If this code was written as part of your employment —
│     on work time or using work tools — your employer may have rights to it
│     depending on your employment agreement. This is worth confirming before
│     contributing. It usually takes one email to HR or your manager.
│     This is not legal advice."
│
└── Clearly personal time, personal project, no work connection
    → No action needed unless the repo's CLA specifically addresses
      employer-assigned contributions.
```

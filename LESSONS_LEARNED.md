# Lessons Learned — OSS Contribution Guardian

Project-specific lessons from building this skill.

---

## 2026-06-05 / 2026-06-06 — Initial Build

| Category | Lesson | Action Taken | Applied To |
|----------|--------|--------------|------------|
| Skill design | Active > passive: Cursor should do things, not tell the user to do things alone. "I'll scan your project" beats "run this command yourself." | Rewrote skill throughout to be active | `skill/SKILL.md` |
| Documentation | Beginner-first documentation requires many more iterations than expected. README needed 5+ commits before it was truly beginner-friendly. | Budget more review rounds for public-facing docs | README, all docs |
| Terminology | Every technical term must be explained inline on first use. Assuming the reader knows "pull request", "fork", "commit" breaks the experience immediately. | Added inline definitions throughout | All skill files |
| Phase ordering | "Who is your intended user" must come before the safety scan. You need to know who you're writing for before you write anything. Earlier versions had this backwards. | Reordered publishing phases | `skill/SKILL.md`, `checklists.md`, guide |
| Git identity | User's git `user.email` must match their GitHub account email for commits to link to their GitHub profile. Work email ≠ GitHub email for many users. | Configured correctly; documented in usage-examples | `docs/usage-examples.md` |
| Sandbox permissions | `git config` and certain git operations require `required_permissions: ["all"]` in the Cursor sandbox. This wasn't obvious. | Added to standard git workflow | `docs/publishing-your-own-work.md` |
| Structure | "Intended user" question shapes everything downstream. A vague audience = a README nobody can follow. | Made it Phase 2 of the publishing guide, before any writing starts | All publishing docs |
| Skill safety | Explaining WHY a skill is safe to install (plain text, no executable code, can't act without permission) matters as much as the safety itself. | Added "Is it safe to install?" section to README | `README.md` |
| Contribution encouragement | Pointing new users at this skill's own repo as their first contribution is a genuinely useful onramp. Low stakes, purpose-built docs project. | Added "practice here first" in Quick Start and top of prompts.md | `README.md`, `skill/prompts.md` |
| Alignment | After iterative edits across many files, SKILL.md and the guide can drift out of sync on phase ordering. Need explicit alignment audit. | Ran audit; fixed 5 misalignments | `skill/SKILL.md`, `skill/checklists.md`, `skill/prompts.md` |

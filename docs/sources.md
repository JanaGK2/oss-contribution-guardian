# Sources and References

This skill is grounded in publicly available, authoritative open-source guidance. No proprietary content has been reproduced. Summaries are written in original wording; links point to upstream sources.

---

## Authoritative Sources

These are the primary knowledge base for this skill's guidance.

### GitHub Open Source Guides
**URL:** https://opensource.guide/
**Why included:** The most widely referenced, community-maintained guide for open-source contributors and maintainers. Covers contribution etiquette, governance, legal basics, and community health.

**Specific guides used:**
- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/) — contribution workflow, finding projects, opening PRs, maintainer expectations
- [The Legal Side of Open Source](https://opensource.guide/legal/) — license types, CLA context, IP basics, employer considerations
- [Building Welcoming Communities](https://opensource.guide/building-community/) — code of conduct norms

### GitHub Docs: Community Standards
**URL:** https://docs.github.com/en/communities
**Why included:** GitHub's own documentation on `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, issue templates, PR templates, and `SECURITY.md`. Directly describes what GitHub surfaces in its "Community Standards" checklist for repositories.

### OpenSSF Best Practices Badge
**URL:** https://bestpractices.coreinfrastructure.org/
**Why included:** The Open Source Security Foundation's criteria for project health. Used as a reference for what constitutes a "mature" OSS project versus an early-stage one. Helps calibrate what absence of governance docs means.

### Developer Certificate of Origin (DCO)
**URL:** https://developercertificate.org/
**Why included:** The authoritative specification for DCO sign-off. Referenced when checking whether a project requires `Signed-off-by` on commits.

### SPDX License List
**URL:** https://spdx.org/licenses/
**Why included:** Canonical list of OSI-approved open-source licenses with SPDX identifiers. Used as the reference for identifying license types found in repositories.

---

## Practical Sources

These supplement the authoritative sources with contributor-facing guidance.

### GitHub Blog: New to Open Source
**URL:** https://github.blog/open-source/new-to-open-source-heres-everything-you-need-to-get-started/
**Why included:** Practical first-contribution guidance from GitHub. Good source for tone and etiquette recommendations.

### REUSE Specification
**URL:** https://reuse.software/spec/
**Why included:** REUSE provides a structured standard for license and copyright declarations in files. Referenced when advising on how to handle files with missing or ambiguous copyright notices.

### Contributor Covenant
**URL:** https://www.contributor-covenant.org/
**Why included:** The most widely adopted open-source Code of Conduct template. Referenced when `CODE_OF_CONDUCT.md` exists in a repo using this standard.

---

## What Is Not Included

- Specific legal interpretations of license compatibility (this is out of scope — consult a lawyer)
- Proprietary or employer-specific contribution policies
- Platform-specific CI/CD or automation tooling
- Guidance specific to any single programming language ecosystem

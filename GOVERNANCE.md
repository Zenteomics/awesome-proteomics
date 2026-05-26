# Governance

This document describes how **awesome-proteomics** is maintained, how decisions are made, and how the taxonomy evolves over time. It is the public-facing governance reference for the project.

For contribution guidelines (formats, checklists, quality bar), see [CONTRIBUTING.md](./CONTRIBUTING.md). For section champion expectations, see [SECTION_CHAMPION_GUIDE.md](./SECTION_CHAMPION_GUIDE.md). This project follows the [awesome-list guidelines](https://github.com/sindresorhus/awesome/blob/main/awesome.md), and formatting decisions reflect those conventions.

---

## Project Roles

### Maintainer

The maintainer has final authority on all editorial and structural decisions. Responsibilities include:

- Reviewing and merging pull requests
- Managing the taxonomy (sections, merges, splits)
- Enforcing the Code of Conduct
- Publishing Zenodo DOI snapshots
- Maintaining CI workflows and the maintenance scorecard
- Recruiting and onboarding section champions

The maintainer is currently [Enes K. Ergin](https://github.com/eneskemalergin) (Zenteomics).

#### Maintainer Succession

If the maintainer becomes inactive for **6 consecutive months** (no PR reviews, no commits, no Discussion responses), the following process applies:

1. The most active section champion opens a Discussion thread titled "Maintainer succession" to confirm inactivity and signal intent to step in.
2. After 30 days with no maintainer response, the champion with the longest active tenure assumes maintainer responsibilities. If no champion is active, any contributor with 10+ accepted PRs may volunteer.
3. The new maintainer updates this document and the README footer to reflect the transition.

Because the project is CC0 1.0 licensed, any community member may fork the repository at any time. This succession process exists to preserve continuity for the canonical repo, not to restrict reuse.

### Section Champions

Section champions are community members who take ownership of one or more sections of the list. They review PRs in their section, keep entries current, and help identify gaps.

**Minimum commitment:** review PRs in your section within 2 weeks, contribute 3 new entries per quarter, and respond when tagged. Champions are **not publicly listed as section leads until they have been active for 3 months.** This prevents dead names from appearing on a new repo and avoids giving the impression of abandoned sections.

When a champion leaves or is removed for inactivity, their section reverts to maintainer-managed status. If the section has high volume, the maintainer should add a "Seeking Champion" note in the relevant GitHub Discussion and actively recruit a replacement.

Full details on credit, probation, and removal are in [SECTION_CHAMPION_GUIDE.md](./SECTION_CHAMPION_GUIDE.md).

### Contributors

Anyone who submits a PR, opens an issue, or participates in Discussions is a contributor. All contributors appear in GitHub's contributor graph. Major contributors (10+ accepted entries or a published guide) are listed as co-authors on the Zenodo DOI record.

---

## Decision-Making

### Editorial Authority

The maintainer has final editorial authority on all content decisions. This includes entry inclusion/removal, guide publication, taxonomy changes, and tag usage.

When the maintainer makes a contested decision, the rationale must be documented publicly (in the PR, issue, or Discussion thread). Transparency is non-negotiable, even when the decision is.

**Scope limits:** The maintainer may not unilaterally change the project license or restructure the taxonomy by merging or splitting 3 or more sections at once. These changes require a Discussion thread with at least 7 days for community input before merging.

### Consensus-First Approach

For non-urgent decisions, the maintainer seeks input from section champions and active contributors before acting. GitHub Discussions is the primary venue for open-ended questions. Issues are for structured proposals.

The goal is rough consensus, not unanimous agreement. When consensus cannot be reached, the maintainer decides and documents why.

---

## Taxonomy Management

### Minimum Viable Taxonomy (MVT)

The list launches with 14 consolidated sections. Sparse subfields are grouped under umbrella headings rather than given empty standalone sections. A fully filled 14-section list looks credible; a patchy 20-section list looks abandoned.

### The 30/10 Rule

The trigger mechanism for splitting a consolidated section:

1. A consolidated section exceeds **30 total entries**.
2. Its largest sub-section contains **10+ entries**.
3. When both conditions are met, evaluate splitting that sub-section into its own top-level section.

Anyone can invoke the 30/10 Rule by opening an issue with the current entry counts. The maintainer reviews and approves or defers the split.

**Example:** "Quantitative Proteomics" consolidates DIA and Targeted. When DIA alone reaches 10+ entries and the total section exceeds 30, DIA becomes its own section.

### Merging Sections

The reverse also applies. If a standalone section drops below **5 meaningful entries** after pruning, consider merging it back into a related section. Sections should not exist to look comprehensive; they should exist because they contain enough quality content to be useful.

### Cross-Reference Disputes

Each tool has one primary entry with the full description. Other sections get a terse cross-reference (see [CONTRIBUTING.md](./CONTRIBUTING.md) for the format). When contributors disagree on which section is primary for a multi-category tool, the maintainer decides based on the tool's most common use case in published literature and documents the reasoning in the PR.

### Annual Taxonomy Review

Once a year (targeting January), the maintainer reviews the full taxonomy:

- Have new subfields emerged that warrant a section? (e.g., nanopore proteomics)
- Have existing sections grown disproportionately?
- Are any sections stale or redundant?
- Does the MVT still reflect how the field is organized?

The review is documented in a GitHub Discussion and any resulting changes go through the normal PR process.

---

## Entry Lifecycle

Every entry in the list moves through a lifecycle:

- **Active:** Tool is maintained, link works, resource is current. Standard listing.
- **Stale:** Tool has not been updated in 2+ years but still works and has users. Remains listed without special marking unless a successor exists.
- **Superseded:** A widely adopted successor exists *and* the original tool's author has stopped development or explicitly recommends the alternative. Moved to the "Deprecated / Legacy" section with a tool obituary (see [CONTRIBUTING.md](./CONTRIBUTING.md) for the obituary format).
- **Dead:** Link broken, repo deleted, or resource gone. Removed on the next maintenance pass. CI catches most of these automatically.

The distinction between Stale and Superseded matters. A tool that has not been updated but still has active users and no clear replacement (e.g., a stable command-line converter) stays listed. A tool whose author has publicly archived the repo and pointed users to a successor gets an obituary.

### Licensing Change Policy

When a previously free tool becomes commercial:

- Update its entry with a `[now commercial]` tag.
- Keep it listed as long as a free tier or meaningful trial exists.
- Remove only if the tool becomes fully paywalled with no free access.
- Document the change in the "Recently Added" changelog.

### Version Tag Policy

The maintainer will reject PRs that add routine version numbers to entries. Version annotations like `[v4.0+]` are accepted **only when a specific version transition matters**: algorithm overhaul, license change, breaking API change, or a fundamental shift in capabilities. Routine version numbers rot quickly and create maintenance burden. Pin specific versions in workflow snippets where reproducibility matters.

---

## Maintenance Scorecard

The maintenance scorecard is a markdown table in the repo that tracks the health of each section:

```markdown
| Section | Last Review | Entries | Stale Flagged |
| --- | --- | --- | --- |
| Discovery Proteomics | 2026-06 | 12 | 1 |
| Quantitative Proteomics | 2026-06 | 9 | 0 |
| Bioinformatics & Computational Tools | 2026-05 | 28 | 3 |
| ... | ... | ... | ... |
```

Updated monthly via script or manual pass. The scorecard is valuable precisely because it is honest about what has not been touched recently. Sections with stale dates are not a failure; they are a transparent signal.

A companion stale-entry report script uses GitHub API data to flag entries whose linked repos have not been updated, helping prioritize manual reviews.

---

## Maintenance Cadence

- **Weekly:** Review open PRs and issues. Keep response time short to encourage repeat contributors.
- **Monthly:** Scan for new tools from recent publications and conferences. Update the "Recently Added" changelog. Update the maintenance scorecard. Post a social update.
- **Quarterly:** Full link audit (in addition to CI catches). Prune dead or superseded entries. Review section balance.
- **Annually** (beginning after the community launch)**:** Major taxonomy review. Update [CONTRIBUTING.md](./CONTRIBUTING.md) with lessons learned. Publish the "State of Proteomics Tools" annual review on Zenodo.

---

## Guide Freshness Policy

Guides use a YAML `status` field in their frontmatter: `current`, `outdated`, or `superseded_by: guides/replacement.md`.

- A guide is marked **"Outdated"** after **18 months** without review.
- The "Last Reviewed" date in the frontmatter is the reference point. CI can flag guides approaching the 18-month threshold.
- Outdated guides are not removed. They remain in the directory with a visible banner so readers know the content may no longer reflect current best practices.
- Anyone can submit an update PR to refresh an outdated guide and reset the review date.
- If a guide is fully replaced by a newer one, set its status to `superseded_by` with a link to the replacement.

---

## Editorial Independence

### Commercial Tools

Inclusion of a commercial tool does not constitute endorsement. Descriptions state technical capabilities and supported formats only. Comparative claims and marketing language are not permitted in list entries.

Vendor employees may contribute, but must disclose their affiliation using the `[Vendor Contributed]` transparency header. All vendor-submitted entries undergo the same quality review as any other PR. The full commercial tool policy is in [CONTRIBUTING.md](./CONTRIBUTING.md).

### Community Notes

Community Notes are formalized footnotes on list entries, clearly separated from the description. They allow the community to add context, corrections, or caveats to any entry without modifying the original description.

**Format:**

```markdown
> **Community Note (YYYY-MM):** [Clarification or context]. See [discussion #N].
```

**Rules:**

- Added via PR, reviewed by the maintainer or a section champion.
- Non-removable by the entry's original contributor or affiliated vendor.
- Must reference a Discussion thread or issue for provenance.
- Should be factual and concise. Community Notes are not the place for opinions or reviews.
- When an entry accumulates **3 or more** Community Notes, the maintainer may consolidate them into a single summary note, preserving the original Discussion references.

### No Benchmarking Claims

List entry descriptions do not include comparative performance claims ("faster than X", "more accurate than Y"). Where a peer-reviewed or widely accepted benchmarking study exists, a benchmark link is appended to the entry. The community handles subjective comparisons in GitHub Discussions.

---

## Conflict Resolution

### Guide Disagreements

When two experts disagree on recommendations in a guide:

1. Attempt to resolve through Discussion or PR comments.
2. If agreement cannot be reached, **publish competing guides.** Both remain in the `guides/` directory with cross-references to each other.
3. Competing guides model scientific debate. They are a feature, not a failure.

The maintainer has final editorial authority on whether a guide meets quality standards, but does not arbitrate scientific disagreements by choosing one perspective over another.

### Entry Disputes

If a contributor disagrees with an entry's inclusion, removal, or description:

1. Open a Discussion thread explaining the concern.
2. Tag the section champion (if one exists) and the maintainer.
3. The maintainer makes a decision and documents the rationale in the thread.

### Code of Conduct Violations

For interpersonal conflicts or conduct concerns, follow the reporting process in [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md). Governance processes do not override the Code of Conduct.

---

## Discussion to PR Pipeline

GitHub Discussions is the informal space for tool recommendations, "what should I use for X?" questions, and community conversation. When a Discussion yields a clear, actionable tool recommendation:

1. Tag the Discussion with the **"Discussion to PR"** label.
2. The recommender (or any contributor) opens a PR adding the tool in the correct format.
3. The PR undergoes the same quality review as any other contribution. The Discussion thread serves as provenance.

This pipeline closes the loop between passive Q&A and active curation. It also gives Discussion participants a clear path to becoming contributors.

---

## Project Health and Transparency

### Project Health Summary

The README displays a one-line Project Health summary below the badges:

```markdown
Links Verified: [Date] | New Tools this Month: N | Stale Entries Pruned: N
```

This is updated monthly via the maintenance scorecard process.

### "Recently Added" Changelog

New entries are logged at the top of the README with dates:

```markdown
YYYY-MM-DD: [Tool Name](url) - One-line description.
```

This doubles as raw material for the RSS feed and social posts. It shows returning visitors that the list is actively maintained.

Entries remain in "Recently Added" for **3 months**, then are removed during the monthly maintenance pass. This keeps the section useful without letting it become a wall of old additions.

### Zenodo DOI

The repository is archived on Zenodo with a citable DOI. The archive is updated at major milestones. Beginning after the community launch, the annual "State of Proteomics Tools" review receives its own DOI version each year, with all contributors listed as co-authors.

---

## Graceful Staleness

This project is designed to remain useful even if active maintenance slows or stops. A solid snapshot with documented curation dates is more honest than a slowly rotting "living" document.

If the repository enters an extended quiet period:

- The "Last Verified" dates on each section tell visitors exactly how fresh the content is.
- The maintenance scorecard shows which sections have been reviewed recently and which have not.
- The CC0 1.0 license allows anyone to fork and continue the work without restriction.
- Guides marked "Outdated" remain accessible with clear banners.

The project does not need to be updated weekly to be valuable. It needs to be honest about when it was last updated.

---

## Amendments

This governance document can be updated via PR. Significant changes (role definitions, decision-making process, taxonomy rules, license) should be discussed in a GitHub Discussion with at least 7 days for community input before being merged.

Minor clarifications and formatting fixes can be merged directly by the maintainer.

---

*Maintained by [Zenteomics](https://github.com/zenteomics). Licensed under CC0 1.0 Universal (CC0-1.0).*

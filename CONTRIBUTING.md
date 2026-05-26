# Contributing to awesome-proteomics

Thank you for your interest in contributing! This guide covers everything you need to know, whether you're adding a single tool, writing a deep-dive guide, or submitting a practitioner workflow.

**Before contributing**, please read our [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to uphold it.

---

## Contribution Tracks

There are three ways to contribute, each with its own scope and review process:

| **Track** | **Effort** | **What you submit** | **Review process** |
| --- | --- | --- | --- |
| **List entry** | 5 minutes | A tool, resource, or paper link with a one-line description | Format check + quality review by maintainer or section champion |
| **Mini-guide** | 1–2 hours | A focused 500-word comparison or decision guide in `guides/` | One reviewer (maintainer or invited expert) |
| **Full guide or workflow** | Half a day+ | An opinionated deep-dive (≤1,500 words) or a step-by-step pipeline with code snippets | One reviewer + editorial check for tone and scope |

All contributions are submitted as **pull requests**. If you're new to GitHub PRs, see [GitHub's guide to creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).

---

## Adding a List Entry

### Entry format

Every entry follows the same canonical format:

```markdown
[Tool Name](https://example.com) - One-line description.
```

With optional metadata tags:

```markdown
[Tool Name](https://example.com) - One-line description. 💰
[Tool Name](https://example.com) - One-line description. 📦 ([benchmark](https://paper-url))
```

### Metadata tags

**Status tags** (all sections):

- 💰 → Commercial (requires paid license for core functionality)
- 📦 → Containerized (Docker/Singularity available)
- 🏭 → Production-grade / high-throughput
- 🧪 → Experimental / research-stage

**Capability tags** (Bioinformatics & tools-heavy sections only):

- Data type: `[TMT]` `[Label-Free]` `[DIA]` `[PTM]`
- Interface: `[CLI]` `[GUI]` `[API]`
- Platform: 🐧 🪟 🍎 (Linux / Windows / macOS). Use **only** when platform support is non-obvious or restricted

**Benchmark links**: where a peer-reviewed or widely accepted benchmarking study exists, append `([benchmark](url))`. Exclude preprint-only or single-author comparisons.

### How to write a one-line description

The description is the hardest part to get right. It should be **technical, factual, and concise,** answering *what the tool does*, not *how great it is*.

| ✅ **Good descriptions** | ❌ **Bad descriptions** |
| --- | --- |
| `Peptide identification engine using MSFragger's ultrafast database search.` | `The world's fastest and most accurate search engine for proteomics.` |
| `DIA quantification with library-free analysis and neural network scoring.` | `Industry-leading DIA software trusted by thousands of researchers.` |
| `Converts Thermo .raw files to mzML, mzXML, and MGF formats.` | `An amazing converter that makes your life easier.` |
| `Label-free quantification with match-between-runs and iBAQ.` | `A comprehensive proteomics platform for all your needs.` |

**Rules of thumb:**

- Start with what the tool *does*, not what it *is* ("Converts…" not "A converter that…")
- Name specific capabilities, formats, or algorithms
- No superlatives ("best", "fastest", "leading", "revolutionary")
- No marketing copy. If it reads like an ad, rewrite it.
- One sentence only. If you need two, the first one is your description.

### Choosing the right section

- Place each entry in the section matching its **primary use case**.
- If a tool spans multiple sections, list the full entry in the primary section and add a terse cross-reference in the other:

```markdown
*See also: [MaxQuant](#discovery-proteomics) (multi-purpose quantification suite)*
```

- Never duplicate the full description in multiple sections.

### Quality bar

We **do not** list:

- Abandoned repos with no documentation and no users
- Vaporware or tools that exist only as a preprint promise
- Low-effort forks of existing tools without meaningful changes
- Resources fully behind paywalls with no free tier (open-access is preferred; if a resource has partial access, note the restrictions)

---

## Adding Non-Tool Contributions

The awesome list is not just software. We welcome:

- **Papers and reviews:** landmark publications, systematic reviews, method comparisons
- **Tutorials and courses:** video series, online courses, workshop materials
- **Datasets:** benchmark datasets, reference proteomes, training data
- **Community channels:** Slack workspaces, Discord servers, mailing lists
- **Podcasts and conferences:** recurring events and media relevant to proteomics

The same format and quality bar apply. All non-tool entries should be genuinely useful to someone entering or working in the field.

---

## Commercial Tool Policy

Commercial tools are welcome; real labs use them, and excluding them would make the list dishonest. However:

1. **Mark with 💰** all commercial entries must carry the commercial tag.
2. **Technical descriptions only:** state capabilities and supported formats (e.g., "Supports TMTpro 18-plex quantification, DIA, and Thermo .raw input"). No comparative claims, no marketing language.
3. **Vendor employees must disclose:** if you work for or are affiliated with the tool's vendor, your PR must include the `[Vendor Contributed]` transparency header at the top of your PR description:

    ```txt
    [Vendor Contributed] I work at / am affiliated with [Company Name].
    ```

4. **Same quality review:** vendor-submitted entries undergo the exact same review as any other PR. Disclosure is about transparency, not penalty.
5. **No benchmarking claims:** do not include comparative performance claims in descriptions. Let the community handle "is it worth it?" in GitHub Discussions.
6. **Licensing changes:** if a free tool becomes commercial, update its entry with a `[now commercial]` tag. Remove only if fully paywalled with no free tier.

---

## Deprecated / Legacy Tool Contributions

We maintain a "Deprecated / Legacy" section documenting tools that have been superseded, abandoned, or are no longer recommended. If you've spent weeks debugging an unmaintained tool only to discover a modern alternative exists, this section is for you.

### Obituary format

```markdown
~~[Tool Name](url)~~ - Superseded by [Successor](url). Original contribution: X.
Reason for deprecation: Y. Last usable version: vN.N (YYYY).
```

Include:

- Why the tool mattered (its original contribution)
- Why it died or was superseded
- What to use instead
- The last known working version (researchers reproducing old results need this)

Community-submitted obituaries are encouraged. A simple PR with the information above is all it takes.

---

## Writing a Guide

Guides live in the `guides/` directory. They are **opinionated deep-dives,** not documentation, not literature reviews, not tutorials. A guide answers: "If I need to do X, what should I use and why?"

### Types of guides

- **Full guide** (≤1,500 words): decision-tree format. "If your sample size is n < 10, use X; if n > 100, use Y." Covers a topic with depth and judgment.
- **Mini-guide** (~500 words): a focused comparison or a quick-start recommendation. Lower barrier, great for first-time contributors.
- **Starter Pack** (1 page): a subtype of mini-guide. "If a PhD student starts tomorrow, what 3 tools do they need?" Scenario-based, immediately actionable.

If your guide exceeds 1,500 words, it's a paper, not a guide. Consider splitting it. Word limits are checked during review.

### Guide template

Every guide must include YAML frontmatter:

```yaml
---
title: "Your Guide Title"
author: "Your Name"
last_reviewed: "YYYY-MM-DD"
tags: [DIA, quantification, comparison]
status: current  # current | outdated | superseded_by: guides/replacement.md
---
```

### Guide proposal process

1. **Open an issue** with the topic, a short abstract, and a rough outline. This prevents duplicate work.
2. **Wait for approval,** the maintainer will confirm scope and fit.
3. **Write in a PR branch** using the template above.
4. **Review,** one reviewer checks for accuracy, clarity, and tone.
5. **Merge and announce,** the guide index and relevant README sections are updated.

### Editorial standards for guides

- **Distinguish facts from opinions.** Factual claims must be cited or reference a specific benchmarking study. Personal recommendations should be clearly framed as such: "In my experience…", "I recommend…"
- **Cross-link to list entries.** Every tool mentioned in a guide should link back to its entry in the README.
- **No vendor favoritism.** If you have a conflict of interest, disclose it in the frontmatter.
- **Competing guides are welcome.** When experts disagree, we publish both perspectives with cross-references. This models scientific debate.

Guides are marked "Outdated" after 18 months if not reviewed. Authors or new contributors can submit update PRs at any time.

---

## Writing a Workflow

Workflows live in `workflows/` and provide **start-to-finish pipelines** for common proteomics tasks.

### Workflow template

Each workflow should include:

- **Task description**: what experiment type and data this workflow handles
- **Step-by-step tool chain**: each step with links back to the tool's entry in the README
- **Input/output formats**: what format goes in, what comes out at each step
- **Code snippets**: Nextflow or Snakemake configuration for reproducibility
- **Alternatives**: at each step, note what else could be used and why you chose this path

A workflow without containerized or scripted steps is a suggestion, not a workflow.

---

## Cross-Reference Policy

To keep the list DRY (Don't Repeat Yourself):

- Each tool has **one primary entry** with the full description and tags.
- Other sections where the tool is relevant get a **terse cross-reference**:

    `*See also: [Tool](#section) (role in this context)*`

- **Bidirectional linking**: list entries link to relevant guides/workflows, and every guide/workflow links back to the specific list entries it mentions.

---

## Pull Request Checklist

Before submitting your PR, confirm:

### For list entries

- [ ]  Link is alive and points to the correct resource
- [ ]  The tool/resource has documentation (README, wiki, or user guide)
- [ ]  For software: the repo shows signs of maintenance or has an established user base
- [ ]  Entry is not already listed (checked cross-references too)
- [ ]  Description is one line, factual, and follows the format guide
- [ ]  Entry is in the correct section, alphabetically placed
- [ ]  Commercial tools marked with 💰
- [ ]  Vendor affiliation disclosed with `[Vendor Contributed]` header (if applicable)
- [ ]  CI passes (link check + awesome-lint)

### For guides and workflows

- [ ]  YAML frontmatter is complete (title, author, last_reviewed, tags, status)
- [ ]  Guide proposal was approved via issue (for full guides)
- [ ]  Word count is within limits (≤500 for mini-guides, ≤1,500 for full guides)
- [ ]  Facts are cited; opinions are clearly marked
- [ ]  Cross-links to relevant README entries are included
- [ ]  `guides/README.md` or `workflows/README.md` index is updated

### For deprecated tool obituaries

- [ ]  Follows the obituary format (successor, original contribution, reason, last version)
- [ ]  Successor tool is already listed in the main list (or included in the same PR)

---

## Use of AI-Assisted Tools

AI tools (LLMs, code assistants, grammar checkers) are **allowed** for drafting contributions. We're not against AI; it can be a genuinely useful writing aid. That said, this is a highly curated resource built to help researchers make better decisions. Every entry, description, and guide has been reviewed by someone who cares about getting it right. Unreviewed AI-generated text undermines that trust.

**The contributor is the final authority.** If you use AI assistance, we ask that you:

- **Verify every claim.** LLMs can hallucinate tool names, fabricate URLs, invent features, and confidently cite papers that don't exist. Please check every link and confirm every capability before submitting. A quick verification on your end saves reviewers from chasing down inaccuracies.
- **Rewrite in your own voice.** AI-generated prose tends toward an overly formal tone ("utilizes", "facilitates", "leverages") that doesn't match how scientists actually talk about tools. If a description reads like it was generated rather than written, reviewers will likely ask you to revise it.
- **Ensure technical accuracy.** AI tools don't know which version of a tool introduced a feature, whether a format is actually supported, or whether a workflow step produces the output you claim. Your domain expertise is what makes the contribution valuable.
- **Take full ownership.** When you open a PR, you're putting your name on it. Review it as if you wrote every word yourself, because as far as this project is concerned, you did.

Reviewers and maintainers volunteer their time to keep this resource reliable. A well-reviewed submission, whether AI-assisted or not, respects that time. A submission with unchecked hallucinations or copy-pasted AI output creates extra work for everyone involved.

AI is a drafting aid, not a contributor. The value of this list comes from expert human judgment: the kind of judgment that knows *why* Tool A is better than Tool B for a specific use case, not just that both exist.

---

## Spell-Check and Formatting

CI runs spell-check with a custom dictionary for scientific and tool-specific terms. If your contribution includes a term that the spell-checker doesn't recognize:

1. Check if it's a genuine scientific/tool term
2. If so, add it to the custom dictionary file via PR
3. The dictionary is published in the repo, anyone can expand it

All entries must pass `awesome-lint` formatting validation.

---

## Recognition and Credit

- **Section champions** are named in the README as section maintainers (after a 3-month active probation period). See [SECTION_CHAMPION_GUIDE.md](./SECTION_CHAMPION_GUIDE.md) for details.
- **Major contributors** (10+ accepted entries or a published guide) are listed as co-authors on the Zenodo DOI record. In academia, citations are the only currency that matters, we want contributors to get real credit.
- **Guide authors** receive full attribution in their guide's frontmatter and in the guides index.
- **All contributors** appear in GitHub's contributor graph.

---

## What We Value

We care about people who understand *why* these sections matter, who know that listing the right three tools is harder than listing thirty, and that a well-written tool obituary saves someone three weeks of frustration.

Quality over quantity. Judgment over aggregation. Honesty over completeness.

---

## Questions?

- **Informal questions**: open a thread in [GitHub Discussions](https://github.com/zenteomics/awesome-proteomics/discussions)
- **Contribution proposals**: open a GitHub Issue
- **Code of conduct concerns**: see [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)

*Inclusion of a tool or resource does not constitute endorsement. This list is maintained by [Zenteomics](https://github.com/zenteomics) and its contributors under the CC0 1.0 license.*

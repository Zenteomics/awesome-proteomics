# Section Champion Guide

First off: thank you for considering this. The fact that you are reading this guide means you care about a corner of the proteomics tool landscape enough to help keep it honest and useful. That matters more than any formal qualification.

Section champions are the people who keep awesome-proteomics alive. The maintainer handles project-wide structure, CI, and governance. Champions bring the deep, day-to-day expertise that makes individual sections genuinely useful to researchers. This guide walks through what the role looks like in practice, how to get started, and how the project supports you along the way.

For the broader governance model, see [GOVERNANCE.md](./GOVERNANCE.md). For contribution formats and quality standards, see [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## The Short Version

If you only remember five things:

1. **Review PRs in your section within 2 weeks.** A comment counts. You do not need to approve immediately.
2. **Add or update 3 entries per quarter.** About one per month. Cross-references and obituaries count.
3. **Respond when tagged.** Even "I will look at this next week" is enough.
4. **You are not publicly listed until 3 months in.** This protects everyone, you included.
5. **You can step down any time.** No guilt. Life changes. The role will still be here if you want to come back.

Everything below is context and detail around those five points.

---

## What Section Champions Actually Do

A section champion takes ownership of one or more sections of the awesome list. You are the person who knows your section best and cares about keeping it useful.

In practice, this means:

- **Reviewing PRs in your section.** When someone submits a new entry or updates an existing one in your area, you are the first reviewer. You check that the tool is real, the description is accurate, and the entry belongs in that section.
- **Keeping entries current.** You notice when a tool goes unmaintained, when a successor emerges, or when a description no longer reflects what the tool actually does. You submit PRs to fix these, or flag them for the maintainer.
- **Identifying gaps.** You know which important tools are missing from your section and can either add them yourself or open "Help Wanted" issues to invite contributions.
- **Reviewing Community Notes.** When someone submits a Community Note (a formalized footnote adding context or corrections to an entry), you review it alongside the maintainer. Community Notes are a key part of keeping entries honest. See [GOVERNANCE.md](./GOVERNANCE.md) for the full format.
- **Answering questions.** When someone asks "what tool should I use for X?" in GitHub Discussions and it falls in your area, you are well-positioned to help. These conversations often turn into new list entries through the Discussion-to-PR pipeline described in [GOVERNANCE.md](./GOVERNANCE.md).

You are not expected to be the sole contributor to your section. You are the person who makes sure it stays healthy.

---

## What We Ask Of You

These are the commitments that make the role work. They are designed to be sustainable for a working researcher, not to fill your calendar.

- **Review PRs within 2 weeks.** When a PR touches your section, respond with a review (approve, request changes, or comment) within 14 days. If you need more time, leave a comment so the contributor knows their PR has not been forgotten. A quick "looks good, will do a detailed review this weekend" goes a long way.
- **Contribute 3 new entries per quarter.** This can be new tools, updated descriptions, cross-references, or obituaries for deprecated tools. Three entries per quarter is roughly one per month. If you are actively using tools in your section, you will likely hit this without trying.
- **Respond when tagged.** When the maintainer or a contributor tags you in an issue, PR, or Discussion, reply within a reasonable timeframe. You do not need to have all the answers. Acknowledging the tag is what matters.

These are floors, not ceilings. Active champions often do more, but the project is built so that meeting these three commitments is enough to keep a section in good shape.

---

## How to Become a Section Champion

### Pre-launch recruitment

Before the community launch, the maintainer reaches out to researchers with deep expertise in specific areas. If you are invited:

1. Confirm which section(s) you want to champion.
2. Prepare at least 5 entries for your section to submit during the seeding phase.
3. Coordinate with the maintainer on the launch announcement. Pre-launch champions are co-authors of the launch thread.

### Post-launch volunteering

After launch, anyone can volunteer to champion a section:

1. Check whether the section already has an active champion. Look at the README or ask in GitHub Discussions.
2. Open an issue titled "Volunteer: Section Champion for [Section Name]" with a brief description of your background and why you are a good fit.
3. The maintainer reviews the request and, if approved, walks you through the section's current state and any known gaps.

You do not need to be a professor or a senior researcher. What matters is that you use the tools in that section regularly and can tell the difference between a genuinely useful resource and one that does not belong.

---

## Your First Three Months

New champions start with a **3-month warm-up period.** During this time:

- You have all the responsibilities and review privileges of a full champion.
- You are **not yet listed publicly** in the README as the section's champion.
- The maintainer checks in informally to see how things are going.

After 3 months of active participation (meeting the commitments above), the maintainer adds your name to the README as the section's champion.

The warm-up period exists to protect both the project and you. For the project: a name on the README with no activity behind it sends the wrong signal. For you: it gives you time to settle into the role without the pressure of being the public face of a section right away. Think of it as a trial run where the only thing being evaluated is whether the role fits your schedule and interests.

---

## Credit and Recognition

Championing a section is volunteer work, and the project makes sure that work is visible:

- **README attribution.** After the warm-up period, your name and GitHub handle appear next to your section in the README. Example: `## Quantitative Proteomics - *championed by [@username](https://github.com/username)*`
- **Zenodo co-authorship.** Champions who meet the major contributor threshold (10+ accepted entries or a published guide) are listed as co-authors on the Zenodo DOI record. This is a citable academic credit.
- **Guide authorship.** Champions are encouraged to write guides in their area of expertise. Guide authors receive full attribution in the frontmatter and the guides index.
- **Launch co-authorship.** Pre-launch champions are co-authors of the launch announcement thread.
- **GitHub contributor graph.** All your PRs and reviews show up in the standard GitHub contributor metrics.

---

## Championing Multiple Sections

You can champion more than one section if your expertise spans multiple areas. A few things to keep in mind:

- The commitments above apply to each section individually. Be realistic about your bandwidth before taking on a second section.
- If you find yourself consistently behind on one section, it is better to step down from one and do the other well than to stretch yourself thin across both.
- The maintainer may check in if your activity drops in one section while remaining strong in another.

---

## Working with the Maintainer

The maintainer and section champions collaborate, not compete. Here is how the relationship works in practice:

- **You are the domain expert.** The maintainer manages the project structure, CI, taxonomy, and governance. You know whether Tool X actually works on Bruker .d files or whether its documentation is misleading. Your judgment on domain-specific quality is trusted.
- **The maintainer has final editorial authority.** If you and the maintainer disagree on an entry's inclusion, the maintainer makes the final call and documents the reasoning. This should be rare, and it does not mean your input was not valued.
- **Taxonomy decisions are collaborative.** If your section is growing and you think it should be split, you are usually the first person to notice. The 30/10 Rule (see [GOVERNANCE.md](./GOVERNANCE.md)) gives you a concrete trigger: when your section exceeds 30 entries and a sub-group has 10+, open an issue and propose a split. The maintainer reviews and approves.
- **You can flag problems without fixing them.** If you spot a stale entry or a gap but do not have time to write the PR, open an issue and tag the maintainer. Flagging is valuable even without a fix.

---

## Working with Other Champions

If you and another champion both touch a tool that spans multiple sections (e.g., a quantification engine that also handles PTM analysis), talk to each other first. The cross-reference policy in [CONTRIBUTING.md](./CONTRIBUTING.md) determines where the primary entry lives, but figuring out which section is "primary" for a borderline tool works better as a conversation than a unilateral decision. If you cannot agree, the maintainer steps in.

---

## Your Section's Health

The project tracks a maintenance scorecard (see [GOVERNANCE.md](./GOVERNANCE.md)) that includes a "Last Review" date and stale entry count for each section. As a champion, you directly influence these numbers. A quarterly scan of your section naturally keeps the scorecard healthy, and an honest scorecard is better than a flattering one. If your section has stale entries, that is not a failure. Flagging them is the job.

---

## Stepping Down and Inactivity

Life changes. Research deadlines pile up, jobs shift, burnout is real. The project is designed to handle champion turnover gracefully, and stepping down is never a black mark.

### Stepping down voluntarily

If you know you can no longer meet the commitments:

1. Let the maintainer know (a quick message or issue is fine).
2. If you have any PRs mid-review, hand them off. A comment like "I am stepping down as champion; @maintainer, this PR needs a reviewer" is enough.
3. The maintainer updates the README and begins recruiting a replacement.

Voluntary step-downs are respected and appreciated. Giving notice is far better than going quiet, and you are always welcome to return later or contribute as a regular contributor.

### If things go quiet

If a champion stops meeting the commitments without notice, the project follows a gradual process designed to check in, not punish:

1. **Around 3 months of inactivity:** The maintainer reaches out privately (GitHub, email, whatever channel works) to see how things are going. No judgment. The goal is to understand whether you plan to continue, need a lighter load, or want to step down.
2. **Around 6 months of inactivity:** The maintainer sends a public ping via GitHub (issue or mention) noting that the role will be reassigned if there is no response within 30 days.
3. **Around 9 months with no response:** The role is reassigned. Your name is removed from the README, and the section reverts to maintainer-managed status until a new champion is found.

If the section has high volume, the maintainer posts a "Seeking Champion" note in GitHub Discussions and actively recruits a replacement.

These timelines are guidelines, not rigid deadlines. The maintainer uses judgment. Someone who posted "I will be offline for a few months, back in September" does not get a formal ping in month 6.

### Coming back

Former champions are welcome to volunteer again at any time. The standard process applies, including a new 3-month warm-up period. No grudges, no extra hoops.

---

## What a Typical Month Looks Like

A quick reference for the rhythm of the role:

- **When a PR arrives in your section:** Review it within 2 weeks. Check that the link works, the description is factual, the entry is not a duplicate, and it meets the quality bar in [CONTRIBUTING.md](./CONTRIBUTING.md). Approve, request changes, or comment.
- **When you discover a new tool:** Add it yourself via PR, or open an issue if you want to discuss placement first.
- **When a tool goes unmaintained:** Check whether it still has active users. If it has a clear successor, write an obituary and move it to the Deprecated / Legacy section. If it is just stale but still useful, leave it listed.
- **When someone asks a question in Discussions:** If it falls in your area, respond. If the conversation leads to a tool recommendation, that is a natural candidate for the Discussion-to-PR pipeline.
- **When a Community Note is submitted:** Review it for accuracy and tone. Community Notes should be factual and concise, not opinions or mini-reviews.
- **Once a quarter:** Scan your section for gaps, stale entries, and outdated descriptions. Submit a PR or open issues for anything that needs attention.
- **When the maintainer tags you:** Respond. Even "I will look at this next week" is helpful.

---

## A Note on Conduct

Section champions are visible community members, and that visibility comes with responsibility. You set the tone for how contributors experience your section. A welcoming, constructive review style encourages repeat contributions. A dismissive or gatekeeping style does not, no matter how technically correct.

Please review and follow the [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md). If you encounter a conduct concern during PR review or Discussions, you do not need to handle it alone. Escalate to the maintainer.

---

## Questions?

If anything in this guide is unclear or feels like it does not account for your situation, open a Discussion thread or reach out to the maintainer directly. The role is meant to be straightforward, and the project works best when champions feel supported, not managed.

---

*Maintained by [Zenteomics](https://github.com/zenteomics). Licensed under CC0 1.0 Universal (CC0-1.0).*

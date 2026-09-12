---
name: write-learning
description: Write, graduate, and review content for this engineering-organization playbook. Use whenever someone asks to write a learning, capture a journal entry, graduate a journal entry into a learning, distill imported material, record a decision, write a playbook, or review or improve any markdown in this repo. Also trigger on "what did we learn about", "write up", "capture this", "turn this into a learning", "review this entry", or when the user describes something the org tried and what happened. If it sounds like it could become an entry in this repo, use this skill.
---

# Writing Learnings

This skill enforces the content standards for this playbook. Read `README.md` for the
content model and `CLAUDE.md` for the hard rules. This skill is about how to write well
inside that model.

**The bar:** every learning should make an experienced engineering leader at another
company change something about how they run their team, or at least argue with it.

## The voice

**We sound like:** an engineering leader debriefing a peer over coffee. Specific, candid
about what went wrong, more interested in the mechanism than in looking smart.

**We do not sound like:** a management book, a LinkedIn post, a consultancy deck, or a
company handbook written by HR.

Use "we" for the org. Use "you" when addressing the reader directly in the lesson or
boundaries. Opinions are required. Hedging is not.

## Banned language

Automatic rewrite:

- "Best practices", "world-class", "high-performing" without a definition
- "Empower", "leverage", "unlock", "foster a culture of", "drive alignment"
- "At scale" without saying what scale
- "Learnings" as a noun in prose (the directory name is enough)
- "It's important to", "it's worth noting", "at the end of the day", "that being said"
- "We believe that": state the belief
- "Stakeholders" when you mean a specific role
- Any sentence that would survive unchanged in a different company's handbook

## Titles are claims

The title of a learning is a sentence a reasonable person could disagree with. It carries
the whole entry for someone skimming the index.

**Strong:**
- "Merging an RFC should be the approval, not a step after it"
- "Auto-closing stale pull requests removed more work than it lost"
- "Code owners by team beat code owners by person once you pass ten engineers"

**Weak:**
- "RFC process"
- "Our approach to pull requests"
- "Thoughts on ownership"

Journal entries get a plainer one-liner. They are not yet claims.

## The TL;DR

The first paragraph must let the reader stop there. Three things, in order:

1. The claim.
2. The evidence in one line, with a number if we have one.
3. The boundary in one line.

Never open with background, org history, or a definition. If the reader needs context,
that is what the Situation section is for.

**Good:** "Moving RFCs from the wiki into the repo as pull requests doubled the number of
reviewed proposals in two quarters. It worked because merge became the approval event.
It would not work for a team that does not already review code in pull requests."

**Bad:** "RFCs are a common way for engineering teams to make decisions. Over the years we
have experimented with several approaches to documenting proposals."

## Structure follows the reader's questions

The learning template maps to what a reader is actually wondering:

| Section                | Reader's question                                    | Weight |
| ---------------------- | ---------------------------------------------------- | ------ |
| Situation              | Is my situation like yours?                          | short  |
| What we tried          | What exactly did you do? Could I copy it?            | medium |
| What happened          | Did it work? How do you know?                        | medium |
| The lesson             | Why did it work? What is the mechanism?              | long   |
| How we apply it today  | What does it look like now?                          | short  |
| Boundaries             | When would this be wrong?                            | medium |
| Open questions         | What are you still unsure about?                     | short  |

"The lesson" is the longest section. If "What we tried" is the longest, the entry is a
process description wearing a learning's clothes. Cut or move the detail.

## Evidence and confidence

`confidence` measures evidence, not conviction.

| Value    | Requires                                                                    |
| -------- | --------------------------------------------------------------------------- |
| `hunch`  | We did it and it felt right. One anecdote, no measurement.                 |
| `tested` | We measured something before and after, or ran a survey, or saw a clear change in a specific metric. |
| `proven` | It survived at least a year, a team change, or a serious attempt to remove it. |

Rules:

- Numbers over adjectives. "Review time dropped" is a hunch. "Median time-to-first-review
  went from four days to one" is tested.
- Say what we cannot attribute. If three things changed at once, say so.
- Survey results are evidence. Include response count and the question asked.
- One anecdote is fine. Label it as one anecdote.
- When in doubt, pick the lower confidence.

## Boundaries are mandatory

Every learning states when it does not apply. At minimum, address org size and stage.
A learning without a boundary is advice, and advice is what we are trying not to write.

Useful prompts: What would have to be true for the opposite to be right? At what team size
did this start or stop working? What did we have already that made it possible?

## Anonymity while writing

The content comes from a real company that is never named. While writing:

- Describe tooling by kind, not brand, unless the brand is the point and is widely used
  (a CI provider is fine; a niche vendor that fingerprints the stack is not).
- Team names by function: "the platform team", "the team owning payments flows".
- Package scopes and org handles become `@company/*` and `our-org`.
- People become roles: "a staff engineer", "the mobile lead".
- Org size as a range, dates absolute.

Before finishing, run the scrub grep from `CLAUDE.local.md`. If that file is missing, stop
and ask for it.

## Formatting

- Short paragraphs. Break at the turn: when a sentence introduces a "but" or a shift, start
  a new paragraph.
- One idea per paragraph. One-sentence paragraphs are fine for emphasis.
- No em dashes. Use commas, periods, or a new sentence.
- Headings inside a section only when the section exceeds roughly six paragraphs, and then
  the heading must carry information: "Why merge-as-approval changed reviewer behavior",
  not "Analysis".
- Tables for comparisons of three or more things. Prose for two.
- Code blocks only for things that are literally code or config, and then generic.

## AI writing patterns to rewrite

- **Staccato fragments.** "No process. No owners. Chaos." Rewrite as a sentence.
- **Aphorisms.** "You can't improve what you don't measure." Say the specific thing.
- **Three-beat reveals.** "Not the tooling. Not the people. The incentives." Rewrite.
- **Parallel ad copy.** "Process tells you what. Culture tells you why." Rewrite.
- **Smug simplicity.** "That's it. That's the whole system." Explain or move on.
- **Front-loaded personality.** A candid opener, a clinical middle, a tidy close. Candor
  belongs in "What happened" and "Boundaries" most of all.
- **Balanced non-conclusions.** "There are trade-offs on both sides." Pick a side; that is
  what the confidence field is for.

## Journal or learning?

Write a **journal entry** when:
- The evidence is one event or one conversation.
- We are not yet sure what the claim is.
- We want to capture it in under ten minutes.

Write or graduate to a **learning** when:
- We can state a claim someone could disagree with.
- We can state at least one boundary.
- There is more than one data point, or one very strong one.

When graduating, list the journal entries in the learning's `journal:` field and fill
`graduated_to` on each of them. Merge freely; several journal entries often become one
learning.

## Decisions and playbooks

A **decision** records a choice at a point in time. It links to the learnings that informed
it in `informed_by`. It is never edited afterwards; reversals are new decisions.

A **playbook** operationalizes learnings into steps. It lists them in `derived_from`. If a
step has no learning behind it, ask whether the step is earned.

## The "would a peer change something?" test

Before finishing a learning, ask: would an engineering leader at a different company read
this and change a process, a policy, or an opinion? If not, the entry needs one of:

- A sharper claim.
- Evidence it currently lacks.
- A boundary that makes the claim precise enough to act on.
- An honest account of what went wrong.

If it still fails, it is a journal entry. Downgrade it without guilt.

## Non-negotiables

1. The title of a learning is a claim.
2. The TL;DR stands alone.
3. Every learning has a Boundaries section with content.
4. `confidence` is set by the evidence rules above, never higher.
5. Any "we did X" is traceable to source material in `.local/source-map.md`.
6. No company, product, vendor-fingerprint, or people identifiers. Scrub grep before done.
7. Markdown only. Imports are converted first and never committed.
8. Index tables in the directory README are updated in the same change.
9. When in doubt, go deeper on the mechanism and shorter on the description.

## Reviewing a draft

Run three passes and report findings by quoting the weak passage, saying why it is weak,
and rewriting it.

**Evidence pass**
- Does every claim in "What happened" have a source or a stated gap?
- Is `confidence` justified by the table above?
- Are numbers real, with units and timeframes?

**Editorial pass**
- Is the title a claim? Could someone disagree with it?
- Can the reader stop after the TL;DR?
- Is "The lesson" the longest section?
- Do Boundaries say when this is wrong?
- Banned language, AI patterns, em dashes, paragraph length.

**Safety pass**
- Scrub grep is clean.
- No individual is identifiable or assessed.
- No customer or product metrics.
- Directory README index updated. Journal `graduated_to` filled if applicable.

---
name: write-learning
description: Write, update, or review entries in this engineering-organization playbook. Use whenever someone asks to write up how we do something, document a process or practice, capture what we learned, add the why behind a practice, or review or improve any markdown in this repo. Also trigger on "write up", "document how we", "capture this", "add an entry", "review this entry", or when the user describes something the org does or tried. If it sounds like it could become an entry in this repo, use this skill.
---

# Writing Entries

Read `README.md` for the entry shape and `CLAUDE.md` for the hard rules. This skill is about
writing well inside them.

**The bar:** an engineering leader at another company could copy the practice from "What we
do", and would learn something from "Why" and "What we learned" that they could not get
from a generic handbook.

## Voice

An engineering leader debriefing a peer. Specific, candid about what went wrong, more
interested in the mechanism than in looking smart. Not a management book, a LinkedIn post,
or an HR handbook. Use "we" for the org. Have opinions.

## Banned language

Rewrite on sight: "best practices", "world-class", "high-performing" without a definition,
"empower", "leverage", "unlock", "foster a culture of", "drive alignment", "at scale" with
no number, "stakeholders" when you mean a role, "it's important to", "it's worth noting",
"at the end of the day", "we believe that". Also any sentence that would survive unchanged
in another company's handbook.

## The three sections

**What we do.** Present tense. Rules, automation, cadence, tooling by kind. A reader should
be able to copy it. If a rule has a number (days until stale, reviewers required), give the
number. This section is required.

**Why.** The problem this solved, what we did before, what we rejected. If the reasoning is
"it seemed sensible", say that in one line and move on. Do not invent rationale that is not
in the sources or from the user.

**What we learned.** Only when there is something real: a surprise, a thing we would change,
a boundary such as team size or stage where this stops working. One honest paragraph beats
three hedged ones. Omit the section rather than pad it.

## Evidence

Numbers over adjectives. "Review time dropped" is weak. "Median time to first review went
from four days to one" is strong. If three things changed at once, say the effect cannot be
attributed. Surveys are evidence; give the response count and the question. One anecdote is
fine when labeled as one.

## Anonymity while writing

Tooling by kind, teams by function, packages as `@company/*`, people as roles, org size as a
range. Run the scrub grep from `CLAUDE.local.md` before finishing. If that file is missing,
stop and ask for it.

## Formatting

Short paragraphs, one idea each. Break at the turn: a "but" or a shift starts a new
paragraph. No em dashes. Sub-headings only inside a long section, and then they carry
information ("Why merge became the approval", not "Details"). Tables for three or more
things compared. Code blocks only for literal config, made generic.

## AI patterns to rewrite

Staccato fragments ("No process. No owners. Chaos."). Aphorisms ("You can't improve what
you don't measure."). Three-beat reveals. Parallel ad copy ("Process tells you what. Culture
tells you why."). Smug simplicity ("That's it."). Balanced non-conclusions ("There are
trade-offs on both sides"); pick a side.

## Reviewing a draft

Quote the weak passage, say why, rewrite it. Check:

- "What we do" is concrete enough to copy and has its numbers.
- "Why" is sourced, not invented.
- "What we learned" is present only if real, and says when this would not apply.
- Banned language, AI patterns, em dashes, paragraph length.
- Scrub grep clean. No individual identifiable. No customer or product metrics.
- Area README index row added or updated.

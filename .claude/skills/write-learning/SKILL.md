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

## The line of an entry

Every entry is a case study of one solution: the need, what we built to meet it, what
worked, what could be improved, and why. Before drafting, write that line in four or five
plain sentences and check it with the user if the sources leave it open. Every paragraph
serves it. A verdict in the opening that the rest of the entry does not argue for breaks the
line; so does a section that tells a different story from the one before it.

Write lessons so they transfer. The reader is at another company and cannot use our history,
only what it taught us. State the lesson in general terms ("a limit on how long an
initiative may run does not hold when the time behind it is borrowed"), not as a record of
what we did ("we wrote a six-week rule and never enforced it").

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

**The first sentence** of an entry says why an engineering org needs this, before anything
describes it: the interruption, the ambiguity, or the cost that exists without it. A reader who
stops there knows the problem. The description follows from it.

**What we do.** Present tense. Rules, automation, cadence, tooling by kind. A reader should
be able to copy it. If a rule has a number (days until stale, reviewers required), give the
number. This section is required. When the practice is a document (a manifesto, a template,
a checklist), quote it, anonymized, and say how it is used. Do not describe its shape or
placement; a reader with the text in front of them can see both.

**Why.** The motive, at the length needed to align a reader on why this exists before they
copy it: the problem we had, what we did before when it matters, what we rejected. The full
history of how the practice came to be is not required. Keep the dated story to the turns
that changed the outcome and leave the rest in the private import. If the reasoning is "it
seemed sensible", say that in one line and move on. Do not invent rationale that is not in
the sources or from the user.

**What we learned.** Only when there is something real: what the practice achieved or failed
to achieve, a surprise, a thing we would change, a boundary such as team size or stage where
this stops working. When there is material for both, split it under "What worked" and "What
could be improved", and tie each shortfall to its cause in the design. Keep the tone of a
team improving its own solution, not of a verdict against it. Do not add closing advice the
user did not give. One honest paragraph beats three hedged ones. Omit the section rather
than pad it.

## Interview before inventing

The sources usually give the practice and rarely the motive or the result. Do not close that
gap with plausible reasoning. Draft "What we do" from the sources, list what they leave open,
then interview the user as the CTO who ran the process.

Ask in one message, at most five questions, each tied to a gap the entry cannot close without
an answer. Under each question, state the inference you would otherwise write, so the reply
can be "yes", a correction, or "we never knew". Cover, in this order:

1. The problem. What was going wrong before, and what made it worth fixing then.
2. What was rejected. The alternatives considered, and why not.
3. The result. What changed after, in numbers where they exist, and what did not change.
4. The boundary. What would make you drop this.

Skip questions the sources already answer, and never ask for facts you can look up. Write the
answers into "Why" and "What we learned" in the org's voice, and save the questions and
answers under `.local/imports/interviews/<date>-<slug>.md` so they are a source like any
other. If the answer to the result question is "we never measured it", the entry says so.

## Evidence

Numbers belong where a reader would copy them: rules, thresholds, cadences in "What we do".
In "Why" and "What we learned", prefer the general lesson to our scoreboard. Leave out
one-off examples (a specific tool bought and dropped, a single project's story), counts of
engineers or capacity at the time, poll and survey tallies, and per-quarter scores. Name the
kind of thing instead: "reducing test flakiness", not the percentages of one quarter. Keep a
number in those sections only when the lesson cannot be stated without it, and never
generalize into a claim the sources do not support. If three things changed at once, say the
effect cannot be attributed.

The private import keeps the detail. The entry keeps what transfers.

Dates and time spans only when they carry the point: how long an attempt sat before it
failed, how long a practice has survived, how quickly something was reused. A practice does
not need the month it started in the prose; `since` in the frontmatter holds that. When a date
does earn its place, write it absolute.

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

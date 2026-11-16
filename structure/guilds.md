---
title: Guilds
status: applied
since: 2024-12
tags: [guilds, developer-experience, ownership, planning, tech-debt]
---

# Guilds

Some engineering work cannot be tied to a product or business goal and is still required:
growing on a healthy architecture, improving observability and resilience before the errors
arrive, keeping the tooling fast. Tying an initiative to a product goal is always the better
route, and when that is not possible the work has no roadmap to sit on and no time set aside
for it. A guild is our answer without full-time people: a group of engineers with its own
roadmap, where anyone can volunteer, working in booked time away from their product team.

## What we do

One engineering guild covers developer experience, cross-cutting tooling and build
infrastructure, shared architectural standards, and any engineering initiative that is not
product work. It has a lead and two domain leads, one for frontend and one for backend.
There is no membership list. Any engineer can pick up an initiative.

The charter is short enough to quote:

> **Purpose.** Ensure that our daily work is delightful and frictionless.
>
> **Principles.**
> - Informed decisions. Before an initiative we ask the six questions below, and weigh the
>   impact on product timelines and team capacity.
> - Value time. Minimize waiting on non-productive things, direct (language server, CI) or
>   indirect (meetings, unnecessary decisions).
> - Tools mean nothing if not adopted.
> - Simplify. Make the right way the easy way.
> - Open. No label required to contribute. Expertise matters, but extra hands are never
>   turned away.
>
> **Success.** Define success criteria before starting an initiative. Example: improve the
> compilation time of a module by x%.

Six questions gate an initiative before it gets on the roadmap:

1. Why is it important to work on this now?
2. How does this fit into the org's future growth?
3. Is there a partial solution that can be achieved?
4. Once developed, do we have the capacity to support it?
5. Are we blocking any future development by not working on this?
6. Does this enable anyone to work more effectively?

Planning is quarterly and starts from problems, not from a list of projects. We poll the
engineers for what hurts, agree on three or four problems, and turn each into an objective
written in an engineer's voice: "I know for sure my build will pass because all checks
passed locally, which is faster." Initiatives then get a priority, an effort estimate, the
objective they serve, where they came from (poll rank, carry-over, brainstorm), and the names
of people who want to work on them.

Capacity is booked as guild weeks. An engineer leaves their product team for one or two full
working weeks and works only on a guild initiative, and the booking goes on a shared
calendar. Each booking is negotiated with the engineer's manager around product deadlines.
The guild lead is an engineering manager and does that negotiating.

The guild oversees the horizontal components that no product team owns, and tracks their
work on its board. It does not hold a monopoly on fixing them. An engineer blocked by one of
those components first decides whether they can do the fix themselves, and if so does it and
records it on the guild board.

Cadence:

| What | When |
| ---- | ---- |
| Guild sync: accomplishments, status, what to communicate outside | Monthly |
| Status of the major initiatives | Every two weeks |
| Written update from anyone on a guild week | Daily, async |
| Progress and learnings presented to all of engineering | At all-hands |
| Written conclusions per goal: what we accomplished, what we missed, what we learned | End of quarter |

Guild pull requests get two reviews: one from someone who knows the area and one from a
randomly picked engineer.

## Why

As engineers we know that certain investments are needed to sustain the company's growth,
even when no product goal asks for them and nothing has broken yet. Before guilds, those
investments ran on the goodwill of teams. Nothing in how we planned gave an engineer time
for them. Some of what goodwill produced turned out to be critical: a workflow engine, the
move to event-driven architecture, hot reloading in parts of the codebase. We needed a
structure that gave engineers that time on purpose.

Full-time dedicated people were not an option. Budget for them was never prioritized, and
our infrastructure was fully managed and ran unsupervised, so nothing forced the question.

So the guild borrows time. It has its own roadmap, engineers volunteer for the initiatives
they care about, and their managers release them for a week or two at a time.

We started with two guilds, frontend and backend, each with a lead, a named member list and
a sponsor engineering manager who negotiated engineers' time with their managers. After
five quarters we merged them into the one described above. Priorities did not run
separately: problems spanned frontend and backend, the backend guild had also become the
home of developer experience, and useful work kept coming from engineers who were on
neither member list.

## What we learned

### What worked

The guild was effective on short to mid-term initiatives with a clear scope and immediate
value: reducing test flakiness, paying down a counted list of design debt, shortening a
slow step in the development loop.

It was the place where we discussed standards and agreed what good meant for us, and where
guidelines for architecture, testing and contribution were written.

It was a place to experiment beyond the daily work: learn a new technology, drive a proof
of concept. The results were presented at all-hands, so what one engineer learned reached
the rest.

It also caught work nobody planned. A large share of the value came from improvements that
were on no roadmap, made by engineers who hit a problem and had a place to fix it. Planning
should leave room for that.

### What could be improved

Partial dedication remained the main issue. When a project could not be finished in the
time committed to it, it turned into a long-running one that spanned several quarters.
Missed goals were mostly a matter of bandwidth, not of the wrong goals. A limit on how long
an initiative may run does not hold when the time behind it is borrowed.

Some initiatives need full-time dedication to get out at all. Those were usually done
outside the guild, inside a team's scope, because that team needed the piece of work. The
guild is not where large or high-stakes changes get delivered.

Support was the third challenge: who is in charge of what the guild built once it is
running? A team organizes itself to support its systems, with a rotation and monitors. The
guild had no such dedication. Priorities conflicted, and support fell back on goodwill,
often from the same few people. Work with little technical appeal, security backlog above
all, had the same problem, because a volunteer structure runs on interest.

Guilds worked for our case. Some of what they carried was fundamental to the company's
growth, and that part would have moved faster with people fully dedicated to it.

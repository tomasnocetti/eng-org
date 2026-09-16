---
title: On-call rotation
status: applied
since: 2024-03
tags: [on-call, incidents, alerts, ownership, rituals]
---

# On-call rotation

Without one person absorbing production alerts and support requests for the week, every failure
interrupts whichever engineer happens to notice it, nobody is clearly responsible for it, and
the teams stop shipping. So one engineer at a time owns all of it for the whole org, assesses
impact, and hands each issue to the team that owns that part of the system. They triage and
route. They do not fix. Anyone senior can call an incident without them, and every critical
incident ends in a written post-mortem.

## What we do

The rotation is org-wide, not per team. Engineers rotate weekly in round-robin order. Each
engineer is secondary for a week and primary the week after, so nobody's first primary week is
their first week on call. Coverage is weekdays, business hours, in one reference timezone. There
is no weekend rotation. The schedule lives in the paging tool and everyone subscribes to its
calendar.

The primary's job is to triage and route. When an alert or escalation comes in, they assess
impact, set a priority, and hand off. Assess: register the issue, find its source in the error
tracker, and pick a priority. Triage: ping the team that owns that part of the system, per the
ownership map, and hand over whatever they found, such as session replays or logs. Handoff is
where the primary's responsibility ends. The owning team decides the real fix and the real
priority; the primary makes sure a ticket exists and that the handoff actually landed. On a P0
or P1 the primary also notifies the secondary and the team lead directly, helps fix, and makes
sure a post-mortem gets written.

The same triage path takes support escalations. Customer-facing teams raise issues through one
channel with a fixed set of categories, and the categories tell the on-call where to route
before they have read the details. Support triages its own bug reports first; the on-call is
pulled in only when support cannot tell what is wrong.

Severity runs P0 to P3, and the clock we enforce is the one on the level, not the on-call's
reaction time.

| Level | What it looks like | Response |
| ----- | ------------------ | -------- |
| P0 | A customer-facing service completely down; core infrastructure or sensitive data compromised in bulk | Everyone, immediately, at any hour |
| P1 | Key functionality broken for many users; a payment failure across customers; suspected unauthorised access to customer data or funds | Response team engaged within one hour |
| P2 | Contained and low impact: high-volume but harmless errors, a misconfiguration caught early | On-call assigned within one business day |
| P3 | Minor: failed logins above threshold, a typo, an edge case | On-call handles it and records it |

When unsure between two levels, pick the higher one. It is easy to stand a response down and
expensive to start one late. Known errors that are not actionable go on an allow-list in code so
they stop alerting at all.

The on-call is not the only way an incident starts. Anyone who thinks something has happened
tells a senior teammate immediately: their team lead, their manager, or the on-call engineer.
Any of those can call an incident, and speed matters more than tidiness. If it is clearly a
system issue, the on-call is the fastest route. A monitored security inbox is always a valid
report path, and the right one for outsiders, for anything involving your own manager, or when
you want a written record. Suspected security incidents are not discussed in open channels until
the response team has decided who should know.

The secondary shadows every P0 and P1, helps a first-time primary set priorities, and takes over
when the primary is out or overwhelmed. When the primary is deep in a P1, the secondary watches
the P2 and P3 queue.

Everyone else has duties too. When an issue is routed to your team, you own it: investigate,
post updates in the channel, open a ticket for follow-up work, and post what you found. In
business hours you are reachable for the on-calls.

The primary does no active feature work that week. Low-priority tickets fill the gaps, and lower
output is expected and said out loud. Taking leave while on rotation means finding your own
replacement first, usually by swapping weeks with someone.

Critical alerts, from health checks and payment exceptions to synthetic monitors, data-integrity
checks and performance thresholds, land in one channel where every alert should be worth looking
at. Error-tracker warnings land in another and get a quick assessment.

Every P0 and P1 gets a post-mortem within 15 business days, and so does anything that exposed a
weakness worth fixing. The template: executive summary, impact, root cause as description,
trigger, resolution and detection, action items typed as prevent, mitigate or process, what went
well, what went wrong, where we got lucky, and a timeline. Every action item has an owner and a
date. Anything with a security dimension also gets a record in the single company-wide incident
register, linked to the engineering write-up.

At the end of the rotation the primary gives the rest of engineering a five-minute story at the
all-hands, built from the on-call dashboard: the period, issues created and resolved, resolution
rate and median time to restore, whether the backlog grew, which team or category is piling up,
one or two issues that mattered with impact and fix, at least one pattern in the data, two or
three learnings, and one next step. Five or six slides, mostly dashboard screenshots. The
dashboard is the source of truth; the slides are highlights.

## Why

The rotation exists to keep teams working. Before it, a failure or a support request landed on
whoever noticed, and a chat channel of alerts and reports pulled engineers out of their sprint
at random. Customers and non-technical teams often found problems before engineering did. Nobody
owned an alert, alerts got lost and came back, and there was no playbook for when something
broke. One person absorbing all of that for a week, with a secondary as fallback, means the
other teams only hear about the issues that are actually theirs, already assessed.

Ownership was never the problem. Which team owned which part of the system was always clear, and
the ownership map made it a lookup. The enemy was noise. That is why the on-call's mandate stops
at handoff: an on-call who tries to fix everything drowns in low-priority errors from systems
they do not know, and the owning team, who could fix it in minutes, never hears. In review, the
head of engineering put it in one line: the process is all around proxying issues, not solving
them.

Noise also decided what we did not do. We deferred 24/7 coverage because routing and criticality
had to be fixed first: paging engineers around the clock on error-tracker noise would be
demoralizing, and nobody should wake at three in the morning because an insignificant query
failed twenty times. Off-hours P0 and P1 are handled by phoning the code owner. Weekends were
never covered, and never needed to be: the one operation that could not wait ran on a vendor's
platform detached from our system, and nothing critical moved on weekends. Fully managed
infrastructure meant infrastructure itself rarely needed anyone.

We tried per-team triage alongside the org-wide rotation and dropped it. With two to five
engineers per team, a rotation inside each team put everyone on call every few weeks and added
overhead without catching anything the org-wide primary was missing. We also considered a small
dedicated rotation for the most sensitive transactional systems and decided the same facts that
ruled out weekends ruled that out too.

The post-mortem rule is the one we hold hardest, because it is how a critical event turns into
prevention rather than a story. What happened, what worked, what did not, what we are changing.
Only the action items change the system, and actions without owners are the most common way a
good review produces nothing. The company-wide register exists because a regulator or a partner
may ask about a security incident later, and a departmental log is not where anyone will look.

## What we learned

Detection of the serious problems got faster. P0 and P1 issues are found by our own alerts now,
through synthetic monitoring, data-integrity checks and performance monitoring, rather than by a
customer. Teams stay in their sprint until an issue is confirmed to be theirs, and handoffs
happen.

We never got good at reducing noise, and it was the hardest part throughout. Browser-driven
errors from the web applications were the worst source, and automation and configuration only
smoothed the on-call's work around the noise rather than removing it. Diagnosing low-priority
issues stayed slow, and after a handoff the owning team often deferred the real fix, which is
their call to make but left the primary watching a queue that did not shrink.

Keeping engineers engaged in the rotation was the other constant effort. The all-hands story is
the main thing that kept the role visible rather than a chore: the on-call is the one person who
has seen the whole system's week, and the story is where that turns into something the org
learns from.

Before copying the shape, ask what your system really needs. Ours could run weekdays only, with
no infrastructure on-call and no dedicated rotation for sensitive systems, because of decisions
made elsewhere, not because on-call is easy. A system without those properties needs a different
rotation, not a copy of this one.

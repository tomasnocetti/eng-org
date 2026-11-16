# Engineer to Engineering Manager: transition playbook

Source document, anonymized. Written 2026-08 from the transitions we had run. Detail that
described a specific person has been removed; the sequence, question sets and failure kinds
are kept. See [Engineering managers](../engineering-managers.md) for how it is used.

This is the sequence a manager runs to take an engineer from "I want to be an EM" to "the
team is theirs". It does not duplicate the other documents:

| Document | Answers |
| -------- | ------- |
| [Position description](position-description.md) | What the role is, and what it is not |
| [Guidelines](guidelines.md) | How to operate as an EM once you are one |
| [Promotion policy](promotion-policy.md) | The bar for confirming the promotion |
| This playbook | The sequence to get someone there |

## Timeline at a glance

Calibration: about 3 months to functional ownership, about 12 months to a consolidated EM.

| Window | Phase | Core move |
| ------ | ----- | --------- |
| Day 0 | Intent + contract | They write the plan. You set cadence and role definition only. |
| Weeks 1-4 | Embed / diagnose | Context homework with a hard checkpoint. No authority transferred. |
| Weeks 4-8 | Rituals + process | Own the ceremonies and the quality process before owning people. |
| Weeks 8-12 | People + stakeholders | 1:1s with reports, then with the PM and peer EMs. |
| Week ~13 | Transition retro | Structured retro covering them, the process, and you. |
| Week ~14 | They write the role | A tracked deliverable that defines the role and its boundaries. |
| Month 6 | Quarterly ownership | They author their own quarterly focus items. |
| Months 6-12 | Calibration | Fixed-question feedback sessions, incident ownership, growth plans for their reports. |
| Month 12 | Competency map | Performance review outcome becomes the standing development contract. |

## Phase 0. Day zero: intent and contract

**Do not hand them a plan.** When the engineer declares the ambition, the first response is:
"Great. Now what's your plan?" Ownership of the path is the first test of the role.

- [ ] They produce a written plan: first steps, and a timeline
- [ ] You set the contract only: weekly 1:1 cadence, who is active vs. supporting, and
      define the role first
- [ ] Write the role and its boundaries down now. Start from the Boundaries section of the
      position description: not a tech lead role, not a coding role, not a solo role
- [ ] Define the boundary with adjacent teams explicitly, in writing
- [ ] Answer the ceiling question up front: what is above EM, what does Senior EM look like,
      what are they pursuing

This is the step most likely to be skipped. Role clarity left open at week zero comes back
in the retro, and boundary questions between teams can resurface more than a year later.

## Phase 1. Weeks 1-4: embed and diagnose

No authority transfers in this window. This deliberate delay is one of the things that works
best.

- [ ] Context homework assigned, with a hard checkpoint date about 3 weeks out
- [ ] What is the PM's role, and where are the boundaries with engineering
- [ ] What are the team dynamics, and what profiles are on the team
- [ ] What are this team's real tradeoffs
- [ ] They get into the conversations and bring ideas, visibly, without authority
- [ ] Understand the rationale behind existing decisions before proposing changes

## Phase 2. Weeks 4-8: rituals and process

Process before people. This is where credibility is built and where delegation starts.

- [ ] Own the ceremonies: standups (consider a sync/async mix), planning
- [ ] Introduce or reinforce a quality ritual: bug bash before significant releases
- [ ] RFC discipline. The single highest-leverage change: the team knows what is next even
      when the manager is absent
- [ ] SOPs for recurring operational work
- [ ] Responsibilities delegated progressively, not in one drop

## Phase 3. Weeks 8-12: people and stakeholders

- [ ] 1:1s with each report
- [ ] They articulate, in their own words, what a 1:1 is for: career path, feedback,
      multidisciplinary
- [ ] 1:1s with the PM
- [ ] 1:1s with peer EMs
- [ ] Stakeholder relationship written down as an explicit deliverable, with concrete
      mechanics: include them in the cross-functional conversations, keep the recurring 1:1,
      know what they are working on, flag ETA changes early, plan strategies together

**Start the PM 1:1s in week 1, not week 8.** Starting them late is a failure of the process,
not of the candidate.

## Phase 4. Week ~13: the transition retro

A structured session, not a check-in. It must cover the manager's own performance, or it
will not surface anything useful.

Question set:

1. What did we do well in the process? What could have been improved?
2. Were the expectations clear?
3. How was the transition from doing the work to managing it?
4. What are your strengths and weaknesses in the role so far?
5. What is still missing: on your side, on the team's side, and on mine?
6. What action items come out of this?

Outputs to expect and capture: where influence should replace imposition, where they need to
be included in strategic decisions, and any remaining ambiguity about what the role covers.

## Phase 5. Week ~14: they write the role

The most reusable move in the sequence. The first time, the retro surfaced a role-clarity
gap and the candidate answered it by publishing the [guidelines](guidelines.md) as a tracked
initiative, leaving a document the whole org still uses.

- [ ] A tracked deliverable, with an owner and a due date, not a side note
- [ ] Since the guidelines now exist, the equivalent is a contribution or revision to them,
      plus a written definition of their team's scope and boundaries

## Phase 6. Months 3-12: calibration

### Quarterly focus items, authored by them

A starting frame:

- Make the PM an ally, with named mechanics
- Build a critical eye for tech strategy, tied to business OKRs
- Plan ahead when things go wrong: step back, identify risks, communicate actively
- Keep a close eye on tech debt and code quality
- Keep every engineer on a growth path

### Recurring feedback sessions: fixed question set

Run this verbatim, repeatedly. Its value is in the repetition.

1. What are your priorities today?
2. What are the team's priorities today?
3. What are you doing to support those priorities?
4. How are you technically supporting the team?
5. Do you have enough context on what the team is doing, its challenges, and its timelines?

### Teach the diagnostic loop, not the answer

When something is off, this is the sequence to coach. The goal is that they learn what
questions to ask, not that you supply conclusions.

1. Step outside the team and look at it critically. Has it had release issues? Has it hit
   ETAs? What is product's perspective? Is the team even aware if these things are going
   badly?
2. Gather enough context to make the right calls
3. Inform product and stakeholders, even when it is bad news. Write the report
4. Drive action items from it

### Other calibration work in this window

- [ ] Incidents and post-mortems treated as a management competency: did the process exist,
      did the prevention loop close
- [ ] They produce growth plans for each of their reports using the
      [growth plan template](growth-plan-template.md)
- [ ] They run their reports' performance reviews
- [ ] They surface and propose promotions for their own people
- [ ] Push abstract goals into action-driven items at every quarterly boundary

## Watchlist

**Becoming the bottleneck is not a one-time lesson.** It appears in different costumes:
centralizing all team communication, covering for a blocked IC, absorbing the team's support
tickets. Watch for it continuously, not once.

- **Hands-on but off the critical path.** The hardest line to hold, and it moves. A new
  manager can be too hands-off one month and over-committed across several projects the next
- **Over-protecting the team.** Absorbing support tickets and interruptions to shield
  engineers reads as care and behaves as a bottleneck
- **Losing system context.** As they move up, the temptation is to stop reading the code.
  Credibility depends on staying close enough to make informed tradeoffs
- **Imposing instead of influencing.** Process changes the team does not see the value in
  will not survive
- **Urgency inflation.** They need to distinguish genuinely urgent from labelled-urgent, and
  push back on the difference
- **Burnout around months 8-9.** The window where new responsibilities and old IC instincts
  overlap most: too many projects, no time for tech debt, support, or PR review
- **Capacity squeeze on their own development.** A backlog of things they want to build that
  never survives incoming initiatives is a signal, not a complaint
- **The ceiling question.** "What's the roadmap for EMs? Senior EMs? What am I pursuing?"
  Have an answer

## Improvement areas that tend to come up

**First 6 months: the delegation shock**

- Overwhelmed by the first wave of delegation: "I cannot do everything at once"
- Risk of becoming a dependency for the team's existing workflows
- Pushing a process the team does not see the value in
- Managing priority and workload expectations with the PM
- Unclear how much technical involvement the role requires
- Pushing tech improvements without enough context, and without giving the team the language
  to explain the value to stakeholders
- Becoming the centralizer when a key IC is a blocker

**Months 6-12: depth and rigor**

- Post-mortem depth on failed projects: how long did it slip, what shipped broken, why
- How to get the team to share what they think, rather than agreeing in the room
- Goals too abstract, needing mapping to action-driven items
- Where the time is going, and whether the team is being supported if focus is elsewhere
- How to elevate the team's technical bar, and what the right level of autonomy is

**Year 2: the manager-level gaps**

- Not hands-on enough in the team's real challenges: you cannot prioritize what you are not
  part of
- When there is a concern, understand where it is coming from rather than agreeing or
  disagreeing with it
- Communication pattern: give context first, then propose the plan
- Handoff process from engineering to other engineers and to operations
- Setting clear KPIs and action items, specifically for growing senior engineers
- Delegating the work that only they know how to do
- Providing clear vision: what is next, and the reasoning behind it

## Required artifacts

A transition is complete when these exist, not when a date passes.

- [ ] Role definition and team boundaries (week 0)
- [ ] Their own written transition plan with a timeline (week 0)
- [ ] Context/diagnosis notes (week 3 checkpoint)
- [ ] Transition retro doc (week ~13)
- [ ] A contribution to the EM guidelines (week ~14)
- [ ] Quarterly focus items in their own words
- [ ] A time-off handoff doc: the real proof the team runs without them. Per-person
      ownership, critical processes, risk mitigation, and what stays on their plate
- [ ] A growth plan per report
- [ ] Performance review outcome as the standing competency map

## Readiness signals

Check them against the [promotion policy](promotion-policy.md) criteria.

- Team autonomy holds during their time off: planning happens, stakeholders stay informed
- Bug volume trends down, with high-priority bugs falling fastest
- Weeks pass with no alerts, and alerts that do fire are acted on
- RFC quality rises, and the team's language improves in demos
- They bring bad news to product before product asks
- They are producing growth plans and promotion proposals for their own people
- They push back on scope and timelines without escalation

## Expanding an existing EM to a second domain

Once someone is a proven EM, the same shape compresses to six weeks. This plan was written
and started but has not been run to completion.

| Week | Focus |
| ---- | ----- |
| 1 | **Rituals.** Join planning and standups, meet the engineers, learn the core business. Output: a written learnings block with domain priorities ranked, open questions, per-person strengths |
| 2 | **Operate.** Own the standup. Learn the domain entities. Build a dashboard to understand product engagement. Diagnose the team's process pain |
| 3 | **People.** 1:1s with each engineer: career paths, where they want to grow, how you help. Pull the product and tech-debt roadmap for the quarter and the year |
| 4 | **Technical strategy.** Tech debt plan, alerts inventory, performance bottlenecks, clean the board |
| 5 | **Growth plans per engineer, and handoff from the outgoing manager** |
| 6 | **Full ownership** |

Hand off domain by domain with named artifacts, not as a single event: each area with its
own open questions and its own gating conversation with the relevant stakeholder.

## Manager's own reminders

- Give clues, not solutions
- Ask the question rather than answering it, including "what is a 1:1 for?"
- The retro covers your performance too, and you must actually collect that feedback
- Feedback is weekly and immediate, not saved for 1:1s or reviews
- Being included in strategic decisions is part of their development, not a courtesy

# Engineering Organization Playbook

A living record of how we craft and run an engineering organization: what we have
applied, what we have learned, and what we have dropped along the way.

Everything here comes from building a real engineering org, from a handful of engineers to
multiple teams. Entries state what we actually did, why, and what happened. The
transferable lesson is separated from the specifics of our implementation so the content is
useful to anyone building a team, not just to us.

## How to navigate

| Directory       | What lives there                                                                 |
| --------------- | -------------------------------------------------------------------------------- |
| `principles/`   | Operating principles and values that shape everything else                       |
| `structure/`    | How the org is shaped: teams, ownership, roles, interfaces between teams          |
| `process/`      | How work flows: RFCs, pull requests, code review, releases, incidents             |
| `practices/`    | Engineering practices and tooling: monorepo, CI/CD, testing, AI-assisted work     |
| `people/`       | Hiring, onboarding, growth, feedback, rituals                                     |
| `decisions/`    | Dated log of org-level decisions, ADR style                                       |
| `learnings/`    | Retrospectives on the org itself: things we tried, kept, or dropped, and why      |
| `playbooks/`    | Step-by-step guides for recurring org activities                                  |
| `templates/`    | Templates for each kind of entry                                                  |
| `sources/`      | Public references that shaped our thinking: books, talks, other orgs' handbooks   |

## Entry format

Each entry is one markdown file with YAML frontmatter. The `status` field is the most
important one:

| Status     | Meaning                                                              |
| ---------- | -------------------------------------------------------------------- |
| `proposed` | We think this is a good idea but have not applied it yet             |
| `applied`  | In use today                                                         |
| `learned`  | Applied long enough to have a clear lesson, positive or negative     |
| `dropped`  | We tried it and stopped. The entry explains why                      |

See `templates/entry.md` for the full shape. Decisions, learnings, and playbooks have their
own templates in the same directory.

## Conventions

- Write in the first person plural. "We" is the engineering org.
- Describe what we did concretely enough to be reproduced, without naming the company,
  its products, or its people.
- Put the generalizable lesson in its own section so a reader can skip our specifics.
- Topic entries are named by topic (`process/rfcs.md`). Decisions and learnings are dated
  (`decisions/2026-04-09-rfcs-as-code.md`).
- Never include customer data, credentials, or individual performance assessments.

## Index

Populated as entries are added. Each directory README lists its own entries.

- [Principles](principles/README.md)
- [Structure](structure/README.md)
- [Process](process/README.md)
- [Practices](practices/README.md)
- [People](people/README.md)
- [Decisions](decisions/README.md)
- [Learnings](learnings/README.md)
- [Playbooks](playbooks/README.md)
- [Sources](sources/README.md)

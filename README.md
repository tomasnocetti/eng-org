# Engineering Organization Playbook

A living record of what we have learned crafting and running an engineering organization.

Everything here comes from building a real engineering org, from a handful of engineers to
multiple teams. The unit of content is a **learning**: a lesson stated as a claim, backed by
what we actually tried and what happened. Descriptions of process and tooling exist only to
support a lesson, never on their own.

## Content model

Content flows through three layers. Each layer is plain markdown.

```
 imports (private)  ->  journal/  ->  <area>/  ->  decisions/  playbooks/
 raw material          quick,        curated       dated         how-to,
 converted to md       dated         lessons,      records       derived from
                       captures      one claim     of choices    lessons
                                     each
```

| Layer         | Purpose                                                                   | Friction |
| ------------- | ------------------------------------------------------------------------- | -------- |
| Imports       | External material (docs, wiki pages, chat threads, PDFs) converted to markdown. Private, never committed. | none |
| `journal/`    | Dated, rough captures of a single learning while it is fresh. Can be a paragraph. | low  |
| Area learning | A curated learning under `principles/`, `structure/`, `process/`, `practices/`, or `people/`. Title is the lesson as a statement. | high |
| `decisions/`  | Dated ADR-style record of a choice, linked to the learnings that informed it. | medium |
| `playbooks/`  | Step-by-step how-to distilled from one or more learnings.                  | medium |

A journal entry graduates to an area learning when it has enough evidence to state a claim
and a boundary (when it does not apply). Several journal entries often merge into one
learning. The journal entry then links forward to it and stays put as history.

## How to navigate

| Directory       | What lives there                                                                 |
| --------------- | -------------------------------------------------------------------------------- |
| `journal/`      | Raw, dated learnings. Start here when capturing something new                    |
| `principles/`   | Learnings about the values and operating principles that shape everything else   |
| `structure/`    | Learnings about how the org is shaped: teams, ownership, roles, interfaces       |
| `process/`      | Learnings about how work flows: RFCs, pull requests, review, releases, incidents  |
| `practices/`    | Learnings about engineering practice and tooling: monorepo, CI/CD, testing, AI    |
| `people/`       | Learnings about hiring, onboarding, growth, feedback, rituals                     |
| `decisions/`    | Dated log of org-level decisions, ADR style                                       |
| `playbooks/`    | Step-by-step guides for recurring org activities                                  |
| `templates/`    | Templates for each kind of entry                                                  |
| `sources/`      | Public references that shaped our thinking: books, talks, other orgs' handbooks   |

## Anatomy of a learning

Every area learning follows `templates/learning.md`:

1. **Title** is the lesson as a claim. "RFCs belong next to the code they describe", not
   "RFC process".
2. **TL;DR** in one paragraph.
3. **Situation**: the context that made this matter, including org size and stage.
4. **What we tried**: the concrete thing we did, reproducible by someone else.
5. **What happened**: evidence. Numbers, survey results, incidents, anecdotes.
6. **The lesson**: the claim, expanded. This is the core of the entry.
7. **How we apply it today**: the current practice, briefly.
8. **Boundaries**: when this does not apply, or what would make us change our mind.
9. **Open questions**.
10. **References**: public material only.

Two frontmatter fields matter most:

| Field        | Values                          | Meaning                                                      |
| ------------ | ------------------------------- | ------------------------------------------------------------ |
| `confidence` | `hunch`, `tested`, `proven`     | How strong the evidence is. Be conservative                  |
| `status`     | `applied`, `evolving`, `dropped`| Whether we still do the thing the lesson describes           |

A `dropped` learning is as valuable as an `applied` one. The lesson is often sharper.

## Conventions

- Markdown everywhere. No PDFs, docx, or exported HTML in the repo. Convert on import.
- Write in the first person plural. "We" is the engineering org.
- Describe what we did concretely enough to be reproduced, without naming the company,
  its products, or its people.
- Area learnings are named by the lesson's short slug (`process/rfcs-live-with-the-code.md`).
  Journal entries and decisions are dated (`journal/2026-09-11-stale-prs.md`).
- Never include customer data, credentials, or individual performance assessments.

## Index

Each directory README lists its entries with confidence and status.

- [Journal](journal/README.md)
- [Principles](principles/README.md)
- [Structure](structure/README.md)
- [Process](process/README.md)
- [Practices](practices/README.md)
- [People](people/README.md)
- [Decisions](decisions/README.md)
- [Playbooks](playbooks/README.md)
- [Sources](sources/README.md)

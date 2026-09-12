# Engineering Organization Playbook

How we run an engineering organization: what we do, why we do it that way, and what we
learned along the way. Drawn from building a real engineering org from a handful of
engineers to multiple teams. The org is never named.

## Layout

| Directory     | What lives there                                                        |
| ------------- | ----------------------------------------------------------------------- |
| `principles/` | The values and operating principles that shape the rest                 |
| `structure/`  | Teams, ownership, roles, how teams interface                            |
| `process/`    | How work flows: RFCs, pull requests, review, releases, incidents        |
| `practices/`  | Engineering practice and tooling: monorepo, CI/CD, testing, AI-assisted |
| `people/`     | Hiring, onboarding, growth, feedback, rituals                           |
| `templates/`  | The entry template                                                      |

Each directory README indexes its entries.

## Entries

One markdown file per topic, named by the topic: `process/rfcs.md`,
`structure/code-ownership.md`. Every entry has the same shape (see `templates/entry.md`):

1. **What we do.** The practice, concrete enough to copy.
2. **Why.** The reasoning, and what we tried before if relevant.
3. **What we learned.** Optional. What surprised us, what we would change, when this
   would not apply.

Sections 2 and 3 grow over time. An entry can start as just "what we do" and gain the
why and the lessons later.

Frontmatter is minimal:

```yaml
---
title: Pull requests
status: applied     # applied | dropped
since: 2025-06      # optional
tags: []
---
```

`dropped` entries stay. They hold the "why" of what replaced them.

## Conventions

- Markdown only. Anything imported from elsewhere is converted first.
- First person plural. "We" is the engineering org.
- Concrete enough to reproduce, without naming the company, its products, its vendors,
  or its people.
- No customer data, credentials, or individual assessments.

## Index

- [Principles](principles/README.md)
- [Structure](structure/README.md)
- [Process](process/README.md)
- [Practices](practices/README.md)
- [People](people/README.md)

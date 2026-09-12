# CLAUDE.md

This repository is a knowledge base, not a codebase. It documents how we build and run an
engineering organization. Read `README.md` first for the directory map and entry format.

## Anonymity is a hard rule

The content is drawn from a real company, but the repository must never identify it.
Do not write the company name, product names, domain, GitHub organization, Slack channel
names, internal codenames, or the names of any employee. This applies to prose, frontmatter,
file names, commit messages, and code snippets. When quoting internal material, rewrite
identifiers to generic ones (`our monorepo`, `the platform team`, `#engineering`).

Before finishing any change, grep the working tree for the identifiers listed in
`CLAUDE.local.md` and fix every hit.

## Private context lives outside git

`CLAUDE.local.md` and the `.local/` directory are gitignored. They hold the company-specific
context: where the source material is checked out, which internal files feed which entries,
and the list of identifiers to scrub. If `CLAUDE.local.md` is missing, ask for it before
writing content entries; do not write from memory.

## Adding an entry

1. Pick the directory from the table in `README.md`. If it is a dated event, use
   `decisions/` or `learnings/`; otherwise it is a topic entry.
2. Copy the matching template from `templates/`.
3. Read the real source material listed in `.local/source-map.md`, then write.
4. Fill in frontmatter. `status` must be one of `proposed`, `applied`, `learned`, `dropped`.
5. Add a row to that directory's `README.md` index table.
6. Update the status column in `.local/source-map.md`.
7. Cross-link related entries with relative markdown links.

## Writing rules

- First person plural. Concrete over abstract. Say what we did, what happened, and what we
  would do differently.
- Put our specific implementation under `## What we did` and the transferable takeaway
  under `## Lesson`. A reader should be able to skip either.
- Dates are absolute (`2026-04-09`), never relative.
- Numbers and survey results are fine when they do not identify the company. Team size
  ranges and percentages are fine; revenue, customer counts, and product metrics are not.
- Prefer one entry per practice. Split when an entry grows past roughly 400 lines.
- Public references (books, talks, other companies' public handbooks) go in the entry's
  `references` frontmatter and in `sources/`.

## Never include

- Customer or business data.
- Credentials, environment files, certificates.
- Individual performance reviews or assessments of named or identifiable people.
- Incident detail that identifies customers or the company. Reduce incidents to the
  process lesson.

## Tooling

No build step. Markdown only. Align tables by hand or with your editor's formatter.

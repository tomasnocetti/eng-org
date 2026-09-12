# CLAUDE.md

This repository is a knowledge base, not a codebase. It records what we learned building
and running an engineering organization. Read `README.md` first for the content model.

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
context: where source material is checked out, which internal files feed which entries,
imported material converted to markdown, and the list of identifiers to scrub. If
`CLAUDE.local.md` is missing, ask for it before writing content; do not write from memory.

## Markdown only

Every committed file is `.md`. Anything fetched from elsewhere (wiki pages, chat threads,
PDFs, slides, docs) is converted to markdown first and stored privately under
`.local/imports/`, then distilled into journal entries or learnings. See
`.local/imports/README.md` for the conversion conventions. Never commit the import itself.

## The content model in one paragraph

Raw material becomes a **journal** entry (dated, rough, one learning). Journal entries with
enough evidence graduate into an **area learning** under `principles/`, `structure/`,
`process/`, `practices/`, or `people/`, titled as a claim and carrying a `confidence` and
`status`. **Decisions** record dated choices and link to the learnings that informed them.
**Playbooks** operationalize learnings into steps. Always start at the journal unless the
evidence is already strong enough for a learning.

## Adding content

1. Read the actual source material listed in `.local/source-map.md`. Do not write from
   memory.
2. Capture in `journal/YYYY-MM-DD-<slug>.md` using `templates/journal.md`. Add a row to
   `journal/README.md`.
3. When graduating: copy `templates/learning.md` into the area directory, name the file by
   the lesson's slug, write the title as a claim, set `confidence` conservatively, list the
   journal entries in `journal:`. Fill `graduated_to` on each of those journal entries.
   Add a row to the area README.
4. Update the status column in `.local/source-map.md`.
5. Cross-link with relative markdown links.

## Writing rules

- First person plural. Concrete over abstract. Claim, evidence, boundary.
- The title of a learning is a sentence someone could disagree with.
- `confidence` is about evidence, not conviction. One anecdote is a `hunch`. A change we
  measured is `tested`. Something that survived a year and a team change is `proven`.
- Dates are absolute (`2026-04-09`), never relative. Org size as a range, never exact.
- Numbers and survey results are fine when they do not identify the company. Team size
  ranges and percentages are fine; revenue, customer counts, and product metrics are not.
- Public references (books, talks, other companies' public handbooks) go in `references`
  frontmatter and in `sources/`.
- Split a learning when it makes two claims.

## Never include

- Customer or business data.
- Credentials, environment files, certificates.
- Individual performance reviews or assessments of named or identifiable people.
- Incident detail that identifies customers or the company. Reduce incidents to the
  process lesson.
- Binary or non-markdown files.

## Tooling

No build step. Markdown only. Align tables by hand or with your editor's formatter.

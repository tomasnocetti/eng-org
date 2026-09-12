# CLAUDE.md

This repository is a knowledge base, not a codebase. It documents how we run an engineering
organization. Read `README.md` for the layout and entry shape.

## Anonymity is a hard rule

The content is drawn from a real company that must never be identifiable. Do not write the
company name, product names, domain, GitHub organization, Slack channel names, internal
codenames, vendor names that fingerprint the stack, or the names of any employee. This
applies to prose, frontmatter, file names, and commit messages. Rewrite identifiers to
generic ones: `our monorepo`, `the platform team`, `@company/*`, `a staff engineer`.

Before finishing any change, run the scrub grep in `CLAUDE.local.md` and fix every hit.

## Private context lives outside git

`CLAUDE.local.md` and `.local/` are gitignored. They hold the source company, where its
material is checked out, which internal files feed which entries (`.local/source-map.md`),
imported material converted to markdown (`.local/imports/`), and the identifier scrub list.
If `CLAUDE.local.md` is missing, ask for it before writing content. Do not write from memory.

## Adding or updating an entry

1. Read the real source material listed in `.local/source-map.md`.
2. Copy `templates/entry.md` into the right area directory, named by topic.
3. Write "What we do" first. Add "Why" and "What we learned" when the sources or the user
   give you something real to say. Leave a section out rather than pad it.
4. Add or update the row in the area README index.
5. Update the status column in `.local/source-map.md`.
6. Run the scrub grep.

## Writing rules

- First person plural. Concrete over abstract.
- Describe tooling by kind unless the brand is the point and widely used.
- Describe the practice, not the artifact. Where a document lives, what it is linked from,
  how many sections or bullets it has, or what its headings are is never content. If the
  document itself is the practice, include it.
- Dates absolute. Team size as a range.
- Numbers are welcome when they do not identify the company. Percentages and team sizes
  are fine; revenue, customer counts, and product metrics are not.
- Markdown only. No binaries, no exports. Convert imports first (see `.local/imports/README.md`).

## Never include

Customer or business data. Credentials. Individual performance assessments. Incident
detail that identifies customers or the company.

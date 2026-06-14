# templates/ — one template per page type

Copy the matching template when creating a new wiki page. Frontmatter follows the schema in [`../CLAUDE.md`](../CLAUDE.md) → *Page conventions*. `{{title}}` and `{{date}}` are Obsidian Templates-plugin placeholders (they auto-fill if you wire up the plugin; otherwise replace by hand).

| Template | Use for | Lands in |
|---|---|---|
| [`concept.md`](concept.md) | a core idea | `wiki/concepts/` |
| [`principle.md`](principle.md) | a first principle | `wiki/principles/` |
| [`competency.md`](competency.md) | a role / skill | `wiki/competencies/` |
| [`framework.md`](framework.md) | a technique / method | `wiki/frameworks/` |
| [`case-study.md`](case-study.md) | a transformation / example | `wiki/case-studies/` |
| [`diagnostic.md`](diagnostic.md) | an assessment rubric | `wiki/diagnostics/` |
| [`source-summary.md`](source-summary.md) | an ingested source | `wiki/sources/` |
| [`synthesis.md`](synthesis.md) | a cross-cutting essay | `wiki/synthesis/` |
| [`entity-person.md`](entity-person.md) | a person | `wiki/entities/people/` |
| [`entity-book.md`](entity-book.md) | a book | `wiki/entities/books/` |
| [`entity-organization.md`](entity-organization.md) | an organization | `wiki/entities/organizations/` |
| [`overview.md`](overview.md) | the single overview page | `wiki/overview.md` |

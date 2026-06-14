# AGENTS.md

This repository is a **persistent knowledge base and AI coach for the Product Operating Model** (Marty Cagan / SVPG), built on the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

**The conventions live in [`CLAUDE.md`](CLAUDE.md). Read it fully before doing anything** — ingesting a source, answering a question, or maintaining the wiki. It is the single source of truth for any agent operating here (Claude, Codex, or otherwise); this file only redirects you there so the rules don't drift across two places.

In short:

- **You curate, the agent maintains.** Sources live in [`raw/`](raw/) and are immutable. Everything the agent writes lives in [`wiki/`](wiki/).
- **Coaching is the default interaction** — active, Socratic, assessment-driven, not lookup. See `CLAUDE.md` → *Coaching stance*.
- **Operations** are Ingest, Coach, and Lint. See `CLAUDE.md` → *Operations*.
- **Conventions** (frontmatter, kebab-case filenames, `[[wikilinks]]`, citations, page templates in [`templates/`](templates/)) are defined in `CLAUDE.md` → *Page conventions*.
- Keep [`index.md`](index.md) and [`log.md`](log.md) current.

If you change conventions, change them in `CLAUDE.md` and leave this pointer intact.

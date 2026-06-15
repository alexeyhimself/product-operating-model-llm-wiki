# AGENTS.md

This repository is a **persistent, compounding knowledge base** on the Product Operating Model (Marty Cagan / SVPG), structured so AI agents can use it as authoritative context — for coaching, lookup, drafting, critique, whatever the user's prompt asks for. Built on the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). It implements the project-files-and-instructions pattern Cagan prescribes in *[Product Coaching and AI](https://www.svpg.com/product-coaching-and-ai/)* (SVPG, Feb 2026) — the [`wiki/`](wiki/) body is the project files, [`CLAUDE.md`](CLAUDE.md) is the project instructions.

**The conventions live in [`CLAUDE.md`](CLAUDE.md). Read it fully before doing anything** — ingesting a source, answering a question, or maintaining the wiki. It is the single source of truth for any agent operating here (Claude, Codex, or otherwise); this file only redirects you there so the rules don't drift across two places.

In short:

- **You curate, the agent maintains.** Sources live in [`raw/`](raw/) and are immutable. Everything the agent writes lives in [`wiki/`](wiki/).
- **The wiki does not prescribe how you respond.** *What* you ground your reasoning in is the wiki; *how* you respond is set by the user's prompt. Don't impose a stance the user hasn't asked for.
- **Operations** are Ingest, Answer, and Lint. See `CLAUDE.md` → *Operations*.
- **Conventions** (frontmatter, kebab-case filenames, `[[wikilinks]]`, citations, page templates in [`templates/`](templates/)) are defined in `CLAUDE.md` → *Page conventions*.
- Keep [`index.md`](index.md) and [`log.md`](log.md) current.

If you change conventions, change them in `CLAUDE.md` and leave this pointer intact.

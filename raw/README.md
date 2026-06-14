# raw/ — source documents (immutable)

Your curated collection of sources on the Product Operating Model: Marty Cagan / SVPG articles, book excerpts, talk and podcast transcripts, plus your own field notes (1:1s, team observations, retro notes). **The coach reads from here but never edits these files.** This is your source of truth.

> **Privacy:** the contents of this folder are **gitignored** — your source files stay on your machine and are never published. What gets published is each source's *provenance*: the citation and link you provide at ingest, recorded in [`../wiki/sources/`](../wiki/sources/).

## Conventions

- One file per source. Prefer Markdown (the Obsidian Web Clipper is great for web articles).
- Name files `YYYY-MM-DD-short-slug.md` when a date matters (e.g. a dated article or your journal entry), otherwise `short-slug.md`.
- Put images and PDFs in [`raw/assets/`](assets/).
- Add a few lines of frontmatter if you can — `source_url`, `author`, `date`, `medium` (article / book-chapter / talk / podcast / field-note) — but it's optional; the coach will fill gaps on ingest.

## After you drop a source here

Tell the coach to **ingest** it (see [`../CLAUDE.md`](../CLAUDE.md) → Operations). One ingest typically: writes a summary page in [`../wiki/sources/`](../wiki/sources/), updates the relevant concept / principle / entity pages, refreshes [`../index.md`](../index.md), and appends an entry to [`../log.md`](../log.md).

## What does NOT go here

Anything the LLM writes — summaries, syntheses, concept pages, diagnostics — lives in [`../wiki/`](../wiki/), never here.

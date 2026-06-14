# LLM Wiki as a Product Operating Model PM Coach

A persistent, compounding knowledge base and **AI coach for the Product Operating Model** ([Marty Cagan](https://www.linkedin.com/in/cagan) / [Silicon Valley Product Group](https://www.svpg.com/)). Built on the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): you curate the sources and ask the questions; an LLM agent reads, summarizes, cross-references, and maintains the wiki — and coaches you against the model.

This repo is **open and community-maintained**. Clone it to use as your own PM coach, or help make it richer by contributing pages back via pull request (see [How to contribute](#how-to-contribute)). It started as structure-only — schema, taxonomy, templates — and grows as sources are ingested and synthesized into the [`wiki/`](wiki/).

## Use it as your PM coach

You don't need to add anything to get value — point an agent at the wiki and ask.

1. **Clone** this repo.
2. **Attach the folder** to Claude ([Cowork](https://claude.com/) / Claude Code). Read-only is fine for pure coaching — the coach reads and cites the wiki but won't change it.
3. **Set the frame** with a starter prompt. The repo's [`CLAUDE.md`](CLAUDE.md) already encodes the coaching stance, so a capable agent picks most of this up on its own — but kicking off explicitly helps:

   > *Act as my Product Operating Model coach using this folder. First read `CLAUDE.md` and follow its conventions and coaching stance. Coach me actively and Socratically: diagnose my situation against the model using `wiki/diagnostics/`, cite the relevant pages, and end with one concrete next step. My situation is: …*

4. **Ask a real question** about your team or org. The coach runs an assessment-driven session, places you on the relevant diagnostic, and gives you a next step.

## Grow & maintain it

To make the wiki richer — and the coach smarter — feed it. This needs **read-write** access (your own clone or fork):

1. Drop a source into [`raw/`](raw/) and say *"ingest this,"* **giving the citation/link** for it. The coach summarizes it into [`wiki/sources/`](wiki/sources/) (recording that provenance), updates the affected pages, refreshes [`index.md`](index.md), and logs it in [`log.md`](log.md).
2. Ask questions; when a session produces a new insight, let the coach **file it back** as a `synthesis/` or `case-study/` page so it compounds.
3. Periodically say *"lint the wiki"* to catch contradictions, stale claims, and orphan pages.
4. See [`backlog.md`](backlog.md) for suggested starter pages, and [`CLAUDE.md`](CLAUDE.md) for the full conventions.

## Layout

| Path | What |
|---|---|
| [`CLAUDE.md`](CLAUDE.md) | Canonical conventions + coaching stance (read first) |
| [`AGENTS.md`](AGENTS.md) | Pointer to `CLAUDE.md` for non-Claude agents |
| [`raw/`](raw/) | Sources you ingest — **local-only** (gitignored); provenance is published in `wiki/sources/` |
| [`wiki/`](wiki/) | Everything the LLM writes (concepts, principles, diagnostics, …) |
| [`templates/`](templates/) | One template per page type |
| [`index.md`](index.md) | Catalog of all pages |
| [`log.md`](log.md) | Chronological record of ingests, queries, lints |
| [`backlog.md`](backlog.md) | Suggested pages to create |

## How to contribute

Pull requests welcome — the goal is a living, community-maintained coach that gets better as more of the SVPG body of knowledge is captured. The most valuable contributions:

- **Sources, ingested.** Summarize a Cagan/SVPG article, talk, or book chapter into a [`wiki/sources/`](wiki/sources/) page (with its citation/link) and wire it into the concept/principle/diagnostic pages it touches.
- **New or sharper pages.** Concepts, principles, frameworks — and especially **diagnostics**, the rubrics the coach assesses against.
- **Corrections & connections.** Fix a misreading, add citations, link orphan pages.

Workflow:

1. **Fork** and create a branch.
2. **Follow [`CLAUDE.md`](CLAUDE.md):** copy the right [`template`](templates/), use kebab-case filenames, YAML frontmatter, and `[[wikilinks]]`, and cite sources — keeping the three voices distinct (**SVPG canon** vs **field note** vs **coach inference**).
3. *(Optional, easiest path)* Attach your fork to Claude read-write, drop your source in [`raw/`](raw/), say *"ingest this,"* and review the diff the coach produces.
4. **Update [`index.md`](index.md)** and append a one-line entry to [`log.md`](log.md).
5. **Open a PR** describing what you added and which pages it touches.

A fuller `CONTRIBUTING.md` checklist can follow as the project grows.

## Sources & copyright

The wiki holds **original summaries, synthesis, and commentary with citations** — never reproductions of Cagan/SVPG books or articles. The contents of [`raw/`](raw/) are **gitignored by default**: your source documents stay on your machine and are never published. What *is* published is each source's provenance — the [`wiki/sources/`](wiki/sources/) page records the citation and link you provide at ingest. In short, the wiki **cites and links** sources; it never reproduces them. Keep any quotes short. The original work — and the value — is the structured, cross-linked synthesis and the coach.

## How this repo was initiated

This scaffold was generated in a single agent session, not hand-built:

1. **Pattern.** Seeded from Andrej Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) — the idea of an LLM-maintained, compounding wiki that sits between you and your raw sources.
2. **Setup choices.** The agent asked three questions before building; the answers shaped the structure:

   | Question | Choice |
   |---|---|
   | How much to pre-fill the wiki vs. leave empty? | **Empty scaffold only** |
   | How should the AI coach behave when queried? | **Active coaching focus** (Socratic, assessment-driven) |
   | Which agent schema/config file drives conventions? | **Both `CLAUDE.md` + `AGENTS.md`** |

3. **Model.** Built with **Claude Opus 4.8** (max reasoning).

To reproduce or adapt for another domain: share [`llm-wiki.md`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) with your agent and change the three choices above.

## Credit

Knowledge domain: the work of Marty Cagan and the SVPG partners (*INSPIRED*, *EMPOWERED*, *TRANSFORMED*, *LOVED*). Wiki pattern: [Andrej Karpathy's LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

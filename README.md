# Product Operating Model — LLM Wiki

A persistent, compounding **knowledge base** on the Product Operating Model ([Marty Cagan](https://www.linkedin.com/in/cagan) / [Silicon Valley Product Group](https://www.svpg.com/)), structured so AI agents (Claude Code, Cowork, Codex CLI, etc.) can use it as authoritative context — for coaching, lookup, drafting, critique, or whatever you frame the session around. Built on the [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): you curate the sources; an LLM reads, integrates, and cross-references the wiki against the conventions in [`CLAUDE.md`](CLAUDE.md). The wiki itself is neutral reference — *what* the agent grounds its reasoning in is this wiki, *how* it responds is set by your prompt.

**Why this wiki exists.** Marty Cagan's [*Product Coaching and AI*](https://www.svpg.com/product-coaching-and-ai/) (SVPG, Feb 2026) argues that the lack of effective product coaching is "the primary obstacle" to PMs becoming strong at product, and prescribes a scalable answer: a foundation model configured with **project files + project instructions + your company's strategic context**, used as a personal product coach. This repo implements the first two layers — the [`wiki/`](wiki/) body is the project files; [`CLAUDE.md`](CLAUDE.md) is the project instructions. It is deliberately **org-agnostic**: the third layer, your company's own strategic context (its [strategic-context baseline](wiki/concepts/strategic-context.md)), lives in your *own* store and is supplied to the agent alongside this wiki — it is never kept here. See [`wiki/concepts/model-as-product-coach.md`](wiki/concepts/model-as-product-coach.md) for the concept page and [`wiki/sources/2026-02-04-cagan-product-coaching-and-ai.md`](wiki/sources/2026-02-04-cagan-product-coaching-and-ai.md) for provenance.

This repo is **open and community-maintained**. The easiest way to use it is one of the **product-coach plugins** — [for Claude Code / Cowork](https://github.com/alexeyhimself/product-operating-model-claude-plugin) or [for Codex CLI](https://github.com/alexeyhimself/product-operating-model-codex-plugin) — each of which bundles this wiki and keeps it in sync. Install the one that matches your agent, ask your questions, and the agent has the wiki as grounding without any clone or setup. To help make it richer, contribute pages back via pull request (see [How to contribute](#how-to-contribute)). It started as structure-only — schema, taxonomy, templates — and grows as sources are ingested and synthesized into the [`wiki/`](wiki/).

## Wiki state

_As of July 12, 2026._

| Item | Amount |
|---|---|
| Sources ingested | 181 |
| Concepts | 47 |
| Frameworks | 20 |
| People | 18 |
| Books | 17 |
| **Total wiki pages** | **355** |

## Use it with an AI agent

The recommended path is one of the **product-coach plugins**, which bundle this wiki. No clone, no folder attach, no `git pull` — the plugin stays in sync with `main` automatically (see [Plugin sync](#plugin-sync)), so what your agent reads is always fresh.

- **Claude:** [`alexeyhimself/product-operating-model-claude-plugin`](https://github.com/alexeyhimself/product-operating-model-claude-plugin)
- **Codex:** [`alexeyhimself/product-operating-model-codex-plugin`](https://github.com/alexeyhimself/product-operating-model-codex-plugin)

### 1. Install the plugin

Follow the install steps in the plugin repo README for your agent — [Claude](https://github.com/alexeyhimself/product-operating-model-claude-plugin) or [Codex](https://github.com/alexeyhimself/product-operating-model-codex-plugin). Either way, the wiki, [`CLAUDE.md`](CLAUDE.md) conventions, and templates all ship with it.

### 2. Ask a real question

Bring a real situation — your team, your role, a decision you're facing — not just a definition. Frame the session however you want (coaching, lookup, draft a strategy, critique a doc); the wiki gives the agent its grounding, your prompt gives it its stance. For a coaching session, this works as a starter prompt:

> *Act as my product coach, grounded in the Product Operating Model wiki bundled with this plugin. Ground every observation in the relevant pages, cite them, and end with one concrete next step. My situation is: …*

After the first session you can drop the preamble and just ask.

### Alternative: clone the repo directly

If you'd rather not use the plugin, you can still clone and attach the folder. This works but you have to manage updates yourself (`git pull`), and writes from a local clone will collide with future pulls — see [How to contribute](#how-to-contribute) before you change anything.

```bash
git clone https://github.com/alexeyhimself/product-operating-model-llm-wiki
cd product-operating-model-llm-wiki
```

**Claude Code (terminal):** run `claude` from inside the repo. [`CLAUDE.md`](CLAUDE.md) auto-loads as the agent's working instructions.

**[Cowork](https://claude.com/) (desktop app):** open Cowork → **New project** → attach this folder. Mark it **read-only** in the folder picker so the agent can read and cite pages but can't write to your clone. `CLAUDE.md` auto-loads as project instructions.

**Codex:** run `codex` from inside the repo. [`AGENTS.md`](AGENTS.md) auto-loads and points at [`CLAUDE.md`](CLAUDE.md), so the same conventions apply.

To stay up to date on the clone path, run `git pull` — the agent picks up new and updated pages automatically on the next session.

## Layout

| Path | What |
|---|---|
| [`CLAUDE.md`](CLAUDE.md) | Canonical wiki conventions (read first) |
| [`AGENTS.md`](AGENTS.md) | Pointer to `CLAUDE.md` for non-Claude agents |
| [`raw/`](raw/) | Sources you ingest — **local-only** (gitignored); provenance is published in `wiki/sources/` |
| [`wiki/`](wiki/) | Everything the LLM writes (concepts, principles, diagnostics, …) |
| [`templates/`](templates/) | One template per page type |
| [`index.md`](index.md) | Catalog of all pages |
| [`log.md`](log.md) | Chronological record of ingests, queries, lints |
| [`backlog.md`](backlog.md) | Suggested pages to create |

## How to contribute

Pull requests welcome — the goal is a living, community-maintained knowledge base that gets richer as more of the SVPG body of knowledge is captured. The bar is **quality**: an ingest touches 10–15 pages, and a careless one silently degrades everything downstream. The most valuable contributions:

- **Sources, ingested.** Summarize a Cagan/SVPG article, talk, or book chapter into a [`wiki/sources/`](wiki/sources/) page (with its citation/link) and wire it into the concept/principle/diagnostic pages it touches.
- **New or sharper pages.** Concepts, principles, frameworks — and especially **diagnostics**, the rubrics for assessing teams/orgs against the model.
- **Corrections & connections.** Fix a misreading, add citations, link orphan pages.

**Model recommendation.** For ingests, use at least **Claude Opus 4.7 with High reasoning effort**. The [`CLAUDE.md`](CLAUDE.md) conventions (root vs supporting source, canon-vs-synthesis voices, org-agnostic scope, wiki-wide integration) are subtle, and smaller/faster models tend to reproduce source text, mis-attribute claims, or silently overwrite contradictions.

Workflow:

1. **Fork** and create a branch.
2. **Follow [`CLAUDE.md`](CLAUDE.md):** copy the right [`template`](templates/), use kebab-case filenames, YAML frontmatter, and `[[wikilinks]]`, and cite sources — keeping the two voices distinct (**SVPG canon** vs **wiki synthesis**) and the wiki **org-agnostic** (no org-specific data).
3. **Ingest.** Attach your fork to Claude read-write, drop your source in [`raw/`](raw/), say *"ingest this,"* and review the diff the agent produces — carefully. Fix anything that violates [`CLAUDE.md`](CLAUDE.md) before committing.
4. **Update [`index.md`](index.md)** and append a one-line entry to [`log.md`](log.md).
5. **Open a PR** with a description that includes:
   - **Source added** — citation and public link.
   - **Model + reasoning effort used** — e.g. *Claude Opus 4.7, High reasoning effort*.
   - **What changed and why** — new pages, edits to existing pages, any contradictions with prior canon and how you resolved them.

A fuller `CONTRIBUTING.md` checklist can follow as the project grows.

## Plugin sync

Pushes to `main` trigger [`.github/workflows/notify-plugin.yml`](.github/workflows/notify-plugin.yml), which pings both product-coach plugin repos — [Claude](https://github.com/alexeyhimself/product-operating-model-claude-plugin) and [Codex](https://github.com/alexeyhimself/product-operating-model-codex-plugin) — to re-sync their bundled copies of the wiki. Requires a `PLUGIN_REPO_TOKEN` repository secret containing a fine-grained PAT with **Contents: Read and write** access to *both* `alexeyhimself/product-operating-model-claude-plugin` and `alexeyhimself/product-operating-model-codex-plugin`.

## Sources & copyright

The wiki holds **original summaries, synthesis, and commentary with citations** — never reproductions of Cagan/SVPG books or articles. The contents of [`raw/`](raw/) are **gitignored by default**: your source documents stay on your machine and are never published. What *is* published is each source's provenance — the [`wiki/sources/`](wiki/sources/) page records the citation and link you provide at ingest. In short, the wiki **cites and links** sources; it never reproduces them. Keep any quotes short. The original work — and the value — is the structured, cross-linked synthesis an agent can reason from.

## How this repo was initiated

This scaffold was generated in a single agent session, not hand-built:

1. **Pattern.** Seeded from Andrej Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) — the idea of an LLM-maintained, compounding wiki that sits between you and your raw sources.
2. **Setup choices.** The agent asked three questions before building; the answers shaped the structure:

   | Question | Choice |
   |---|---|
   | How much to pre-fill the wiki vs. leave empty? | **Empty scaffold only** |
   | How should the AI behave when queried? | **No prescription** — the wiki is reference only; the user's session prompt sets the stance (coaching, lookup, drafting, critique…) |
   | Which agent schema/config file drives conventions? | **Both `CLAUDE.md` + `AGENTS.md`** |

3. **Model.** Built with **Claude Opus 4.8** (max reasoning).

To reproduce or adapt for another domain: share [`llm-wiki.md`](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) with your agent and change the three choices above.

## Credit

Knowledge domain: the work of Marty Cagan and the SVPG partners (*INSPIRED*, *EMPOWERED*, *TRANSFORMED*, *LOVED*). Wiki pattern: [Andrej Karpathy's LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

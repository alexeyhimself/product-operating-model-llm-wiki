---
title: Model as Product Coach
type: concept
aliases: [model-as-coach, ai-product-coach, foundation-model-as-coach]
status: drafting
tags: [coaching, ai, learning, foundation-models, core-concept]
sources: ["[[2026-02-04-cagan-product-coaching-and-ai]]"]
related: ["[[product-coaching]]", "[[trust-over-control]]", "[[marty-cagan]]", "[[svpg]]", "[[overview]]"]
created: 2026-06-14
updated: 2026-06-14
---

# Model as Product Coach

> Using a foundation model (Claude, Gemini, GPT), configured with **project files + project instructions + your company's strategic context**, as a personal product coach. Articulated by [[marty-cagan|Cagan]] in [[2026-02-04-cagan-product-coaching-and-ai|Product Coaching and AI]] (Feb 2026) as SVPG's scalable answer to the shortage of effective human [[product-coaching]].

## Why it matters
**SVPG's official position shift after two decades.** The previous canon: your manager should coach you to learn the product model. The new canon: most managers can't or won't, so use a foundation model as your coach — Cagan considers it "at least as good as most managers" and infinitely more scalable. For product creators (PMs, designers, engineers), Cagan now believes the model is "good enough" to develop product sense and contribute at the level needed. The strong human coach remains preferred where available — particularly for product leaders navigating transformation politics.

## How it works — Cagan's prescription
Configure the model with three layers of context:

1. **Project files** — what the model should ground its reasoning in. Cagan's reference example: [svpg.com/examples](https://www.svpg.com/examples). **This wiki is one such project-files set** — the [`wiki/`](../) body is the knowledge.
2. **Project instructions** — how the model should behave with that knowledge. *Crucially*, instruct it to **prioritize the product operating model** (vs the project model). Foundation models otherwise "appear confused" because the product world holds many competing voices. **This wiki's [`CLAUDE.md`](../../CLAUDE.md) is the project instructions.**
3. **Your company's strategic context** — [[product-vision|vision]], [[product-strategy|strategy]], team topology, [[team-objectives|team objectives]]. Cagan: the model becomes genuinely useful when it knows your domain. Add this as a [`case-study`](../case-studies/) / field note.

Use it to develop product sense, learn your company / industry / users / metrics / constraints, prepare for decisions, and seek critique. **Question its outputs; look for critique and mistakes, not affirmation.** The model is non-deterministic — the same question can yield a different (and not necessarily better) answer tomorrow.

## What it replaces
A weekly 1:1 with a manager who doesn't have time, didn't grow up in the product model, or both. *And* expensive external coaching that most companies won't pay for. Cagan: an aspiring product creator "in San Francisco, or Sao Paulo, or Lagos, or anywhere else in the world with an internet connection and a connected device, now has 7×24 access to the advice and assistance of an experienced product coach, representing the aggregated learnings of some of the best minds in product."

## Anti-patterns
- **PM theater.** Using AI to *accelerate the project model* — aggregating feedback, generating roadmaps, writing PRDs or user stories — rather than to learn the product model. Cagan: "an agent — or your engineer or designer — could just as easily do this themselves." Future page: `[[product-management-theater]]`.
- **Blind acceptance.** Treating model output as canonical without questioning. The right stance is critique-seeking.
- **No strategic context.** Generic coaching with no anchoring to your company yields generic advice.
- **Wrong model framing.** Forgetting to instruct the model on which operating model — product vs project — you're trying to learn. Defaults are a fuzzy average.

## Where the human coach still wins
- **Product leaders during transformation.** People problems — relationships, power dynamics, [transformation politics](https://www.svpg.com/transformation-politics/), [building strategic context with stakeholders](https://www.svpg.com/coaching-strategic-context/). SVPG is concentrating its human-coach network here.
- **Strong human coaches**, when you have access. Cagan: "I am still the number one fan of human product coaching." Model-as-coach is the scalable answer for the millions of product creators *without* access to a strong human coach, not the preferred answer for those who have one.
- **Leader setup recommended by Cagan:** model-as-coach **plus** a strong human leadership coach — that combination "gives you the best chance of getting to a successful outcome."

## In your context
This wiki is project files for model-as-product-coach; [`CLAUDE.md`](../../CLAUDE.md) is the project instructions. Add your company's strategic context as a [`case-study`](../case-studies/) / field note and you have Cagan's full prescription. _Field note placeholder — what's your strategic context, and how is the model coaching you actually performing? Where is it strongest? Where is it weakest?_

## Related
- [[product-coaching]] — the broader concept; this is the AI-specific form.
- [[trust-over-control]] — "active coaching" is the leadership behavior the model now extends to anyone with an internet connection.
- [[marty-cagan]], [[svpg]] — the position shift.
- diagnostics: `[[model-as-coach-readiness]]` (future — is your setup aligned with Cagan's prescription?)

## Sources
- [[2026-02-04-cagan-product-coaching-and-ai]] — Cagan/SVPG, Feb 2026; primary canon for this concept.

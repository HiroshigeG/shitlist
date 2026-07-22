# SHITLIST

**A living radar for creative slop — published as an idea, in the open, while I build it.**

You bring an idea or a direction; Shitlist tells you **how slop it is RIGHT NOW** — the obvious version everyone would make, the clichés you're brushing against *this month*, the references you're copying without noticing — and challenges you to go further.

**It never writes the idea. It keeps the creative honest.**

## The insight that makes it a product

Slop **moves.** The "fresh" AI aesthetic of three months ago is today's cliché. A frozen slop-detector is useless in six months. So the core isn't a list of clichés — it's a **living, dated corpus** of what became banal *this quarter*, refreshed from the actual flood. Real-time cultural awareness, not a dead list. No static guideline document has it.

## Read the spec

The full super-spec is in **[SPEC-shitlist.md](SPEC-shitlist.md)**: the four-layer living slop model (dated cliché corpus, reference index, feedback log, learned calibration), the flow, how it learns without fine-tuning, the data tables, the eval plan, and the open decisions.

## Status — honest

- **Stage:** super-spec (July 2026), design frozen enough to build. This repo is the thinking, published before the code — the same way I published [taco-score](https://github.com/HiroshigeG/taco-score) with its validation protocol frozen before the data grew.
- **v1:** one screen, paste → slop map + logged thumbs up/down, hand-curated dated corpus for one category, retrieval active.
- **v2:** semi-automatic ingest of trending AI content (the real cultural refresh), per-team calibration, a Slack bot, freshness trends over time.

## Sibling project

**[Brand QA](https://github.com/HiroshigeG/brand-qa)** asks the other question — *"is it ours?"* (brand-soul fidelity). Shitlist asks *"is it fresh — right now?"* (originality vs. the current flood). Same philosophy: **AI as a critical foil, never the author.** They share infrastructure: living model + retrieval + feedback log + evals + human-in-the-loop.

## License

MIT. Ideas want to be argued with — if you build this before I do, tell me what broke.

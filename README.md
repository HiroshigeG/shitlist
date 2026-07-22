# Slop Radar & Brand QA

**Two specs for creative quality in the AI era — published as ideas, in the open, while I build them.**

AI can generate a thousand assets before lunch. That created two questions nobody's tooling answers well:

| Tool | The question it answers | The axis |
|---|---|---|
| **[Slop Radar](SPEC-slop-radar.md)** | *"Is this fresh — right now?"* | Originality vs. the current flood |
| **[Brand QA](SPEC-brand-qa.md)** | *"Is this ours?"* | Brand soul vs. generic-with-a-logo |

Same philosophy in both: **the AI is a critical foil, never the author.** It takes the predictable half of the space off the table and challenges the human — who keeps the pen.

## Why "slop radar" and not another idea generator

The insight that makes it a product: **slop moves.** The "fresh" AI aesthetic of three months ago is today's cliché. A frozen slop-detector is useless in six months. So the core isn't a list of clichés — it's a **living, dated corpus** of what became banal *this quarter*, refreshed from the actual flood. That's cultural awareness in real time, and no static guideline document has it.

Brand QA is the sibling: existing tools (CreativeX, Adobe Brand Intelligence) check **compliance** — logo visible, colors right, product in frame. Nobody checks the **soul**: does this *feel* like the brand, or is it category-generic luxury wearing the logo? That's the art director's eye, encoded as a curated codebook the human writes and the model reasons against.

## Status — honest

- **Stage:** super-specs (July 2026), design frozen enough to build. This repo is the thinking, published before the code — the same way I published [taco-score](https://github.com/HiroshigeG/taco-score) with its validation protocol frozen before the data grew.
- **Being built as:** capstone for an AI-builders program, then portfolio tools.
- **v1 scope (each):** one screen, one curated corpus/codebook, retrieval + human feedback loop logged from day one.
- **v2:** semi-automatic trend ingestion (Slop Radar), multi-brand + video + batch (Brand QA).

## The part that compounds

Both tools get better with use, without fine-tuning:
- **Slop Radar** — corpus refresh (dated entries), retrieval per call, and thumbs-up/down calibration per team: *your* slop threshold isn't a junior's.
- **Brand QA** — the codebook is the asset; every human "correct/defend" verdict refines the rubric. The QA **is** an eval system.

## Stack (deliberately boring)

Supabase + pgvector (corpora, codebooks, calls, calibration) · Claude as the critic engine · n8n for refresh/ingest pipelines · a single-screen front end · eval loops from day one (precision/recall on curated known-slop vs. known-fresh sets).

## License

MIT. Ideas want to be argued with — if you build this before I do, tell me what broke.

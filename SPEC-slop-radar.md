# SUPER SPEC — Slop Radar

*Creative-AI tool #1 · super-spec v2 (July 2026) · status: design frozen, building*

---

## One line

You bring an idea or a direction; the tool tells you **how slop it is RIGHT NOW** — the obvious version everyone would make, the clichés you're brushing against *this month*, the references you're copying without noticing — and challenges you to go further. **It never writes the idea: it keeps the creative honest, and it knows what became banal in real time.**

## The insight that makes it a product (not a toy)

Slop **moves.** The "fresh" AI aesthetic of 3 months ago is today's cliché. A **frozen** slop detector is useless in six months. The scarce thing is not "a list of clichés" — it's **knowing what became banal NOW**, because AI culture shifts faster than any written guideline.

Knowing what's flooding the AI feed at this moment is a real, cultivated OSINT skill — watching synthetic content propagate is my research beat. The tool is that eye on the flood, productized. → moat + genuine utility.

## Principle: HUMAN IN THE LOOP

The AI claims the **predictable / commodity** half of the space — *"a machine would make these, and it knows they're everywhere now"* — and clears it out of the way. The creative stays the author. **The tool never writes the idea.**

## Who it's for

- **Agency creatives** who must stay *ahead* of the culture, not inside it.
- **AI-native filmmakers** (me): escaping the default-AI aesthetic.
- **Brand & consulting teams:** "how do we guarantee our output doesn't look like everyone else's".

## The core: a LIVING SLOP MODEL (4 layers)

1. **Living Cliché Corpus** — not a static list: a corpus of tropes *updated with current culture* (the AI aesthetics flooding the feed now, the over-used viral formats, the directorial moves that became defaults). Media embedded and **dated** → it knows what's slop *this quarter*. ← persistence + learning.
2. **Reference Index** — the canon of the known already-done (films, campaigns, iconic ads) to catch *what you're copying* unconsciously.
3. **Calls + Feedback Log** — every radar call + your **thumbs up/down** ("yes, that's slop" / "no, it's fresh because X"). ← the taste signal.
4. **Learned Calibration** — the threshold of *this* team/creative (your slop ≠ a junior's slop), distilled from feedback.

## How it works (flow)

0. **(Optional) Context** — brand/brief/world: calibrates the territory.
1. **Input** — your direction (a paragraph).
2. **The radar runs → the slop map:**
   - **The obvious version** — it *deliberately* generates the most clichéd concept implied, named. The mirror.
   - **Clichés you're touching NOW** — the closest tropes from the living corpus, *with how current they are* ("this move is in ~200 AI films this quarter").
   - **What you're copying** — the known references being echoed.
   - **Originality distance** — how far you are from the predictable (0–100), with the why, *tuned to your threshold*.
   - **ONE provocation** — a single sharp push to go further.
3. **You** — push the idea, or give feedback on the call (which calibrates the radar). **The idea stays yours.**

## How it LEARNS (honest, no smoke)

NOT fine-tuning. **Refresh + retrieval + calibration:**

- **Corpus refresh (cultural drift) — the strong piece:** a periodic ingest of "what is slop now" (curated + semi-automatic from trending-AI-content sources). The corpus is *dated* → the radar knows what became banal recently. This is the thing no static tool has.
- **Retrieval:** new idea → fetch the current clichés + the most similar references → into the reasoning context.
- **Feedback calibration:** your up/downs on calls distill the team's threshold.

> All buildable: Supabase + pgvector (corpus/references/calls embedded), n8n (refresh + ingest pipelines), Claude (the critic engine + feedback distillation).

## Data — precise tables (Supabase + pgvector)

`users` · `teams` · `projects` · `runs` (input+output, history) · **`cliche_corpus`** (trope + media + *date* + source + embedding ← the living part) · `reference_index` (known works + embedding) · **`calls_feedback`** (call + human verdict + why ← the signal) · `calibration` (per-team threshold).

## Why it's genuinely useful now

It doesn't say *"this word is overused"*. It says: *"careful — this entire look is flooding the feed this quarter, ~200 AI films used exactly this move; here's why your idea reads as generic NOW, and this was fresh 4 months ago."* **Real-time cultural awareness, not a dead list.**

## Evals

- Test set: **known-slop** vs. **known-fresh** directions (curated + dated).
- Metrics: radar precision/recall; false positives (flags the fresh), false negatives (misses the cliché); does **calibration** improve with feedback?
- Bonus (strong story): does predicted "freshness" hold up over time as the corpus refreshes?
- Error analysis → refine corpus/threshold.

## Scope

- **v1:** one screen, paste → slop map (obvious version + current clichés + what you copy + provocation) + **logged thumbs up/down**. Hand-curated corpus for **one** category, *dated*. Retrieval active.
- **v2 (the "wow"):** semi-automatic ingest of trending AI content (the real cultural refresh), per-team calibration, Slack bot ("drop the idea, I'll tell you if it's slop NOW"), freshness trend over time.

## Moat

- The **living, current corpus** (it moves with the culture) — a static tool doesn't have it.
- The curation of "what is slop now" = OSINT expertise on synthetic-content floods, not copiable from a doc.
- Accumulated per-team calibration = proprietary data that compounds.

## Demo pitch

> *"Paste your idea. In 10 seconds it tells you not just whether it's a cliché — but whether it's becoming one NOW, how many times it's already been done this quarter, and challenges you to go further. It's the radar that knows what's already slop before the market does. It keeps the human ahead — it doesn't take the pen."*

## Open decisions

- v2 living-corpus sources (curated + trending: which feeds/archives?).
- v1 category (luxury/jewellery is a strong candidate — dense aesthetic codes, fast-moving clichés).
- Score or qualitative only? (qualitative + a light score, consistent with Brand QA).

---

*Sibling: **Brand QA** (`SPEC-brand-qa.md`). Slop Radar asks "is it fresh (NOW)?" (originality + cultural drift). Brand QA asks "is it ours?" (fidelity + client memory). They share the infrastructure: living model + memory/retrieval + feedback log + evals + human-in-the-loop. Build the first, the second costs less.*

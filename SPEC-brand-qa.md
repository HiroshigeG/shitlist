# SPEC — Brand QA / "On-brand, or on autopilot?"

*Creative-AI tool #2 · v1 (July 2026) · status: design frozen, building after Slop Radar*

---

## One line

Upload a piece of creative + a brand's codes; the tool tells you whether it **honors the soul of the brand** (not its assets) — where it drifts, and why. **It flags, it doesn't reject.**

## The problem (why it exists) + the trap

AI generates 1,000 assets; which ones *are actually the brand*? Existing tools (**CreativeX, Adobe Brand Intelligence**) check **compliance**: logo visible? colors right? product in frame? — mechanical, computer vision. **Nobody checks the soul:** *"does this feel like this maison, or is it generic luxury wearing the logo?"*. That is the **soul / register** axis — the art director's eye — and they don't touch it.

> ⚠️ **Trap to avoid:** do NOT rebuild compliance (that market is taken, and it's not the edge). Build **soul fidelity**.

## Principle: HUMAN IN THE LOOP

It flags and explains; **the human corrects or defends** (a drift can be deliberate — a refresh). It never auto-rejects. It's a *supporting check*, not a gate.

## Who it's for

- **Brand teams / brand guardians** (in-house + agencies).
- **Consultancies:** creative-quality governance at scale, measurable.
- **Filmmakers / ADs:** verifying your AI work stays inside the brand's world.

## How it works (flow)

1. **Setup (once per brand): the CODEBOOK.** Not the logo+colors PDF — the *codes*: world, register, tension, what the brand **IS** and what it **NEVER is**. (An invented maison for the demo: warm Roman boldness, jewellery as rebirth/seduction; NEVER cold-minimalist, NEVER ironic.) Written by **the human** who knows the brand.
2. **Input:** a piece of creative — concept, frame/still, script, cut, batch of assets.
3. **The fidelity read:**
   - **On-brand or autopilot?** — does it feel like *this* brand, or a generic version of the category?
   - **Where it drifts:** precise flags ("reads more like a rival maison because X", "cold tone, the brand is warm/baroque", "could be any house").
   - **Codes honored vs. betrayed:** mapped against the codebook.
   - **Direction of the fix (not the fix):** "to feel more like the brand, push on X".
4. **You:** correct or defend.

## Input / Output (precise)

- **Input:** text or image (the creative) + selected brand.
- **Output (structured):** `{ verdict (on-brand ↔ autopilot), drift_flags[], codes_honored[], codes_betrayed[], fix_direction }`.

## Under the hood

- LLM (+ **vision** for frames) reasoning **against the codebook** as a rubric.
- The **codebook** is the asset: QA quality = code quality (written by an AD, not scraped).
- **Zero generation:** judgment with reasons, nothing else.

## Data (Supabase)

`brands` · **`codebooks`** · `submissions` (creative in) · `reads` (output + history) · `rubric`.

## Evals — the heart, and the strongest story

- Per-brand test set: curated **on-brand** vs. **off-brand** creatives.
- Metrics: does the QA catch real drift? false positives (flags on-brand work)? false negatives?
- Error analysis → refine codebook/rubric. The QA **is** an eval system — that's the point.

## Scope

- **v1:** **one** brand codebook (an invented but believable maison — no IP risk, full freedom), input one concept/frame → fidelity read (on-brand? where does it drift? codes honored/betrayed? fix direction). Text + one image.
- **v2:** multi-brand, video/cut analysis, batch mode, Slack brand-guardian, team fidelity history.

## Differentiation / moat

- CreativeX/Adobe = **compliance** (assets). This = **soul** (codes / register). Different axis.
- The curated codebook = an AD's reading of the brand, not a mechanical check.
- The most **evals-native** of the pair: quality governance you can measure.

## Demo pitch

> *"Upload your creative. It won't tell you if the logo is right — it tells you whether it actually **feels** like the brand, or it's a generic version wearing the logo. The taste-level brand check nobody else does."*

## Open decisions

- v1 brand: invented-but-credible (free) vs. a real maison (stronger demo, IP risk). Current lean: invented.
- Images/text only in v1; video in v2.
- Verdict: qualitative scale or score? (qualitative + a light score → consistent with Slop Radar).

---

*Sibling: **Slop Radar** (`SPEC-slop-radar.md`). Brand QA answers "is it ours?" (fidelity axis). Slop Radar answers "is it fresh?" (originality axis). Same philosophy: AI as the critical foil, the human stays the author.*

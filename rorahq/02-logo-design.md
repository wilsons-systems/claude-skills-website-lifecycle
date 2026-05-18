# Rora — Logo Design Spec

**Skill:** `logo-design`  
**Date:** May 2026  
**Status:** Ready to execute — prompts and spec below

---

## Architecture decision: Concept B — Monogram Mark + Wordmark ✅

**Why:** Rora needs an app icon (demo platform), favicon, chat widget avatar, social profile, and email signature — all of which need a standalone mark. A wordmark-only logo (Concepts A or D) cannot do that job. Concept B gives both: the mark lives independently, the wordmark with mark is the primary lockup.

**Not Concept A (flowing wordmark):** Beautiful, but no standalone mark.  
**Not Concept E (interlocked RR letterform):** Interesting but risks being unreadable at small sizes.

---

## Mark decision: B2 — Interlocked RR ✅

Two lowercase "r" letters — one forward, one reversed — interlocking at the stem. Forms a single, unique glyph.

**Why B2 over B1 (circle monogram) or B3 (wave arc):**
- B2 is meaningful — it references the name's origin (Roman + Ralphie) without spelling it out
- B2 is ownable — no other brand uses it
- B2 scales — the interlocked form reads as a shape at 16px, as a detail-rich mark at 200px
- B3 (wave arc) risks reading as "flow" or "stream" — too generic for a consultancy

**Mark construction:**
- Two mirrored lowercase "r" glyphs from the primary typeface
- Reversed "r" flipped horizontally, stems aligned centrally
- Where the stems meet: a subtle visual join (overlap or notch)
- No enclosing shape (circle, square) — the mark is the letterform alone
- Rendered in a single colour only

---

## Typography decision: Satoshi ✅ (primary), Söhne (if budget allows)

| | Satoshi (free, Fontshare) | Söhne (Klim, paid) |
|---|---|---|
| Feel | Geometric with warmth — slight personality | Premium neo-grotesque — pure precision |
| Case for | Free, available now, works immediately | Timeless, used by Vercel — premium signal |
| Case against | Slightly less distinctive | £180 for desktop licence |
| Verdict | Use Satoshi for MVP. Commission Söhne if/when first 5 clients signed. |

**Wordmark specs:**
- Typeface: Satoshi Medium (400/500 weight)
- Case: all lowercase — "rora"
- Letter-spacing: -0.03em (tight but not crushed)
- Mark-to-wordmark gap: equal to cap-height of the wordmark
- Colour: #1B2430 (deep navy) on light backgrounds; #F5F1EB (cream) reversed

---

## Full logo system

### Primary lockup (horizontal)
Mark left, wordmark right. Used in: nav bar, email signature, business card, invoice header.

### Stacked lockup (vertical)
Mark above wordmark. Used in: social profile, LinkedIn company page header, presentation title slide.

### Mark only
The interlocked RR. Used in: favicon, app icon (chat widget, assessment tool), social avatar (32×32 and 400×400), loading spinner.

### Wordmark only
"rora" without the mark. Used in: embossed/engraved contexts, single-colour print, where the mark would be too small to read.

---

## Colour variants

| Variant | When to use |
|---|---|
| Navy on cream (#1B2430 on #F5F1EB) | Default — website, documents, all digital |
| Navy on white (#1B2430 on #FFFFFF) | Hero sections, white-background contexts |
| Cream on navy (#F5F1EB on #1B2430) | Dark backgrounds, reversed contexts |
| Single colour black | Print, embossing, monochrome contexts |
| Single colour white | Dark backgrounds where navy isn't available |

No coral in the logo. Coral is an accent colour — the logo stays 2-colour maximum.

---

## AI generation prompts (use these in sequence)

### Round 1 — Moodboard (Midjourney v7)

```
Logo design moodboard, minimalist premium wordmark logos for a boutique AI consultancy called "rora", lowercase custom geometric sans-serif typography, editorial feel, deep navy and warm cream colour palette, small geometric monogram mark, inspired by Stripe, Linear, Vercel, no text, pure logo tile concepts --ar 16:9 --style raw --v 7
```

```
Abstract geometric monogram marks, two mirrored lowercase r letterforms interlocked at the stem, boutique consultancy brand identity, deep slate navy on cream, flat vector, no gradients, 20 variations shown as tiles --ar 16:9 --style raw --v 7
```

### Round 2 — Primary concept (Recraft.ai — use for SVG output)

```
Minimalist logo for "rora" — lowercase geometric sans-serif wordmark in deep navy #1B2430, paired with a small geometric mark showing two mirrored lowercase r letterforms interlocked. Warm cream background #F5F1EB. Editorial, restrained, premium. Inspired by Linear and Stripe. Flat vector, no gradients, no drop shadows.
```

```
Standalone monogram mark — two mirrored lowercase "r" letterforms, one forward one reversed, interlocked at the stem to form a single unified glyph. Deep navy #1B2430 on cream #F5F1EB. Geometric, precise, scales from 16px to 400px. Flat vector only.
```

### Round 3 — Wordmark refinement (Adobe Firefly — commercially safe)

```
Premium minimalist wordmark logo reading "rora", all lowercase, Satoshi or similar geometric sans-serif typeface, deep navy #1B2430 on warm cream #F5F1EB, tight letter-spacing, single weight, editorial and timeless. Flat vector output, no icon, no tagline, no gradients, no effects.
```

---

## Fiverr brief (paste this when hiring a designer to refine)

**Budget:** £100–200  
**Deliverable:** Vector refinement of AI-generated concept — production-ready SVG  
**Brief:**

> I need a designer to take an AI-generated logo concept and refine it to production quality. This is NOT a full logo design brief — the concept is already chosen. Your job is: correct the kerning, ensure the mark scales cleanly from 16px to 400px, fix any proportion issues, and export in all required formats.
>
> **Brand:** Rora — AI consultancy for UK small businesses  
> **Style:** Premium, minimal, editorial. Inspired by Stripe and Linear.  
> **Typeface:** Satoshi Medium, all lowercase "rora", letter-spacing -0.03em  
> **Mark:** Two mirrored lowercase "r" glyphs interlocked at the stem, single colour, no enclosing shape  
> **Colours:** Primary #1B2430 (deep navy), background #F5F1EB (warm cream)
>
> **Deliverables required:**
> - Primary lockup (mark + wordmark, horizontal) — SVG + PNG @2x
> - Stacked lockup (mark above wordmark) — SVG + PNG @2x
> - Mark only — SVG + PNG @2x
> - Wordmark only — SVG + PNG @2x
> - Reversed version (cream on navy) for each variant above
> - Favicon set: 16px, 32px, 180px apple-touch-icon PNG
> - Social avatar: 400×400 PNG (mark only)
>
> All SVGs must be clean paths — no embedded fonts, no raster images inside the SVG.

---

## Production deliverables checklist

- [ ] Primary lockup (horizontal) — SVG + PNG @1x, @2x, @3x
- [ ] Primary lockup (horizontal) — reversed — SVG + PNG
- [ ] Stacked lockup — SVG + PNG
- [ ] Stacked lockup — reversed — SVG + PNG
- [ ] Mark only — SVG + PNG @1x, @2x, @3x
- [ ] Mark only — reversed — SVG + PNG
- [ ] Wordmark only — SVG
- [ ] Wordmark only — reversed — SVG
- [ ] Monochrome (black) versions — SVG
- [ ] Monochrome (white) versions — SVG
- [ ] Favicon: 16px PNG
- [ ] Favicon: 32px PNG
- [ ] Apple touch icon: 180×180 PNG
- [ ] Social avatar: 400×400 PNG (mark only)
- [ ] Email signature: 200×60 PNG (primary lockup, horizontal)

**Store all assets in:** `wilsons-systems/ai-consultancy-web/public/brand/`

---

## Website implementation notes

Once assets are ready:

1. Replace `public/favicon.ico` with new favicon set (16px, 32px, 180px)
2. Replace placeholder logo in `components/layout/nav.tsx` with SVG import
3. Add logo to `app/opengraph-image.tsx` — replace text-only OG card
4. Add to `app/about/page.tsx` — Ryan's about section with Rora mark as section indicator
5. Update `public/apple-touch-icon.png` with 180×180 version

---

## Quality tests

Before signing off any logo version:

| Test | Pass criteria |
|---|---|
| Favicon at 16px | Mark is recognisable as a shape — not a blob |
| Nav bar at 32px height | Wordmark is readable, mark is visible |
| Business card at 50mm width | Full lockup is clean, nothing merging |
| Hero at 200px width | All proportions correct, no optical awkwardness |
| Single colour | Works in pure black — no detail depends on colour |
| Reversed | Reads correctly on the navy background |
| Embossed (greyscale) | Holds at mid-tone without losing definition |

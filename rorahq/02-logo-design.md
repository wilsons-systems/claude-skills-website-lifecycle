# Rora — Logo Design Specification

**Document status:** Production reference  
**Last updated:** May 2026  
**Owner:** Ryan Wilson, Pier 7 Projects Ltd

---

## Architecture Decision: Concept B

**Monogram mark + lowercase wordmark.**

Rora uses a two-part system: a mark (the interlocked RR monogram) and a wordmark (the lowercase letters "rora" set in Söhne or Satoshi). These two elements are always used together in primary applications — except at very small sizes (favicon, app icon) where the mark operates alone.

**Why Concept B, not a wordmark-only or icon-only approach:**

A wordmark alone at small sizes becomes illegible and loses distinctiveness in browser tabs, app icons, and social thumbnails. An icon-only approach places too much weight on a mark that is not yet established in memory. Concept B solves both problems: the wordmark carries the name clearly across web and print, while the mark functions independently at small sizes and builds recognition over time.

The architecture also provides a natural visual rhythm in the navigation bar — the mark grounds the left edge, the wordmark follows — without requiring the full brand name to be spelled out as a decorative element.

---

## Mark Decision: Interlocked RR (B2)

**The mark is two letterforms — R and R — interlocked to read as a single, unified shape.**

This is not a literal illustration. It is a constructed letterform: two R characters sharing geometry in a way that creates a mark that is ownable, scalable, and meaningful without being legible to anyone who doesn't know what it stands for.

**Why this mark works:**

- Ownable. Interlocked-letter monograms are a credible tradition in premium branding (fashion, finance, craft). Done well, they signal: this was built to last.
- Scalable. A constructed letterform works at 16px (favicon) and at 400px (hero). A complex illustration does not.
- Legible as abstraction. Someone who doesn't know the origin of the mark sees a confident, considered symbol. That is sufficient.
- The double-R structure creates natural symmetry that aids visual balance in all orientations.

**Construction notes for the designer:**

The two R forms should share a shared vertical stroke — the left stem of the second R becomes the right stem of the first R, or one R is mirrored and interlocked through a geometric intersection. The result should feel like a single mark, not two letters placed side by side. The counter (the enclosed space) of each R should remain open and legible even at 32px. Avoid over-complicating the junction — the simplest overlap that reads as intentional is the right answer.

---

## Typography

### Primary Typeface: Söhne

**Söhne** (Klim Type Foundry) is the primary typeface for the Rora wordmark and all headline/display use. It is a contemporary grotesque with warmth in its details — closer to Akzidenz-Grotesk than Helvetica, more humanist than geometric, less cold than Inter.

For the wordmark specifically:
- **Weight:** Regular (400). Single weight only.
- **Case:** Lowercase. "rora" — never "Rora", never "RORA".
- **Letter-spacing:** -0.03em. Tight but not compressed. The letters should feel considered, not cramped.
- **No modification:** Do not alter the letterforms. Do not stretch, condense, or distort.

### Free Alternative: Satoshi

If Söhne is unavailable (for web use before a licence is in place, or for a designer working without access), **Satoshi** (by Indian Type Foundry, free via Fontshare) is the approved substitute. It shares similar humanist grotesque qualities — slightly warmer than Inter, tighter than DM Sans.

Satoshi wordmark settings:
- **Weight:** Regular (400)
- **Case:** Lowercase
- **Letter-spacing:** -0.025em (Satoshi's spacing is slightly tighter than Söhne by default; adjust accordingly)

### Web Typography Fallback Stack

```css
font-family: 'Söhne', 'Satoshi', -apple-system, BlinkMacSystemFont, 'Inter', sans-serif;
```

---

## Colour

### Primary Application

| Element | Colour | Hex |
|---|---|---|
| Wordmark "rora" | Deep navy | #1B2430 |
| Monogram mark | Deep navy | #1B2430 |
| Background (all standard use) | Cream | #F5F2ED |

### Accent Application

| Element | Colour | Hex |
|---|---|---|
| Mark accent detail | Dusty coral | #E8A38A |
| Mark (reversed application) | White | #FFFFFF |
| Wordmark (reversed application) | White | #FFFFFF |

**Coral accent rule:** Coral (#E8A38A) is used on one specific part of the mark — a stroke, a counter fill, a single geometric element — to create distinctiveness and warmth. It is never applied to the wordmark itself. It is never the dominant colour. It does not appear as background. On reversed (dark background) applications, the coral accent may remain or drop to white, depending on context — the designer should supply both versions.

### Reversed Logo

On navy (#1B2430) or dark backgrounds: wordmark and mark in white (#FFFFFF), coral accent retained or dropped as specified above.

On coral (#E8A38A) backgrounds: wordmark and mark in navy (#1B2430). No coral accent on coral background — it would disappear.

### Monochrome Logo

All elements in single colour. Use navy on light backgrounds. Use white on dark backgrounds. No coral. No grey. Monochrome version is for single-colour print, embroidery, embossing.

---

## AI Generation Prompts

These prompts are ready to paste. They are designed to generate reference material for a human designer — not a finished logo. Use the output to refine the brief, identify the strongest geometric approach, and brief a Fiverr or freelance designer.

---

### Recraft (recraft.ai)

**Prompt 1 — Mark exploration:**

```
Minimalist monogram logo mark. Two interlocked letter R forms sharing a central vertical stroke, creating a unified single symbol. Clean geometric construction. No serifs. No decoration. Deep navy blue #1B2430 on cream white #F5F2ED background. Vector style. Flat, no shadows, no gradients. Works at 32x32 pixels. Professional, editorial, quiet confidence. Similar construction logic to Chanel CC or Gucci GG but original geometry. Do not add any text.
```

**Prompt 2 — Full lockup:**

```
Wordmark logo for brand named "rora". Lowercase sans-serif letters only. Tight letter-spacing. Weight: regular, not bold. Typeface similar to Söhne or Satoshi grotesque. Set in deep navy #1B2430 on cream #F5F2ED background. To the left of the wordmark, a small square monogram mark — two interlocked R letterforms. Mark and wordmark aligned on baseline. No tagline. No decorative elements. No icon other than the monogram mark. Vector flat design.
```

---

### Midjourney v7

**Prompt 1 — Mark only:**

```
minimal monogram mark, two interlocked letter R shapes sharing central vertical stroke, geometric sans-serif construction, flat vector, no gradients, deep navy #1B2430 on cream background, professional brand identity, scales to 16px favicon, negative space is intentional, no flourishes, editorial craft aesthetic --style raw --ar 1:1 --v 7
```

**Prompt 2 — Full logo lockup:**

```
brand logo for company named rora, lowercase wordmark in humanist grotesque typeface similar to Söhne, tight tracking -0.03em, regular weight, deep navy on cream, small geometric monogram mark to left of wordmark, two interlocked R letterforms as mark, flat vector SVG style, no shadows no gradients, clean editorial minimalist, one accent detail in dusty coral #E8A38A on the mark only --style raw --ar 3:1 --v 7
```

---

### Adobe Firefly

**Prompt 1 — Mark:**

```
Minimalist typographic monogram logo mark. Two letter R shapes interlocked, sharing one vertical stroke. Constructed from clean geometric forms with no serifs or decoration. Navy blue on cream background. Flat vector design. No shadow. No gradient. Mark must be legible and balanced at small sizes. Style reference: premium editorial brand identity, similar in restraint to Aesop or Linear brand marks.
```

**Prompt 2 — Lockup:**

```
Complete logo lockup: small square monogram mark on the left (two interlocked R letterforms in navy) followed by lowercase wordmark "rora" in a clean regular-weight grotesque sans-serif with tight letter spacing. Navy on cream. One small coral accent element on the mark. Flat vector. No tagline. No decoration. Professional, restrained, editorial.
```

---

## Production Deliverables Checklist

The following files are required before the logo is considered complete. No file should be a rasterised version of another — SVG files must be built as vectors.

### SVG Files (Master)

- [ ] `rora-logo-primary.svg` — Mark + wordmark, navy on transparent background
- [ ] `rora-logo-reversed.svg` — Mark + wordmark, white on transparent background
- [ ] `rora-logo-monochrome.svg` — Mark + wordmark, single colour (navy), transparent background
- [ ] `rora-mark-primary.svg` — Mark only, navy, transparent background
- [ ] `rora-mark-reversed.svg` — Mark only, white, transparent background
- [ ] `rora-wordmark-only.svg` — Wordmark only, no mark, navy, transparent background

### PNG Files (Rasterised from SVG)

| File | Size | Use |
|---|---|---|
| `rora-logo-400.png` | 400px wide | Hero, proposals, presentations |
| `rora-logo-200.png` | 200px wide | Email header, documents |
| `rora-logo-100.png` | 100px wide | Smaller UI contexts |
| `rora-logo-reversed-400.png` | 400px wide | Dark background use |
| `rora-logo-reversed-200.png` | 200px wide | Dark background documents |

### Favicon Files

| File | Size | Notes |
|---|---|---|
| `favicon-16.png` | 16×16px | Browser tab (mark only) |
| `favicon-32.png` | 32×32px | Retina browser tab (mark only) |
| `favicon-180.png` | 180×180px | Apple touch icon (mark only, with cream background) |
| `favicon.ico` | Multi-size | Contains 16, 32, 48 in one file |

### Social and App Icons

| File | Size | Notes |
|---|---|---|
| `rora-avatar-400.png` | 400×400px | LinkedIn, Twitter/X, Google Business |
| `rora-avatar-1600.png` | 1600×1600px | High-resolution social use |
| `rora-email-signature.png` | 200×60px | Email signature (mark + wordmark on cream) |

---

## Fiverr Brief Template

Use this template verbatim when briefing a designer on Fiverr or equivalent. Paste into the project brief field.

---

**Project title:** Minimalist monogram logo — "rora" brand

**What I need:**

A professional logo for a brand called Rora (lowercase: "rora"). The logo has two parts:

1. A monogram mark — two letter R shapes interlocked to create a single unified symbol. The two Rs share a central vertical stroke. This should feel geometric and balanced, not decorative. Reference the visual logic of Chanel CC or Gucci GG but in a completely original form.

2. A lowercase wordmark — the letters "rora" set in a clean, regular-weight humanist grotesque sans-serif. Think Söhne, Satoshi, or similar. Tight letter-spacing (-0.025em to -0.04em). Regular weight only, not bold.

**Colours:**

- Deep navy: #1B2430 (mark and wordmark colour on light backgrounds)
- Cream: #F5F2ED (background)
- Dusty coral: #E8A38A (one small accent detail on the mark only — not the wordmark, not the background)

**Style references:**

- Aesop (quiet, editorial, type-led)
- Linear (precise, clean, no decoration)
- Mast Brothers (craft, restrained, confident)

**What I do NOT want:**

- No gradients anywhere
- No drop shadows or glows
- No rounded pill shapes
- No "tech startup" blue or purple
- No AI robot imagery, no circuits, no data visualisation metaphors
- No italic type
- No font weights heavier than Regular
- Do not add a strapline or tagline to the logo

**Deliverables I need:**

- SVG: primary (mark + wordmark), reversed (white on dark), monochrome
- SVG: mark only (for favicon use)
- PNG: 400px, 200px, 100px wide versions of primary
- PNG: 180×180px (mark only, cream background — for Apple icon)
- PNG: 400×400px (mark only for social avatar)
- PNG: 200×60px (email signature horizontal lockup)
- Favicon .ico file (16, 32, 48 multi-size)

**Brand context:**

This is a small UK AI consultancy for local businesses. The brand personality is quietly confident — professional, warm, not "tech startup". The logo should feel like it belongs on good stationery as much as on a website.

---

## Application Notes

### Navigation Bar

The logo appears at the left edge of the navigation bar. The mark sits first, the wordmark follows immediately to its right with 8px separation. Both are set at the same optical height — the mark is a square, so height matches the cap-height of the wordmark. At 32px tall navigation (standard desktop), the logo unit is approximately 120px wide total.

On scroll, if the nav compresses, the wordmark may drop out and the mark operates alone — but only if this behaviour is explicitly designed and the mark has been confirmed to read clearly at 24px.

### Favicon

Mark only. No wordmark. The mark on a cream (#F5F2ED) square background at 180px, cropped to circle in browser contexts that require circular icons. The mark itself is centred with 20% padding on all sides. At 16px the coral accent may be dropped to preserve legibility — the mark must read as a coherent shape, not a collection of pixels.

### Business Card

Front face: mark + wordmark centred or left-aligned, in navy on cream stock. The card stock colour is the "background" — do not print a cream rectangle on white card, use cream-toned card as the physical substrate.

Reverse: contact details in navy. No additional decoration. Ryan's name, title, phone, email, rorahq.co.uk. Type size: 9pt for detail, 10pt for name.

Suggested print spec: 350gsm uncoated cream board. Blind emboss on the mark if budget allows.

### Email Signature

The email signature logo is the horizontal lockup (mark + wordmark) at 200×60px, exported as PNG with a cream background. It is not transparent — email clients render transparency unreliably. The image links to rorahq.co.uk.

Below the logo image: Ryan's name in plain text (so it renders on email clients that block images), then role, phone, website. Keep the signature to 5 lines of text maximum below the logo.

# Rora — Brand Style Guide

**Skill:** `brand-style-guide`  
**Date:** May 2026  
**Version:** 1.0 — canonical reference  
**Status:** Locked ✅

---

## 1. Brand story

Rora was built by Ryan Wilson — an electrician from Lytham St Annes who ran a 6-person trades business and hit the same wall every small business owner hits: too much admin, not enough time. He built AI systems to fix it. Quote time dropped from 47 minutes to 12. Leads stopped going cold overnight. Invoices chased themselves. It worked. Rora is what happens when you do the same for other businesses.

The brand promise: **"We built it for ourselves first. Now it's yours."**

This is not a footnote — it is the entire business. Every piece of copy, every design decision, every case study should reinforce this story.

---

## 2. Logo system

### Primary lockup
Interlocked RR monogram mark (left) + lowercase "rora" wordmark (right).  
Use: navigation, email signature, business card, invoice header, document headers.

### Stacked lockup
Mark above wordmark.  
Use: social profiles, LinkedIn company header, presentation title slides.

### Mark only
The interlocked RR glyph, standalone.  
Use: favicon, chat widget avatar, app icon, loading states, social avatars (400×400).

### Wordmark only
"rora" without the mark.  
Use: embossing, single-colour print, contexts where the mark would be too small.

### Clear space
Minimum clear space around any lockup = the height of the lowercase "o" in the wordmark. Nothing enters this zone.

### Don'ts
- Do not stretch, distort, or rotate the logo
- Do not add a drop shadow, glow, or bevel
- Do not use coral or any other colour as the logo colour — navy or cream only
- Do not add a tagline inside the logo lockup
- Do not place the logo on a patterned or photographic background without a solid colour block behind it
- Do not use an outline version of the logo

---

## 3. Colour

### Primary palette

| Name | Hex | RGB | Use |
|---|---|---|---|
| Deep Navy | `#1B2430` | 27, 36, 48 | Wordmark, headings, body text, borders |
| Warm Cream | `#F5F1EB` | 245, 241, 235 | Page background, card backgrounds |
| Muted Sand | `#EDEAE4` | 237, 234, 228 | Secondary surfaces, hover states, dividers |
| Dusty Coral | `#C8715A` | 200, 113, 90 | Primary CTAs, highlights, accent moments |
| White | `#FFFFFF` | 255, 255, 255 | Hero sections, overlaid text on navy |

### Usage rules

1. **Navy on cream** is the default text combination. Never navy directly on white — the contrast is harsh.
2. **Coral** appears on a maximum of 2–3 elements per page: the primary CTA button, one section highlight, and one decorative element if needed. More than this dilutes its impact.
3. **White** is reserved for hero sections. The shift from white hero to cream content marks the visual transition from selling to explaining.
4. **Never add blue** to the palette in any form after migration from periwinkle.
5. **Contrast:** Navy on cream = 9.5:1 (passes WCAG AAA). Coral must only appear as a background with white text — coral on cream fails contrast.

### CSS variables (Tailwind v4 / Next.js)

```css
:root {
  --color-navy:    #1B2430;
  --color-cream:   #F5F1EB;
  --color-sand:    #EDEAE4;
  --color-coral:   #C8715A;
  --color-white:   #FFFFFF;

  /* Aliases */
  --color-background:   var(--color-cream);
  --color-foreground:   var(--color-navy);
  --color-primary:      var(--color-coral);
  --color-surface:      var(--color-sand);
}
```

---

## 4. Typography

### Typefaces

| Role | Typeface | Weight | Notes |
|---|---|---|---|
| Display (hero headings) | Satoshi | 700 Bold | Tight tracking (-0.02em) |
| Body headings | Satoshi | 600 SemiBold | Normal tracking |
| Body text | Satoshi | 400 Regular | 1.6 line-height |
| Caption / label | Satoshi | 500 Medium | 0.05em tracking, uppercase optional |

**Web stack fallback:** `'Satoshi', 'Inter', system-ui, -apple-system, sans-serif`

**Future upgrade:** Söhne (Klim Type Foundry) for display headings when budget allows. Same weights, same hierarchy — a drop-in replacement.

### Type scale (mobile-first, rem)

| Token | Size | Weight | Use |
|---|---|---|---|
| `display-xl` | 3.5rem / 56px | 700 | Hero headline only |
| `display-lg` | 2.5rem / 40px | 700 | Page section headlines |
| `heading-lg` | 1.75rem / 28px | 600 | Card headlines, sub-sections |
| `heading-sm` | 1.25rem / 20px | 600 | Labels, small headings |
| `body-lg` | 1.125rem / 18px | 400 | Lead paragraphs, intro copy |
| `body` | 1rem / 16px | 400 | Standard body copy |
| `caption` | 0.875rem / 14px | 500 | Labels, metadata, footnotes |

### Rules
- Never use more than 3 type sizes in a single section
- Line-height for body: 1.6. Line-height for display: 1.1–1.2.
- Paragraph max-width: 65ch — wider than this becomes unreadable on desktop
- Never use italic for anything other than quotations or code

---

## 5. Imagery direction

**What to show:**
- Real screenshots of the Rora tools in action (the assessment, canvas, brief tools)
- Real business environments — trade vans, desks, phones with notifications
- Ryan — genuine setting, not a studio portrait. A single well-composed photo on a job site or at a real desk is worth more than any stock image

**What never to use:**
- Stock photos of people in business attire shaking hands
- Abstract AI imagery (glowing brains, neural network graphics, floating orbs)
- Illustrations of robots
- Any image that could appear on a competitor's site without change

**Photography treatment:**
- Warm, slightly desaturated — consistent with the cream/navy palette
- Natural light preferred
- No heavy Lightroom presets
- If using screenshots: crop cleanly, use a browser chrome mock-up at 2x resolution, navy drop shadow beneath

---

## 6. Voice summary

**Three traits:**
1. Quietly confident — states what it does, proves it, never boasts
2. Straight-talking — plain English, no jargon, no buzzwords
3. Reliably human — warm but not casual, professional but not cold

**10 do/don't pairs:**

| Do | Don't |
|---|---|
| "Quote time dropped from 47 minutes to 12" | "Dramatically reduces admin time" |
| "Your leads, captured automatically" | "Our AI-powered lead capture solution" |
| "We built it for ourselves first" | "Trusted by businesses across the UK" |
| "Nothing new to learn" | "Seamless integration with your existing workflow" |
| "We fix it if it's not right" | "We offer comprehensive post-implementation support" |
| "Your business, running in the background" | "Enabling operational efficiency at scale" |
| "13 questions. 3 minutes." | "Complete our comprehensive assessment form" |
| Short sentences. Full stops. | Long relative clauses that continue the same thought and add qualifications... |
| Lead with the problem | Lead with the feature |
| Use "you" and "your business" | Use "clients" or "businesses" third-person |

---

## 7. Applications

### Email signature

```
[Name]
Rora — AI automation for small businesses
[mark only logo, 32px high]
rorahq.co.uk | hello@rorahq.co.uk
Pier 7 Projects Ltd | Company No. 12894305
```

### LinkedIn company page
- Banner: Navy background, cream wordmark centred, tagline below in caption weight
- Profile image: Mark only (interlocked RR), navy on cream, 400×400

### Invoice header
- Primary wordmark (mark + "rora"), top-left
- Navy on cream/white
- Company details below in caption weight

### Business card
- Front: White card, navy logo centre or top-left, coral accent line
- Back: Navy card, cream logo, contact details in cream caption weight

---

## 8. Dos and don'ts

**Do:**
- Update this guide when any brand element changes — it is the canonical reference
- Use real numbers and specifics whenever possible
- Test every page against the 3 voice traits before publishing
- Ask: "Would an electrician from Lytham St Annes feel spoken to, or spoken at?"

**Don't:**
- Use any colour not in the palette
- Add a new typeface without updating this guide
- Use the logo at less than 24px height
- Place coral text on cream or white (fails contrast)
- Let copy drift toward corporate language — run the vocabulary ban list regularly

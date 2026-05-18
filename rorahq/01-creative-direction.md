# Rora — Creative Direction Brief

**Skill:** `creative-direction`  
**Date:** May 2026  
**Status:** Locked ✅

---

## Project context

Rora is an AI consultancy for UK small businesses (3–25 staff). The brand promise is "We built it for ourselves first. Now it's yours." The founder is a NICEIC-qualified electrician from Blackpool who automated his own trades business and now does the same for other local businesses. The audience is not a tech buyer — they are a busy owner who distrusts hype and responds to proof.

The website is live (rorahq.co.uk, Next.js 15, Vercel). A navy/cream/coral theme is built behind `?theme=navy`. The live theme is periwinkle (#6C8EEF). **This brief resolves that palette debate.**

---

## The 4 axes

### Axis 1 — Tone Register: **Conversational**

Not professional (too cold for this audience — they're hiring a person, not a firm).  
Not playful (risks feeling lightweight against a serious admin-pain proposition).  
**Conversational** — warm, direct, first-person comfortable. Reads like a skilled tradesperson who knows their job and doesn't oversell.

> The category default (AI tools, SaaS, consultancies) is loud and professional. Differentiation is warmth without casualness.

**What this means in practice:**
- "you" and "your business" throughout — never third-person about the client
- Short sentences. Confident full stops. No winding qualifications.
- Personal specifics ("47 minutes per quote", "6pm lead, 8am in Simpro") over category generics
- The founder's voice — not a committee's

**Rejection:** Provocative is wrong. Rora is not a challenger brand; it's a trusted advisor.

---

### Axis 2 — Aesthetic Philosophy: **Editorial Restrained**

The category default for AI consultancies is Polished Standard — clean grids, gradient CTAs, hero animations, floating illustrations. Every competitor looks the same.

**Editorial Restrained** signals confidence through what it leaves out. White space is abundant. Every element earns its place. There is no visual noise. This is the aesthetic of Stripe, Linear, Aesop — brands that trust the reader to pay attention.

**What this means in practice:**
- One primary image per section, never a grid of icons
- Typography does the heavy lifting — generous leading, considered hierarchy
- Colour used sparingly — backgrounds are neutral, accent colour appears at 2–3 moments per page maximum
- No gradients, no floating particle animations, no "3 cards with icons and text" layouts unless content demands it
- Enough white space that the copy feels important, not crowded

**Rejection:** Polished Standard is too generic. Controlled Maximalist is wrong for this audience — it signals complexity, which is the opposite of what Rora sells.

---

### Axis 3 — Audience Relationship: **Peer (expert-to-peer)**

Not authority-to-student ("here's what AI is"). Not vendor-to-buyer ("here's our solution"). **Peer** — one business owner talking to another. The implicit message is: I've been where you are, this is what I did, it works, here's how.

**What this means in practice:**
- Lead with the founder's experience, not the service catalogue
- "We know this works because we're running on it" is more powerful than any feature list
- Case studies should read like one owner telling another owner a story — not a case study template
- The assessment quiz should feel like a conversation, not a form

**Rejection:** Authority-to-student would produce long explanatory copy about "what AI is" — wrong. The audience already knows AI exists. They want to know if it works for a business like theirs.

---

### Axis 4 — Sensory Ambition: **Quiet Precision**

Not loud (not a startup energy brand). Not minimal-to-the-point-of-cold. **Quiet precision** — every detail is considered, nothing is accidental, but it never draws attention to itself. The feeling is: this was made carefully.

**What this means in practice:**
- Typographic micro-decisions matter (letter-spacing, line-height, font pairing)
- Colour tokens are specific and consistent — not approximate
- Layout alignment is exact
- Interactions are subtle (no bouncing elements, no aggressive hover states)
- The logo, when it exists, will be the most considered thing on the page

---

## Palette decision: **Navy/Cream/Coral** ✅ — periwinkle retired

This is the correct call. Reasons:

| | Periwinkle (#6C8EEF) | Navy/Cream/Coral |
|---|---|---|
| Category signal | SaaS-generic (indistinguishable from 100 other AI tools) | Premium craft (Stripe, Mubi, Aesop energy) |
| Audience fit | Techy, startup-adjacent — wrong for Blackpool trades audience | Warm, grounded, professional — right |
| Editorial Restrained compatibility | ❌ Periwinkle fights editorial restraint — it's inherently energetic | ✅ Navy/cream/coral supports restraint natively |
| Longevity | Periwinkle is trending (2024–2026) — will date | Navy/cream/coral is timeless |
| Logo compatibility | Periwinkle accent logo will look generic | Navy wordmark on cream, coral CTA — distinctive |

**Locked palette:**

```
Primary (wordmark, headings, borders):  #1B2430  deep navy
Background (page default):              #F5F1EB  warm cream
Accent (CTAs, highlights — sparingly):  #C8715A  dusty coral
Surface (cards, secondary bg):          #EDEAE4  muted sand
White (hero backgrounds, overlays):     #FFFFFF
```

**Usage rules:**
- Navy on cream for all body text — never navy on white (too harsh)
- Coral used on a maximum of 2–3 elements per page (primary CTA, one highlight, one section break)
- White used for hero sections only — creates contrast against cream content sections
- No blue tones anywhere after migration

**Implementation in `ai-consultancy-web`:**  
Remove the `?theme=navy` preview flag. Promote navy/cream/coral to the default CSS variables in `app/globals.css`. Remove the `ThemeApplier` component from `app/layout.tsx` once migration is confirmed.

---

## Synthesis

Rora should feel like the best electrician you've ever hired — shows up on time, does exactly what they said, charges fairly, doesn't make you feel stupid, and the work is clearly done by someone who cares. Not slick. Not shouty. Just completely competent and quietly confident.

The aesthetic equivalent: clean cream page, navy type, one coral button. Every word chosen. No filler. The founder's face on the about page. Real numbers in the case study. That's it.

---

## Rejection list

- Gradients of any kind
- Hero animations that loop indefinitely (the Remotion demo is an exception — it demonstrates a product)
- Floating illustration sets
- "3 icons in a row with caption text" layout patterns
- Emojis in body copy
- Blue in any form after palette migration
- Stock photography of people
- Words: "revolutionary", "cutting-edge", "seamless", "next-level", "game-changing", "robust", "scalable", "leverage", "synergy", "unlock"

---

## Open questions resolved

**Q: Keep the animated Remotion demo?**  
Yes — it demonstrates a real product. Consistent with "proof over promise." Keep it but reduce the animation loop time and ensure it works at all breakpoints.

**Q: Dark mode?**  
No. The navy/cream/coral palette is a light palette. A dark mode would require a separate design system. Not worth the complexity at this stage.

**Q: Should the hero be full-width cream or white?**  
White hero, transition to cream at the first content section. This creates visual contrast and marks the shift from "selling" (hero) to "explaining" (content).

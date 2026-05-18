# Rora — Brand Style Guide

**Document status:** Canonical production reference  
**Last updated:** May 2026  
**Owner:** Ryan Wilson, Pier 7 Projects Ltd  
**Company:** Pier 7 Projects Ltd, 12894305

This document is the single source of truth for Rora's visual and verbal identity. A designer or agency should be able to implement Rora's brand correctly using this document alone, without a briefing call. If there is a conflict between this document and any other Rora material, this document takes precedence.

---

## 1. Brand Story

Rora was built by someone who felt the problem first. Ryan Wilson ran an electrical contracting business — good work, steady clients, too much admin. Every quote took close to an hour. Leads came in at 10pm and went cold by the time the van was loaded in the morning. Invoices went out late. Follow-up calls didn't happen. The work was fine. The paperwork was eating the business. So Ryan built a system to handle it: automated quotes, lead capture that responded before he could, invoicing that went out on completion. Quote time dropped by 75%. Leads stopped going cold. The system ran in the background while the work happened in the foreground.

Rora is what came from that. Not a software product. Not a consultancy that writes reports. A service that builds the same kind of working system — tuned to your business, not a generic template — and hands it over running. The promise is simple: your business keeps moving even when you're not looking at it. Ryan built it for himself first. That's why it works.

---

## 2. Logo System

### Primary Mark

The Rora logo consists of two elements used together in all primary applications:

1. **Monogram mark** — an interlocked RR symbol, constructed from two R letterforms sharing a central vertical stroke, forming a single unified geometric shape.
2. **Wordmark** — the letters "rora" in lowercase, set in Söhne Regular (or Satoshi Regular as fallback), with letter-spacing of -0.03em.

In all standard applications, the mark appears to the left of the wordmark, aligned on their shared baseline. The gap between mark and wordmark is 8px at standard size (32px height), scaling proportionally.

### Colour

| Context | Mark | Wordmark | Background |
|---|---|---|---|
| Standard (light) | Navy #1B2430 | Navy #1B2430 | Cream #F5F2ED |
| Reversed (dark) | White #FFFFFF | White #FFFFFF | Navy #1B2430 |
| Monochrome | Single colour | Single colour | Transparent |

Coral (#E8A38A) is used as an accent on one specific geometric element of the mark in standard and reversed versions. It is never applied to the wordmark.

### Clear Space Rule

Maintain clear space around the complete logo unit equal to the cap-height of the wordmark on all four sides. Nothing — no text, no image, no border, no other element — enters this zone.

At 32px logo height, this equates to approximately 20px clear space on all sides.

### Size Minimums

| Application | Minimum width |
|---|---|
| Digital (full lockup) | 80px wide |
| Print (full lockup) | 25mm wide |
| Mark only (favicon) | 16px |
| Mark only (print) | 8mm |

Below these minimums, the logo becomes illegible. Do not use the full lockup below 80px — use the mark alone.

### Approved Uses

- Navy on cream background (standard)
- White on navy background (reversed)
- Navy on white background (acceptable alternative to cream)
- Single colour on any background with sufficient contrast (minimum 4.5:1 ratio, WCAG AA)

### Six Logo Don'ts

- Do not apply a drop shadow or outer glow to any part of the logo
- Do not stretch, condense, rotate, or distort the mark or wordmark in any direction
- Do not use the wordmark in any weight other than Regular (no bold, no light, no italic)
- Do not apply a gradient to the mark, wordmark, or background behind the logo
- Do not place the logo on a photographic or patterned background — solid colour only
- Do not use the wordmark in uppercase or mixed case — it is always lowercase "rora"

---

## 3. Colour System

### Primary Palette

**Deep Navy — #1B2430**  
RGB: 27, 36, 48  
Usage: Primary text colour. Logo mark and wordmark. Section backgrounds where contrast is needed. UI elements (buttons, borders, active states). The dominant chromatic colour of the brand.  
Ratio: 25% of total colour presence on any given page.

**Cream — #F5F2ED**  
RGB: 245, 242, 237  
Usage: Primary background colour for all pages and documents. Card backgrounds. Light surface areas. Never as a text colour on a white background (insufficient contrast).  
Ratio: 70% of total colour presence. This is the resting state of the brand. Most of the page is cream.

**Dusty Coral — #E8A38A**  
RGB: 232, 163, 138  
Usage: Accent only. One element per view: a button, an underline, the coral detail on the logo mark, a section divider. Never as a body background. Never as a text colour (fails accessibility contrast). Never on more than one element per page section.  
Ratio: 5% maximum. If in doubt, use less.

**White — #FFFFFF**  
RGB: 255, 255, 255  
Usage: Reversed logo backgrounds. Modal overlays. Form fields. Specific UI contexts where cream would reduce contrast. Not a substitute for cream in general layout.

### Colour Ratios Summary

| Colour | Hex | Ratio |
|---|---|---|
| Cream | #F5F2ED | 70% |
| Navy | #1B2430 | 25% |
| Coral | #E8A38A | 5% max |
| White | #FFFFFF | Contextual |

### Colours Never to Use

- Periwinkle or any blue-purple in the #6B7EFF family
- Any gradient combining two or more of the above colours
- Pure black (#000000) — use navy instead
- Warm grey or cool grey as brand colours — not part of the palette
- Neon or saturated accent colours of any kind

---

## 4. Typography

### Primary Typeface: Söhne

Söhne (Klim Type Foundry) is Rora's primary typeface. It is a humanist grotesque with warmth — confident without being cold, precise without being sterile.

Licence required: Yes (web and desktop licence from klim.co.nz).

### Free Alternative: Satoshi

Satoshi (Indian Type Foundry, via Fontshare) is approved for use where Söhne is not yet licensed. It shares similar weight and warmth characteristics. Available free for commercial use.

### Web Fallback Stack

```css
font-family: 'Söhne', 'Satoshi', -apple-system, BlinkMacSystemFont, 'Inter', sans-serif;
```

### Type Scale

| Role | Size (desktop) | Size (mobile) | Weight | Tracking |
|---|---|---|---|---|
| Display — hero headline | 64px | 40px | Regular (400) | -0.02em |
| Display — section headline | 56px | 36px | Regular (400) | -0.02em |
| Display — sub-section | 40px | 28px | Regular (400) | -0.02em |
| Body — primary | 18px | 16px | Regular (400) | 0 |
| Body — secondary | 16px | 15px | Regular (400) | 0 |
| Caption / label | 14px | 13px | Regular (400) | 0.01em |
| Navigation | 15px | 15px | Regular (400) | 0.01em |

### Weight Rules

- Only Regular (400) is used in the Rora brand at all sizes and all contexts
- No bold, no medium, no light, no italic
- Hierarchy is created by size and spacing, not weight
- Exception: UI states (active nav item) may use a 1px heavier optical weight via CSS `font-weight: 450` if supported — never heavier

### Line Height

| Role | Line height |
|---|---|
| Display | 1.1 |
| Body | 1.6 |
| Caption | 1.4 |
| Navigation | 1.0 |

### Paragraph Spacing

Between paragraphs: 1em (equal to font size). Do not use margin-bottom greater than 1.5em for body copy. Let whitespace in the layout do the work of separating sections, not excessive paragraph spacing.

---

## 5. Imagery Direction

### What Rora Uses

- **Real screenshots of Rora's actual systems** — the quoting interface, the automation flow, the lead capture pipeline. These are the most powerful images available. They show the work without claiming anything.
- **Contextual photography of real environments** — a properly lit commercial kitchen, a trade van, a workshop. Authentic settings that Rora's ICP recognises as their own world. Not staged.
- **Typographic or data-driven visuals** — a timeline showing a quote process before and after, a simple stat shown large on cream. These earn attention without requiring photography.

### What Rora Never Uses

- Stock photography of people in offices, open-plan workspaces, or "team" scenarios
- Laptop-on-desk imagery (particularly the MacBook-on-white-desk or MacBook-near-coffee trope)
- Any image generated to look like a product interface but isn't a real one
- Photography of data centres, server racks, or abstract "technology" imagery
- Photographic backgrounds behind text or logos
- Illustrated characters or mascots
- 3D renders of any kind

### Motion

Motion is used only when it earns trust — not for decoration.

Acceptable motion:
- A tooltip appearing on hover (100ms, no bounce)
- A form field showing a success state (a checkmark appearing, 150ms ease-out)
- A screenshot scrolling to show more content when the user is ready to see it
- A subtle fade-in for content sections as they enter the viewport (max 300ms, no movement on Y axis greater than 8px)

Not acceptable:
- Hero sections rotating through multiple taglines or images
- Particle effects or ambient background animation
- Cursor-following effects of any kind
- Page transition animations
- Counting animations ("47 → current number" effects on stats)
- Looping video backgrounds

---

## 6. Voice Summary

### Three Personality Traits

**Quietly confident.** Rora never boasts. The work speaks. No superlatives, no hype words, no "best in class." Confidence shows up in specificity and restraint — in what is not said as much as what is.

**Straight-talking.** Plain English, always. If a sentence sounds like it was written for a procurement committee, rewrite it. The reader is a business owner who can smell bullshit from a trade counter. Say what you mean.

**Reliably human.** Warm without being casual. Professional without being cold. Like a skilled tradesperson who shows up on time, does the work, doesn't overpromise. The tone respects the reader's intelligence and their time.

### Six Do/Don't Pairs

| Do | Don't |
|---|---|
| Lead with the problem the reader recognises | Lead with what Rora does or offers |
| Use concrete specifics ("47 minutes per quote") | Make abstract claims ("significant time savings") |
| Use "you / your" throughout | Use "businesses" or "clients" when you mean the reader |
| Write short sentences. Full stops. Then the next thought. | Write long compound sentences with multiple ideas joined by em-dashes and semicolons that eventually lose the point |
| Say what a thing does ("sends the invoice automatically") | Say what powers it ("AI-driven invoice automation") |
| Let the reader reach their own conclusion | Tell the reader what to think ("amazing results", "transformative") |

### Banned Word List

The following are banned from all Rora copy across all channels — website, email, proposals, social, documentation.

Seamless — Robust — Cutting-edge — Streamline — Leverage — Solutions — Powerful — AI-powered — Next-level — Revolutionary — Game-changer — Nurture — Funnel — Onboarding (replace with "getting started") — Synergy — Holistic — Deep dive — Pain points (replace with "problems" or be specific) — ROI (say what it saves/earns specifically) — Innovative — Best-in-class — World-class — Transformative — End-to-end — Scalable (unless describing a specific technical capability) — Ecosystem — Empower — Enable — Facilitate.

---

## 7. Applications

### Email Signature

**Specification:**

```
[Logo image: rora-email-signature.png, 200×60px, links to rorahq.co.uk]

Ryan Wilson
Founder, Rora
07XXX XXXXXX
ryan@rorahq.co.uk
rorahq.co.uk
```

- Logo image: cream background, mark + wordmark, navy, 200×60px PNG
- Image linked to rorahq.co.uk
- Plain text below image (renders even when images are blocked)
- Font in email client: system default (do not specify a custom font in email signatures — it won't render)
- No banner image, no tagline, no social icons, no legal disclaimer unless legally required

### LinkedIn Profile Banner

**Dimensions:** 1584×396px (LinkedIn recommended)  
**Layout:** Cream (#F5F2ED) background. Logo (mark + wordmark) left-aligned, vertically centred, at approximately 200px wide. Tagline "Your business, running in the background." right-aligned, vertically centred, in navy, Söhne/Satoshi Regular, 24px.  
**Do not:** Use a photographic background. Add decorative elements. Include contact details (LinkedIn provides these).

### Invoice Header

**Layout:** Logo (mark + wordmark) top-left, approximately 160px wide. Company details right-aligned: Pier 7 Projects Ltd, Blackpool, Lancashire. VAT number (if registered). Company number 12894305.  
**Colours:** Navy on white/cream. No coral in invoice context.  
**Font:** Söhne/Satoshi for the logo. System font (Arial or similar) for the invoice body — do not embed custom fonts in PDF invoices as they increase file size and reduce compatibility.

### Proposal Cover

**Layout:** Full cream page. Logo centred, approximately 240px wide, positioned in the upper third of the page. Proposal title centred below logo, Söhne Regular 28px navy. Client name and date centred below title, 18px navy. No imagery. No decorative elements. A single 1px navy rule between the logo and the title is acceptable.

---

## 8. Dos and Don'ts

### 5 Dos

**Do use generous whitespace to establish credibility.**  
A page with breathing room signals that Rora doesn't need to cram in features and benefits. It signals patience and craft. Leave more space than feels comfortable — the discomfort usually means you're getting it right.

**Do lead every piece of copy with the problem.**  
Before any description of what Rora does, name the problem the reader is already living. "Every quote takes the best part of an hour" before "Rora cuts that to four minutes." The problem makes the solution legible.

**Do use the approved typeface at all approved weights — and only those.**  
Söhne Regular. That's the decision. It applies to headlines, body, captions, nav, buttons. Consistency in a single weight creates a more distinctive visual identity than a five-weight system used inconsistently.

**Do apply coral to exactly one element per view.**  
Coral earns its power through rarity. On a button, it says: this is the action. On the logo mark, it says: this is Rora. On both at the same time, it says nothing. One element per view. Apply, then stop.

**Do use real product screenshots wherever possible.**  
The quote flow, the automation pipeline, the lead inbox — these are the most compelling images Rora has. They show what the product does without making a claim. A real screenshot is worth twenty descriptive paragraphs.

---

### 5 Don'ts

**Don't use gradients on any element.**  
Not on buttons. Not on backgrounds. Not on text. Not on the logo. Gradients are the primary visual signal of the SaaS aesthetic Rora is explicitly rejecting. A navy button with a gradient becomes a periwinkle SaaS button. Keep it flat.

*Wrong:* A button with a navy-to-blue gradient background.  
*Right:* A flat navy (#1B2430) button with white text.

**Don't open a section with a rhetorical question.**  
"Tired of doing everything yourself?" "Wish you had more time?" These questions are a cliché of marketing copy. They feel manipulative to an ICP that has seen a hundred of them. Open with a statement that names the problem directly — no question mark needed.

*Wrong:* "Struggling to keep up with your admin?"  
*Right:* "Most of the admin in your business follows the same pattern, every time."

**Don't use more than two levels of type hierarchy on one page section.**  
A headline and body copy. That's it. No sub-headline plus body plus caption plus pull quote all competing for attention. Pick the hierarchy that serves the content, then commit to it.

*Wrong:* A services section with a 40px header, a 24px sub-header, 18px body copy, and a 14px caption — all within six lines.  
*Right:* A 40px section header, then 18px body copy. The whitespace between them does the rest.

**Don't use stock photography of people.**  
Not even "authentic-looking" stock. Not Unsplash photography of smiling tradespeople. Not a team photo from a stock library. Rora's ICP will recognise it and the trust signal collapses. Use real screenshots, real environments, or no image at all.

*Wrong:* A hero section with a stock photo of an electrician looking at a tablet.  
*Right:* A hero section with Rora's actual quoting interface screenshotted on a cream background.

**Don't add social proof numbers you cannot verify.**  
"Hundreds of businesses", "97% satisfaction", "10,000 hours saved" — these are claims that invite scepticism and cannot be backed up at Rora's current scale. The honest position is early-stage with a small number of clients who have real results. Name them. Quote them. Measure and cite specifically. The specificity of real data is more convincing than the scale of invented data.

*Wrong:* "Join hundreds of businesses automating with Rora."  
*Right:* "Quote time dropped from 47 minutes to 4. That's from Wilsons' first month."

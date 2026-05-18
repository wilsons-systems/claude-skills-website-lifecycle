# Rora — On-Page SEO Audit

**Skill:** `seo-onpage`  
**Date:** May 2026  
**Scope:** All 7 main pages + top 3 sector pages  
**Status:** Audit complete — rewrites ready to implement

---

## Audit method

For each page: score current title/meta/H1 against keyword intent, then provide the replacement. Priority: Critical (blocks ranking), Important (significant impact), Nice-to-have (polish).

---

## Page 1 — Homepage (`/`)

**Target query:** "AI consultant Lytham St Annes" / "AI automation small business Lancashire"

**Current title tag:**
> Rora — AI Automation for Small Businesses

**Assessment:** No geo. No specific audience signal. Generic.

**New title tag:**
> Rora — AI Automation for Small Businesses | Lytham St Annes, Lancashire

**Current meta description:**
> *(likely auto-generated or missing)*

**New meta description:**
> We built AI systems for our own 6-person trades business — cut quote time by 75%, automated lead capture, cleared a 50-invoice backlog. Now we do the same for small businesses across the Fylde Coast and Lancashire. Free assessment →

**Current H1:**
> Your business, running in the background.

**Assessment:** ✅ Keep as-is. This is the headline, not the SEO H1 — but as the hero, it's fine. Add a visually-hidden SEO-oriented H1 before the hero, or ensure the page description in the metadata section carries the keyword weight.

**Internal linking opportunities:**
- Link "Free AI Assessment" in hero CTA to `/assessment`
- Link service mentions ("quotes", "lead capture", "invoicing") to `/what-we-build` specific sections
- Link the Wilsons case study to `/case-studies`

**Priority: Critical** — geo terms completely missing from title.

---

## Page 2 — Services / What We Build (`/what-we-build`)

**Target query:** "AI automation for small business UK" / "automate quotes trades"

**Current title tag:**
> What We Build — Rora

**New title tag:**
> AI Automation for Trades & Small Businesses — What Rora Builds

**Current meta description:**
> *(missing or generic)*

**New meta description:**
> Lead capture, quote automation, invoice chasing, custom admin tools — built for real small businesses. From one workflow to your entire operation. See what we build and what it costs.

**Current H1:**
> What We Build

**New H1 (update `<h1>` in page component):**
> AI automation for trades businesses and local SMBs

**Internal linking:**
- Each service section should link to the relevant sector page (e.g. "If you're a trades business →" to `/ai-for-electricians`)
- Link to `/assessment` ("Not sure what you need? Start with the free assessment")

**Priority: Important**

---

## Page 3 — Pricing (`/pricing`)

**Target query:** "AI automation pricing UK" / "how much does AI automation cost small business"

**Current title tag:**
> Pricing — Rora

**New title tag:**
> AI Automation Pricing for Small Businesses — Rora

**New meta description:**
> Most clients start from £150/month. No lock-in, no long contracts. See what's included and what to expect — or start with a free AI assessment and we'll scope it for your business.

**H1 (currently likely "Pricing" or "Our Packages"):**

**New H1:**
> What AI automation costs — and what you get for it

**FAQ section additions (for FAQ schema in Step 8):**
Add these explicitly as `<details>` or accordion items so they can receive FAQ schema:
- "How much does AI automation cost for a small business?"
- "Is there a contract or minimum term?"
- "What's included in the monthly fee?"
- "Can I start with just one automation?"
- "What if it doesn't work for my business?"

**Priority: Important**

---

## Page 4 — About (`/about`)

**Target query:** "AI consultant Lytham St Annes" / "Rora AI" + brand searches

**Current title tag:**
> About — Rora

**New title tag:**
> About Rora — AI Automation Consultancy | Lytham St Annes

**New meta description:**
> Ryan Wilson is a NICEIC electrician from Lytham St Annes who automated his own 6-person trades business with AI — and now does the same for local businesses across the Fylde Coast, Preston, and Lancashire.

**H1 (likely "About" or "About Rora"):**

**New H1:**
> Built by a trades business owner, for trades business owners

**Content improvements:**
- Add explicit mention of Lytham St Annes as base location
- Add service area mention: "Serving businesses across the Fylde Coast, Preston, and Lancashire"
- Add Ryan's photo (highest single conversion gap — see voice audit)
- Add company details: Pier 7 Projects Ltd, Co. No. 12894305

**Priority: Critical** — currently no geo signals on About page.

---

## Page 5 — Case Studies (`/case-studies`)

**Target query:** "AI automation case study UK trades" / "Simpro automation results"

**Current title tag:**
> Case Studies — Rora

**New title tag:**
> AI Automation Case Studies — Real Results for UK Trades Businesses | Rora

**New meta description:**
> How a 6-person electrical business cut quote time from 47 minutes to 12, automated overnight lead capture, and cleared a 50-invoice backlog with AI. Real numbers, real business.

**H1:**

**New H1:**
> What AI automation actually delivers — real case studies

**Content notes:**
- Olive Tree case study: add real numbers once Ryan has them (month 1 email automation results)
- Wilsons card should show all 4 metrics (quote time, invoice backlog, leads, hours saved)
- Add a "This is our own business" badge/note to the Wilsons card — it's the strongest trust signal on the site

**Priority: Important**

---

## Page 6 — Contact (`/contact`)

**Target query:** "AI automation consultant Lytham St Annes contact" / brand navigational

**Current title tag:**
> Contact — Rora

**New title tag:**
> Contact Rora — AI Automation for Fylde Coast & Lancashire Businesses

**New meta description:**
> Get in touch with Rora. Based in Lytham St Annes, serving businesses across Preston, Blackpool, and Lancashire. Or start with a free AI assessment — no call required.

**H1:**

**New H1:**
> Get in touch

*(H1 can stay simple on contact pages — the title/meta carry the keyword weight)*

**Content improvements:**
- Add "Based in Lytham St Annes, Fylde Coast" somewhere visible on the page
- Add company registration to footer if not already there
- Once WhatsApp Business number is confirmed: restore WhatsApp link

**Priority: Important**

---

## Page 7 — Free Assessment (`/assessment`)

**Target query:** "free AI assessment small business UK" / "AI readiness check"

**Current title tag:**
> Free AI Assessment — Rora

**New title tag:**
> Free AI Readiness Assessment for Small Businesses — Rora

**New meta description:**
> 13 questions. 3 minutes. Get a personalised AI readiness report showing exactly where AI could help your business and what it would cost. Free — no sales call required.

**H1:**

**New H1:**
> Find out how AI-ready your business is — free assessment

**Content improvements:**
- Add "No sales call required to get your report" copy near the submit button
- Add a brief "What you'll get" list before the quiz starts:
  - Your AI readiness score (0–100)
  - 3 specific recommendations for your business
  - Indicative costs
  - Honest assessment of what's viable

**Priority: Important**

---

## Sector Page 1 — AI for Electricians (`/ai-for-electricians`)

**Target query:** "AI for electricians UK" / "Simpro automation" / "AI quote generator for electricians"

**Current title tag:**
> AI for Electricians — Rora

**New title tag:**
> AI Automation for Electricians | Simpro Integration & Quote Generation — Rora

**New meta description:**
> We built AI quote generation and lead automation for our own electrical business. Cut quote time from 47 minutes to 12. Automated lead capture from Gmail and WhatsApp. Works with Simpro. Free assessment →

**H1:**

**New H1:**
> AI automation for electrical contractors — built by one of us

**Content expansion (currently thin — needs this):**
- Add Simpro integration section: "The only AI consultancy with deep Simpro expertise"
- Explain the voice-to-quote workflow specifically for electricians
- Add a "What Simpro automation looks like" walkthrough (3 steps)
- Link to Wilsons case study

**Priority: Critical** — this is the highest-intent sector page and the most differentiated content Rora has. Currently too thin to rank.

---

## Sector Page 2 — AI for Plumbers (`/ai-for-plumbers`)

**New title tag:**
> AI Automation for Plumbers and Heating Engineers — Rora

**New meta description:**
> Lead capture, quote automation, and job management AI for plumbing businesses. Works with ServiceM8, Simpro, or your existing system. See what changes — free assessment included.

**H1:**
> AI for plumbers — less admin, more jobs

**Priority: Nice-to-have** (electricians page first)

---

## Sector Page 3 — AI for Builders (`/ai-for-builders`)

**New title tag:**
> AI Automation for Builders and Construction Businesses — Rora

**New meta description:**
> Quote generation, subcontractor communication, project admin — we automate the parts of a building business that eat time. Plain English, no IT department needed. Free assessment →

**H1:**
> AI for builders — from first enquiry to final invoice

**Priority: Nice-to-have** (electricians page first)

---

## Implementation summary

| Page | Change | Priority |
|---|---|---|
| Homepage | Add geo terms to title tag | 🔴 Critical |
| About | New title, meta, H1 + geo content | 🔴 Critical |
| /ai-for-electricians | New title, meta, H1 + expand Simpro content | 🔴 Critical |
| Pricing | New title, meta, H1 + FAQ items | 🟡 Important |
| What We Build | New title, meta, H1 | 🟡 Important |
| Case Studies | New title, meta, H1 + real numbers | 🟡 Important |
| Contact | New title, meta + geo mention | 🟡 Important |
| Assessment | New title, meta, H1 + pre-quiz copy | 🟡 Important |
| Plumbers / Builders | New title, meta, H1 | 🟢 Nice-to-have |

**How to implement in Next.js 15:**
Each page's `export const metadata` object in the page component. Update `title`, `description`, and ensure `openGraph.title` and `openGraph.description` are also updated (they were added in the April 27 SEO pass but need updating with the new copy).

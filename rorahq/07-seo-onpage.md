# Rora — On-Page SEO Audit
**File:** `07-seo-onpage.md`
**Status:** Production-ready — implement before first Google Search Console submission
**Scope:** All key pages. Based on current site structure and known content.
**Note:** Where current state is marked "assumed", verify against live site before implementing.

---

## Page Audit Table

### 1. Homepage (/)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Assumed: "Rora — AI Automation" or similar | `Rora — AI Automation for UK Small Businesses` (48 chars) |
| Meta description | Unknown/assumed missing | `We automate the admin that eats your day — leads, quotes, invoices, and more. Built in Blackpool. Book a free assessment.` (124 chars) |
| H1 | "Your business, running in the background." | Keep. This is locked and works. Ensure it's an H1 tag, not styled div. |
| Internal links | Assumed: nav links to all pages | Add in-body links to /what-we-build, /assessment, /case-studies from relevant sections |
| Schema | None (blocked by hookify) | LocalBusiness JSON-LD — see 08-seo-technical.md |
| Image alt text | Unknown | Any hero image: "Rora AI automation dashboard — Blackpool SMB" |

---

### 2. What We Build / Services (/what-we-build)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `AI Automation Services for UK Businesses — Rora` (49 chars) |
| Meta description | Unknown | `Lead capture, quoting, invoicing, AI websites — we build and run your automations from £1,500. Free assessment available.` (122 chars) |
| H1 | "From your first lead to your last invoice — we can automate the lot." | Good. Keep. Verify it's an H1 tag. |
| Internal links | Unknown | Link to /pricing (pricing anchor), /assessment (CTA), relevant sector pages from each service card |
| Schema | None | Service schema — one per main service offering |
| Image alt text | Unknown | Service icons: "AI lead capture automation for trades businesses" |

---

### 3. Pricing (/pricing)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `Rora Pricing — AI Automation for UK SMBs` (42 chars) |
| Meta description | Unknown | `AI Automation from £1,500 + £200/mo. AI Website from £1,500 + £150/mo. Transparent pricing, no hidden costs. See what's included.` (131 chars) |
| H1 | Unknown | `Straightforward pricing. No surprises.` |
| Internal links | Minimal assumed | Link to /what-we-build (what's included detail), /assessment (can't decide CTA), /contact (custom quote) |
| Schema | None | FAQPage JSON-LD — see FAQ section below |
| Image alt text | N/A (pricing tables) | N/A |

---

### 4. About (/about)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `About Rora — AI Consultant, Blackpool` (38 chars) |
| Meta description | Unknown | `Ryan Wilson built AI automation for his own electrical business. Now he does it for yours. Based in Blackpool, working UK-wide.` (127 chars) |
| H1 | Unknown | `AI automation consultant, Blackpool — built it for ourselves first.` |
| Internal links | Minimal | Link to /case-studies (proof), /assessment (next step), /what-we-build (services) |
| Schema | None | Person schema (Ryan Wilson) + LocalBusiness |
| Image alt text | Ryan's photo missing | When added: "Ryan Wilson, founder of Rora — AI automation consultant, Blackpool" |

**Note:** Ryan's photo is the highest single conversion gap on this page. A clear headshot with accurate alt text also contributes to E-E-A-T signals for Google. See 08-seo-technical.md item 11.

---

### 5. Case Studies (/case-studies)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `AI Automation Case Studies — Rora` (34 chars) |
| Meta description | Unknown | `See how Rora cut quote time by 75% and cleared a 50-invoice backlog in month 1. Real results for UK trades businesses.` (120 chars) |
| H1 | Unknown | `What it actually looks like in a real business.` |
| Internal links | Unknown | Link back to relevant sector pages (/ai-for-electricians from Wilsons), /contact (enquiry CTA), /pricing |
| Schema | None | Article or ItemList schema for case study cards |
| Image alt text | Unknown | "Wilsons Systems electrical — before and after AI automation with Rora" |

---

### 6. Contact (/contact)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `Contact Rora — AI Automation Consultant, Blackpool` (51 chars) |
| Meta description | Unknown | `Get in touch with Rora. Based in Blackpool, working across Lancashire and the UK. Free 30-minute call — no commitment needed.` (125 chars) |
| H1 | Unknown | `Let's talk. No hard sell, no jargon.` |
| Internal links | Minimal | Link to /assessment (for those not ready to call), /about (who you're contacting) |
| Schema | None | LocalBusiness (address, phone, email) |
| Image alt text | N/A | N/A |

---

### 7. Free Assessment (/assessment)

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `Free AI Assessment for UK Businesses — Rora` (44 chars) |
| Meta description | Unknown | `13 questions. 13 minutes. Get your personalised AI Readiness Report — free. Find out exactly where automation would help.` (122 chars) |
| H1 | Unknown | `Find out if your business is ready for AI — in 13 minutes.` |
| Internal links | Minimal | Link back to /what-we-build (what we'd actually do), /pricing (cost context) |
| Schema | None | FAQPage — common questions about the assessment process |
| Image alt text | N/A (quiz interface) | N/A |

---

### 8. /ai-for-electricians

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `AI Automation for Electricians UK — Rora` (41 chars) |
| Meta description | Unknown | `Stop losing quotes and leads to manual admin. Rora automates your quoting, invoicing, and lead capture. Built for UK electricians.` (131 chars) |
| H1 | Unknown | `AI automation for electricians — built by one, run for all.` |
| Internal links | Minimal | Link to /case-studies (Wilsons Systems proof), /assessment, /pricing |
| Schema | None | Service schema + LocalBusiness |
| Image alt text | Unknown | "Electrician using automated quoting system on mobile — Rora AI" |

---

### 9. /ai-for-plumbers

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `AI Automation for Plumbers UK — Rora` (37 chars) |
| Meta description | Unknown | `Automate your quotes, leads, and invoices. Rora builds AI systems for UK plumbers — so you spend less time on admin and more time on jobs.` (139 chars) |
| H1 | Unknown | `AI automation for plumbers — less admin, more jobs.` |
| Internal links | Minimal | Link to /assessment, /what-we-build, /pricing |
| Schema | None | Service schema |
| Image alt text | Unknown | "Plumber checking automated invoice system on phone — Rora AI automation" |

---

### 10. /ai-for-builders

| Element | Current State | Recommendation |
|---|---|---|
| Title tag | Unknown | `AI Automation for Builders UK — Rora` (37 chars) |
| Meta description | Unknown | `Builders spend hours on quotes, chasing invoices, and managing leads. Rora automates the lot — from £1,500. Free assessment available.` (135 chars) |
| H1 | Unknown | `AI automation for builders — your office runs itself.` |
| Internal links | Minimal | Link to /ai-for-construction (related), /assessment, /pricing |
| Schema | None | Service schema |
| Image alt text | Unknown | "Builder reviewing automated quoting workflow on tablet — Rora AI" |

---

## TOP 3 PRIORITY FIXES (Expanded Notes)

### Priority 1: /about Page — Title, H1, and Ryan's Photo Alt Text

**Why this is top priority:**
The /about page is where local intent searches land ("AI consultant Blackpool") and where prospective clients decide if they trust the person behind the business. Both Google and humans need the same thing from this page: a clear signal that a real, expert, local person runs this business.

**Specific fixes:**

1. Set the title tag to: `About Rora — AI Consultant, Blackpool` (38 chars, includes primary local keyword)
2. Write the H1 as: `AI automation consultant, Blackpool — built it for ourselves first.` — this gives Google a clear keyword signal without it reading like keyword stuffing.
3. First 100 words of body copy must include: "Blackpool", "AI automation", and Ryan's name. These are the three signals Google needs to confirm local relevance.
4. Meta description must include: "Blackpool", a result (75% reduction in quote time), and a CTA.
5. When Ryan's photo is added (see 08-seo-technical.md item 11), the alt text must be: `Ryan Wilson, founder of Rora — AI automation consultant, Blackpool`. No generic "profile photo" or "headshot" alt text — Google reads this as part of E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness).

---

### Priority 2: Pricing Page — FAQ Schema and Meta Description

**Why this is second priority:**
The pricing page is the highest-intent page after the contact page. Anyone who reaches it is actively evaluating buying. Two things hurt conversion and rankings here: no schema (missed rich snippet opportunity) and an unknown/weak meta description (low click-through rate from search results).

**Specific fixes:**

1. Rewrite the meta description to include a price anchor: `AI Automation from £1,500 + £200/mo. AI Website from £1,500 + £150/mo. Transparent pricing, no hidden costs.`
2. Add FAQ schema (full JSON-LD in the FAQ section below). This makes Rora eligible for Google's FAQ rich results — free expanded real estate in search.
3. Ensure the H1 is "Straightforward pricing. No surprises." — leads with the reassurance buyers need before they even read the numbers.
4. Add 3 internal links from the pricing page: to /what-we-build (for detail), to /assessment (for those undecided), and to /contact (for custom enquiries).

---

### Priority 3: Homepage — H1 Tag Verification and Internal Link Depth

**Why this is third priority:**
The headline is locked and strong. But if it's rendered as a styled `<div>` or `<p>` rather than an actual `<h1>` tag, Google treats the page as having no H1 — a basic on-page failure that limits ranking ability.

**Specific fixes:**

1. Inspect the homepage HTML and confirm the headline "Your business, running in the background." is wrapped in `<h1>` tags (not `<div class="text-4xl">` or similar). If not — change the element, not the style.
2. Add in-body text links (not just nav links) to: /what-we-build (from the Solution section), /case-studies (from the Proof section), and /assessment (from the CTA section). Google values contextual links within body copy more than nav links.
3. Confirm the meta description is set and under 155 characters. The current sub-headline is 38 words — good for users, too long for a meta description. They need to be separate.

---

## FAQ PAGE RECOMMENDATION

### Add FAQ Section to Pricing Page

Add a visible FAQ section at the bottom of `/pricing` with schema markup. This serves two purposes: it answers the objections that prevent conversion, and it gives Rora eligibility for Google FAQ rich results (additional search real estate at no cost).

### 6 FAQ Pairs (Pricing Page)

**Q1: What's included in the £1,500 setup fee?**
The setup fee covers the full build: scoping, configuration, integration with your existing tools, testing, and handover. You get a working automation from day one — not a template that needs configuring.

**Q2: What does the monthly fee pay for?**
Ongoing hosting, monitoring, and support. If something breaks, we fix it. If you need a small change, we handle it. The monthly fee keeps your automation running and keeps us available when you need us.

**Q3: How long does setup take?**
Most businesses have a working automation within 48 hours of the initial call. Complex builds with multiple integrations take up to two weeks. We'll tell you the exact timeline before you commit.

**Q4: Can I start with just one automation?**
Yes. Most clients do. We'll identify the one thing that saves you the most time first — usually lead capture or quoting — and start there. You can add more automations as your business grows.

**Q5: Do I need to sign a long-term contract?**
No. The monthly retainer is month-to-month. If you want to pause or stop, you can. The automations we've built remain yours — we'll hand over documentation so you know what you've got.

**Q6: What if I already use Simpro, Xero, or another system?**
We work with them. Rora connects your existing tools — it doesn't replace them. If you're already using Simpro, Xero, or Google Workspace, we build around what you have, not over it.

---

### FAQ Schema JSON-LD — Ready to Paste

Add this inside a `<script type="application/ld+json">` tag on the `/pricing` page. Note: requires hookify `application/ld+json` exception to be active first (see 08-seo-technical.md item 1).

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What's included in the £1,500 setup fee?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "The setup fee covers the full build: scoping, configuration, integration with your existing tools, testing, and handover. You get a working automation from day one — not a template that needs configuring."
      }
    },
    {
      "@type": "Question",
      "name": "What does the monthly fee pay for?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Ongoing hosting, monitoring, and support. If something breaks, we fix it. If you need a small change, we handle it. The monthly fee keeps your automation running and keeps us available when you need us."
      }
    },
    {
      "@type": "Question",
      "name": "How long does setup take?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Most businesses have a working automation within 48 hours of the initial call. Complex builds with multiple integrations take up to two weeks. We'll tell you the exact timeline before you commit."
      }
    },
    {
      "@type": "Question",
      "name": "Can I start with just one automation?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Most clients do. We'll identify the one thing that saves you the most time first — usually lead capture or quoting — and start there. You can add more automations as your business grows."
      }
    },
    {
      "@type": "Question",
      "name": "Do I need to sign a long-term contract?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No. The monthly retainer is month-to-month. If you want to pause or stop, you can. The automations we've built remain yours — we'll hand over documentation so you know what you've got."
      }
    },
    {
      "@type": "Question",
      "name": "What if I already use Simpro, Xero, or another system?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "We work with them. Rora connects your existing tools — it doesn't replace them. If you're already using Simpro, Xero, or Google Workspace, we build around what you have, not over it."
      }
    }
  ]
}
```

---

## IMAGE ALT TEXT GUIDANCE

Write alt text that describes what the image shows and who it's for — not what it looks like. "Ryan Wilson, Rora founder, reviewing an automation workflow on a laptop" is useful. "Photo of a man at a desk" is not. Avoid keyword stuffing in alt text (e.g., "AI automation Blackpool Lancashire AI consultant Ryan Wilson") — Google treats this as spam and it fails accessibility guidelines. One clear, descriptive sentence per image is enough.

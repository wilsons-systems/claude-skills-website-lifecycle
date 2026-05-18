# Rora — Technical SEO Fix Checklist
**File:** `08-seo-technical.md`
**Status:** Production-ready — work through in order. Items 1–4 are search prerequisites; do not defer.
**Site:** rorahq.co.uk — Next.js 15, Vercel, Cloudflare DNS
**Code repo:** wilsons-systems/ai-consultancy-web

---

## How to Use This Checklist

Work through items in order. Items 1–4 are hard prerequisites for Google indexing and local discovery — none of the other SEO work matters until these are done. Items 5–12 are conversion and compliance improvements that can be batched.

Mark each item complete with [x] when done.

---

## ITEM 1 — JSON-LD LocalBusiness Schema

**What it is:** Structured data that tells Google exactly what Rora is, where it is, and what it does. Without it, Google has to guess from body text. With it, Rora becomes eligible for Knowledge Panel display, local pack results, and rich snippets.

**Why it matters:** LocalBusiness schema is the single most impactful structured data addition for a local service business. It directly improves local search visibility and is required for Google Business Profile integration to work at its best.

**Current blocker:** Hookify security hook blocks `<script type="application/ld+json">`. Fix this first.

### Step 1: Fix hookify config

In your hookify security configuration, add `application/ld+json` to the allowed script types list. The exact config key depends on your hookify version — look for a `allowedScriptTypes`, `scriptTypeWhitelist`, or `csp.scriptTypes` key. Add `"application/ld+json"` to the array. This does not introduce a security risk — JSON-LD is not executable JavaScript.

### Step 2: Create the schema component

Create a new file at `app/schema.tsx`:

```tsx
export function LocalBusinessSchema() {
  const schema = {
    "@context": "https://schema.org",
    "@type": "LocalBusiness",
    "name": "Rora",
    "alternateName": "Rora AI Consultancy",
    "description": "AI automation consultancy for UK small businesses. We automate lead capture, quoting, invoicing, and admin — so your business runs faster, 24/7.",
    "url": "https://rorahq.co.uk",
    "telephone": "[PHONE_PLACEHOLDER]",
    "email": "ryan@rorahq.co.uk",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "Blackpool",
      "addressRegion": "Lancashire",
      "addressCountry": "GB"
    },
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": "53.8175",
      "longitude": "-3.0357"
    },
    "areaServed": [
      {
        "@type": "City",
        "name": "Blackpool"
      },
      {
        "@type": "AdministrativeArea",
        "name": "Fylde Coast"
      },
      {
        "@type": "AdministrativeArea",
        "name": "Lancashire"
      },
      {
        "@type": "Country",
        "name": "United Kingdom"
      }
    ],
    "serviceType": [
      "AI Automation Consultancy",
      "Business Process Automation",
      "AI-Powered Website Development",
      "Lead Capture Automation",
      "Invoice Automation",
      "CRM Integration"
    ],
    "founder": {
      "@type": "Person",
      "name": "Ryan Wilson"
    },
    "legalName": "Pier 7 Projects Ltd",
    "priceRange": "££",
    "openingHoursSpecification": {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "18:00"
    }
  };

  return (
    <script
      type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify(schema) }}
    />
  );
}
```

### Step 3: Add to layout

In `app/layout.tsx`, import and render inside `<head>`:

```tsx
import { LocalBusinessSchema } from './schema';

// Inside the <head> section:
<LocalBusinessSchema />
```

**Replace `[PHONE_PLACEHOLDER]` when the WhatsApp Business number is confirmed.**

---

## ITEM 2 — FAQ Schema on Pricing Page

**What it is:** Structured data that marks up FAQ content so Google can display it as expandable Q&A directly in search results — giving Rora more screen space without a higher ranking.

**Why it matters:** FAQ rich results are free additional visibility. For a pricing page specifically, they pre-answer objections before the user even clicks — which improves click-through rate and pre-qualifies visitors.

**Prerequisite:** Item 1 hookify fix must be complete.

### Implementation

Add to `app/pricing/page.tsx` (or the relevant pricing route):

```tsx
export function PricingFAQSchema() {
  const schema = {
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
  };

  return (
    <script
      type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify(schema) }}
    />
  );
}
```

Add `<PricingFAQSchema />` inside the `<head>` section of the pricing page, or render it in the page component and let Next.js handle placement.

Verify the schema at: https://search.google.com/test/rich-results

---

## ITEM 3 — Google Business Profile

**What it is:** A free Google listing that shows Rora in local search results, Google Maps, and the Knowledge Panel on the right side of search. For local service businesses, this is often more valuable than the website at this stage.

**Why it matters:** A verified Google Business Profile is the single fastest path to appearing when someone in Blackpool or Lancashire searches for an AI consultant. It also feeds reviews, photos, and business information directly into Google Search. Do not delay this.

**Estimated time:** 15 minutes to create, ~2 weeks to receive the verification postcard.

### Exact Steps

1. Go to https://business.google.com
2. Sign in with the Google account that will manage Rora's business presence (ideally a dedicated Google Workspace account, not a personal Gmail).
3. Click "Manage now" or "Add your business."
4. Enter the business name: **Rora**
5. Choose the primary category: **Business Management Consultant** (most accurate available — do not use "Software Company" or "IT Company").
6. Secondary categories to add: **Marketing Consultant**, **Computer Consultant**
7. Select "I deliver goods and services to my customers" — Rora is a service-area business, not a walk-in premises.
8. Set your service area:
   - Blackpool
   - Fylde
   - Lancashire
   - (optionally: "United Kingdom" for national reach)
9. Add phone number (once confirmed WhatsApp Business number is live).
10. Add website: https://rorahq.co.uk
11. Choose verification method: **Postcard by mail**. Enter the Blackpool address. Postcard arrives in approximately 2 weeks.

### After Verification

- Add all services: AI Automation, AI-Powered Website, Monthly AI Retainer, Free AI Assessment.
- Write a business description (use this copy): "Rora is an AI automation consultancy based in Blackpool. We help UK small businesses automate their admin — lead capture, quoting, invoicing, and more. Built by Ryan Wilson, who cut his own quote time by 75% before doing the same for clients."
- Upload at minimum: logo, a cover photo, and Ryan's headshot.
- Set business hours.
- Enable messaging (Google Business messaging connects to Gmail or the GBP app).

**Do not skip this item.** It is more important for local search visibility than any code change on the website.

---

## ITEM 4 — Google Search Console: Sitemap Submission

**What it is:** Google Search Console is the tool Google provides to monitor how it crawls and indexes your site. Submitting the sitemap tells Google exactly which pages exist and should be indexed.

**Why it matters:** Without sitemap submission, Google relies entirely on discovering pages through links. New sites with few external links can take months to be fully indexed. Submitting the sitemap can reduce this to days.

**Prerequisite:** DNS access to Cloudflare (for verification).

### Exact Steps

1. Go to https://search.google.com/search-console
2. Click "Add property."
3. Choose "Domain" (not "URL prefix") and enter: `rorahq.co.uk`
4. Google will display a DNS TXT record to add — copy it. It looks like: `google-site-verification=XXXXXXXXXXXXX`
5. Go to Cloudflare DNS for rorahq.co.uk.
6. Add a new TXT record:
   - Name: `@`
   - Content: the full verification string from Google
   - TTL: Auto
7. Return to Google Search Console and click "Verify." DNS propagation is usually instant on Cloudflare.
8. Once verified, go to **Sitemaps** in the left sidebar.
9. Enter: `https://rorahq.co.uk/sitemap.xml`
10. Click "Submit."

### After Submission

- Check that the sitemap returns a 200 status and is valid XML. Visit https://rorahq.co.uk/sitemap.xml in a browser — it should list all key pages.
- In Search Console, check "Coverage" after 24–48 hours to see if any pages are being excluded or throwing errors.
- If any pages appear as "Excluded > Noindex", check that `robots.txt` and the Next.js metadata config are not accidentally noindexing production pages.

---

## ITEM 5 — OG Image Colour Update

**What it is:** The Open Graph (OG) image is what appears when a link to rorahq.co.uk is shared on social media, WhatsApp, or iMessage. Currently, it uses an old periwinkle background (#6C8EEF) which no longer matches the brand.

**Why it matters:** Every shared link is a brand impression. The wrong colours undermine credibility and visual consistency — especially important when sending a link to a potential client.

**File to edit:** `app/opengraph-image.tsx`

### Exact Change

Locate the background colour value. It will look something like:

```tsx
// Current (old periwinkle):
style={{ background: '#6C8EEF' }}
// or
fill="#6C8EEF"
// or
backgroundColor: '#6C8EEF'
```

Replace with:

```tsx
// Updated (navy):
style={{ background: '#1B2430' }}
// or
fill="#1B2430"
// or
backgroundColor: '#1B2430'
```

For text/foreground elements, ensure text colour is set to cream `#F5F2ED`:

```tsx
// Text colour:
color: '#F5F2ED'
```

The complete updated ImageResponse should produce: navy `#1B2430` background, cream `#F5F2ED` text, Rora wordmark and tagline.

After editing, clear Cloudflare cache and verify the new image appears at: https://rorahq.co.uk/opengraph-image

Test share previews at: https://developers.facebook.com/tools/debug/ and https://cards-dev.twitter.com/validator

---

## ITEM 6 — Container Width Mismatch

**What it is:** The site navigation uses `max-w-6xl` (72rem / 1152px) while content areas use `max-w-7xl` (80rem / 1280px). This creates a visible misalignment: content extends 128px wider than the nav on large screens, breaking visual alignment.

**Why it matters:** This is a layout integrity issue. It looks unpolished on wide monitors, which is where potential clients reviewing the site on a desktop will notice it. It also affects perceived professionalism.

**File to edit:** `components/layout/nav.tsx`

### Exact Change

Find the nav container element — it will look like:

```tsx
<div className="max-w-6xl mx-auto px-4 ...">
```

Change `max-w-6xl` to `max-w-7xl`:

```tsx
<div className="max-w-7xl mx-auto px-4 ...">
```

One line. One class name. Verify on a wide monitor after deployment that nav and content now align.

---

## ITEM 7 — Skip-to-Content Link

**What it is:** A hidden link that appears only when keyboard users focus it (e.g., pressing Tab on page load). It allows keyboard and screen reader users to skip over the navigation and jump directly to the main content.

**Why it matters:** Required for WCAG 2.1 AA compliance (the UK accessibility standard under the Equality Act 2010). Failing this is both an accessibility issue and a legal risk. It is also a ranking signal — Google's quality guidelines reference accessibility as part of page quality assessment.

**File to edit:** `app/layout.tsx`

### Exact Addition

Add the skip link immediately after the opening `<body>` tag, before `<header>`:

```tsx
<body>
  <a
    href="#main-content"
    className="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 z-50 bg-navy text-cream px-4 py-2 rounded focus:outline-none focus:ring-2 focus:ring-cream"
  >
    Skip to main content
  </a>
  <header>
    {/* existing header/nav */}
  </header>
  <main id="main-content">
    {/* existing main content */}
  </main>
```

If `bg-navy` and `text-cream` are not Tailwind utility classes in your config, replace with inline hex values or the appropriate config class names for `#1B2430` and `#F5F2ED`.

Also add `id="main-content"` to the `<main>` element if it doesn't already have one.

---

## ITEM 8 — Footer Company Registration

**What it is:** Legal identification of the registered company behind Rora. Required under the Companies Act 2006 for all UK companies with a website.

**Why it matters:** Legally required. Also a trust signal — showing a company registration number confirms Rora is a real, verifiable business. This matters to prospective clients who are evaluating a £1,500+ purchase.

**File to edit:** Footer component (likely `components/layout/footer.tsx` or similar).

### Exact Copy to Add

Add this sentence to the footer, in a small text size below the main footer content:

```
Rora is a trading name of Pier 7 Projects Ltd. Company number 12894305. Registered in England and Wales.
```

This should sit alongside (or just below) copyright information. It does not need to be prominent — small text, subdued colour is appropriate — but it must be on every page via the shared footer component.

---

## ITEM 9 — ICO Registration

**What it is:** Registration as a data controller with the Information Commissioner's Office (ICO) under the UK GDPR. If Rora collects any personal data (names, emails, enquiry forms, assessment responses), registration is required.

**Why it matters:** Legally required under the Data Protection Act 2018. Penalty for non-registration: up to £4,000 fine. Cost to register: £52/year (tier 1 — turnover under £632,000). This is not optional.

### Steps to Register

1. Go to https://ico.org.uk/registration
2. Complete the self-assessment — answer "yes" to processing personal data.
3. Select Tier 1 (small businesses/sole traders) — £52/year.
4. Pay by card.
5. You will receive a registration number in the format: **ZA followed by 6 digits** (e.g., ZA123456).
6. The registration is valid for 12 months and must be renewed annually.

### After Registration

Open `app/privacy-policy/page.tsx` and find the ICO_NUMBER placeholder. Replace it with the actual registration number received:

```tsx
// Find:
ICO_NUMBER
// or:
[ICO registration number]

// Replace with your actual number, e.g.:
ZA123456
```

Also add the ICO registration number to the footer alongside the company registration details:

```
ICO registration: ZA123456
```

---

## ITEM 10 — WhatsApp Business Number

**What it is:** Two placeholder links in the codebase (`[WHATSAPP]`) that point to the confirmed WhatsApp Business number — one in the footer and one on the contact page.

**Why it matters:** WhatsApp is the primary contact channel for many trades businesses and hospitality clients. Missing or broken WhatsApp links are a direct conversion loss — a plumber who wants to send a quick message will leave if there's no easy option.

### Steps

1. Set up WhatsApp Business on the confirmed number (if not already done).
2. Search the codebase for `[WHATSAPP]`:

```bash
grep -r "\[WHATSAPP\]" --include="*.tsx" --include="*.ts" .
```

3. Replace each instance with the WhatsApp click-to-chat link format:

```
https://wa.me/44XXXXXXXXXX
```

Where `44XXXXXXXXXX` is the UK number without the leading 0, e.g., `447700900123`.

4. For the link text in the footer, use: `Chat on WhatsApp →`
5. For the contact page, the button should read: `Message us on WhatsApp →`

---

## ITEM 11 — Ryan's Photo (About Page)

**What it is:** A real headshot of Ryan Wilson for the /about page. Currently the page has a placeholder or missing image.

**Why it matters:** This is the single highest-converting missing element on the site. Prospective clients spending £1,500–£2,200+ on an AI system need to trust the person building it. A real face — specifically Ryan's face — converts significantly better than any written claim. Google's E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) guidelines also specifically reward evidence of real people behind a business.

### Photo Specification

- Minimum resolution: 400×400px. 600×600 or higher preferred.
- Format: JPEG or WebP. Name it `ryan-wilson-rora.jpg` (descriptive filenames contribute marginally to image SEO).
- Style: Natural light, neutral or uncluttered background, approachable expression. Business casual — not formal corporate.
- Crop: Circular crop applied in CSS (`rounded-full`). Ensure the face is centred and not cut off.
- Location: `/public/images/ryan-wilson-rora.jpg`

**A phone selfie in good light is better than waiting for a professional shoot.** Do not block the site launch or the About page on this — upload a decent phone photo now and replace with a professional shot later. The absence of any photo is a far bigger problem than an imperfect one.

### Implementation

```tsx
<Image
  src="/images/ryan-wilson-rora.jpg"
  alt="Ryan Wilson, founder of Rora — AI automation consultant, Blackpool"
  width={400}
  height={400}
  className="rounded-full"
/>
```

---

## ITEM 12 — robots.txt Verification

**What it is:** The `robots.txt` file tells search engine crawlers which pages they are and aren't allowed to index. Misconfigured `robots.txt` can accidentally block the entire site from being indexed.

**Why it matters:** If `Disallow: /` is present in production (a common mistake left over from staging config), Google will not index any page. This is silent — no error, just no traffic.

### Verification Steps

1. Visit https://rorahq.co.uk/robots.txt in a browser.
2. Confirm the file contains at minimum:

```
User-agent: *
Disallow: /api/
Allow: /

Sitemap: https://rorahq.co.uk/sitemap.xml
```

3. Confirm:
   - `Disallow: /` is NOT present (this would block the whole site).
   - `/api/*` routes are disallowed (prevents crawling of API endpoints).
   - The sitemap URL is listed.
   - `noindex` is not set in `next.config.js` or in a meta robots tag in `app/layout.tsx` for the production environment.

4. Check for a `<meta name="robots" content="noindex">` tag in the HTML source of the homepage. If present on production, remove it.

### To Check for noindex in Next.js config

In `app/layout.tsx`, look for:

```tsx
export const metadata: Metadata = {
  robots: {
    index: false,  // <-- THIS IS THE PROBLEM
  }
}
```

In production, this should be:

```tsx
robots: {
  index: true,
  follow: true,
}
```

Or simply not set (the default is indexable).

---

## Quick Reference: Priority Order

| # | Item | Effort | Blocks |
|---|---|---|---|
| 1 | JSON-LD LocalBusiness schema | Medium (hookify fix + schema component) | Local search, Knowledge Panel |
| 2 | FAQ schema on pricing page | Low (copy-paste JSON-LD) | Rich results in search |
| 3 | Google Business Profile | Low-medium (15 min setup + 2 week postcard wait) | Local pack, Maps, all local rankings |
| 4 | Google Search Console sitemap | Low (20 min) | Knowing if indexing is working at all |
| 5 | OG image colour | Very low (one CSS value) | Brand consistency on social/WhatsApp shares |
| 6 | Container width mismatch | Very low (one Tailwind class) | Visual polish |
| 7 | Skip-to-content link | Low (copy-paste JSX) | Accessibility compliance |
| 8 | Footer company reg | Very low (one sentence) | Legal compliance |
| 9 | ICO registration | Low (£52, 20 min) | Legal compliance |
| 10 | WhatsApp number | Low (find/replace) | Conversion on contact page |
| 11 | Ryan's photo | Medium (logistics, not code) | Highest single conversion gap |
| 12 | robots.txt verification | Very low (browser check) | Confirms none of the above SEO work is wasted |

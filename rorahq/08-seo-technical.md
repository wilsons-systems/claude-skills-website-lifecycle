# Rora — Technical SEO & Launch Fix Checklist

**Skill:** `seo-technical`  
**Date:** May 2026  
**Status:** Ordered fix list — work top to bottom

---

## Priority 1 — Blockers (fix before promoting the site)

### 1.1 — JSON-LD LocalBusiness Schema

**Why it matters:** Tells Google exactly what Rora is, where it's based, and what it does. Required for local search visibility. Currently blocked by a hookify security hook that prevents script injection patterns.

**Fix:**
Add an exception in hookify for `type="application/ld+json"` script tags. This is a data-only script — no executable code — so the security concern is a false positive.

In hookify config, add:
```js
// Allow JSON-LD structured data scripts (not executable — data only)
allowScriptTypes: ['application/ld+json']
```

Once unblocked, add to `app/layout.tsx` inside `<head>`:

```html
<script
  type="application/ld+json"
  dangerouslySetInnerHTML={{
    __html: JSON.stringify({
      "@context": "https://schema.org",
      "@type": "LocalBusiness",
      "name": "Rora",
      "legalName": "Pier 7 Projects Ltd",
      "url": "https://rorahq.co.uk",
      "logo": "https://rorahq.co.uk/brand/rora-logo.png",
      "description": "AI automation consultancy for small businesses. We automate lead capture, quoting, invoicing, and admin — built by a trades business owner who automated his own business first.",
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Lytham St Annes",
        "addressRegion": "Lancashire",
        "postalCode": "FY8",
        "addressCountry": "GB"
      },
      "geo": {
        "@type": "GeoCoordinates",
        "latitude": 53.7268,
        "longitude": -2.9637
      },
      "areaServed": [
        "Lytham St Annes",
        "Fylde Coast",
        "Preston",
        "Blackpool",
        "Lancashire",
        "United Kingdom"
      ],
      "serviceType": [
        "AI Automation",
        "Business Automation",
        "Lead Capture Automation",
        "Quote Generation",
        "Invoice Automation"
      ],
      "priceRange": "££",
      "foundingDate": "2026",
      "contactPoint": {
        "@type": "ContactPoint",
        "contactType": "customer support",
        "email": "hello@rorahq.co.uk",
        "availableLanguage": "English"
      }
    })
  }}
/>
```

**Status:** ⏳ Blocked by hookify — needs exception first

---

### 1.2 — FAQ Schema (Pricing page)

**Why it matters:** FAQ schema can produce rich results (expanded answers in Google search). Pricing page FAQs are ideal candidates.

**Add FAQ schema to `app/pricing/page.tsx`:**

```html
<script
  type="application/ld+json"
  dangerouslySetInnerHTML={{
    __html: JSON.stringify({
      "@context": "https://schema.org",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How much does AI automation cost for a small business?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most clients start from around £150/month. Setup costs vary by scope — trial builds are free. No long contracts."
          }
        },
        {
          "@type": "Question",
          "name": "Do I need to learn a new system?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. We connect what you already use — your email, quoting software, and calendar. You don't manage the automation. You just see the results."
          }
        },
        {
          "@type": "Question",
          "name": "Is there a minimum contract?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No minimum term after the trial period. If it's not working within 60 days, you don't continue."
          }
        },
        {
          "@type": "Question",
          "name": "What if the automation doesn't work for my business?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "We fix it. We built these systems for our own business — if something's not right, it's our problem to sort, not yours."
          }
        }
      ]
    })
  }}
/>
```

**Status:** ⏳ Same hookify blocker as 1.1

---

### 1.3 — Google Business Profile

**Why it matters:** The #1 local SEO action available. Rora won't appear in "AI consultant near me" or maps results without it. Postcard verification takes 2 weeks — start immediately.

**Steps:**
1. Go to `business.google.com`
2. Create profile: Business name = "Rora", Category = "Business management consultant" (closest match)
3. Address: Lytham St Annes, Lancashire FY8 (use office or home address — this is verified by postcard)
4. Phone: add once available
5. Website: `https://rorahq.co.uk`
6. Description (use this exactly):
   > Rora is an AI automation consultancy for small businesses in the Fylde Coast, Preston, and Lancashire. We automate lead capture, quotes, invoicing, and admin — built by a trades business owner who automated his own 6-person business first. Free AI assessment at rorahq.co.uk.
7. Request postcard verification — allow 2 weeks
8. While waiting: upload logo, add services, add opening hours

**Secondary categories to add:**
- "Information technology consultant"
- "Software company" (if allowed as secondary)

**Status:** 🔴 Not started — start today

---

### 1.4 — Google Search Console

**Why it matters:** Without this, you don't know whether Google can crawl the site, and the sitemap isn't submitted.

**Steps:**
1. Go to `search.google.com/search-console`
2. Add property: `https://rorahq.co.uk` (URL prefix)
3. Verify via HTML tag — add the meta verification tag to `app/layout.tsx`:
   ```jsx
   // In metadata object:
   verification: {
     google: 'YOUR_VERIFICATION_CODE_HERE'
   }
   ```
4. Submit sitemap: `https://rorahq.co.uk/sitemap.xml` (already exists from April 27 session)
5. Check coverage report — ensure 0 indexing errors

**Status:** 🔴 Not started

---

## Priority 2 — Website code fixes (can be batched in one PR)

### 2.1 — OG Image colour (wrong hex)

**File:** `app/opengraph-image.tsx`  
**Issue:** Hardcoded periwinkle hex (#6C8EEF) — predates palette migration  
**Fix:** Update to navy (#1B2430) background with cream (#F5F1EB) text and coral (#C8715A) accent

```tsx
// Change:
background: '#6C8EEF'

// To:
background: '#1B2430'

// Change text colour:
color: '#F5F1EB'
```

---

### 2.2 — Nav/content container mismatch

**Files:** `components/layout/nav.tsx` and page components  
**Issue:** Nav is `max-w-6xl`, content sections are `max-w-7xl` — creates a visible misalignment on wide screens  
**Fix:** Make nav `max-w-7xl` to match content, OR change all content to `max-w-6xl` for a tighter layout

**Recommendation:** Change all to `max-w-6xl`. At 7xl (80rem / 1280px), lines of body text become too long for comfortable reading. 6xl (72rem / 1152px) is the right cap for a consultancy site.

```tsx
// In nav.tsx — change:
className="max-w-6xl mx-auto"

// In all page components — change:
className="max-w-7xl mx-auto"
// To:
className="max-w-6xl mx-auto"
```

---

### 2.3 — Skip-to-content link

**File:** `app/layout.tsx`  
**Why:** Accessibility requirement (WCAG 2.4.1) + small SEO signal  
**Fix:** Add as the very first element inside `<body>`:

```tsx
<a
  href="#main-content"
  className="sr-only focus:not-sr-only focus:fixed focus:top-4 focus:left-4 focus:z-50 focus:px-4 focus:py-2 focus:bg-navy focus:text-cream focus:rounded"
>
  Skip to main content
</a>
```

Add `id="main-content"` to the `<main>` element.

---

### 2.4 — Company registration in footer

**File:** `components/layout/footer.tsx`  
**Fix:** Add to footer bottom bar:

```tsx
<p className="text-sm text-muted">
  Pier 7 Projects Ltd · Company No. 12894305 · Registered in England and Wales
</p>
```

---

### 2.5 — "Service 1/2/3/4" internal labels

**Issue:** Placeholder service names in data arrays (identified in April 27 audit)  
**Fix:** Search codebase for "Service 1", "Service 2" etc. and replace with real service names:
- Service 1 → "Lead & Enquiry Automation"
- Service 2 → "Quote & Job Automation"
- Service 3 → "Invoice & Admin Automation"
- Service 4 → "Custom Tools & Dashboards"

```bash
grep -r "Service [1-4]" app/ components/
```

---

### 2.6 — WhatsApp Business links (restore when ready)

**Files:** `components/layout/footer.tsx`, `app/contact/page.tsx`  
**Status:** Removed April 27 pending WhatsApp Business number confirmation  
**Action when number is confirmed:** Restore the 2 footer links using the business number. Use format: `https://wa.me/44XXXXXXXXXX`

---

## Priority 3 — Content gaps (Ryan's actions required)

### 3.1 — Ryan's photo on About page

**Why it matters:** The #1 conversion gap on the site. "Built by someone who automated their own business first" lands differently with a face attached.  
**Spec:** One genuine photo. Not a studio portrait. On site, at a desk, or at the business — real setting. Circular crop at 400×400. Warm, natural light.  
**File location when ready:** `public/images/ryan-wilson.jpg`  
**Implementation:** Add to `app/about/page.tsx` in the founder section.

---

### 3.2 — Olive Tree real case study numbers

**Status:** Contract signed, £1,750 setup / £450/mo. Phase 1 email automation live.  
**Needed:** Before/after metrics — what has changed since the automation went live?  
- Email response time: before → after
- Lead volume captured: before → after
- Any specific result Ryan can cite

**Once available:** Update `/case-studies` page Olive Tree card with real numbers. Remove "placeholder" status.

---

### 3.3 — ICO Registration

**Status:** Pending (£52 at ico.org.uk)  
**Blocker:** Cannot sign Data Processing Agreements with clients until this is complete.  
**Action:** Register at ico.org.uk/registration. Update `app/privacy-policy/page.tsx` — replace "ICO registration is in progress" with the actual ICO registration number.

---

## Priority 4 — Performance (nice-to-have, already mostly good)

### 4.1 — Core Web Vitals baseline

The site is Next.js 15 on Vercel with static rendering — it should already be fast. Verify:
1. Run PageSpeed Insights on `https://rorahq.co.uk`
2. Target: LCP < 2.5s, INP < 200ms, CLS < 0.1
3. If LCP is slow: check the Remotion demo video — ensure it has `loading="lazy"` and a poster image
4. Run both mobile and desktop — mobile is the priority for this audience

---

### 4.2 — Canonical tag check

The `vercel.json` www→non-www redirect is in place (from April 27). Verify:
- `https://www.rorahq.co.uk` → 301 → `https://rorahq.co.uk` ✅
- `https://ai-consultancy-web.vercel.app` → should not be indexed. Confirm `robots: { index: false }` is set on the Vercel preview domain or that it's not accessible publicly.

---

## Full checklist (copy this into Todoist)

**Blockers — fix first:**
- [ ] Add hookify exception for `application/ld+json` scripts
- [ ] Add LocalBusiness JSON-LD schema to `app/layout.tsx`
- [ ] Add FAQ JSON-LD schema to `app/pricing/page.tsx`
- [ ] Start Google Business Profile verification (2-week lead time)
- [ ] Submit sitemap to Google Search Console

**Code fixes — batch PR:**
- [ ] Update OG image colours in `app/opengraph-image.tsx`
- [ ] Fix container mismatch (nav → `max-w-6xl` everywhere)
- [ ] Add skip-to-content link in `app/layout.tsx`
- [ ] Add company reg to footer in `components/layout/footer.tsx`
- [ ] Fix "Service 1/2/3/4" labels in data arrays
- [ ] Update all page metadata with new title tags and meta descriptions from `07-seo-onpage.md`

**Ryan's actions:**
- [ ] Register ICO (£52 at ico.org.uk)
- [ ] Get and add Ryan's photo to about page
- [ ] Confirm Olive Tree case study numbers
- [ ] Confirm WhatsApp Business number → restore footer links

**Content:**
- [ ] Expand `/ai-for-electricians` with Simpro automation section
- [ ] Create `/simpro-automation` page (or redirect to electricians page with Simpro anchor)
- [ ] Add 3 local geo terms to about page copy (Lytham St Annes, Preston, Fylde Coast)
- [ ] Write first blog article: "How we cut quote time from 47 minutes to 12"

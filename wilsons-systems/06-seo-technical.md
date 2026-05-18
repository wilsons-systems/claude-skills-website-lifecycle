# Technical SEO — Wilsons Systems

**Client:** Wilsons Systems / Wilsons Electrical Ltd
**Skill applied:** SEO Technical
**Date:** May 2026

---

## Current State

- **Platform:** WordPress (version unknown) on Cloudflare CDN
- **Page speed:** Not yet measured — assumed poor (typical WordPress default)
- **Mobile performance:** Unknown — assumed low, given no click-to-call and no documented responsive testing
- **Schema markup:** None
- **Sitemap:** Not confirmed as submitted to Google Search Console
- **Known issues:** Wrong H1, thin content, comment form on homepage, no service/location pages, no schema, image alt text using filenames, no click-to-call on mobile

---

## Fix List — Ordered by Priority

Items are ordered: fix the things that cost the most to leave broken first, then fix the things that compound over time, then optimise.

---

### Fix 1 — H1 Tag on Homepage

**Priority: Immediate — today**
**Effort: 10 minutes**

**Current state:** The H1 is "About Us." This is the single biggest ranking signal on the page, and it tells Google the page is about a company description — not about electrical services in Blackpool.

**Fix:**

Change the H1 to:

```
Blackpool's Most Trusted Electrical & Smart Home Contractors
```

Or the more keyword-direct variant:

```
Electrician Blackpool & Fylde Coast — Wilsons Systems
```

**How to fix in WordPress:**

Option A (recommended if using a page builder like Elementor or the Block Editor):
1. Log into WordPress admin
2. Pages > Home > Edit
3. Find the H1 element — it may be in a Hero block or a Heading block set to H1
4. Change the text to the recommended wording
5. Save and publish
6. Verify with browser dev tools (right-click > Inspect > search for `<h1>`)

Option B (if H1 is hardcoded in the theme):
1. Appearance > Theme Editor (or access via FTP/SFTP)
2. Search for "About Us" in the homepage template file
3. Replace with the new H1 text
4. Save

**Do not have two H1 tags on the page.** If the page builder creates a heading and the theme also outputs one, use browser inspect to confirm which is the H1 and remove or demote the other to H2.

---

### Fix 2 — LocalBusiness JSON-LD Schema

**Priority: Immediate — this week**
**Effort: 20 minutes to paste; 5 minutes to verify**

**Current state:** No structured data on any page. Google has no machine-readable confirmation of the business name, address, phone number, services, or opening hours.

**Fix:**

Paste the following JSON-LD into the `<head>` of every page. The easiest method on WordPress is the "Insert Headers and Footers" plugin (free, by WPCode). Go to Settings > Insert Headers and Footers > paste in the Scripts in Header box.

```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ElectricalContractor",
  "name": "Wilsons Systems",
  "alternateName": "Wilsons Electrical Ltd",
  "url": "https://wilsonssystems.com",
  "logo": "https://wilsonssystems.com/wp-content/uploads/[logo-filename].svg",
  "image": "https://wilsonssystems.com/wp-content/uploads/[team-photo-filename].jpg",
  "description": "NICEIC Approved Contractor and Control4 Authorised Dealer serving Blackpool and the Fylde Coast for over 40 years. Multi-discipline electrical, security, CCTV, smart home, fire alarms, EV chargers and networking.",
  "telephone": "[PHONE]",
  "email": "[EMAIL]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[STREET ADDRESS]",
    "addressLocality": "Blackpool",
    "addressRegion": "Lancashire",
    "postalCode": "[POSTCODE]",
    "addressCountry": "GB"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "[LATITUDE]",
    "longitude": "[LONGITUDE]"
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Blackpool"
    },
    {
      "@type": "City",
      "name": "Lytham St Annes"
    },
    {
      "@type": "City",
      "name": "Poulton-le-Fylde"
    },
    {
      "@type": "City",
      "name": "Cleveleys"
    },
    {
      "@type": "City",
      "name": "Thornton"
    },
    {
      "@type": "City",
      "name": "Fleetwood"
    },
    {
      "@type": "City",
      "name": "Kirkham"
    },
    {
      "@type": "City",
      "name": "Preston"
    }
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": [
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday"
      ],
      "opens": "08:00",
      "closes": "17:00"
    }
  ],
  "sameAs": [
    "https://www.google.com/maps?cid=[GOOGLE_BUSINESS_PROFILE_CID]",
    "https://www.facebook.com/[FACEBOOK_PAGE_URL]",
    "https://www.checkatrade.com/trades/[CHECKATRADE_SLUG]"
  ],
  "hasMap": "https://www.google.com/maps?cid=[GOOGLE_BUSINESS_PROFILE_CID]",
  "priceRange": "££",
  "currenciesAccepted": "GBP",
  "paymentAccepted": "Cash, Bank Transfer, Card",
  "founder": {
    "@type": "Person",
    "name": "Ryan Wilson",
    "jobTitle": "Managing Director and NICEIC Qualified Supervisor"
  },
  "knowsAbout": [
    "Electrical Installation",
    "EICR Inspections",
    "Consumer Unit Upgrades",
    "House Rewiring",
    "Security Alarm Systems",
    "CCTV Installation",
    "Fire Alarm Systems",
    "Control4 Smart Home",
    "EV Charger Installation",
    "UniFi Networking"
  ],
  "hasCredential": [
    {
      "@type": "EducationalOccupationalCredential",
      "credentialCategory": "NICEIC Approved Contractor"
    },
    {
      "@type": "EducationalOccupationalCredential",
      "credentialCategory": "Control4 Authorised Dealer"
    },
    {
      "@type": "EducationalOccupationalCredential",
      "credentialCategory": "Part P Registered"
    }
  ]
}
</script>
```

**Placeholders to replace before pasting:**
- `[PHONE]` — actual phone number in format `+441253XXXXXX`
- `[EMAIL]` — contact email address
- `[STREET ADDRESS]`, `[POSTCODE]` — registered business address
- `[LATITUDE]`, `[LONGITUDE]` — from Google Maps (right-click on pin > copy coordinates)
- `[GOOGLE_BUSINESS_PROFILE_CID]` — find in the GBP URL when logged in, or from Maps share link
- `[logo-filename].svg` — actual logo filename once SVG is uploaded
- `[team-photo-filename].jpg` — main team/site photo once uploaded
- `[FACEBOOK_PAGE_URL]` — if Facebook is active; remove `sameAs` entry if not

**How to verify:** After publishing, paste the page URL into [Google's Rich Results Test](https://search.google.com/test/rich-results). It should detect the `ElectricalContractor` type and show no errors.

---

### Fix 3 — Remove Comment Form from Homepage

**Priority: Immediate — today**
**Effort: 5 minutes**

**Current state:** A comment form is visible on the homepage. It is attracting spam and makes the page look like a blog post rather than a business homepage.

**Fix:**

In WordPress:
1. Pages > Home > Edit
2. Look for a Comments block or a comment form widget — delete it
3. If comments are enabled at the page level: in the right sidebar under Discussion, uncheck "Allow comments"
4. Alternatively: Settings > Discussion > uncheck "Allow people to post comments on new articles" (disables comments site-wide — usually safer for a business site)

If the comment form is appearing from the theme and cannot be found in the editor, add this to your child theme's `functions.php`:

```php
// Disable comments on all pages and posts
add_action('init', function() {
    remove_post_type_support('page', 'comments');
    remove_post_type_support('post', 'comments');
});
```

---

### Fix 4 — Google Business Profile — Review Growth Process

**Priority: This week**
**Effort: 1 hour setup, then 5 minutes per job ongoing**

**Current state:** 13 Google reviews. Target: 50+ within 6 months. Google Business Profile listing exists but has not been fully optimised.

**Step 1 — Audit and update the GBP listing:**

Log into [business.google.com](https://business.google.com) and verify/update:

| Field | What to check / set |
|-------|---------------------|
| Business name | "Wilsons Systems" — must match the website name exactly |
| Primary category | **Electrician** — this must be the primary category |
| Additional categories | Security alarm installer, CCTV installer, Home automation company, Fire alarm supplier, EV charging station (if applicable) |
| Business description | Write 250+ words covering all services, NICEIC approval, Control4 dealership, 40 years, service area |
| Phone number | Must match the website exactly (NAP consistency) |
| Website URL | `https://wilsonssystems.com` |
| Service area | Add all towns: Blackpool, Lytham St Annes, Poulton-le-Fylde, Cleveleys, Thornton, Fleetwood, Kirkham, Preston, Chorley, Lancaster |
| Services | Add all services from the IA in File 2 — GBP has a services field |
| Photos | Minimum 10 photos: team photo, van(s), at least 3 completed project photos, office/premises if applicable, NICEIC certificate, Control4 badge |
| Opening hours | Set correctly including any emergency callout notes |

**Step 2 — Get the review link:**

1. In Google Business Profile, go to Home > Get more reviews
2. Copy the short review link (format: `g.page/[business-name]/review`)
3. Save this link — it goes directly to the Google review form

**Step 3 — Review request process (WhatsApp template):**

Send this message to every customer within 24 hours of job completion:

> Hi [Name], thanks for having us out today. If you're happy with the work, would you mind leaving us a quick Google review? It takes about 2 minutes and really helps small businesses like ours. Here's the link: [REVIEW LINK]
>
> — Ryan / Wilsons Systems

**Step 4 — Track progress:**

Create a simple spreadsheet: job date, customer name, WhatsApp sent (Y/N), review received (Y/N). Review it weekly. If a customer said they would leave one and hasn't after 2 weeks, one follow-up is acceptable.

**Target timeline for 50 reviews:**
- Currently 13
- Need 37 more
- Wilsons does approximately 3–5 jobs per week
- 30% response rate to review requests = 1–1.5 reviews per week
- At 1.5 per week: 37 reviews in ~25 weeks (6 months)
- If response rate is higher, or if satisfied past customers are contacted, target can be hit faster

**Past customer outreach (one-time effort):**
Ryan can send a review request to every satisfied customer from the last 2 years via WhatsApp or text. This could generate 10–15 reviews in the first week. Do this once, then rely on the ongoing post-job process.

---

### Fix 5 — XML Sitemap — Submit to Google Search Console

**Priority: This week**
**Effort: 15 minutes**

**Current state:** Sitemap status unconfirmed. Likely not submitted to Google Search Console if the site has not been actively managed.

**Step 1 — Generate the sitemap:**

If Yoast SEO is installed (standard on most WordPress sites):
- The sitemap is automatically generated at `https://wilsonssystems.com/sitemap_index.xml`
- Go to Yoast SEO > General > Features — ensure "XML sitemaps" is toggled on
- Verify the sitemap exists by visiting the URL above in a browser

If Rank Math is installed:
- Sitemap is at `https://wilsonssystems.com/sitemap.xml`
- Settings > Sitemap — ensure all page types are included

**Step 2 — Submit to Google Search Console:**

1. Log into [Google Search Console](https://search.google.com/search-console) — verify ownership if not already done (Cloudflare makes DNS verification the easiest method)
2. In the left menu: Sitemaps
3. Paste the sitemap URL and click Submit
4. Check back after 24 hours — GSC will show how many URLs were indexed vs submitted

**Step 3 — Submit to Bing Webmaster Tools:**

Bing has roughly 6–10% of UK search traffic. Worth 5 minutes:
1. Register at [bing.com/webmasters](https://www.bing.com/webmasters)
2. Add the site and submit the sitemap URL

---

### Fix 6 — Image Alt Text

**Priority: Week 2**
**Effort: 1–2 hours (manual), or 30 minutes with a plugin**

**Current state:** All images are using filenames as alt text (e.g., `IMG_4521.jpg`). This wastes a ranking signal and fails accessibility standards.

**Fix formula:**

```
[service] in [location] — Wilsons Systems
```

**Examples:**

| Filename (current) | Alt text (recommended) |
|--------------------|-----------------------|
| `IMG_4521.jpg` | `consumer unit installation Blackpool — Wilsons Systems` |
| `DSC_0012.jpg` | `house rewiring Lytham St Annes — Wilsons Systems` |
| `photo1.jpg` | `Hikvision CCTV installation Blackpool — Wilsons Systems` |
| `team.jpg` | `Wilsons Systems team — electricians Blackpool` |
| `van.jpg` | `Wilsons Systems van — NICEIC approved electricians Fylde Coast` |

**How to fix in WordPress:**

Option A (manual): Media Library > select each image > edit alt text field. Time-consuming but accurate.

Option B (plugin): "SEO Optimized Images" plugin auto-generates alt text from the attachment title — faster but requires titles to already be set correctly. Better as a foundation than a complete fix.

Option C (if using Yoast): Yoast will flag images with missing alt text in its analysis. Use this to find offenders quickly.

**Priority order for manual fixing:** Homepage images first, then service page images, then blog images.

---

### Fix 7 — Page Speed

**Priority: Week 2–3**
**Effort: 2–4 hours depending on current WordPress configuration**

**Current state:** Not measured. WordPress without caching and image optimisation typically scores 30–60 on Google PageSpeed Insights mobile. Target: 70+ mobile, 85+ desktop.

**Step 1 — Measure current state:**

Run the current homepage through:
- [PageSpeed Insights](https://pagespeed.web.dev/) — Google's official tool; mobile score is what matters most
- [GTmetrix](https://gtmetrix.com) — gives more detail on what's slowing the page down

Note the current scores before making changes. Then re-test after each fix to confirm improvement.

**Step 2 — Install a caching plugin:**

Recommended: **WP Rocket** (paid, approximately £45/year — worth every penny) or **W3 Total Cache** (free but more complex to configure).

WP Rocket default settings will handle:
- Page caching
- Browser caching
- GZIP compression
- Database optimisation

**Step 3 — Cloudflare caching (free, already available):**

In the Cloudflare dashboard:
1. Caching > Configuration > Caching Level: Standard
2. Browser Cache TTL: 4 hours
3. Create a Page Rule for `/wp-admin/*` to bypass cache (so admin edits don't get cached)
4. Speed > Optimization > Auto Minify — enable for CSS, JS, HTML
5. Speed > Optimization > Rocket Loader — test this carefully; it can break some plugins

**Step 4 — Convert images to WebP:**

WebP is ~30% smaller than JPEG for the same quality. WordPress 5.8+ supports WebP natively.

Options:
- **ShortPixel** (freemium): bulk converts existing images and serves WebP to supporting browsers. Best balance of quality and compression.
- **Smush** (free tier): similar functionality, slightly less aggressive compression
- **Cloudflare Image Resizing** (paid Cloudflare plan): handles it at CDN level without a plugin

**Step 5 — Defer JavaScript:**

WP Rocket handles this. If not using WP Rocket, install **Async JavaScript** (free plugin). Deferring non-essential JavaScript means the page visually loads faster even if total load time is similar.

---

### Fix 8 — Click-to-Call

**Priority: Immediate — today or this week**
**Effort: 30 minutes**

**Current state:** Phone number is visible on the site but likely not formatted as a clickable link on mobile. On mobile, every phone number must be tappable — this is a direct conversion issue.

**Fix:**

Every instance of the phone number on the site must use this HTML:

```html
<a href="tel:+441253XXXXXX">01253 XXXXXX</a>
```

Replace `XXXXXX` with the actual digits. The `href` must use the international format with `+44` and no leading zero.

**Locations that must have click-to-call:**
1. Header — visible on all pages, all device sizes
2. Homepage hero — immediately visible on load
3. Homepage contact/CTA section
4. Every service page (in the page body and sidebar if applicable)
5. Every location page
6. Footer
7. Contact page

**Mobile header specific:**

On mobile, the phone number in the header should be formatted as an icon + number or a styled button — not just plain text that might be too small to tap accurately. Minimum tap target size: 44×44 pixels (Apple HIG recommendation, also used by Google's mobile usability guidelines).

```html
<!-- Example mobile header click-to-call button -->
<a href="tel:+441253XXXXXX" class="cta-phone-mobile">
  <svg><!-- phone icon svg --></svg>
  01253 XXXXXX
</a>
```

CSS minimum:
```css
.cta-phone-mobile {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  min-height: 44px;
  padding: 10px 16px;
  font-size: 16px; /* prevents iOS auto-zoom on tap */
  font-weight: 600;
  color: #ffffff;
  background: #cc1414; /* red accent */
  border-radius: 4px;
  text-decoration: none;
}
```

---

### Fix 9 — HTTPS and Mixed Content

**Priority: Week 1**
**Effort: 30 minutes to audit, variable to fix**

**Current state:** Site is on Cloudflare, which typically handles HTTPS termination. However, internal links or media may still reference `http://` URLs.

**Fix:**

**Step 1 — Verify Cloudflare SSL:**
Cloudflare dashboard > SSL/TLS > Overview. Should show "Full (strict)" mode. If it's showing "Flexible," upgrade to Full Strict — Flexible mode has security implications.

**Step 2 — Force HTTPS:**
Cloudflare > SSL/TLS > Edge Certificates > Always Use HTTPS: On
This redirects all HTTP requests to HTTPS at the CDN level.

**Step 3 — Update WordPress site URL:**
WordPress Admin > Settings > General:
- WordPress Address (URL): `https://wilsonssystems.com`
- Site Address (URL): `https://wilsonssystems.com`

If these show `http://`, changing them to `https://` will fix the WordPress-generated URLs.

**Step 4 — Fix mixed content:**
Install **Really Simple SSL** plugin (free). It automatically finds and fixes `http://` references in the database and outputs HTTP to HTTPS in served pages.

**Step 5 — Verify:**
In Chrome, load the homepage and open DevTools > Console. Any mixed content warnings appear here. Target: zero warnings, padlock icon visible and green (or default locked state in modern Chrome).

---

### Fix 10 — robots.txt

**Priority: Week 1**
**Effort: 10 minutes**

**Current state:** Unverified. WordPress generates a default robots.txt via a virtual file — it may or may not be optimal.

**Verify and fix:**

Visit `https://wilsonssystems.com/robots.txt` in a browser. The correct content should be:

```
User-agent: *
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php

Sitemap: https://wilsonssystems.com/sitemap_index.xml
```

This allows Googlebot to crawl everything except the admin area, and tells all crawlers where to find the sitemap.

**Things to avoid in robots.txt:**
- `Disallow: /` (blocks everything — catastrophic)
- Disallowing `/wp-content/uploads/` (blocks image indexing)
- Blocking CSS or JS files (Google needs these to render pages)

If a plugin has added unnecessary disallow rules, remove them. The WordPress default is usually safe — just add the sitemap URL if it's missing.

---

### Fix 11 — Mobile-First Check

**Priority: Week 1–2**
**Effort: 1–2 hours testing + variable fix time**

**Current state:** Unknown. WordPress themes are generally responsive, but responsive is not the same as optimised for mobile.

**Testing protocol:**

1. Chrome DevTools > Device toolbar > select "iPhone SE" (375px wide — smallest common screen still in significant use)
2. Check every page type: homepage, service page, contact page
3. Check at 390px (iPhone 14 standard) and 428px (iPhone 14 Plus)

**Things to check and minimum standards:**

| Element | Minimum Standard |
|---------|-----------------|
| Navigation | Hamburger menu that collapses cleanly — no overflow, no horizontal scroll |
| Phone number | Click-to-call link, minimum 44×44px tap target |
| CTA buttons | Minimum 44×44px, full width or near-full width on mobile |
| Font size | Minimum 16px for body text (prevents iOS auto-zoom) |
| Images | Must not exceed viewport width — `max-width: 100%` on all `<img>` |
| Form fields | Minimum height 44px, font size 16px (prevents zoom on focus) |
| Spacing | Adequate padding between tappable elements (minimum 8px gap) |
| Horizontal scroll | None. Zero. Any horizontal scroll is a failure. |

**Run Google's Mobile-Friendly Test:**
Visit [search.google.com/test/mobile-friendly](https://search.google.com/test/mobile-friendly) and paste the site URL. Fix any issues it flags.

**Check Core Web Vitals on mobile:**
PageSpeed Insights shows mobile and desktop scores separately. The mobile CWV score matters most for ranking (Google uses mobile-first indexing).

---

## Rebuild Note — Next.js / Cloudflare Pages

If wilsonssystems.com is rebuilt on Next.js (App Router) deployed to Cloudflare Pages, the following items from the fix list are resolved by default or trivially:

| Fix # | Item | Status in Rebuild |
|-------|------|-------------------|
| 1 | H1 tag | Solved by writing the correct H1 in JSX |
| 3 | Comment form | Does not exist in a custom build — not an issue |
| 7 | Page speed | Next.js with Cloudflare Pages typically scores 90+ by default: SSG pages, automatic image optimisation (`next/image`), edge CDN delivery, no WordPress overhead |
| 11 | Mobile first | Solved by building mobile-first from the start in CSS |

**Items that still require active implementation in a rebuild:**

| Fix # | Item | Action Required in Rebuild |
|-------|------|---------------------------|
| 2 | LocalBusiness schema | Implement in `app/layout.tsx` or as a shared component |
| 4 | Google Business Profile | Not related to tech stack — process-based |
| 5 | XML Sitemap | Use `next-sitemap` package to auto-generate |
| 6 | Image alt text | Write correct alt text for every `<Image>` component at build time |
| 8 | Click-to-call | Implement in header component with correct `href="tel:"` |
| 9 | HTTPS | Cloudflare handles this — configure SSL/TLS as per Fix 9 |
| 10 | robots.txt | Add `public/robots.txt` to the repo |

**Next.js sitemap implementation:**

Install `next-sitemap`:
```bash
npm install next-sitemap
```

Add `next-sitemap.config.js` to project root:
```js
/** @type {import('next-sitemap').IConfig} */
module.exports = {
  siteUrl: 'https://wilsonssystems.com',
  generateRobotsTxt: true,
  robotsTxtOptions: {
    policies: [
      { userAgent: '*', allow: '/' },
    ],
  },
  exclude: ['/api/*', '/admin/*'],
  changefreq: 'weekly',
  priority: 0.7,
  transform: async (config, path) => {
    // Give homepage and high-priority pages higher priority
    const highPriority = ['/', '/services/smart-home/control4', '/locations/electrician-blackpool']
    return {
      loc: path,
      changefreq: config.changefreq,
      priority: highPriority.includes(path) ? 1.0 : config.priority,
      lastmod: new Date().toISOString(),
    }
  },
}
```

Add to `package.json` scripts:
```json
"postbuild": "next-sitemap"
```

This generates both `sitemap.xml` and `robots.txt` automatically on every build.

---

## Monitoring — Ongoing

Once the fixes above are implemented, set up basic monitoring so regressions are caught early:

| Tool | What to monitor | Frequency |
|------|----------------|-----------|
| Google Search Console | Impressions, clicks, average position, Coverage errors, Core Web Vitals | Weekly |
| Google Analytics 4 | Organic sessions, conversion events (form submissions, phone link clicks), top landing pages | Weekly |
| Google Business Profile | Profile views, search queries, review count, photo views | Monthly |
| PageSpeed Insights | Mobile and desktop scores for homepage and top 3 service pages | Monthly |
| Manual SERP check | Search "electrician Blackpool", "EICR Blackpool", "Control4 installer Blackpool" — note position | Monthly |

All of these tools are free. The time investment is approximately 30 minutes per month once set up.

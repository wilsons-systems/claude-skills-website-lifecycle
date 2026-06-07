# Technical SEO — Wilsons Systems

## Framing

The site is technically solid. The technical foundations that many sites lack are already in place. This document does not list them as fixes needed — they are done. The focus is on the genuine remaining gaps, ordered by impact.

---

## Already Done — Do Not List as Actions Required

The following technical elements are confirmed complete as of March 2026. Do not recommend implementing any of these:

- Schema markup on every page (LocalBusiness/Electrician, FAQPage, BreadcrumbList, Review JSON-LD) ✓
- sitemap.xml ✓
- robots.txt ✓
- Breadcrumb schema ✓
- Real Review schema with named reviewers (Russell Dawson, Iain McIntyre, Andrew Wild) ✓
- WebP image conversion across all images ✓
- Google Fonts loaded non-render-blocking ✓
- Custom 404 page ✓
- PageSpeed Desktop 99–100 ✓
- PageSpeed Mobile 91–96 ✓
- Tailwind CDN removed (saves 124KB) — do not add back ✓
- hCaptcha removed (saves 195KB, 990ms TBT removed) — do not add back ✓
- Internal linking implemented (service↔service, service↔location, location↔location) ✓
- Per-page keyword audit complete ✓
- Canonical tags ✓
- Cloudflare Workers hosting (fast, globally distributed) ✓

---

## Gap 1: Google Analytics 4 — Critical

**Status: Not set up. This is the most important missing element.**

Without GA4, there is no data on:
- Which pages are receiving traffic
- Which pages drive enquiries (form submissions, Quick Quote completions)
- Whether the AI chatbot generates enquiries that convert
- Which geographic areas the traffic comes from
- Mobile vs desktop split
- What users do before and after visiting the homepage

Every decision about what to build next is currently based on assumptions rather than evidence. GA4 fixes this.

### Setup steps

1. Go to analytics.google.com → sign in with the business Google account
2. Create a new GA4 property: property name "Wilsons Systems", reporting time zone "United Kingdom", currency "British Pound (£)"
3. Create a Web data stream: URL https://www.wilsonssystems.com, stream name "Wilsons Systems Website"
4. Copy the Measurement ID (format: G-XXXXXXXXXX)

### Implementation on the static site

The site uses static HTML files deployed via a `deploy.sh` script. There are two approaches:

**Option A (recommended): Google Tag Manager**
- Create a GTM container at tagmanager.google.com
- Add the GTM snippet to `<head>` and `<body>` of every HTML page
- Configure GA4 as a tag within GTM, using the Measurement ID
- Advantage: Future tracking changes (adding conversion events, heatmaps, etc.) can be made in GTM without touching HTML files
- This is the cleaner long-term approach

**Option B: Direct GA4 tag**
- Add the GA4 `gtag.js` snippet directly to the `<head>` of every HTML page
- Simpler but means editing all 30+ HTML files for any tracking change

**Implementation approach for static files:**
Since all pages are plain HTML, the cleanest approach is to add the GA4/GTM snippet to a shared header template that is injected at build time by `deploy.sh`. If no shared template currently exists, the snippet needs to be added to each HTML file — consider creating a shared `_header.html` partial that gets included during the build, reducing future maintenance burden.

### Conversion events to configure

Set these up immediately after GA4 is live:

| Event name | Trigger | What it measures |
|---|---|---|
| `contact_form_submit` | Contact form submission (thank you page or form event) | Direct enquiries |
| `quick_quote_complete` | Quick Quote form completion | Quote requests (highest intent) |
| `chatbot_enquiry` | Chatbot session that results in a contact attempt | Chatbot-driven leads |
| `phone_click` | Click on the phone number (click-to-call) | Calls initiated from the site |
| `guide_view` | Pageview on /guides/* | Content engagement |

For the phone click event: the phone number should be wrapped in a `tel:` link (`<a href="tel:01253795050">01253 795050</a>`). GA4 can then track clicks on this link as a conversion event using a GTM click trigger.

### GA4 custom reports to set up

Once data is flowing (allow 30 days for meaningful data):
- **Landing page performance:** Which pages receive the first visit, and what % of those sessions result in a conversion event
- **Conversion by service:** Tag pages by service category and measure which service areas generate the most enquiries
- **Location performance:** GA4's geographic report will show whether Lytham St Annes traffic converts differently from Blackpool traffic — this directly informs the Lytham-primary strategy

---

## Gap 2: Google Search Console — Critical

**Status: Not set up. Must be done alongside GA4.**

Without Search Console, there is no visibility on:
- Which search queries drive clicks to the site
- Whether all 30+ pages are indexed by Google
- Whether any pages have crawl errors or indexing issues
- Whether the sitemap is being processed
- Whether any manual actions (penalties) have been applied

Search Console is free and takes 15 minutes to set up.

### Setup steps

1. Go to search.google.com/search-console
2. Add property → URL prefix → enter: `https://www.wilsonssystems.com`
3. Verify ownership via DNS: Google will provide a TXT record value
4. In Cloudflare dashboard → DNS → Add record → Type: TXT, Name: @ (root), Value: [Google's TXT record value], TTL: Auto
5. Return to Search Console → click Verify
6. Once verified: Sitemaps → Add sitemap → enter: `sitemap.xml`
7. Allow 48–72 hours for Google to process the sitemap

### What to check weekly (15 minutes)

- **Coverage report:** Are all 30+ pages in the "Valid" state? Any "Excluded" or "Error" pages need investigation.
- **Performance report:** Which queries are generating impressions and clicks? This will reveal keywords the site is ranking for that are not yet in the keyword strategy.
- **Core Web Vitals:** Will show real-user data for LCP, INP, and CLS. This supplements the lab data from PageSpeed Insights.
- **Manual Actions:** A clean manual actions report confirms no penalties. Check monthly.

### Link GA4 to Search Console

Once both are set up: in GA4 → Admin → Property Settings → Search Console Links → Link → select the Search Console property. This adds a "Search Console" report to GA4 showing which queries led to clicks that then resulted in sessions — the most useful cross-referencing view available.

---

## Gap 3: Google Business Profile Audit

**Status: GBP listing exists. Needs a thorough audit and update.**

GBP is one of the primary ranking factors for local search. A listing with incomplete service categories, sparse photos, and no recent posts will rank below a fully optimised listing from a competitor.

### Categories

**Primary category:** Electrician ✓ (likely already set)

**Secondary categories to add (if not already set):**
- Security system supplier
- Home automation company
- CCTV installer
- Smart home installer
- Electrical installation service
- Security system installer

Google allows up to 10 categories. Use all relevant ones. The secondary categories expand the search queries for which the GBP listing appears.

### Business description

The GBP description is 750 characters max (but only ~250 show without "more" click). The first 250 characters should carry the most important information:

Suggested description:
> NICEIC approved electrical contractors and Control4 Authorised Dealers serving Lytham St Annes and the Fylde Coast since 1984. We specialise in smart home automation, CCTV and security alarms, EV charger installation, house rewiring, consumer unit upgrades, and EICR testing. Covering Lytham St Annes, Blackpool, Poulton-le-Fylde, Fleetwood, Kirkham, and Preston.

### Services list

GBP has a services section where individual services can be listed with names and descriptions. Many businesses leave this incomplete. Ryan should log in and add every service Wilsons offers:
- House Rewiring
- Consumer Unit Upgrades
- EICR Testing
- Emergency Electrician
- EV Charger Installation
- Heat Pump Electrical Work
- Smart Home Installation (Control4)
- Multi-Room Audio
- Lighting Control
- Home Cinema
- CCTV Installation (Hikvision)
- Security Alarm Installation (Texecom)
- Access Control (Videx)
- Gate Automation
- Networking & Data

### Photos to add

GBP listings with 10+ photos receive significantly more engagement. Priority photos:
1. Team photo (Ryan + team, ideally in front of the van or a completed installation)
2. Van / vehicles (legitimacy signal — shows a real business with physical assets)
3. Corka Bridge House Control4 installation (or another premium smart home install)
4. Hikvision CCTV installation (professional camera installation, equipment rack)
5. Consumer unit installation (clean, professional work)
6. NICEIC certificate / accreditation (physical paperwork = trust)
7. Office / workshop at 6E Peel Hall Business Village (legitimacy signal)

All photos should be high quality (minimum 720px, ideally 1080p+). Avoid screenshots and placeholder images.

### Q&A section

Seed the GBP Q&A section with the 8 questions from the homepage FAQ. Businesses can post their own questions and answers — this ensures accurate answers appear rather than leaving it to the public. Log in as the business owner, go to the listing, find the Q&A section, and post each question with its answer.

### Posts

Google Business posts appear in the knowledge panel for local searches. They remain visible for approximately 7 days (standard posts) or until manually removed (offers/events). The algorithm appears to give a small ranking lift to active listings.

**Post schedule:** One post per month minimum. Content ideas:
- Completed project highlight (brief description, 1–2 photos)
- New guide published (link to the /guides/ page)
- Seasonal tip (winter — check your consumer unit; spring — time for an EICR if your rental is due)
- Service spotlight (rotate through different services each month)

---

## Gap 4: Placeholder Image Replacement

**Status: Some placehold.co URLs remain on the site.**

Placehold.co is a third-party image placeholder service. Pages containing these URLs:
- Make a network request to a third-party domain (minor performance consideration)
- Clearly signal to Google (and users) that the page is not finished
- Lose the E-E-A-T opportunity that a real photograph would provide
- Cannot have meaningful alt text because the image has no meaningful content

**Priority order for replacement:**
1. Smart home / Control4 page — highest value service, most premium audience
2. CCTV and security pages — real installation photos demonstrate capability
3. About page — team photo is the single most impactful human trust signal
4. Projects page — every entry needs a real photo; placeholder photos make project write-ups unconvincing
5. Homepage — if any placehold.co images remain in the hero or services grid

If professional photography is not immediately available: clear, well-lit smartphone photographs of real completed installations are substantially better than placeholders. The bar is "genuine" not "perfect."

---

## Gap 5: Directory Listings / NAP Citations

**Status: Not confirmed as set up across key directories.**

NAP consistency (Name, Address, Phone) across online directories is a local SEO trust signal. The more places Google finds consistent NAP data, the more confident it is that the business is real, established, and located where it claims.

**Canonical NAP (use exactly this format everywhere):**

- **Name:** Wilsons Systems
- **Address:** 6E Peel Hall Business Village, Blackpool, FY4 5JX
- **Phone:** 01253 795050
- **Website:** https://www.wilsonssystems.com

Do not use variations (no "Wilson's Systems", no "Wilson Systems", no abbreviating the address). Inconsistency creates confusion in Google's local index.

**Directories to claim/create (in priority order):**

| Directory | Why it matters | Notes |
|---|---|---|
| NICEIC contractor finder | Clients actively search niceic.com for approved contractors — direct referral traffic | Log in at niceic.com/contractors, claim the Wilsons listing, ensure photo and services are current |
| Google Business Profile | Already exists — see Gap 3 | Audit and update as above |
| Checkatrade | High-volume local trades directory, good domain authority | Create listing with full NAP and services list |
| Trustpilot | Increasingly checked by consumers before booking | Create company page, invite existing happy clients to leave reviews |
| Yell.com | Old but still indexed by Google | Claim or create listing with NAP |
| Local.co.uk | UK local directory, decent local SEO value | Create listing |
| Yelp UK | Lower volume but another citation | Create listing |
| Scoot | UK directory | Create listing |
| 118 118 | Legacy but still carries citation value | Create/claim listing |

**Time to implement:** Approximately 2–3 hours to create and verify all listings. The NICEIC finder is the most valuable single directory for direct referral traffic — prioritise that one first.

---

## Gap 6: E-E-A-T Improvements

**Status: Schema is in place, but human expertise signals are thin.**

Google's E-E-A-T (Experience, Expertise, Authoritativeness, Trust) framework is particularly scrutinised for trades and home service queries — categories where bad advice or unqualified work could cause real harm. The site's schema and credentials are in place, but the human layer is missing.

**What to add:**

**About page — named individuals with qualifications:**
Adding Ryan Wilson by name with his NICEIC Qualified Supervisor status, and noting his years in the trade, creates an explicit expertise claim that Google can evaluate. Other named staff members add depth. See `05-seo-onpage.md` for the About page brief.

**Guide pages — author attribution:**
Any new guide pages published under `/guides/` should be attributed to Ryan Wilson by name with his qualifications in the page byline. This creates an author entity that Google can associate with qualified expertise in electrical and security work.

**Format example:**
`Written by Ryan Wilson, NICEIC Qualified Supervisor | Managing Director, Wilsons Systems`

**Review volume:**
13 verified Google reviews is a start, but it is below the volume where the count itself becomes a trust signal. See `04-homepage-copy.md` for the review request process. Target: 50+ reviews within 12 months.

---

## Gap 7: sitemap.xml lastmod Dates

**Status: Minor maintenance task.**

All pages in sitemap.xml currently show `<lastmod>2026-03-15</lastmod>`. When content is updated on any page, the lastmod date for that page should be updated to the date of the change. Stale lastmod dates across all pages simultaneously signals to Googlebot that nothing has changed — which may reduce crawl frequency over time.

**Fix:** Update the `deploy.sh` script or build process to automatically set the lastmod date to the current date for any page that has been modified since the last deploy. If automation is not practical, manually update lastmod dates whenever substantial content changes are made to a page.

This is a low-priority maintenance task — the indexing impact is marginal — but it is worth building into the workflow as content updates become more frequent.

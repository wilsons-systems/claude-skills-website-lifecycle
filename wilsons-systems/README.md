# Wilsons Systems — Website Assessment (June 2026)

## About This Assessment

This replaces a previous assessment that was written from an outdated wiki document. That document described a thin WordPress site in early development. **It was wrong.** The actual Wilsons Systems website is a well-built, high-performing static HTML site with 30+ pages, near-perfect PageSpeed scores, and solid technical SEO foundations already in place.

The purpose of this assessment is to document what is actually there, identify the genuine remaining gaps, and provide a realistic action plan — not to recommend a rebuild or re-implement work that is already done.

---

## Actual State of the Site (as of 15 March 2026)

**Tech stack:** Static HTML files deployed to Cloudflare Workers. Not WordPress. Not Next.js. Plain HTML with inline CSS.

**Live URL:** https://www.wilsonssystems.com

**GitHub repo:** wilsons-systems/wilsons-systems-site

**Performance:**
- PageSpeed Insights — Desktop: 99–100
- PageSpeed Insights — Mobile: 91–96
- These are exceptional scores. Do not add Tailwind CDN, hCaptcha, or any other heavyweight dependency that would degrade them.

**Content:** 30+ pages fully built and indexed, including 8 discipline service pages, 7 sub-service pages, 5 location pages, 6 comparison/guide pages, about, contact, projects, quick quote, privacy, custom 404.

**Technical SEO:** Schema markup on every page (LocalBusiness/Electrician, FAQPage, BreadcrumbList, Review), sitemap.xml, robots.txt, breadcrumb schema, WebP images, non-render-blocking Google Fonts, canonical tags.

**Functionality:** AI chatbot (Claude Haiku 4.5 via Cloudflare Worker), Quick Quote system (customer form → GCP Cloud Function → auto-creates Simpro customer + quote), trust bar with NICEIC/Control4/Hikvision VASP/Videx/Texecom badges on every page.

---

## Skills Applied in This Assessment

| File | Skill(s) | Angle |
|---|---|---|
| 01-brand-assessment.md | creative-direction, brand-voice | Validate the existing direction; identify where sub-service pages may drift from brand; give Ryan guidance for new content |
| 02-information-architecture.md | information-architecture | Document the current IA accurately; identify the three genuine gaps (EV charger page, gate automation page, guides index) |
| 03-seo-keywords.md | seo-keyword | Find next-tier keyword opportunities the site doesn't yet target; cluster by effort and value |
| 04-homepage-copy.md | landing-page-copy | Incremental improvements only — do not touch anything that could affect rankings; focus on conversion uplift |
| 05-seo-onpage.md | seo-onpage | Spec the two new pages; identify safe improvements to existing pages without URL or H1 changes |
| 06-seo-technical.md | seo-technical | The site is technically solid — focus on the real remaining gaps: GA4, Search Console, GBP audit, NAP citations |

---

## 10-Action Priority Matrix

These are the **only** things that are genuinely pending. Everything else is already done.

| Priority | Action | Blocked by | Effort | Impact |
|---|---|---|---|---|
| 1 | Set up Google Analytics 4 + configure conversion events | Ryan (account access) | Low | Critical — currently flying blind |
| 2 | Verify Google Search Console + submit sitemap | Ryan (DNS access) | Low | Critical — no ranking data without this |
| 3 | Google Business Profile audit (categories, services, photos, Q&A, posts) | Ryan | Medium | High — GBP is a primary local ranking factor |
| 4 | Replace placeholder images (placehold.co URLs remain on some pages) | Ryan (real photography) | Medium | High — placeholder images signal unfinished content to Google |
| 5 | Add team profiles to About page (names, qualifications, photos) | Ryan (team info) | Low | High — E-E-A-T signal; Lytham audience buys from people they trust |
| 6 | Create /ev-charger-installation/ page | None — can draft now | Medium | High — zero local competition, growing search volume |
| 7 | Create /gate-automation/ page | None — can draft now | Medium | Medium — Wilsons offers this service, no page exists |
| 8 | Create /guides/ index page listing all 6 existing guides | None — can draft now | Low | Medium — currently guides are orphaned, no index |
| 9 | Claim/create directory listings (NICEIC finder, Checkatrade, Trustpilot, Yell) | Ryan | Medium | Medium — NAP consistency + citation signals |
| 10 | Implement review request process (WhatsApp/SMS template post-job) | Ryan | Low | Medium — 13 reviews is low; target 50+ |

**Not on this list because they're already done:** schema, sitemap, breadcrumbs, WebP images, internal linking, keyword audit, Tailwind removal, hCaptcha removal, per-page schema, FAQ schema, review schema, location pages, comparison/guide pages, custom 404, robots.txt.

---

## SEO Preservation Rules

These constraints apply to any future changes to the site. Violating them risks losing existing rankings.

1. **Never change URLs.** Every existing URL must remain exactly as-is. If a page needs restructuring, add content — do not rename or redirect unless absolutely necessary.
2. **Never remove existing content.** Adding content is safe. Removing or replacing existing copy risks losing keyword coverage.
3. **Never change the homepage H1.** "Electricians in Lytham St Annes & Blackpool — Smart Home, CCTV & Security Specialists" is ranking. Leave it.
4. **Never change the homepage title tag.** "Electricians Lytham St Annes | CCTV, Security & Smart Homes | Wilsons Systems" is ranking. Leave it.
5. **Never add back Tailwind CDN** (124KB removed deliberately for PageSpeed).
6. **Never add back hCaptcha** (195KB + 990ms TBT removed deliberately).
7. **Never add Lancashire Safe Trader** (removed deliberately from all pages).
8. **Never create a fire alarms page** (Wilsons does not install fire alarms).
9. **Never say "only dealer" or "#1"** for Control4 — say "Authorised Dealer since 2014" or "long-standing dealer."
10. **Lytham St Annes is the primary location.** Blackpool is secondary. Do not reverse this in any new content.

---

## Brand North Star

Dark, cinematic, tech-luxury. Think Tesla meets Control4.

Primary audience: Affluent homeowners in Lytham St Annes commissioning £5k–£50k+ projects. They are intelligent people making significant investments. Treat them accordingly — no price-led language, no generic contractor tone.

Typography: Space Grotesk headings, Plus Jakarta Sans body.

Palette: #111111 background, #C41E2A red accent, white text.

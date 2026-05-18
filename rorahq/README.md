# rorahq/ — Rora Skills-Based Audit Outputs

This directory contains deliverables produced by the Claude Skills website lifecycle process for Rora (rorahq.co.uk). Each file is a production-ready output from a specific skill run. Nothing here is a draft or a template — these are the actual documents to implement.

**Site:** rorahq.co.uk
**Brand:** Rora — AI automation consultancy for UK local SMBs
**Business entity:** Pier 7 Projects Ltd, company number 12894305, Blackpool
**Code repository:** wilsons-systems/ai-consultancy-web (Next.js 15, Vercel, Cloudflare DNS)

---

## How to Use This Directory

Read each file in order. The numbering reflects the recommended implementation sequence — earlier files inform later ones. For example, the keyword research in `06-seo-keywords.md` maps to specific pages, and those pages are audited in `07-seo-onpage.md`, and the technical fixes that make those pages rank are in `08-seo-technical.md`.

Each file is standalone — you can open any one and act on it without reading the others first. But the full picture only comes from working through them as a set.

---

## Skill → File Mapping

| File | Skill | Description |
|---|---|---|
| `05-homepage-copy.md` | `homepage-copy` | Complete homepage copy, 7-section framework, all CTAs and proof points |
| `06-seo-keywords.md` | `seo-keywords` | Keyword research by cluster — local, problem, solution, discovery, sector |
| `07-seo-onpage.md` | `seo-onpage` | On-page audit for all 10 key pages — title tags, meta descriptions, H1s, schema |
| `08-seo-technical.md` | `seo-technical` | Ordered technical fix checklist — 12 items, copy-paste ready code where applicable |
| `README.md` | `lifecycle-index` | This file — index, mapping, and implementation guide |

**Files not yet created (planned):**
| File | Skill | Description |
|---|---|---|
| `01-brand-voice.md` | `brand-voice` | Brand voice guide, tone rules, banned phrases, sector tone variations |
| `02-icp.md` | `icp` | Ideal Customer Profile — trades, hospitality, professional services |
| `03-competitor-audit.md` | `competitor-audit` | Competitor positioning, content gaps, differentiation opportunities |
| `04-content-plan.md` | `content-plan` | 90-day content calendar, blog topics, sector page rollout plan |

---

## Implementation Notes

### Where the code lives

All website code changes described in these documents are implemented in: `wilsons-systems/ai-consultancy-web`

These documents describe **what to implement**. The code changes themselves happen in the repository. If there is ever a conflict between what a document says and what's in the codebase, the codebase is the source of truth for current state — the documents reflect the target state.

### File references

Technical fixes in `08-seo-technical.md` reference specific file paths. These are relative to the repository root of `wilsons-systems/ai-consultancy-web`:
- `app/layout.tsx` — root layout (schema, skip link)
- `app/schema.tsx` — new file to create for LocalBusiness JSON-LD
- `app/opengraph-image.tsx` — OG image component
- `app/pricing/page.tsx` — pricing page (FAQ schema)
- `app/privacy-policy/page.tsx` — ICO number placeholder
- `components/layout/nav.tsx` — nav container width fix
- `components/layout/footer.tsx` — company registration copy

### SEO copy implementation

Title tags and meta descriptions from `07-seo-onpage.md` are implemented via Next.js Metadata API in each page's `export const metadata` object, not in the HTML directly. Example:

```tsx
export const metadata: Metadata = {
  title: 'About Rora — AI Consultant, Blackpool',
  description: 'Ryan Wilson built AI automation for his own electrical business. Now he does it for yours. Based in Blackpool, working UK-wide.',
};
```

---

## Adapting This Process for a Client (e.g., The Skinician)

This directory structure and skill sequence can be replicated for any client engagement. Here is what changes and what stays the same.

### Files that change entirely

| File | What changes |
|---|---|
| `05-homepage-copy.md` | Complete rewrite — new brand voice, ICP, proof points, CTAs |
| `06-seo-keywords.md` | Entirely new keyword clusters based on client sector and geography |
| `07-seo-onpage.md` | All page names, titles, descriptions, and H1s change |
| `08-seo-technical.md` | Items 3, 4, 8, 9, 10, 11 are client-specific. Items 1, 2, 5, 6, 7, 12 are likely to remain (same tech stack) |

### Files that are largely templates

These files follow the same structure for every client — only the content changes:
- `README.md` — update client name, entity, repo, file mapping
- `07-seo-onpage.md` — the audit table format is reusable; the content is client-specific

### Process for a new client

1. Run the `icp` skill to define the ICP.
2. Run the `brand-voice` skill to establish tone rules.
3. Run the `competitor-audit` skill to identify differentiation.
4. Run the `homepage-copy` skill — outputs into `05-homepage-copy.md`.
5. Run the `seo-keywords` skill — outputs into `06-seo-keywords.md`.
6. Run the `seo-onpage` skill — outputs into `07-seo-onpage.md`.
7. Run the `seo-technical` skill — outputs into `08-seo-technical.md`.
8. Update `README.md` with the client mapping and status.

For The Skinician specifically: the sector is beauty/aesthetics. The ICP is different (B2C, not B2B). The local modifiers change. But the 7-section homepage framework, the keyword cluster approach, and the technical checklist all carry across without structural change.

---

## Status Tracking

### Deliverables

- [x] `05-homepage-copy.md` — Complete. All 7 sections written. Olive Tree testimonial placeholder marked.
- [x] `06-seo-keywords.md` — Complete. 5 clusters, 60+ keywords, quick wins and gaps identified.
- [x] `07-seo-onpage.md` — Complete. 10 pages audited, FAQ schema ready to paste.
- [x] `08-seo-technical.md` — Complete. 12 items in priority order, code snippets included.
- [x] `README.md` — This file.
- [ ] `01-brand-voice.md` — Not yet created.
- [ ] `02-icp.md` — Not yet created.
- [ ] `03-competitor-audit.md` — Not yet created.
- [ ] `04-content-plan.md` — Not yet created.

### Key Pending Actions (Ryan to action)

- [ ] Fix hookify `application/ld+json` exception — blocks Item 1 (schema)
- [ ] Create Google Business Profile and start postcard verification — 2-week lead time, start immediately
- [ ] Submit sitemap in Google Search Console — takes 20 minutes, unblocks indexing visibility
- [ ] Register with ICO — £52/year, legally required
- [ ] Confirm WhatsApp Business number — unblocks 2 live links in site
- [ ] Upload Ryan's headshot to `/public/images/ryan-wilson-rora.jpg` — highest single conversion gap
- [ ] Insert real Olive Tree testimonial quote into `05-homepage-copy.md` and homepage component
- [ ] Update OG image hex from #6C8EEF to #1B2430 in `app/opengraph-image.tsx`
- [ ] Add company registration to footer: "Rora is a trading name of Pier 7 Projects Ltd. Company number 12894305."
- [ ] Verify `robots.txt` at https://rorahq.co.uk/robots.txt confirms no `Disallow: /`

### Milestone: Ready for Google Indexing

The site is ready to be treated as live from an SEO perspective when all of the following are true:
- [ ] Google Business Profile verified
- [ ] Sitemap submitted in Search Console
- [ ] robots.txt confirmed clean
- [ ] LocalBusiness JSON-LD rendering on homepage
- [ ] No placeholder content visible on any indexed page

# Rora: RampStack Skills Retrospective

**Project:** Rora — AI consultancy marketing site for UK SMBs
**Repo:** wilsons-systems/ai-consultancy-web
**Built:** Apr 19–26, 2026 (one-week sprint)
**Stack:** Next.js 16 + React 19 + TypeScript 5 + Tailwind CSS 4 + Shadcn/ui + Anthropic SDK + Cloudflare Workers
**Scope:** 35+ pages, 7 interactive AI demos, sector landing pages (construction, property, legal, finance, healthcare), GDPR-compliant, WCAG AA verified

---

## What Was Built

A production-ready marketing site with:

- 6 core marketing pages (home, about, pricing, what-we-build, contact, case-studies)
- 8 sector landing pages targeting UK SMB verticals
- 7 live AI demos (Signal, Audit, Brief, Parse, Canvas, Sector picker, Demo) with demo-mode fallbacks
- 4-step assessment quiz backed by Cloudflare Workers
- Full legal suite (privacy policy, terms, cookies) with real GDPR data flow documentation
- Claimed PageSpeed 99/100, WCAG AA contrast verified throughout

Overall quality: strong frontend execution and SEO fundamentals. The gaps are entirely operational: analytics not wired, no tests, no maintenance runbook, two placeholder links shipped.

---

## Skills Audit

### Used well (implicit or explicit)

| Skill | Evidence in Rora |
|---|---|
| `brand-identity` | Consistent visual identity, logo, color tokens throughout |
| `brand-style-guide` | Tailwind + Shadcn tokens applied uniformly |
| `landing-page-copy` | Keyword-first page titles, sector-specific hero copy |
| `seo-onpage` | Sitemap, robots.txt, JSON-LD schemas, OG images |
| `seo-technical` | Clean URL structure, canonical tags, meta descriptions |
| `frontend-component-build` | Shadcn/ui component library, reusable layout primitives |
| `accessibility-audit` | WCAG AA contrast verified, semantic HTML |
| `security-baseline` | Origin checking on Workers, IP rate limiting, streaming via Claude Sonnet |
| `performance-optimization` | PageSpeed 99/100 claimed |

### Skipped or compressed to the point of risk

| Skill | What happened | The cost |
|---|---|---|
| `brand-discovery` | No documented brief; brand built assumption-first | No single source of truth for positioning; harder to brief freelancers or extend later |
| `creative-brief` | No upfront brief artefact | Copy and visual direction evolved ad-hoc across the sprint |
| `information-architecture` | 35+ pages built bottom-up, not from a sitemap exercise | Sector pages added on day 6 as a reactive SEO move, not planned |
| `seo-keyword` | Done as a day-7 "pass" not as input to IA and copy | Keyword intent didn't shape page structure from the start; some titles retrofitted |
| `content-strategy` | No content plan | Sector pages lack a pillar/cluster architecture; SEO surface is shallow |
| `analytics-strategy` | Framework wired, analytics never actually installed | No data from day one; impossible to measure launch impact |
| `monitoring-and-alerting` | No error tracking or uptime monitoring documented | Silent failures in Workers demos would go undetected |
| `launch-runbook` | No pre-flight checklist | Placeholder links (WhatsApp, ICO) shipped to production |
| `after-action-report` | No post-launch review | Learnings not captured; same patterns likely to repeat |
| `ux-research` / `jtbd-framing` | Sector targeting is assumption-driven | No evidence that construction/property/legal SMBs were validated as target segments |
| `okr-design` | No documented success metrics | "Launched" is the finish line, but what does success actually mean? |
| `email-deliverability` | Not configured | Assessment leads captured but no transactional email verified |
| `email-sequences` | Not built | Captured leads have no nurture path |
| `design-system` | Shadcn customisations undocumented | Design tokens not extracted to a living reference; hard to hand off |
| `cro-optimization` | No systematic CRO | Assessment quiz is a good conversion mechanic but unoptimised |

---

## What to Do Differently Next Time

This is a sequenced playbook for a project of Rora's shape: B2B marketing site with interactive demos, multi-vertical targeting, 1–2 week build window.

### Phase 0: Discovery (2 days, before any design or code)

Run these skills in order. Nothing starts until this phase is signed off.

1. **`brand-discovery`** — client brief, audience definition, competitor landscape, positioning statement
2. **`jtbd-framing`** — for each target vertical (construction, legal, etc.), what is the job the buyer is hiring an AI consultancy to do?
3. **`information-architecture`** — full sitemap agreed before any routing decisions; sector pages planned from day 1 not day 6
4. **`seo-keyword`** — keyword research feeds directly into IA and page titles; not a post-build pass
5. **`okr-design`** — define what success means: inbound leads per week, assessment completions, trial signups, organic ranking targets

**Rule:** no Figma, no code, no copy until Phase 0 deliverables exist and are reviewed.

### Phase 1: Brand + Content (Days 1–3)

1. **`brand-ideation`** → **`brand-identity`** → **`brand-style-guide`** → **`brand-voice`** — do this end-to-end before opening a code editor
2. **`creative-brief`** → **`creative-direction`** — document the art direction for demos, imagery, and video if applicable
3. **`content-strategy`** → **`pillar-content-architecture`** — sector pages get their own pillar/cluster plan, not ad-hoc copy
4. **`landing-page-copy`** — all key pages written before components are built; copy shapes layout, not the other way around

### Phase 2: Build (Days 4–6)

1. **`design-system`** — before writing the first component, document the Shadcn customisations, token overrides, and component contract
2. **`frontend-component-build`** — build against the documented system
3. **`accessibility-audit`** — run axe-core during build on each component; not a final-day check
4. **`seo-onpage`** + **`seo-technical`** — implemented as the pages are built, not retro-applied on day 7
5. **`performance-optimization`** — Lighthouse CI in PR checks from day 1

### Phase 3: Pre-Launch Gate (Day 7)

This phase is a hard gate. Nothing ships until every item is verified.

1. **`launch-runbook`** — checklist must confirm: zero placeholder links, zero TODO copy, all forms tested, all Workers deployed and tested
2. **`analytics-strategy`** — GA/Plausible/Cloudflare Analytics wired, verified firing on a real device before launch
3. **`monitoring-and-alerting`** — uptime monitoring and error tracking (Sentry or equivalent) configured and alerting to a real channel
4. **`security-baseline`** — document what rate limiting, origin checks, and auth flows are in place; not assumed
5. **`email-deliverability`** — SPF, DKIM, DMARC configured; transactional email tested end-to-end

### Phase 4: Post-Launch (Week 2+)

1. **`after-action-report`** — 48-hour post-launch retrospective while it's fresh
2. **`analytics-strategy`** (review pass) — review first week of data against OKRs
3. **`cro-optimization`** — systematic optimisation of the assessment → contact conversion funnel
4. **`email-sequences`** — build nurture sequence for assessment leads
5. **`usability-testing`** / **`user-feedback-aggregation`** — real user data to validate the sector targeting assumptions
6. **`seo-competitor`** + **`seo-content-gap-audit`** — now the site is live, run the Ahrefs audit suite

---

## Sprint Compression Notes

A one-week sprint is real. Not every skill gets full treatment. Here is where to compress and where not to.

**Never compress:**
- `launch-runbook` — a 30-minute checklist prevents placeholder links shipping
- `analytics-strategy` — wiring analytics takes 20 minutes and is irreversible once you lose day-one data
- `okr-design` — 1 hour upfront defines success; without it you can't prioritise

**Compress with intent:**
- `brand-discovery` → run as a 90-minute brief-writing session, not a 3-day workshop
- `ux-research` → replace with a 1-hour assumption-mapping exercise; mark assumptions as hypotheses to validate post-launch
- `content-strategy` → produce a 1-page content plan covering pillar pages and sector verticals; enough to prevent reactive additions

**Skip and schedule for post-launch:**
- `email-sequences` → build the capture mechanism, schedule the sequences for week 2
- `cro-optimization` → you need data before you can optimise; schedule for week 3
- `seo-competitor` / full Ahrefs audit suite → schedule for week 4 once the site is indexed

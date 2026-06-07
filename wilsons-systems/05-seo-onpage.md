# On-Page SEO — Wilsons Systems

## Framing

The site's on-page SEO is already solid. Schema is on every page. Per-page keyword audit was completed in March 2026. This document covers three things:

1. Full specs for the two new pages that need creating (EV charger, gate automation)
2. Spec for the missing /guides/ index page
3. Safe, incremental improvements to existing pages — no URL changes, no H1 changes

---

## New Page Specs

### Page Spec 1: /ev-charger-installation/

**URL:** `/ev-charger-installation/`
**Parent service pillar:** Electrical
**Priority:** Immediate — this is the highest-value missing page

**Title tag:** `EV Charger Installation Lytham St Annes & Blackpool | Wilsons Systems`

**Meta description (160 chars max):**
`NICEIC certified EV charger installation across Lytham St Annes, Blackpool and the Fylde Coast. Home and commercial EV charging points installed by qualified electricians.`

**H1:** `EV Charger Installation on the Fylde Coast — NICEIC Certified`

**Opening paragraph (brand voice — write this verbatim or close to it):**

> As more homeowners across Lytham St Annes and the Fylde Coast make the switch to electric vehicles, a properly installed home charging point is the obvious next step. As NICEIC Approved Contractors, we install EV charging points to the latest wiring regulations — ensuring your installation is safe, warranty-compliant, and carried out by qualified electricians who understand both the electrical requirements and the practical realities of charging at home. We cover Lytham St Annes, Blackpool, Poulton-le-Fylde, and the wider Lancashire area.

**Page structure (H2 headings):**
- Why choose a professional EV charger installation?
- Which EV charger is right for your home? (covers tethered vs untethered, 7kW vs 22kW, popular brands such as Ohme, Zappi, Pod Point)
- The installation process — what to expect
- OZEV grant (if applicable — check whether Wilsons is registered; if not, mention the grant exists and that OZEV-approved installers are required)
- Areas we cover (Lytham St Annes, Blackpool, Poulton-le-Fylde, Fleetwood, Kirkham, Preston)
- FAQ — EV charger installation (4–6 questions)
- CTA — Quick Quote / Get in touch

**Schema types:**
- Service (serviceType: "EV Charger Installation", areaServed: Lytham St Annes + Blackpool + Fylde Coast)
- LocalBusiness (inherit from sitewide schema — NICEIC, address, telephone)
- FAQPage (for the FAQ section)
- BreadcrumbList (Home > EV Charger Installation)

**Internal links to add:**
- From `/electrician-lytham-st-annes/` — add a reference to EV charger installation as a related service
- From the homepage services grid — add EV charger as a visible service option
- From `/heat-pump-electrician/` — cross-link (both are low-carbon home technology services)
- From relevant location pages — "EV charger installation in [town]" with a link to this page

**Image alt text examples:**
- "EV charging point installed by Wilsons Systems, Lytham St Annes"
- "NICEIC approved EV charger installation, Fylde Coast"

---

### Page Spec 2: /gate-automation/

**URL:** `/gate-automation/`
**Parent service pillar:** Security
**Priority:** 3 months

**Title tag:** `Electric Gate Automation Blackpool & Fylde Coast | Wilsons Systems`

**Meta description (160 chars max):**
`Electric gate installation and automation across Blackpool, Lytham St Annes and the Fylde Coast. Supply, installation and servicing by Wilsons Systems.`

**H1:** `Electric Gate Installation & Automation — Fylde Coast`

**Opening paragraph (brand voice):**

> An automated gate is one of the most visible security and kerb appeal upgrades a property can have — and on the Fylde Coast, where we see a wide range of residential and commercial properties, the demand for well-installed gate automation has grown considerably. We supply and install electric gate systems for residential driveways, commercial entrances, and agricultural sites, covering everything from the initial survey and groundwork coordination through to commissioning and ongoing servicing.

**Page structure (H2 headings):**
- Swing gates vs sliding gates — which is right for your property?
- Integration with access control and intercoms (cross-link to access control / Videx page)
- The installation process
- Servicing and maintenance
- Areas we cover
- FAQ — electric gate installation
- CTA

**Schema types:**
- Service (serviceType: "Electric Gate Automation")
- LocalBusiness
- FAQPage
- BreadcrumbList (Home > Gate Automation)

**Internal links to add:**
- From access control / Videx page — gate automation as a related service
- From security alarms page — gate automation as part of a complete security solution
- From relevant location pages
- From the homepage, if gate automation is listed in the Security section of the services grid

---

### Page Spec 3: /guides/ (Index Page)

**URL:** `/guides/`
**Priority:** Low effort — create immediately

**Title tag:** `Electrical & Security Guides | Wilsons Systems`

**Meta description:**
`Guides and advice from Wilsons Systems — covering home security, smart home technology, electrical work, and more. Written by our qualified team.`

**H1:** `Guides & Advice from Wilsons Systems`

**Page structure:**
A clean list of all 6 existing guides with:
- Guide title (linked to the guide page)
- One-sentence description of what the guide covers
- The relevant service area (Electrical / Security / Smart Homes)

No complex navigation needed — a simple, readable index is sufficient.

**Schema:** ItemList listing all guide pages (ListItem with URL and name for each guide).

**Internal links:**
- From the homepage — add a "Guides & Resources" link in the navigation or footer
- From each individual guide page — "See all guides" link back to this index
- From relevant service pages — where a guide is directly relevant, link to the guide from the service page and vice versa

---

## Existing Page Improvements

### /about/ — Add team profiles

**No URL change. No H1 change. Add content only.**

The About page currently lacks named team members. This is the single most important E-E-A-T improvement available — Google's guidelines for YMYL (Your Money/Your Life) and trades categories specifically look for demonstrated human expertise.

**What to add:**
- Ryan Wilson — Managing Director. NICEIC Qualified Supervisor. [X] years in the electrical trade. Brief background paragraph in brand voice — not a CV, not a corporate bio, but a genuine description of how he got here and what he focuses on.
- Named senior team members with qualifications — even first name and certification is better than no attribution. Example: "Jon — Senior Electrician, 18th Edition, 20+ years."
- A photograph of Ryan (and ideally the team). This is the single most humanising element possible.

**Alt text for team photo:** "Ryan Wilson, Managing Director of Wilsons Systems, Blackpool"

### /projects/ — Add real project descriptions

**No URL change. No H1 change. Add content.**

The /projects/ page exists but is likely sparse. Each project entry should include:
- Project name or descriptor (e.g. "Corka Bridge House — Control4 Integration")
- Location area (general — Lytham St Annes, Blackpool, etc. — no exact addresses for privacy)
- Services provided (brief list)
- Brief outcome description (2–3 sentences in brand voice)
- Photograph (real, not placeholder)

**Example project entry (draft):**

> **Corka Bridge House — Full Control4 Smart Home Integration, Lytham St Annes**
>
> A full Control4 smart home integration across a five-bedroom property in Lytham St Annes, covering 14 zones of multi-room audio, comprehensive lighting scene control, automated blinds integration, and gate control — all operated from a single Control4 interface. The project also included a full Hikvision CCTV installation and a Texecom Premier Elite security system, giving the client a genuinely unified view of their home from a single touchpoint.

Each project entry strengthens the E-E-A-T signal and provides keyword-carrying content without requiring URL or structural changes.

### /eicr-testing/ — Add landlord section

**No URL change. No H1 change. Insert new section.**

The EICR page exists. Landlords are a high-value recurring revenue audience — they need EICR certificates on a 5-year cycle for every rental property they own. A landlord with 10 properties is worth 10 jobs, and they tend to be organised about compliance because the legal obligation is clear.

**Section to add (insert as a new H2 section without changing existing content):**

**H2:** EICR Testing for Landlords and Letting Agents

**Copy brief:**
- Explain the legal obligation: since 1 April 2021, all private rental properties in England require an EICR from a qualified electrician every 5 years, or at change of tenancy if sooner
- Explain that the EICR must be carried out by a qualified person (and that Wilsons' NICEIC status confirms this)
- Mention that Wilsons can manage multiple properties for letting agents — reducing the administrative burden
- CTA: contact form / Quick Quote

**Schema:** This content does not require additional schema — it sits within the existing Service + FAQPage schema context. The new copy will be crawled and indexed as part of the existing page.

---

## Image Alt Text Audit

All existing images should follow the pattern: `[Service] by Wilsons Systems, [location]`

Examples:
- CCTV camera installation photo: `"Hikvision CCTV installation by Wilsons Systems, Blackpool"`
- Consumer unit photo: `"Consumer unit upgrade by Wilsons Systems, Lytham St Annes"`
- Control4 panel: `"Control4 smart home installation by Wilsons Systems, Fylde Coast"`
- Team photo (when added): `"Wilsons Systems electrical team, Blackpool, Lancashire"`

**Placeholder images:** Any remaining placehold.co URLs have no useful alt text because they have no useful visual content. Replacing placeholder images with real photographs is the single highest-impact image action — each replacement simultaneously improves E-E-A-T, alt text, and the visual impression for users. Prioritise:
1. Smart homes / Control4 page images (highest value service, most premium audience)
2. CCTV page images
3. About page (team photo)
4. Projects page (all entries)

---

## Title Tag and Meta Description Audit — Existing Pages

The existing per-page keyword audit (March 2026) should have covered this. The following is a checklist for any new pages or pages that have not been reviewed:

- Title tag: under 60 characters, lead with primary keyword, end with brand name
- Meta description: under 160 characters, include a secondary keyword, include a CTA word ("installed", "call", "get a quote")
- H1: one per page, matches or closely relates to title tag keyword intent
- First paragraph: mentions primary keyword within the first 100 words
- Headings hierarchy: H1 → H2 → H3 — no skipped levels, no duplicate H1s

# Information Architecture — Wilsons Systems

## Summary

The IA is largely correct and well-structured. The URL hierarchy is logical, the internal linking strategy is implemented, and the navigation covers the three main service pillars. This document maps what exists accurately, identifies the genuine gaps, and specifies what should be built next.

---

## Current Sitemap (Confirmed)

### Core pages
- `/` — Homepage
- `/about/` — About Wilsons Systems
- `/contact/` — Contact page (form only — no email address published)
- `/projects/` — Completed project showcase
- `/quick-quote/` — Quick Quote form (→ GCP Cloud Function → Simpro)
- `/privacy/` — Privacy policy
- `/404` — Custom 404 page

### Primary service page (electrical — primary location)
- `/electrician-lytham-st-annes/` — Primary electrical service page. Lytham St Annes is the PRIMARY focus.

### Sub-service pages (electrical)
- `/house-rewiring/`
- `/consumer-unit-upgrades/`
- `/eicr-testing/`
- `/emergency-electrician/`
- `/heat-pump-electrician/`

### Sub-service pages (smart home / AV)
- `/multi-room-audio/`
- `/lighting-control/`

### Discipline service pages (8 total — exact URLs to confirm against live site, but these represent the structure)
- Smart homes / Control4
- CCTV / Hikvision
- Security alarms / Texecom
- Access control / Videx
- Networking
- Home cinema / AV
- Electrical (primary — covered by electrician-lytham-st-annes)
- Commercial (mentioned but possibly thin)

### Location pages (5)
- `/blackpool/` or `/electrician-blackpool/`
- `/poulton-le-fylde/`
- `/fleetwood/`
- `/kirkham/`
- `/preston/`

Note: Lytham St Annes is covered by the primary service page (`/electrician-lytham-st-annes/`), not a dedicated location page. This is a valid structural choice — the service page with the primary keyword functions as both.

### Guides section (6 pages, no index page)
- `/guides/texecom-connect-app/`
- `/guides/diy-vs-professional-alarm-installation/`
- `/guides/wireless-vs-wired-alarm/`
- `/guides/hikconnect/`
- `/guides/hikvision-health-monitoring/`
- `/guides/control4-vs-diy/`

### Infrastructure
- `sitemap.xml`
- `robots.txt`

**Total: 30+ pages confirmed.**

---

## Navigation Hierarchy

The site uses a 3-column dropdown navigation already implemented:

| Column 1: Electrical | Column 2: Security | Column 3: Smart Homes & AV |
|---|---|---|
| Lytham St Annes (primary) | CCTV | Control4 / Smart Homes |
| House Rewiring | Security Alarms | Multi-Room Audio |
| Consumer Unit Upgrades | Access Control | Lighting Control |
| EICR Testing | Gate Automation (missing) | Home Cinema |
| Emergency Electrician | | |
| Heat Pump Electrician | | |
| EV Charger Installation (missing) | | |

The navigation structure is sound. The two gaps highlighted above are genuine — services Wilsons offers with no corresponding page.

---

## Internal Linking Strategy — Documented

The internal linking strategy is already implemented. The logic is:

**Service ↔ Service:** Each service page links to related services where there is a natural upgrade or companion relationship.
- Example: EICR testing page links to consumer unit upgrades (EICR often reveals the need for a new consumer unit)
- Example: Security alarms page links to CCTV and access control (natural security bundle)
- Example: Smart homes page links to lighting control and multi-room audio (sub-services of the smart home offer)

**Service ↔ Location:** Each service page links to location pages where the service is particularly relevant; each location page links back to key services.
- Example: Electrician page links to Blackpool, Poulton, Fleetwood, Kirkham, Preston location pages
- Example: Location pages link to the relevant primary service page

**Location ↔ Location:** Location pages link to adjacent location pages to build a geographic cluster.
- Example: Blackpool page links to Poulton-le-Fylde, Fleetwood; Kirkham page links to Preston

This creates a well-structured cluster that Google can interpret as geographic and topical authority across the Fylde Coast.

---

## Genuine Gaps in the IA

### Gap 1: /guides/ index page

**Status: Missing.**

The 6 guide pages under `/guides/` exist and are likely indexed, but there is no `/guides/` index page listing them. This means:
- There is no single page a user can navigate to see all guides
- Google has no hub page to establish the guides section as a coherent topical cluster
- There is no obvious location to add new guides in the navigation

**Fix:** Create `/guides/` as a simple index page listing all 6 guides with title, description, and link. This is low effort and immediately useful. See `05-seo-onpage.md` for the page spec.

### Gap 2: /ev-charger-installation/ page

**Status: Missing. High priority.**

EV charger installation is mentioned in CLAUDE.md as a service Wilsons offers, and it appears in the homepage FAQ. There is no dedicated page. This is a high-growth search category with low local competition — Wilsons is leaving this traffic entirely uncaptured.

**Fix:** Create `/ev-charger-installation/` as a sub-service page under Electrical. See `05-seo-onpage.md` for the full page spec.

### Gap 3: /gate-automation/ page

**Status: Missing.**

Gate automation is listed in CLAUDE.md as a service. It would sit logically under Security as a companion to access control. No page exists, and the keyword cluster ("electric gate installation Blackpool", "gate automation Fylde Coast") has low local competition.

**Fix:** Create `/gate-automation/` as a sub-service page under Security. See `05-seo-onpage.md` for the full page spec.

### Gap 4: Lytham-specific non-electrical landing pages

**Status: Optional — medium-term opportunity.**

Lytham St Annes is the primary geographic target for the affluent audience. Currently, the only Lytham-specific page is `/electrician-lytham-st-annes/`. For the smart home, CCTV, and security services — where the Lytham audience is the ideal buyer — there are no Lytham-specific pages.

Potential additions:
- `/smart-homes-lytham-st-annes/` — targets "smart home installer Lytham St Annes"
- `/cctv-lytham-st-annes/` — targets "CCTV installation Lytham St Annes"

These would follow the same pattern as the existing location pages but serve the high-value Lytham audience specifically for non-electrical services. This is a 3–6 month priority, not immediate.

### What Must NOT Be Added

**Fire alarm page — do not create.** Wilsons does not install fire alarms. Although fire alarms are mentioned tangentially in the commercial FAQ, a dedicated page would generate enquiries Wilsons cannot fulfil. This would damage conversion rate and waste Google's goodwill on a page that converts to nothing.

**Ajax alarms page — do not create.** Wilsons installs Texecom only.

---

## Blog/Content Hub Structure

The `/guides/` section is the content hub. Do not create a separate `/blog/` — this would split the topical authority that is already building around `/guides/`.

**Current state:** 6 guides exist, no index, no ongoing content plan.

**Recommended structure:**
- Add `/guides/` index page immediately (documents existing 6 guides, provides navigation anchor)
- Add 1–2 new guide pages per month on a rolling basis
- Attribute guides to Ryan Wilson by name for E-E-A-T purposes

**New guide priorities (in order):**

| Priority | Guide title | Target intent | Aligns to |
|---|---|---|---|
| 1 | How much does a house rewire cost? | Informational / high volume | /house-rewiring/ |
| 2 | EICR guide for landlords | Commercial intent / recurring revenue | /eicr-testing/ |
| 3 | Control4 vs competitors comparison | Buyer research / high value | Smart homes page |
| 4 | EV charger buying guide | Growing volume / no Wilsons page yet | /ev-charger-installation/ (to create) |
| 5 | Home cinema costs and planning guide | Premium audience / Lytham target | Home cinema page |

Each guide should follow the same structure as existing guides (long-form, detailed, genuine information) and include a clear CTA back to the relevant service page.

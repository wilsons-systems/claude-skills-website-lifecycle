# RampStack Library: Improvement Proposals

Derived from the Rora retrospective. Each proposal is framed as an actionable spec — enough to author a skill or make a targeted change.

---

## New Skills

### 1. `project-intake`

**Category:** Strategy and Discovery (position 0 — first skill in the full-lifecycle sequence)

**The gap:** There is no skill that answers "given this project shape and constraints, which skills do I use and in what order?" Every project starts the same way — someone opens the skills catalog and has to manually figure out the sequence. This is where projects go wrong. Rora started coding on day 1 because there was no intake ritual.

**What it does:** Takes a project brief (type, timeline, team size, budget signal, existing brand Y/N) and outputs a recommended skill sequence with estimated effort per phase, explicit skips with rationale, and a one-page project brief template.

**Trigger phrases:** "we're about to start a new project", "what skills do we need for X", "help me plan a website build", "we have 2 weeks to launch"

**Key outputs:** skill sequence doc, effort estimate, phase gates, go/no-go criteria per phase

---

### 2. `ai-demo-design`

**Category:** Development

**The gap:** Interactive AI demos — streaming responses, pre-recorded fallback scenarios, demo-mode keyboard shortcuts, Cloudflare Workers backends — are now a repeatable pattern for AI product sites. Rora had 7 demos built with no reusable framework. The same pattern will recur on every AI consultancy or AI product site.

**What it does:** Covers the full demo design loop: defining demo scenarios, fallback UX (what happens without an API key or in a sales demo context), streaming vs. mock response architecture, demo-mode activation patterns, scenario management as the product evolves.

**Trigger phrases:** "we need a live demo on the marketing site", "interactive AI showcase", "product tour with real AI", "demo with prerecorded responses"

**Key outputs:** demo scenario inventory, fallback UX spec, demo-mode activation design, scenario maintenance runbook

**Note:** Reference the Rora pattern (Cmd+Shift+D for pre-recorded responses) as a concrete example in the reference files.

---

### 3. `compliance-and-legal`

**Category:** Operations

**The gap:** The `security-baseline` skill covers infrastructure security. Nothing covers the legal layer: GDPR/UK GDPR, AI consent disclosures, cookie consent architecture, ICO registration, data flow documentation, privacy policy content. Rora's legal work was substantial — real data flow docs, AI-specific consent language — and was done with no skill to guide it.

**What it does:** Covers the legal and compliance surface of a website or SaaS product: privacy policy requirements, cookie consent implementation (banner architecture, consent modes), AI-specific disclosure requirements, data flow mapping, ICO/DPA registration (UK context), terms of service structure.

**Trigger phrases:** "we need a privacy policy", "GDPR compliance", "cookie consent", "AI disclosure", "data processing documentation"

**Stack-agnostic note:** Reference Cookiebot, Usercentrics, Osano as consent management options. Reference ICO guidance and EU AI Act for AI-specific disclosures.

---

### 4. `pricing-page-design`

**Category:** Content (or Growth)

**The gap:** Pricing pages are structurally distinct from `landing-page-copy`. They involve tier architecture, anchoring psychology, toggle patterns (monthly/annual), social proof placement at the decision point, FAQ positioning, and trial vs. demo CTA logic. `landing-page-copy` doesn't cover this. Rora has a pricing page; it was built without a framework.

**What it does:** Covers the full pricing page design loop: tier naming and architecture, feature matrix construction, anchoring (which tier to highlight), billing toggle UX, social proof at the decision point, FAQ content strategy, and the CTA hierarchy (free trial vs. book demo vs. contact sales).

**Trigger phrases:** "pricing page", "tier structure", "pricing strategy for the website", "how should we present pricing"

---

### 5. `developer-documentation`

**Category:** Operations

**The gap:** When a project ships, the codebase documentation (CLAUDE.md, architecture overview, worker deployment runbook, environment setup) is almost always missing or a stub. Rora's CLAUDE.md is a stub. A new developer needs 2–3 hours to understand Next.js → Cloudflare Workers → Microsoft Graph OAuth → Claude Sonnet. This is avoidable.

**What it does:** Covers the documentation a codebase needs to be maintainable: architecture overview (system diagram narrative), environment setup, deployment runbook, third-party integration map, known gotchas, local development guide.

**Trigger phrases:** "document the codebase", "write a CLAUDE.md", "onboard a new developer", "deployment runbook", "architecture documentation"

**Note:** Complements `team-onboarding-playbook` (which covers human onboarding) — this skill is specifically about codebase documentation.

---

## Improvements to Existing Skills

### `launch-runbook` — add a no-placeholder gate

**Change:** Add an explicit pre-flight check item: "Search the deployed site for placeholder text — `[placeholder]`, `#coming-soon`, `TODO`, `lorem ipsum`, dummy phone numbers, dead mailto links. Zero failures required to proceed."

**Why:** Rora shipped with WhatsApp and ICO placeholder links. A launch-runbook checklist item catches this in 5 minutes. It didn't exist.

---

### `analytics-strategy` — make pre-launch verification a hard gate

**Change:** Add a "Launch verification" section with a single required step: verify analytics is firing on a real device (not localhost) before marking launch complete. Include a 3-step verification process: open network tab, load a page, confirm the analytics payload appears.

**Why:** Rora had analytics wired at the code level but never installed/verified. Day-one data is gone. This is irreversible. A 15-minute verification step prevents it.

---

### `seo-keyword` — reposition as prerequisite for information-architecture

**Change:** Add to the "When to use" section: "Run this skill before finalising information architecture. Keyword intent should shape page structure and URL taxonomy, not be applied retroactively." Add a cross-reference to `information-architecture` with the note: "If you haven't completed `seo-keyword` yet, do that first."

**Why:** On Rora, SEO was a day-7 pass. Keyword research after IA and copy are written means retrofitting titles and adding reactive pages. Running it first means the structure is right from the start.

---

### `design-system` — add component library customisation section

**Change:** Add a section: "When using a component library (Shadcn/ui, Radix, Mantine, etc.)." Cover: how to document token overrides, where to store the custom token file, how to document component variants that deviate from defaults, and what a handoff-ready design system reference looks like when the base is an open-source library.

**Why:** Most projects today extend a component library rather than building from scratch. The current skill reads as if you're building a design system from zero. The customisation-documentation pattern is different and equally important.

---

### `okr-design` — add to Strategy and Discovery cross-references

**Change:** Add `okr-design` to the cross-references section of `brand-discovery`, `information-architecture`, and `content-strategy` with the note: "Define success metrics before this phase closes." Also add `okr-design` to the recommended Sprint Track for any project type (see structural improvements below).

**Why:** OKRs read as a product-team concern. For a 1-week sprint marketing site, OKR design is just "what does a successful launch look like?" — it takes 30 minutes and prevents launching without a definition of success.

---

## Structural Improvements

### Add `prerequisites` field to SKILL.md frontmatter

**Change:** Add an optional `prerequisites` field to the YAML frontmatter spec:

```yaml
prerequisites:
  - brand-discovery
  - information-architecture
```

Skills with clear upstream dependencies (e.g. `seo-keyword` needs `brand-discovery`) should list them. This makes sequencing machine-readable for catalog tooling and surfaces it in the rampstack.co skills directory.

---

### Add `effort` field to SKILL.md frontmatter

**Change:** Add an optional `effort` field:

```yaml
effort: "half-day"
```

Allowed values: `15-30 min`, `half-day`, `1 day`, `2-3 days`, `ongoing`. Used for sprint planning. The project-intake skill would aggregate these to produce a phase effort estimate.

---

### Add Sprint Tracks to the catalog

**What:** A "Sprint Tracks" section in the README and a `/docs/sprint-tracks/` directory. Each track is a one-page sequenced skill list for a common project type, with explicit skips and rationale.

**Four initial tracks to write:**

1. **1-week marketing site sprint** — highest-ROI skills only, explicit skips with rationale, phase gates compressed to hours not days
2. **B2B SaaS launch** — full lifecycle; the Threshold walkthrough already covers this but a standalone track doc makes it more actionable
3. **SEO content site** — content and SEO heavy; pillar architecture, programmatic SEO, Ahrefs audit suite, growth tooling
4. **AI product demo site** — leverages the new `ai-demo-design` skill; targets teams building AI-native marketing sites

**Why:** The Threshold reference build is the only sequencing guide today, and it's embedded in walkthrough format. Teams with different project shapes need different sequences. Sprint tracks make this immediately actionable without reading a full walkthrough.

---

### Add a "1-week sprint" reference build

**What:** A companion reference build to Threshold showing what a compressed 5-day marketing site sprint looks like. Use Rora's project shape (AI product, SMB targeting, multi-vertical, 7 demos) as the template — anonymised and fictionalised.

**Key difference from Threshold:** Threshold shows the full lifecycle done right. The sprint build shows the lifecycle compressed — including explicit notes on what was skipped, what trade-offs were made, and what the post-launch backlog looks like. The sprint build is more honest about real-world constraints.

**Deliverables it would demonstrate:**
- Phase 0 brief produced in 90 minutes
- Keyword research feeding into IA on day 1
- Analytics wired before launch (not after)
- Launch runbook checklist with no-placeholder gate
- Post-launch backlog itemising what was deliberately deferred

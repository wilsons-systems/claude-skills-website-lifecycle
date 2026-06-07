# Homepage Copy Assessment — Wilsons Systems

## Framing

The homepage is already built, ranking, and converting. This is not a rewrite brief. The SEO preservation rules are absolute: do not touch the title tag, do not touch the H1, do not change any URL. This document identifies incremental improvements — additions and refinements that lift conversion without disturbing what is working.

---

## Hero Section — Confirmed Copy (Do Not Change)

**Title tag (must not change):**
"Electricians Lytham St Annes | CCTV, Security & Smart Homes | Wilsons Systems"

**H1 (must not change):**
"Electricians in Lytham St Annes & Blackpool — Smart Home, CCTV & Security Specialists"

Both are well-constructed. The H1 leads with Lytham (primary, affluent audience) and includes Blackpool (wider reach), then lists the three service pillars. There is nothing to improve here. The risk of any change outweighs any potential gain.

**Hero subtext / supporting copy:** Assess on the live site. If it currently describes the offer well and includes a clear CTA, leave it. If it is generic or missing a CTA, the only safe addition is a social proof line below the H1 — see below.

---

## What Could Be Added (Without Affecting Rankings)

### 1. Social proof metric

A quantified trust line near the hero section would reinforce credibility for first-time visitors. This does not require a page change that touches keyword-bearing elements.

Suggested line: "Trusted by 500+ homes and businesses across the Fylde Coast for over 40 years."

Alternatively, if job completion data is available from Simpro: "Over [X] jobs completed across Lancashire — with a 5-star Google rating."

This line sits below the H1 as supporting copy, not as a heading. It does not affect title tag or H1.

### 2. Quick Quote CTA — review the button copy

The Quick Quote system is a genuine differentiator — instant quote generation via Simpro integration is not what a typical local electrician offers. The CTA button copy should communicate this clearly.

**Assess the current button text.** If it says "Get a Quote" or "Contact Us", this is underperforming. The correct copy for a quick-response system is:

- "Get Your Quick Quote" (clear, action-oriented, unique)
- "Get a Same-Day Quote" (if response time can be guaranteed)
- "Quick Quote — 2 Minutes" (communicates ease, reduces friction)

The button should be high-contrast against the dark background (#C41E2A red is already defined for this purpose) and appear in the hero section — not buried below the fold.

### 3. FAQ section — review the 8 questions

The homepage FAQ uses FAQPage schema and contributes to visibility in Google's FAQ rich results. The 8 questions are a good number — do not add more without removing an equivalent one. The right set of questions to keep are the ones that:
a) Represent genuine pre-booking objections
b) Are specific enough to carry keyword value

**Questions likely already there (based on CLAUDE.md and site structure):**
- What areas do you cover?
- Are you NICEIC approved?
- Can you install Control4 systems?
- Do you install EV chargers? (if this is there, it supports the case for a dedicated page)
- What's the difference between a consumer unit and a fuse box?

**Questions possibly missing from the current 8:**
- "How quickly can you attend for an emergency?" — critical pre-booking question for emergency electrical work. If not in the FAQ, add it. If the 8 is already full, replace the weakest existing question.
- "Do you offer payment plans?" — not answered anywhere on the site. If Wilsons does offer staged payment or finance, this should be answered prominently. If they do not, the question can be skipped — do not raise an objection you cannot answer positively.
- "Can I see examples of your work?" — if the /projects/ page exists, the FAQ can direct users there: "Yes — visit our projects page to see examples of completed smart home, CCTV, and electrical installations." This is a useful internal link opportunity.

### 4. Areas we cover section

This section already exists. One safe improvement: link each town name to its corresponding location page. This passes internal link equity to the location pages and gives users a clear click path to location-specific content.

**Example change:** "Lytham St Annes" in the areas list links to `/electrician-lytham-st-annes/`, "Blackpool" links to the Blackpool location page, "Poulton-le-Fylde" links to `/poulton-le-fylde/`, and so on.

This is a minimal HTML change (wrapping existing text in anchor tags) with meaningful SEO and UX benefit.

---

## The #1 Conversion Gap: Real Photography

If the smart home, CCTV, and Control4 sections of the homepage still use placehold.co placeholder images, this is the single most impactful improvement available.

The Lytham St Annes audience — affluent homeowners making £5k–£50k+ investment decisions — will notice placeholder imagery. They compare Wilsons against other premium installers. A competitor with real photography of finished Control4 installs will convert better, all else being equal.

**Specifically needed:**
- A real photograph of a Control4 panel or touch screen in a high-end Lytham or Fylde Coast property
- A real photograph of a Hikvision CCTV installation (professional rack, cameras in situ)
- A real photograph of a completed electrical installation (new consumer unit, or clean cable management)

If professional photography is not immediately available, clear smartphone photos of real installations are substantially better than placehold.co. The bar is not high — it is genuine versus obviously fake.

---

## Social Proof: Google Review Volume

The site embeds real Google reviews (Russell Dawson, Iain McIntyre, Andrew Wild) in Review JSON-LD schema. This is correct and valuable. However, 13 reviews total is below the threshold where the review count itself becomes a positive trust signal. At 50+ reviews, the volume becomes a selling point. At 100+, it is a significant competitive advantage.

**Review count target: 50+ within 12 months.**

The most effective method is a consistent post-job request process. The following WhatsApp message template should be sent to every completed job, within 24 hours of completion:

---

**WhatsApp review request template:**

Hi [Name], thanks for having us out today — really glad to get your [service type, e.g. consumer unit upgrade / Control4 installation / CCTV install] sorted. If you have 2 minutes, a Google review would mean a lot to us — it helps other homeowners on the Fylde Coast find us: [Google review direct link]. Ryan & the Wilsons team

---

Notes on the template:
- Use the customer's first name (personalisation lifts response rate)
- Specify the service type (jogs their memory, makes the message feel personal not generic)
- Give a reason that appeals to community reciprocity ("helps other homeowners") rather than just asking for a favour
- Include the direct Google review link (not the Google Maps page — the direct review link opens the review box immediately)
- Keep the tone warm but not sycophantic — consistent with the brand voice
- No emojis beyond a single thumbs up — matches the brand register

**How to get the direct Google review link:** In Google Business Profile → "Get more reviews" → copy the direct link. It looks like: https://g.page/r/[business-ID]/review

**Volume goal:** Send to every completed job. If Wilsons completes 10–15 jobs per week, a 20–30% response rate yields 2–4 new reviews per week. At that rate, 50 reviews is achievable within 4–6 months.

---

## Copy Tone Check for the Homepage

The homepage copy should be assessed against the brand voice criteria. Specifically:

- Does the hero subtext use the advisory register ("we recommend", "in our experience") or does it drift into contractor clichés ("fully qualified", "competitive rates")?
- Does the services grid describe services in terms of what the client gets (outcomes) or what Wilsons does (inputs)?
- Does the Control4 section describe the Control4 experience — what it feels like to use a properly integrated system — or does it list technical specifications?

If any of these are drifting toward generic contractor language, the fix is targeted copy replacement on those specific elements — not a page rewrite. The H1 and page structure do not change.

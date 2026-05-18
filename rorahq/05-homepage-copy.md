# Rora — Homepage Copy (Full Rewrite)

**Skill:** `landing-page-copy`  
**Date:** May 2026  
**Conversion goal:** Free AI Assessment completion → discovery call booking  
**Brand voice:** Quietly confident, straight-talking, reliably human  
**Status:** Ready to implement in `app/page.tsx`

---

## Section 1 — Hero

**Pre-heading (small label above headline):**
> AI automation for small businesses

**Headline:**
> Your business, running in the background.

*Keep the locked tagline. It is the strongest line on the page.*

**Sub-headline:**
> Most businesses run on four systems that don't talk to each other, leads that go cold overnight, and quotes that take an hour to write. We connect them, automate the work, and hand you back your evenings.

**Reassurance line (below sub-headline, smaller weight):**
> Nothing new to learn. We connect what you already use.

**Primary CTA:**
> See what's possible for your business →

*Links to `/assessment`*

**Social proof hook (directly under CTA — small text):**
> Trusted by trades businesses across the Fylde Coast and Lancashire

---

## Section 2 — Proof bridge (full-width centred, large type)

*This section acts as a pivot — it acknowledges the scepticism and answers it before the visitor asks.*

**Headline:**
> Built by someone who automated their own business first.

**Three-beat sub-line:**
> Quote time: 47 minutes → 12.  Leads: captured overnight, not next morning.  Invoices: chased automatically, not by hand.

**Body:**
> These aren't projections. They're what happened when we fixed our own business. Rora does the same for yours.

---

## Section 3 — Problem

*Make the pain specific. The visitor should recognise themselves.*

**Section label:** THE PROBLEM

**Headline:**
> The admin doesn't stop when you leave site.

**Body:**
> A lead comes in at 7pm. Nobody enters it until tomorrow. By then the prospect has already called someone else.
>
> A job finishes on Friday. The invoice doesn't go out until Tuesday. That's four days of cash sat on a spreadsheet.
>
> You spend 45 minutes writing a quote that took 15 minutes to spec. Then you do it again. And again.
>
> The work is good. The business runs fine. But the admin is always one step behind.

---

## Section 4 — Solution

**Section label:** WHAT WE BUILD

**Headline:**
> From your first lead to your last invoice — we automate the lot.

**Intro paragraph:**
> Most clients start with one thing. Automating quotes, or capturing leads, or chasing invoices. That first fix usually proves the point. Then we go further.

**Three service blocks:**

---

**Block 1: Lead & Enquiry Automation**

> An email lands at 10pm. By morning it's a lead in your system, the prospect has an auto-reply, and you've got a job to look at. Nothing touched — just handled.
>
> Works with: Gmail, WhatsApp, website contact forms, Instagram DMs.

**Mini CTA:** What does this look like? →

---

**Block 2: Quote & Job Automation**

> Describe the job in plain English — or by voice note on the drive over. We produce a structured quote: line items, labour, materials, margin. Ready to send before you've started the next job.
>
> Works with: Simpro, ServiceM8, plain email — we meet your system, not the other way round.

**Mini CTA:** See a live example →

---

**Block 3: Admin & Invoicing Automation**

> Every Monday morning: what's overdue, what needs chasing, what's at risk. Invoices chased automatically at set intervals. No more calls you'd rather not make.
>
> The backlog doesn't come back.

**Mini CTA:** How does it run? →

---

**Bespoke build note (below three blocks):**

> Need something more specific? That's where we start. Custom dashboards, client portals, live job trackers, sector-specific tools — if it's a recurring headache, it's buildable.

---

## Section 5 — Proof (case study card)

**Section label:** REAL RESULTS

**Headline:**
> A 6-person electrical business. Before and after.

**Case study card — Wilsons Electrical:**

> **The situation:** 50+ overdue invoices. Quotes taking 47 minutes each. Leads coming in overnight with no one to respond.
>
> **What we built:** AI quote generation from voice note. Automated lead capture from email and WhatsApp. Daily admin briefing with overdue invoice list.
>
> **The result:**
> - Quote time: 47 min → 12 min
> - Invoice backlog: cleared in first month
> - Overnight leads: responded to automatically, in Simpro by morning
> - Hours saved per week: ~6
>
> *This is our own business. The numbers are real.*

**CTA under card:**
> Read the full case study →  
> Or: See your own numbers with the free assessment →

---

## Section 6 — Objection handling

*The three objections this audience brings: "it won't work for my business", "I'll have to learn something new", "it'll cost too much".*

**Section label:** THE HONEST BIT

**Headline:**
> Three questions we get asked every time.

**Q&A format:**

---

**Q: Will this actually work for a business like mine?**

> We only take on clients we're confident we can improve. The free assessment tells you honestly — whether that's a yes with a clear plan, or a "not right now, but here's why."

---

**Q: Do I need to learn a new system?**

> No. We connect what you already use — your email, your quoting software, your calendar. You don't touch the automation. You just see the results.

---

**Q: What does it cost?**

> Most clients start from around £150/month. No setup fees on trial builds. No long contracts — if it's not working within 60 days, you don't continue.

---

## Section 7 — Final CTA

**Headline:**
> See what your business could look like.

**Body:**
> 13 questions. 3 minutes. We'll tell you exactly where AI makes a difference in your business — and what it would cost.

**Primary CTA (large, coral button):**
> Get your free AI assessment →

**Secondary CTA (text link below):**
> Or get in touch directly → hello@rorahq.co.uk

**Reassurance micro-copy (below CTA):**
> No sales call required to get your report. No commitment. Just an honest assessment.

---

## Implementation notes

**File:** `app/page.tsx`

**Changes from current version:**
1. Section 1 sub-headline: replace with new version above
2. Section 2 (pivot/proof bridge): update numbers to match Wilsons actual figures
3. Section 3 (problem): replace "tangle of disconnected systems" copy with specific scenarios above
4. Section 4 (solution): replace service card copy with outcome-led versions above
5. Section 5 (case study): ensure Olive Tree numbers are added once Ryan provides final data; Wilsons card should show real numbers as above
6. Section 6 (FAQ/objection): check current FAQ items — ensure all 3 objections are covered with direct, plain-English answers
7. Section 7 (final CTA): change "Find out what's possible" → "See what your business could look like"

**Ryan's photo:** Needs adding to section 2 or section 5. Circular crop, genuine setting. Without it, section 2 reads as a claim. With it, it reads as a person making a claim — far higher trust signal.

---

## Template note for client work (The Skinician)

The 7-section structure adapts directly. Swap:
- Section 2: Ryan's automation story → Lauren's treatments + appointment workflow story
- Section 3: "admin after site" → "enquiries missed on Instagram overnight"
- Section 5: Wilsons case study card → Skinician results (after 60 days)
- Section 6: "learn a new system?" objection stays. Cost objection: "£200/month, 30 days notice"
- Section 7: CTA → book a free consultation rather than assessment quiz

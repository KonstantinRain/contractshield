## Technical notes for v0

- Output plain HTML with Tailwind CSS utility classes
- Do not use React, Vue, or any JS framework
- Use semantic HTML: `<nav>`, `<main>`, `<section>`, `<footer>`, `<article>`
- Add `id` attributes to all sections for smooth-scroll navigation
- Add `scroll-behavior: smooth` to the html element
- FAQ accordion: vanilla JS with `classList.toggle`, CSS `max-height` transition
- Mobile hamburger menu: vanilla JS toggle for showing/hiding nav links
- All CTA `href` values should be `"#"` as placeholders
- The hero product mockup must be built entirely in HTML/CSS — no image files
- Comparison table: wrap in `overflow-x-auto` div for mobile horizontal scrolling
- Import DM Sans from Google Fonts in the head
- Ensure accessible contrast ratios on all text
- Use `loading="lazy"` on any images below the fold
- Total page should feel cohesive and professional, like a real product landing page from a funded startup


# ContractShield Landing Page — v0 Prompt

## Global instructions

Generate a single-page landing page as **plain HTML with Tailwind CSS classes**. This will be used in a Ruby on Rails app. Do not use React, JSX, or JavaScript frameworks. Use vanilla JS only where needed (mobile menu toggle, FAQ accordion, scroll navigation). The page must be fully responsive and mobile-first.

**Design system:**
- Primary colour: teal `#0F6E56` (buttons, accents, highlights)
- Primary hover: `#085041`
- Primary light: `#E1F5EE` (backgrounds, badges)
- Risk red: `#E24B4A`, background `#FCEBEB`
- Risk amber: `#EF9F27`, background `#FAEEDA`
- Risk green: `#639922`, background `#EAF3DE`
- Text primary: `#1a1a1a`
- Text secondary: `#6b6b6b`
- Backgrounds: white `#ffffff` and light gray `#f8f8f6`
- Borders: `#e5e5e3`
- Font: `"DM Sans", sans-serif` — import from Google Fonts
- Border radius: 8px for small elements, 12px for cards, 16px for large panels
- No gradients. No shadows heavier than `shadow-sm`. Clean, flat, professional.
- Tone: fintech/insurtech, not legaltech. This should feel like a business protection tool, not a law firm website.
- Target audience: UK SME operations directors and founders (10–80 employees), non-lawyers who sign contracts regularly.

---

## Navigation bar (fixed top)

A fixed top navigation bar, white background, subtle bottom border. Horizontally laid out:

**Left:** ContractShield logo — use an inline SVG of a small shield icon in teal, followed by the text "ContractShield" in font-weight 600.

**Centre (desktop) / hamburger menu (mobile):**
- The problem
- How it works
- Why not ChatGPT
- Pricing
- FAQ

Each link smooth-scrolls to the corresponding section ID.

**Right:** Two buttons:
- "Log in" — text link, no background
- "Try free" — small teal button (`bg-[#0F6E56] text-white px-4 py-2 rounded-lg text-sm font-medium`)

Mobile: collapse centre links into a hamburger menu. Keep "Try free" button visible.

---

## SECTION 1 — Hero (compact, 5% of visual weight)

**Goal:** Immediately communicate what this is and for whom. Compact, not a full-viewport hero. No wasted space.

**Layout:** Two columns on desktop (text left 45%, visual right 55%). Stacked on mobile (text first, visual below).

**Left column:**

Headline (h1, text-3xl md:text-4xl, font-bold, leading-tight):
"Get clarity before you sign."

Subheadline (text-lg, text-secondary, max-w-md, margin-top 12px):
"AI contract risk review built for business owners, not lawyers. Upload a supply contract, get a colour-coded risk report in 2 minutes."

CTA group (margin-top 24px, flex row, gap 12px):
- Primary button: "Review your first contract free" — teal bg, white text, rounded-lg, px-6 py-3, font-medium
- Secondary button: "See how it works ↓" — outlined, border-[#0F6E56], text-[#0F6E56], rounded-lg, px-6 py-3 — scrolls to How It Works section

Trust badges row (margin-top 16px, flex row, gap-6, text-xs, text-secondary):
- "✓ No sign-up required"
- "✓ GDPR compliant"
- "✓ Data never stored"
- "✓ Built for UK law"

**Right column:**

An embedded product screenshot mockup. Build this as a styled HTML composition (not an image) that looks like an email client with the ContractShield sidebar open. This is critical — it's the first thing people see.

The mockup should be contained in a rounded-xl border card with a subtle shadow-sm, showing:

**Email area (left ~60%):**
- A grey toolbar with three coloured dots (red/amber/green, 8px circles) and text "Inbox"
- From line: "David Palmer — Meridian Supplies Ltd"
- Subject: "New supply agreement for Q3 — please review and sign"
- Brief email body text (2-3 lines)
- An attachment bar: PDF icon + "Meridian_Supply_Agreement_Q3.pdf · 847 KB"
- Below the attachment: a green-bordered prompt bar with teal background (#E1F5EE):
  - Left side: star icon + "Contract detected — check for risks?" + "2-min AI review · £3"
  - Right side: "Review now" button (small, teal bg)

**Sidebar panel (right ~40%):**
- Header bar: shield icon + "ContractShield" + "close" link
- Risk score circle: "71" inside an amber-bordered circle, "MEDIUM RISK" label below
- Three small summary boxes in a row: "3 High risk" (red bg), "4 Medium" (amber bg), "6 Low" (green bg)
- Two clause cards with red left border:
  - "Liability — uncapped" with a one-line explanation
  - "Payment terms — 90 days" with a one-line explanation
- One clause card with amber left border:
  - "Force majeure — missing"
- Two action buttons: "Download PDF report" (teal) and "Send to colleague" (outlined)

Make the mockup scaled down to fit the hero section, approximately 400-500px tall. Use `transform: scale(0.85)` or similar on mobile to prevent overflow. The entire mockup should feel like a real product screenshot, not an illustration.

---

## SECTION 2 — The problem (15% of page)

**Goal:** Make the pain visceral. Sarah should read this and think "that's me."

**Background:** Alternating white/light-gray section (`bg-[#f8f8f6]`).

**Section ID:** `id="the-problem"`

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Most small businesses sign contracts they don't fully understand."

**Subheadline (text-center, text-secondary, max-w-2xl, mx-auto):**
"No in-house lawyer. No time. No budget for a solicitor. So the contract gets signed anyway — and the problems come later."

**Three pain-point cards** in a row (desktop) or stacked (mobile). Each card has a large stat number, a description, and a source:

Card 1 (red-tinted):
- Stat: "£70.4bn"
- Description: "owed to UK SMEs in outstanding late payments — often caused by weak contract terms that were never reviewed."
- Source: "Hiscox, 2025"

Card 2 (red-tinted):
- Stat: "90%"
- Description: "of UK companies experienced late payments last year. The contracts they signed didn't protect them."
- Source: "Coface, 2025"

Card 3 (red-tinted):
- Stat: "62%"
- Description: "of small business invoices are paid late. Most SME owners don't know their contracts entitle them to statutory interest."
- Source: "FreeAgent, 2025"

**Below the stats, a full-width callout box** (white card, teal left border, padded):

"A typical UK solicitor charges £300–500 to review a single contract and takes 5–10 business days. Most SME owners don't pay that. They sign, hope for the best, and find out they had no protection when things go wrong."

---

## SECTION 3 — Product (60% of page, the core)

This is the largest section. It is divided into **five subsections** that flow naturally into each other.

---

### SUBSECTION 3A — How it works

**Background:** White.

**Section ID:** `id="how-it-works"`

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Three steps. Two minutes. One less risk."

**Layout:** Three-step horizontal flow on desktop, vertical stacked on mobile. Each step is connected by a dashed line or arrow.

**Step 1:**
- Number circle: "1" in teal circle
- Icon: envelope/inbox icon
- Title (font-semibold): "Contract arrives in your inbox"
- Description (text-sm, text-secondary): "Our Outlook and Gmail add-on automatically detects contract attachments. A prompt appears: 'Contract detected — check for risks?' You can also drag and drop a PDF on our web app."

**Step 2:**
- Number circle: "2" in teal circle
- Icon: magnifying glass / scan icon
- Title: "AI reviews against UK standards"
- Description: "Our engine checks every clause against UK supply contract benchmarks — UCTA, Late Payment Act, UK GDPR. It scores risk severity and flags missing protections you didn't know to look for."

**Step 3:**
- Number circle: "3" in teal circle
- Icon: document/report icon
- Title: "Get your risk report"
- Description: "A colour-coded report with a 0–100 risk score, clause-by-clause breakdown, missing clause warnings, and suggested counter-language you can copy and send to your supplier."

---

### SUBSECTION 3B — What the report looks like

**Background:** `bg-[#f8f8f6]`

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Every clause scored. Every risk explained."

**Subheadline (text-center, text-secondary, max-w-2xl, mx-auto):**
"Not a wall of AI text. A structured risk report you can act on, share with your team, or use to negotiate with your supplier."

**Layout:** A large centred mockup card (max-w-2xl, mx-auto) showing the report view in detail. Build this as a styled HTML panel:

**Inside the report mockup:**

Top area — risk score:
- Large circle with "71" inside, amber border, "MEDIUM RISK" label
- Below: "Meridian Supply Agreement Q3 2026 · 14 pages · Reviewed in 94 seconds"

Summary row — three mini metric cards:
- "3 High risk" (red bg)
- "4 Medium" (amber bg)
- "6 Low risk" (green bg)

Section label: "HIGH RISK ISSUES" (uppercase, small, muted)

Three clause cards, each with coloured left border (3px solid), containing:

Card 1 (red border):
- Title: "Liability — uncapped"
- Body: "No limitation of liability clause found. Your exposure is unlimited under this contract. UK market standard for supply agreements caps total liability at 100–150% of the annual contract value."
- Link: "View suggested clause →" (teal text)

Card 2 (red border):
- Title: "Payment terms — 90 days net"
- Body: "Payment is due 90 days after invoice. The UK average for supply contracts is 30 days. Under the Late Payment of Commercial Debts (Interest) Act 1998, you are entitled to charge 8% + Bank of England base rate on overdue invoices."
- Link: "View negotiation talking points →" (teal text)

Card 3 (red border):
- Title: "Force majeure — missing"
- Body: "This contract contains no force majeure clause. Neither party can suspend obligations during pandemics, natural disasters, or supply chain disruptions. 89% of UK supply contracts include this provision."
- Link: "View suggested clause →" (teal text)

Section label: "MISSING CLAUSES" (uppercase, small, muted)

Two cards with amber left border:
- "GDPR data processing addendum — Required under UK GDPR if personal data (e.g. delivery addresses) flows through the supply chain."
- "Termination for convenience — No exit clause outside material breach. You are locked in for the full contract term."

Bottom bar:
- Two buttons: "Download full PDF report" (teal bg) and "Send report to colleague" (outlined)
- Small disclaimer: "Risk assessment, not legal advice. Data processed in UK. Zero retention."

---

### SUBSECTION 3C — Where it works (integrations)

**Background:** White.

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Works where you already work"

**Subheadline:**
"You don't need to learn a new tool or change your workflow. ContractShield embeds where contracts already arrive."

**Layout:** Horizontal row of integration cards on desktop (3-column grid), stacked on mobile.

**Card 1 — Outlook add-on:**
- Large email/Outlook icon (build as simple SVG — an envelope shape)
- Title: "Microsoft Outlook"
- Description: "Contracts arrive as attachments. Our add-on detects them and shows a review prompt in the sidebar. One click to review, results appear without leaving Outlook."
- Badge: "Available now" (small teal pill)

**Card 2 — Gmail add-on:**
- Large Gmail icon (build as simple SVG — an envelope shape with red accent)
- Title: "Gmail"
- Description: "Same experience in Gmail. The add-on detects PDF and DOCX attachments, prompts for review, and delivers the risk report in the sidebar panel."
- Badge: "Available now" (small teal pill)

**Card 3 — Web upload:**
- Large upload/browser icon (build as simple SVG — an arrow-up in a browser frame)
- Title: "Web app"
- Description: "No add-on? No problem. Drag and drop any contract on our web app for the same risk review. Works with PDF and DOCX."
- Badge: "Available now" (small teal pill)

**Below the main cards, a "Coming soon" row** with smaller, muted cards in a 3-column grid:

- Xero icon + "Xero — Link contract risk scores to your supplier records" + "Coming soon" badge (gray pill)
- QuickBooks icon + "QuickBooks — Contract intelligence meets accounting" + "Coming soon" badge
- DocuSign icon + "DocuSign — Risk check before you sign" + "Coming soon" badge

---

### SUBSECTION 3D — What makes it different (vs ChatGPT)

**Background:** `bg-[#f8f8f6]`

**Section ID:** `id="why-not-chatgpt"`

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Why not just paste it into ChatGPT?"

**Subheadline (text-center, text-secondary, max-w-2xl, mx-auto):**
"Fair question. Here's the honest answer."

**Brief paragraph** (text-center, max-w-3xl, mx-auto, text-sm leading-relaxed):
"General AI tools can summarise a contract if you know the right questions to ask. But they don't proactively check for missing clauses, don't score risk against UK legal benchmarks, give different answers every time, and their output is a conversation — not a structured report you can act on."

**Comparison table** — responsive. On desktop: full table. On mobile: wrap the table in a div with `overflow-x-auto` for horizontal scroll.

Table columns: Feature | ChatGPT / Claude | Solicitor | ContractShield (highlighted)

Apply a subtle teal background (#E1F5EE) to the ContractShield column cells.

Table content:

| Feature | ChatGPT / Claude | Solicitor | ContractShield |
|---|---|---|---|
| Price | £20/mo subscription | £300–500 per review | **£3 per contract** |
| UK law built in | Generic, US-biased training | Yes — expert knowledge | Yes — UK playbooks for UCTA, Late Payment Act, UK GDPR |
| Finds missing clauses | Only if you ask the right question | Yes | Yes — automatically, against a supply contract checklist |
| Structured risk score | No — prose paragraphs | No — verbal or email advice | 0–100 score with red / amber / green clause ratings |
| Consistent output | Different answer every time | Depends on the solicitor | Same methodology, same scoring, every time |
| Turnaround | Instant if you know what to prompt | 5–10 business days | 2 minutes |
| Data privacy | Unclear — may train on your data | Legal privilege applies | GDPR compliant, zero data retention, UK-processed |
| Actionable output | "You should consult a lawyer" | Advice via email | PDF report with counter-language you can send to your supplier |

Use checkmark and cross icons in the table cells where appropriate for visual scannability.

Below the table, a single callout line (text-center, font-semibold, text-lg, mt-8):
"ChatGPT is a conversation. ContractShield is a risk report."

---

### SUBSECTION 3E — What it checks

**Background:** White.

**Headline (h2, text-xl font-bold, text-center):**
"Built for the contracts UK small businesses actually sign"

**Subheadline (text-center, text-secondary):**
"Starting with supply agreements — the highest-risk, most commonly ignored contract type for SMEs."

**Layout:** A grid of contract types. One featured card (supply agreements, span 2 columns on desktop) and five standard cards.

**Featured card** (larger, teal border-2, span full width or 2 cols):
- Badge: "Core speciality" (teal bg, white text, small rounded pill)
- Title: "Supply & vendor agreements"
- Two-column list of what gets checked: "Liability caps · Payment terms · Force majeure · Delivery obligations · Warranty periods · Termination rights · GDPR data processing · Indemnification · Insurance requirements · Dispute resolution"

**Standard cards** (smaller, gray border, single column each — arrange as 2x3 or 3x2 grid):
- "Service contracts" — IT, marketing, cleaning, consulting agreements
- "Freelancer & contractor agreements" — Scope of work, IP ownership, payment, termination
- "NDAs & confidentiality" — Scope, duration, carve-outs, permitted disclosure
- "SaaS & software terms" — Auto-renewal, data rights, SLA commitments, liability
- "Commercial leases" — Break clauses, rent review, repair obligations, deposit terms

---

## SECTION 4 — Pricing (20% of page)

**Background:** `bg-[#f8f8f6]`

**Section ID:** `id="pricing"`

**Headline (h2, text-2xl md:text-3xl, font-bold, text-center):**
"Cheaper than the risk of not checking."

**Before pricing cards — a benefits summary row:**
Four compact benefit pills/badges in a horizontal centred row (flex-wrap, gap-3):
- "✓ Full risk report with every review"
- "✓ UK supply contract playbook"
- "✓ Missing clause detection"
- "✓ Suggested counter-language"

Each pill: bg-white, border, rounded-full, px-4 py-2, text-sm.

**Pricing cards** — two cards side by side on desktop (max-w-3xl mx-auto, grid grid-cols-2 gap-6), stacked on mobile. The Pro card has a "Most popular" badge and a teal top border.

**Card 1 — Pay as you go:**
- White card, rounded-xl, border, padding 32px
- Header: "Pay as you go" (text-lg, font-semibold)
- Price block: "£3" (text-4xl, font-bold) + "per contract" (text-sm, text-secondary)
- Horizontal divider
- Features list (text-sm, each line with a gray checkmark icon):
  - Full colour-coded risk report
  - 0–100 risk score
  - Missing clause detection
  - Suggested counter-language
  - PDF export & sharing
  - UK supply contract playbook
- CTA button (full width): "Review your first contract free" — outlined teal border, teal text
- Subtext below button (text-xs, text-secondary, text-center): "No subscription. No commitment."

**Card 2 — Pro (featured):**
- White card, rounded-xl, border-2 border-[#0F6E56], padding 32px
- "Most popular" badge at very top of card (teal bg, white text, text-xs, rounded-full, px-3 py-1, positioned at top-centre, slightly overlapping the card top edge)
- Header: "Pro" (text-lg, font-semibold)
- Price block: "£29" (text-4xl, font-bold) + "/month" (text-sm, text-secondary)
- Horizontal divider
- Intro line: "Everything in pay-as-you-go, plus:" (text-sm, text-secondary, italic)
- Features list (text-sm, each line with a teal checkmark icon):
  - Unlimited contract reviews
  - All contract types supported
  - Outlook & Gmail add-on access
  - Priority processing
  - Contract review history & dashboard
  - Team sharing & collaboration
- CTA button (full width): "Start 14-day free trial" — solid teal bg, white text, font-medium
- Subtext below button (text-xs, text-secondary, text-center): "Cancel anytime. No lock-in."

**Below pricing cards, a centred callout (mt-8, text-center):**
Paragraph in text-sm text-secondary: "A single missed liability clause can cost you £10,000+. This costs less than a sandwich."

---

## SECTION 5 — FAQ

**Background:** White.

**Section ID:** `id="faq"`

**Headline (h2, text-2xl font-bold, text-center):**
"Frequently asked questions"

**Layout:** Accordion-style FAQ, max-w-3xl mx-auto. Use vanilla JavaScript for expand/collapse. Each item is a bordered row. Clicking toggles the answer visibility and rotates a chevron icon.

Style: each FAQ item is a div with bottom border. Question row is flex with justify-between, py-4, cursor-pointer. Answer is hidden by default, shown with smooth max-height CSS transition when active.

**Q1: Is this legal advice?**
A: No. ContractShield is a risk assessment tool, not a law firm. We help you understand what's in your contracts and flag potential issues. We always recommend consulting a solicitor for high-stakes, unusual, or business-critical situations. Think of us as the first check — not the last word.

**Q2: How accurate is the AI?**
A: Our engine uses leading large language models with UK supply contract playbooks that check against specific legislation — UCTA, Late Payment of Commercial Debts Act, UK GDPR. It benchmarks every clause against standard commercial terms. No AI is perfect, which is why we give you a risk score and flag issues for your judgment — not a legal opinion.

**Q3: Is my contract data safe?**
A: Yes. Documents are encrypted in transit and at rest, processed in the UK, and deleted immediately after review. We never store your contracts. We never use them for AI training. Full GDPR compliance with zero data retention.

**Q4: What types of contracts can I review?**
A: We specialise in UK supply and vendor agreements — the most common and most commonly ignored contract type for SMEs. We also support service contracts, freelancer agreements, NDAs, SaaS terms, and commercial leases.

**Q5: How is this different from ChatGPT?**
A: ChatGPT gives you a conversation. We give you a structured risk report. Our tool proactively checks for missing clauses, scores every clause against UK benchmarks, and provides counter-language you can copy and send — without needing to know what questions to ask.

**Q6: Can I use this outside the UK?**
A: Our playbooks are currently built for English law (England & Wales). EU supply contract support is on our roadmap. Contact us if you need a different jurisdiction.

**Q7: Do I need to install anything?**
A: For the web app, no — just upload a file. For the Outlook or Gmail add-on, install a lightweight extension from the Microsoft or Google marketplace. Takes under a minute, no IT support needed.

**Q8: What happens after my 3 free reviews?**
A: Pay £3 per contract as you go, or upgrade to Pro at £29/month for unlimited reviews. Your card is saved securely via Stripe — every review after that is one click.

---

## SECTION 6 — Final CTA

**Background:** `bg-[#0F6E56]` (solid teal), all text white.

**Layout:** Centred text block, compact vertical padding (py-16 md:py-20).

**Headline (h2, text-2xl md:text-3xl, font-bold, text-white, text-center):**
"Your next contract could cost you £10,000 — or £3."

**Subheadline (text-white/80, text-center, max-w-xl, mx-auto, mt-4):**
"Review it before you sign. Your first three contracts are free."

**CTA button (centred, mt-6):**
"Review your first contract free" — white bg, text-[#0F6E56], rounded-lg, px-8 py-4, font-semibold, text-lg, hover shadow

**Trust line (text-white/60, text-sm, text-center, mt-4):**
"No sign-up · No credit card · GDPR compliant · 2-minute review"

---

## SECTION 7 — Footer

**Background:** `bg-[#1a1a1a]`, text gray-400 for links, text gray-300 for headings.

**Layout:** 4-column grid on desktop (lg:grid-cols-4), 2-column on tablet (sm:grid-cols-2), single column on mobile. Padding py-12 px-6.

**Column 1 — Brand:**
- ContractShield logo (shield icon + text, white)
- One-liner (text-sm, text-gray-500): "AI contract risk review for UK small businesses."
- Social icons row (mt-4): LinkedIn, X/Twitter — small SVG icons, text-gray-500, hover text-white

**Column 2 — Product:**
- Column heading (text-sm, font-semibold, text-gray-300, uppercase tracking-wider, mb-3): "Product"
- Links (text-sm, text-gray-500, hover text-white, block, mb-2 each):
  - How it works
  - Integrations
  - Pricing
  - Risk report example
  - API access

**Column 3 — Resources:**
- Column heading: "Resources"
- Links:
  - Blog
  - UK supply contract guide
  - Late payment rights
  - FAQ
  - Help centre

**Column 4 — Legal:**
- Column heading: "Legal"
- Links:
  - Terms of service
  - Privacy policy
  - Cookie policy
  - Refund policy
  - Contact

**Bottom bar** (border-t border-gray-800, mt-8, pt-6, flex justify-between items-center, flex-wrap, gap-4):
- Left: "© 2026 ContractShield Ltd. Registered in England & Wales." (text-xs, text-gray-600)
- Right: "ContractShield is a risk assessment tool, not a law firm. This is not legal advice." (text-xs, text-gray-600)

---

## Technical notes for v0

- Output plain HTML with Tailwind CSS utility classes
- Do not use React, Vue, or any JS framework
- Use semantic HTML: `<nav>`, `<main>`, `<section>`, `<footer>`, `<article>`
- Add `id` attributes to all sections for smooth-scroll navigation
- Add `scroll-behavior: smooth` to the html element
- FAQ accordion: vanilla JS with `classList.toggle`, CSS `max-height` transition
- Mobile hamburger menu: vanilla JS toggle for showing/hiding nav links
- All CTA `href` values should be `"#"` as placeholders
- The hero product mockup must be built entirely in HTML/CSS — no image files
- Comparison table: wrap in `overflow-x-auto` div for mobile horizontal scrolling
- Import DM Sans from Google Fonts in the head
- Ensure accessible contrast ratios on all text
- Use `loading="lazy"` on any images below the fold
- Total page should feel cohesive and professional, like a real product landing page from a funded startup

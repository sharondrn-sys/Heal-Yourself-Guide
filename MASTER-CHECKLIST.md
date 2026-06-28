# Heal Yourself — Master Page Checklist
*Single source of truth. Reconciled from v4, unnamed June 2026, and Full Audit versions.*
*Updated: June 2026 — post Session 11 (Fix #5 inline iHerb links)*

---

## CANONICAL RULES (Never Override)

1. **Footer:** ft-inner CSS classes — NOT inline styles
2. **html element:** `overflow-x:hidden` FORBIDDEN — breaks position:sticky site-wide. Body only.
3. **Print functions:** String concatenation only — never backticks/template literals
4. **jump-nav-inner:** `min-width:0` — never `max-content`
5. **Footer nav tag:** `<div>` — never `<nav>`
6. **Citations JS:** Must go AFTER any template literals containing `</body></html>`
7. **Nav order (non-negotiable):** Home · Before You Begin · Protocols ▾ · Research · About
8. **dd-subs:** `position:absolute;left:100%;top:0` side panel — never inline expand (causes cursor jump)
9. **iHerb links:** `www.iherb.com` only — never `il.iherb.com`
10. **Language:** "reverse" / "heal" — never "cure". "may improve" — never "proven" or "cures"
11. **Sticky nav bars — every page with sections must have one:** Protocol pages use `.phase-nav` or `.jump-nav` with `position:sticky;top:var(--nav-h);z-index:90`. Subpages use `.jump-nav` with the same. Never `top:56px` — always `top:var(--nav-h)`.
12. **Part A / Part B banners must be sticky:** Both banners use `position:sticky;top:var(--nav-h);z-index:91` so the reader always knows which part they're in.
13. **Sticky context button (protocol pages):** `position:fixed` — must be at body level, never nested inside a `position:sticky` or `position:relative` ancestor. Observes the first non-sticky section inside Part B via scroll event (not IntersectionObserver). Both the floating button AND the companion bar "Jump to:" button must be wired to the same `setPartA()`/`setPartB()` functions.
14. **`toggleMobileNav()` JS insertion rule:** Must go AFTER any print popup `document.write()` strings that contain `</body></html>`. If placed before, the function lands inside the string and is never callable. Always verify with: search for `'<script>\nfunction toggleMobileNav'` — if found, the function is trapped.
11. **Never pull from GitHub without explicit session authorization from Sharona**
12. **Div balance check after every change:** `<div` count must equal `</div` count

---

## A. HEAD / SEO (Every Page)

- [ ] `<title>` — unique, keyword-rich, under 60 chars: "Topic — Subtopic | Heal Yourself"
- [ ] `<meta name="description">` — unique, 150–160 chars, primary keyword
- [ ] `<link rel="canonical">` — correct full URL
- [ ] `<meta property="og:title">`
- [ ] `<meta property="og:description">` — 1–2 sentences, emotional hook
- [ ] `<meta property="og:url">` — canonical URL
- [ ] `<meta property="og:type">` — "website" for index, "article" for all others
- [ ] `<meta property="og:site_name">` — "Heal Yourself Guide"
- [ ] `<meta name="twitter:card">` — "summary"
- [ ] `<meta name="twitter:title">`
- [ ] `<meta name="twitter:description">`
- [ ] `<script type="application/ld+json">` — Article or MedicalWebPage schema

---

## B. NAVIGATION (Every Page)

- [ ] Nav order: Home · Before You Begin · Protocols ▾ · Research · About
- [ ] Logo left, links to index.html, SVG sun 28px inline, font-size 22px
- [ ] `toggleNavDropdown()` JS present
- [ ] Dropdown closes on outside click (document click listener)
- [ ] Mobile hamburger — slides from right, 260px, overlay
- [ ] `nav-hamburger` / `navHamburger` id present
- [ ] `nav-overlay` present
- [ ] Skip-to-content link present (`class="skip-link"`)
- [ ] Dropdown dd-subs use side panel CSS (not inline)
- [ ] All emoji in nav marked `aria-hidden="true"`

### Protocols Dropdown Contents (canonical):
- 🌿 Full Body Detox → Start Here tag + Daily Schedule + Shopping List
- 🧠 Brain Protocol + Daily Schedule + Shopping List
- ⚗️ DMSO Protocol + Daily Schedule + Shopping List
- 🫁 Oxygen Therapy + H2O2 + Ozone + Hyperbaric anchors
- 🔬 Hidden Deficiencies + Daily Schedule + Shopping List
- 🌱 Dr. Sebi Alkaline + Daily Schedule + Shopping List
- 🧬 Parkinson's Protocol + Daily Schedule + Shopping List + Must-Have + Symptom Guide
- ☰ All Protocols (separator line above, links to protocols.html)

---

## C. SHARE BUTTONS (Every Page)

- [ ] Floating share bar — left side desktop, bottom bar mobile (768px breakpoint)
- [ ] Float bar: WhatsApp pill (#25D366) + Facebook pill (#1877F2)
- [ ] Float bar hidden on print
- [ ] Bottom share block above email signup — "Know someone who needs this?"
- [ ] Bottom block: WhatsApp + Facebook buttons with labels
- [ ] Share JS uses `window.location.href` — NOT hardcoded URL
- [ ] `sf-wa` + `sf-fb` IDs on float bar; `wa-share-btn` + `fb-share-btn` on bottom block

---

## D. EMAIL SIGNUP (Every Page)

- [ ] `<script id="mcjs">` present — exactly once
- [ ] Email input + submit button
- [ ] Unique input ID per page (e.g. `mc-email-detox`)
- [ ] Submit validates email format
- [ ] Success message on submit
- [ ] "Free · No spam · Unsubscribe anytime" note

### Page order (bottom of every page):
1. Companion links block (protocol pages)
2. Share block
3. Email signup
4. Footer

---

## E. IHERB AFFILIATE (Protocol + Shopping Pages)

- [ ] Every purchasable supplement links to iHerb with `?rcode=GUW6132`
- [ ] iHerb support block with code GUW6132 prominently displayed
- [ ] iHerb button → `https://www.iherb.com/?rcode=GUW6132`
- [ ] Wording (exact): "new customers save 10%, returning customers save 5%"
- [ ] No supplement without iHerb link OR explicit "free / grow it / avoid" label
- [ ] No iHerb banner (permanently removed)
- [ ] N/A for: index, about, research, protocols, privacy-policy, terms-of-service, 404

---

## F. MEDICAL DISCLAIMER (Every Page)

- [ ] Visible callout box in page body — NOT only in footer
- [ ] Above first actionable content on protocol pages
- [ ] Covers: pregnant/breastfeeding, under 18, cancer treatment, kidney disease, drug interactions
- [ ] Parkinson's pages: specific Levodopa/Mucuna warning
- [ ] Footer short disclaimer also present

---

## G. PART A / PART B (Protocol Main Pages Only)

- [ ] Part A banner (sage green) — `id="part-a"`
- [ ] Part A sticky jump nav — `justify-content:center`, `min-width:0`
- [ ] Part B banner (terracotta) — `id="part-b"`
- [ ] Part B companion links block immediately after banner (📋 Daily + 🛒 Shopping)
- [ ] Part B sticky jump nav
- [ ] **Sticky floating button** — `class="sticky-partb"` — allows jumping between Part A and Part B
- [ ] "← Part A" / "Part B →" links use inline style — NOT `pn-home` class

---

## H. CITATIONS (Content Pages)

- [ ] Superscript citations: `<sup class="cite">` with `onclick="openCitations(N)"`
- [ ] Citations drawer: `id="citations-drawer"` — fixed bottom, slides up
- [ ] Citations overlay: `id="citations-overlay"` — click to close
- [ ] Each citation has `id="cite-N"`
- [ ] Active citation gets `.cite-active` highlight
- [ ] "View Full Research Library →" link → `research.html`
- [ ] `openCitations()` and `closeCitations()` JS present
- [ ] JS inserted AFTER any print popup template literals
- [ ] N/A for: daily schedules, shopping lists, 404, privacy-policy, terms-of-service

---

## I. FOOTER (Every Page)

- [ ] Uses `ft-inner` CSS class structure
- [ ] Left column: brand name + disclaimer text + © 2026
- [ ] Right column: Home · Before You Begin · All Protocols · Research · About · Privacy Policy · Terms of Use · Contact
- [ ] Contact: `mailto:healyourselfguide101@gmail.com`
- [ ] `footer{background:var(--bg-footer);padding:40px 24px;}`
- [ ] Current page link gets active style
- [ ] Footer uses `<div>` not `<nav>`

---

## J. TECHNICAL (Every Page)

- [ ] Div balance: `<div` count == `</div` count
- [ ] `html{}` does NOT have `overflow-x:hidden`
- [ ] `body{}` has `overflow-x:hidden`
- [ ] `section[id]` has `scroll-margin-top` for sticky nav offset
- [ ] No duplicate mcjs script tags
- [ ] Print styles hide nav, share, footer, buttons
- [ ] `lang="en"` on `<html>` tag
- [ ] `aria-label` on floating share bar
- [ ] No dead internal links
- [ ] Page loads without console errors

---

## K. DESIGN SYSTEM (Every Page)

```css
--bg:#f4efe6; --bg-warm:#faf7f2; --bg-deep:#ede7db;
--bg-stone:#e5dfd4; --bg-nav:#2c3a2e; --bg-footer:#263028;
--ink:#1e1a14; --ink-mid:#3d3426; --ink-light:#5c5144;
--sage:#3d6b4a; --sage-mid:#5a8c6a; --sage-light:#7aac8a;
--sage-pale:#e4f0e8; --sage-nav:#8ab89a;
--terra:#8c5a3c; --terra-light:#b07a58; --terra-pale:#f5ede6;
--honey:#a07830; --honey-pale:#f5eddb;
```

- [ ] Nav alpha: 0.80 (not 0.65)
- [ ] ink-light: #5c5144 (not #7a6e5c)
- [ ] Fonts: Playfair Display · Jost · DM Mono
- [ ] Nav logo font-size: 22px

---

## PAGE STATUS — Post Session 10 Audit

| Page | Head | Nav | Share | Email | iHerb | Disclaim | Footer | PartAB | Sticky | Citations | DivBal | Done |
|------|------|-----|-------|-------|-------|----------|--------|--------|--------|-----------|--------|------|
| index.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| before-you-begin.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | ⚠️ |
| Full_Body_Detox_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Full_Body_Detox_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Full_Body_Detox_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Brain_Protocol.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ⚠️ |
| Brain_Protocol_Daily_Schedule.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Brain_Protocol_Shopping_List.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ❌+2 | ❌ |
| DMSO_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| DMSO_Daily_Schedule.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| DMSO_Shopping_List.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Oxygen_Therapy.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Hidden_Deficiencies.html | ✅ | ✅ | ❌ float | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ |
| Hidden_Deficiencies_Daily_Schedule.html | ⚠️ schema | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Hidden_Deficiencies_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Dr_Sebi_Alkaline_Protocol.html | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ |
| Dr_Sebi_Alkaline_Protocol_Daily_Schedule.html | ⚠️ schema | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | ⚠️ |
| Dr_Sebi_Alkaline_Protocol_Shopping_List.html | ⚠️ schema | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | ⚠️ |
| Parkinsons_Protocol.html | ✅ | ✅ | ✅ | ✅ | ❌ inline | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ |
| Parkinsons_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Parkinsons_Shopping_Table.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Parkinsons_Must_Have.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| Parkinsons_Symptoms.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| protocols.html | ❌ canon/schema | ✅ | ❌ both | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ❌ |
| research.html | ❌ canon/schema | ✅ | ❌ both | ✅ | ❌ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | ❌ |
| about.html | ⚠️ schema | ✅ | ❌ bottom | ✅ | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| privacy-policy.html | ❌ og/schema | ✅ | ❌ both | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ⚠️ |
| terms-of-service.html | ❌ canon/schema | ✅ | ❌ both | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ⚠️ |
| 404.html | ❌ canon/schema | ✅ | ❌ both | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ⚠️ |

---

## OPEN ISSUES — Priority Order

### 🔴 Fix immediately (structural/functional)
1. **Brain_Protocol_Shopping_List.html** — div imbalance (+2)
2. **Brain_Protocol.html** — sticky Part B button missing
3. **Hidden_Deficiencies.html** — floating share bar missing

### 🟡 Batch-fixable (mechanical, low risk)
4. **JSON-LD schema** — missing on 18 pages (all except Full Body Detox, DMSO, Oxygen, Hidden Def, Dr Sebi main, Parkinson's main + subpages)
5. **Canonical/OG URL tags** — missing on protocols.html, research.html, terms-of-service.html, 404.html
6. **Share bars** — missing float bar and/or bottom block on: protocols.html, research.html, about.html, privacy-policy.html, terms-of-service.html, 404.html
7. **Email signup (mcjs)** — missing on Dr_Sebi_Alkaline_Protocol.html + both subpages
8. **iHerb** — missing on Dr_Sebi_Alkaline_Protocol_Daily_Schedule.html

### ✅ Completed this session (Fix #5 — inline iHerb links)
- Full_Body_Detox_Protocol.html — 4 new inline links
- Brain_Protocol.html — 20 new inline links  
- Dr_Sebi_Alkaline_Protocol.html — 13 new inline links
- Oxygen_Therapy.html — 1 new inline link
- DMSO_Protocol.html — 6 new inline links
- **HELD** Parkinsons_Protocol.html + Hidden_Deficiencies.html — safety review required before Fix #5

### 🔵 Requires content work (cannot batch)
9. **Citations** — missing drawer on all daily schedules, shopping lists, and several main pages
10. **Search function** — documented in Full Audit as ❌ NOT DONE; implementation TBD
11. **Breadcrumbs** — documented in Full Audit as ❌ NOT DONE

### ⚠️ Safety-flagged (do not touch content without Safety Review Log)
- DMSO_Oxygen_Therapy.html — orphaned, dosing content review pending
- Hidden_Deficiencies pages — supplement-drug interaction screening
- Parkinson's pages — full audit review pending
- Affiliate-link + disease-claim pattern — legal review before scaling traffic

---

## DEFERRED / STRATEGIC (Not This Session)
- No search — implementation not agreed. Was in Full Audit as future work only.
- No breadcrumbs — same.
- Lead magnet / testimonials / social proof — editorial, Sharona's call
- Make.com Facebook/Instagram auto-posting — pending setup
- YouTube channel setup

---
*This file lives in the repo root. Update the PAGE STATUS table after every session.*
*Run the audit script before every push to catch regressions.*

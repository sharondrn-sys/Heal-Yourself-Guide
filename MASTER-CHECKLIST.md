# Heal Yourself — Master Page Checklist
*Single source of truth.*
*Updated: June 2026 — post Session 12. Live audit run against actual repo.*

---

## CANONICAL RULES (Never Override)

1. **Footer:** `ft-inner` CSS classes — NOT inline styles
2. **html element:** `overflow-x:hidden` FORBIDDEN — breaks `position:sticky` site-wide. Body only.
3. **Print functions:** String concatenation only — never backticks/template literals
4. **jump-nav-inner:** `min-width:0` — never `max-content`
5. **Footer nav tag:** `<div>` — never `<nav>`
6. **Citations JS:** Must go AFTER any template literals containing `</body></html>`
7. **Nav order (non-negotiable):** Home · Before You Begin · Protocols ▾ · Research · About
8. **dd-subs:** `position:absolute;left:100%;top:0` side panel — never inline expand (causes cursor jump)
9. **iHerb links:** `www.iherb.com` only — never `il.iherb.com`
10. **Language:** "reverse" / "heal" — never "cure". "may improve" — never "proven" or "cures"
11. **Sticky nav bars:** Protocol pages use `.phase-nav` or `.jump-nav` with `position:sticky;top:var(--nav-h);z-index:90`. Never `top:56px` — always `top:var(--nav-h)`.
12. **Part A / Part B banners must be sticky:** Both use `position:sticky;top:var(--nav-h);z-index:91`
13. **Sticky context button:** `position:fixed` — must be at body level, never inside a `position:sticky` or `position:relative` ancestor. Uses scroll event (not IntersectionObserver).
14. **`toggleMobileNav()` insertion rule:** Must go AFTER any print popup `document.write()` strings containing `</body></html>`. If placed before, the function is trapped inside the string.
15. **Never pull from GitHub without explicit session authorization from Sharona**
16. **Div balance check after every change:** `<div` count must equal `</div` count (strip `<script>` blocks before counting)

---

## PAGE STATUS — Live Audit (Session 12)

| Page | Head | Nav | Share | Email | iHerb | Disclaim | Footer | PartAB | Sticky | Cite | DivBal | **Done** |
|------|------|-----|-------|-------|-------|----------|--------|--------|--------|------|--------|----------|
| index.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| before-you-begin.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | ✅ | ✅ | ✅ |
| about.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| protocols.html | ✅ | ✅ | ✅ | ✅ | N/A | ❌ | ✅ | N/A | N/A | ❌ | ✅ | ❌ |
| research.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |
| privacy-policy.html | ✅ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| terms-of-service.html | ✅ | ✅ | ✅ | N/A | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| 404.html | ✅ | ✅ | ✅ | N/A | N/A | ❌ | ✅ | N/A | N/A | N/A | ✅ | ❌ |
| Full_Body_Detox_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Full_Body_Detox_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | N/A | ❌ | ❌ | N/A | N/A | N/A | ✅ | ❌ |
| Full_Body_Detox_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Brain_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Brain_Protocol_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Brain_Protocol_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| DMSO_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| DMSO_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| DMSO_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Oxygen_Therapy.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Hidden_Deficiencies.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Hidden_Deficiencies_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Hidden_Deficiencies_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | N/A | N/A | N/A | ✅ | ❌ |
| Dr_Sebi_Alkaline_Protocol.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Dr_Sebi_Alkaline_Protocol_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Dr_Sebi_Alkaline_Protocol_Shopping_List.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Parkinsons_Protocol.html | ✅ | ✅ | ✅ | ✅ | ⏸ hold | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ⚠️ |
| Parkinsons_Daily_Schedule.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Parkinsons_Shopping_Table.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Parkinsons_Must_Have.html | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | N/A | N/A | N/A | ✅ | ✅ |
| Parkinsons_Symptoms.html | ✅ | ✅ | ✅ | ✅ | N/A | ✅ | ✅ | N/A | N/A | ❌ | ✅ | ⚠️ |

**Key:** ✅ done · ❌ missing · ⚠️ partial · ⏸ on hold · N/A not applicable

---

## OPEN ISSUES — Prioritised

### 🔴 Fix immediately

| # | Page | Issue |
|---|------|-------|
| 1 | `Full_Body_Detox_Daily_Schedule.html` | Disclaimer missing · Footer structure broken |
| 2 | `Hidden_Deficiencies_Shopping_List.html` | Footer structure broken (`ft-inner` / `ft-nav` missing) |
| 3 | `protocols.html` | Disclaimer missing |
| 4 | `404.html` | Disclaimer missing |

### 🟡 Fix next (content / citations)

| # | Page | Issue |
|---|------|-------|
| 5 | `index.html` | Citations drawer missing |
| 6 | `about.html` | Citations drawer missing |
| 7 | `protocols.html` | Citations drawer missing |
| 8 | `research.html` | Citations drawer missing |
| 9 | `Parkinsons_Symptoms.html` | Citations drawer missing |

### ⏸ On hold — safety review required before touching

| Page | Hold reason |
|------|-------------|
| `Parkinsons_Protocol.html` | iHerb inline links (Fix #5) — safety review pending |
| `Hidden_Deficiencies.html` | iHerb inline links (Fix #5) — supplement-drug interaction screening pending |
| `DMSO_Oxygen_Therapy.html` | Orphaned — full content/dosing safety review pending. Do NOT link in nav or include in batch ops. |

---

## UX BRIEF BACKLOG — Fixes 1–9 (HealYourselfGuide_UX_Brief.md)

All fixes from the brief. None started yet unless noted.

### Fix #1 — Simplify Global Navigation
**All HTML pages** · Medium priority · Low effort
- Replace protocol dropdown in nav with flat: `Home · Start Here · Protocols · About`
- `Protocols` links to `protocols.html` (discovery page) — dropdown removed entirely
- Mobile hamburger mirrors same 4 items
- Research link moves to footer only
- **Status: ❌ Not started**

### Fix #2 — Homepage Entry Selector ("Where do you need to start?")
**`index.html`** · Very High priority · Medium effort
- Add section directly below hero with 3 condition buttons:
  - 🧬 Parkinson's Disease → `start-here-parkinsons.html`
  - 🧠 Brain Fog & Cognitive Decline → `start-here-brain.html`
  - 🌿 I Just Feel Off — General Detox → `start-here-general.html`
- Below buttons: "Not sure? Start with Before You Begin →"
- Depends on Fixes #7, #8, #9 (pages must exist first)
- **Status: ❌ Not started**

### Fix #3 — Flip Part A / Part B on All Protocol Pages
**All protocol main pages** · Very High priority · Low-Medium effort
- Make Part B the default visible section (appears first)
- Move Part A below Part B
- Make Part A collapsible (`<details>`/`<summary>`) — collapsed by default
- Update hero CTA buttons: primary = Part B, secondary = Part A
- Affected: Full_Body_Detox_Protocol, Brain_Protocol, Parkinsons_Protocol, DMSO_Protocol, Oxygen_Therapy, Hidden_Deficiencies, Dr_Sebi_Alkaline_Protocol
- **Status: ❌ Not started**

### Fix #4 — Promote Daily Schedule as Primary CTA on Protocol Pages
**All protocol main pages** · High priority · Low effort
- Add CTA block at top of Part B (before first protocol step):
  `📋 View Your Daily Schedule →` + `🛒 Shopping List →`
- Styled as sage green border / linen background box
- On Daily Schedule pages: add visible `← Back to Full Protocol` link at top
- **Status: ❌ Not started**

### Fix #5 — Inline iHerb Affiliate Links at First Mention
**All protocol main pages** · High priority · Medium effort (most error-prone)
- ✅ Full_Body_Detox_Protocol.html — done (+4 links)
- ✅ Brain_Protocol.html — done (+20 links)
- ✅ Dr_Sebi_Alkaline_Protocol.html — done (+13 links)
- ✅ Oxygen_Therapy.html — done (+1 link)
- ✅ DMSO_Protocol.html — done (+6 links)
- ⏸ Parkinsons_Protocol.html — safety review hold
- ⏸ Hidden_Deficiencies.html — safety review hold

### Fix #6 — Hide / Remove "Coming Soon" Foundations Section
**`index.html`** · Medium priority · Low effort
- Remove the 8-card "Foundations of Health" section entirely (preferred)
- Or replace "Coming Soon" with "In progress — join the list to be notified"
- **Status: ❌ Not started**

### Fix #7 — New Page: `start-here-parkinsons.html`
**New file** · High priority · Medium effort
- Emergency lane for Parkinson's diagnosis visitors
- Hero → honest truth section → 3-step path → free actions → daily schedule CTA → iHerb → share
- Mobile-first, WhatsApp-shareable
- ⚠️ Requires safety review before publishing (Parkinson's content)
- **Status: ❌ Not started**

### Fix #8 — New Page: `start-here-brain.html`
**New file** · High priority · Medium effort
- Entry page for brain fog / cognitive decline visitors
- Same structure as Fix #7
- **Status: ❌ Not started**

### Fix #9 — New Page: `start-here-general.html`
**New file** · High priority · Medium effort
- Entry page for visitors without a specific diagnosis
- Simpler: single starting point = Full Body Detox
- **Status: ❌ Not started**

---

## SITE BUILD BACKLOG (Pages Not Yet Built)

| Page | Status | Notes |
|------|--------|-------|
| `faq.html` | ❌ Not built | — |
| `sitemap.xml` | ❌ Not built | — |
| `robots.txt` | ❌ Not built | — |
| `start-here-parkinsons.html` | ❌ Not built | Fix #7 · Safety review required |
| `start-here-brain.html` | ❌ Not built | Fix #8 |
| `start-here-general.html` | ❌ Not built | Fix #9 |

---

## SAFETY REVIEW LOG

Pages that require a safety review entry before going live or receiving content changes:

| Page | Review status | Blocker |
|------|--------------|---------|
| `Parkinsons_Protocol.html` | ⏸ Pending | iHerb inline links; Levodopa/Mucuna interaction warning audit |
| `Hidden_Deficiencies.html` | ⏸ Pending | Supplement-drug interaction screening |
| `start-here-parkinsons.html` | ⏸ Pending | New page — full content review before publish |
| `DMSO_Oxygen_Therapy.html` | ⏸ Pending | Dosing content; keep orphaned from nav until cleared |

---

## DEFERRED / STRATEGIC

- Make.com Facebook/Instagram auto-posting — pending setup
- Search function — not agreed, future work
- Breadcrumbs — not agreed, future work
- Lead magnet / testimonials / social proof — editorial, Sharona's call
- YouTube channel setup

---

*This file is the single source of truth. Update PAGE STATUS after every session.*
*Run the live audit script before every push.*

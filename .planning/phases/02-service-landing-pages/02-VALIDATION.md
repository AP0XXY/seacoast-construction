---
phase: 2
slug: service-landing-pages
status: draft
nyquist_compliant: true
wave_0_complete: false
created: 2026-06-20
---

# Phase 2 — Validation Strategy

> Per-phase validation contract for feedback sampling during execution.

---

## Test Infrastructure

| Property | Value |
|----------|-------|
| **Framework** | Manual validation (static HTML site — no test runner) |
| **Config file** | none |
| **Quick run command** | Open HTML file in browser, visually inspect |
| **Full suite command** | Visual inspection of all 6 pages + Lighthouse audit |
| **Estimated runtime** | ~30 seconds per page |

---

## Sampling Rate

- **After every task commit:** Visual check of the modified page in browser
- **After every plan wave:** Check all modified pages render correctly
- **Before `/gsd:verify-work`:** Full suite must be green (all 6 pages load, nav works, forms functional)
- **Max feedback latency:** 30 seconds

---

## Per-Task Verification Map

| Task ID | Plan | Wave | Requirement | Threat Ref | Secure Behavior | Test Type | Automated Command | File Exists | Status |
|---------|------|------|-------------|------------|-----------------|-----------|-------------------|-------------|--------|
| 02-01-01 | 01 | 1 | ARCH-03, REST-01–06 | — | N/A | manual | `ls concrete-restoration.html` + visual check | ✅ W0 | ⬜ pending |
| 02-01-02 | 01 | 1 | WATR-01–04 | — | N/A | manual | `ls waterproofing.html` + visual check | ✅ W0 | ⬜ pending |
| 02-01-03 | 01 | 1 | STUC-01–04 | — | N/A | manual | `ls stucco-repair.html` + visual check | ✅ W0 | ⬜ pending |
| 02-02-01 | 02 | 1 | COAT-01–03 | — | N/A | manual | `ls protective-coatings.html` + visual check | ✅ W0 | ⬜ pending |
| 02-02-02 | 02 | 1 | BALC-01–03 | — | N/A | manual | `ls balcony-restoration.html` + visual check | ✅ W0 | ⬜ pending |
| 02-02-03 | 02 | 1 | PAIN-01–03 | — | N/A | manual | `ls painting.html` + visual check | ✅ W0 | ⬜ pending |

*Status: ⬜ pending · ✅ green · ❌ red · ⚠️ flaky*

---

## Wave 0 Requirements

- [x] No test framework needed — static HTML site, all validation is visual/manual
- [x] Browser available for visual testing

*Existing infrastructure covers all phase requirements.*

---

## Manual-Only Verifications

| Behavior | Requirement | Why Manual | Test Instructions |
|----------|-------------|------------|-------------------|
| Page renders correctly | REST-01 through PAIN-03 | Static HTML — no test runner | Open each HTML file in browser, verify layout matches UI-SPEC |
| Nav links work | ARCH-03 | Client-side links | Click each nav link, verify correct page loads |
| Form pre-selects service | CONTEXT D-16 | JavaScript behavior | Visit each service page, verify dropdown shows correct service |
| Responsive layout | UX-01 | Visual verification | Resize browser to 320px, 768px, 1024px, 1440px — verify layout adapts |
| Internal links work | SEO-05 | Client-side links | Click "Related Services" links on each page |
| Lighthouse 90+ | Phase 5 goal | Performance audit | Run `npx lighthouse <url>` if available, else manual check |

---

## Validation Sign-Off

- [x] All tasks have `<automated>` verify or manual verification commands
- [x] Sampling continuity: no 3 consecutive tasks without verification
- [x] Wave 0 covers all MISSING references
- [x] No watch-mode flags
- [x] Feedback latency < 30s
- [x] `nyquist_compliant: true` set in frontmatter

**Approval:** pending

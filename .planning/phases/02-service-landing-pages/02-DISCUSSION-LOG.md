# Phase 2: Service Landing Pages - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-06-20
**Phase:** 2-service-landing-pages
**Areas discussed:** Page structure, Content depth, Gallery approach, Internal linking (all via best practices — no user discussion)

---

## Page Structure & Sections

| Option | Description | Selected |
|--------|-------------|----------|
| Standardized template | Same section order for all 6 pages (Hero → Problem/Solution → Process → Benefits → Gallery → CTA) | ✓ |
| Flexible per service | Different sections per service based on content needs | |
| Minimal | Hero + content + CTA only, no gallery/process | |

**User's choice:** Claude discretion — applied SEO best practices (standardized structure)
**Notes:** Consistent section ordering helps search engines understand page patterns and improves crawl efficiency.

---

## Content Depth Per Service

| Option | Description | Selected |
|--------|-------------|----------|
| Equal depth | All 6 pages get identical section types, service-specific content | ✓ |
| Primary keyword priority | Concrete restoration page gets more content, others shorter | |
| Variable | Some services get more sections based on complexity | |

**User's choice:** Claude discretion — equal depth with slight primary keyword emphasis
**Notes:** Concrete restoration (primary keyword) gets ~150 extra words. All others equal length. Maintains consistent SEO crawl structure.

---

## Before/After Gallery Approach

| Option | Description | Selected |
|--------|-------------|----------|
| Static grid | 3-4 stock images in CSS grid, no JS | ✓ |
| Slider/carousel | Interactive image carousel with JS | |
| Lightbox | Click-to-expand gallery with modal | |

**User's choice:** Claude discretion — static grid (best practices)
**Notes:** Avoids JavaScript dependencies, keeps page fast (Lighthouse 90+ target), works on all devices. Stock images with `<!-- SWAP: -->` comments for future replacement.

---

## Internal Linking Strategy

| Option | Description | Selected |
|--------|-------------|----------|
| Related services section + contextual body links | 2-3 related services per page + 1-2 natural body links | ✓ |
| Footer only | Links only in shared footer (already exists) | |
| Exhaustive | Link to all 5 other services on every page | |

**User's choice:** Claude discretion — related services + contextual links
**Notes:** Footer links already cover all 6 pages from Phase 1. Adding a "Related Services" section per page creates topical clusters for SEO. Contextual body links where natural reinforce topic relationships.

---

## Claude's Discretion

- Specific copy for each service page's problem/solution and process sections
- Which 2-3 services to link as "Related" on each page
- Hero background image selection from Unsplash
- Exact meta description copy per page
- Spacing, padding, and responsive refinements
- Active nav link highlighting CSS

## Deferred Ideas

None — all decisions stayed within phase scope.

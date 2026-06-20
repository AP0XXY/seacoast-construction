# Phase 4: SEO Optimization & Schema - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-06-20
**Phase:** 4-SEO Optimization & Schema
**Areas discussed:** LocalBusiness Schema, Service Schema, Internal Linking Topology, Heading Hierarchy Audit, Keyword Placement

---

## LocalBusiness Schema

| Option | Description | Selected |
|--------|-------------|----------|
| ConcreteContractor (subclass) | Use @type: ConcreteContractor with full NAP, serviceArea, hours | ✓ |
| General LocalBusiness | Use @type: LocalBusiness with basic info only | |
| Organization | Use @type: Organization (less specific for local SEO) | |

**User's choice:** [auto] ConcreteContractor — most specific type for local SEO ranking
**Notes:** Includes name, address, phone, serviceArea, openingHours, priceRange, sameAs

---

## Service Schema

| Option | Description | Selected |
|--------|-------------|----------|
| @type: Service per page | Each service page gets its own Service schema with name, description, provider, areaServed | ✓ |
| @type: Product | Use Product type instead (less appropriate for service business) | |
| No schema on service pages | Only do LocalBusiness on homepage | |

**User's choice:** [auto] Service schema on all 6 service pages — required for rich snippets
**Notes:** Service name in schema matches H1 exactly for consistency

---

## Internal Linking Topology

| Option | Description | Selected |
|--------|-------------|----------|
| Hub-and-spoke | Concrete restoration = hub, all services link back + 2 related | ✓ |
| Flat network | Every page links to every other page equally | |
| Minimal | Only nav links, no body cross-links | |

**User's choice:** [auto] Hub-and-spoke — concrete restoration is the primary keyword, strongest topical authority signal
**Notes:** Phase 2 already started this with "Related Services" sections; verify bidirectional links

---

## Heading Hierarchy Audit

| Option | Description | Selected |
|--------|-------------|----------|
| Audit all 7 pages | Check H1→H2→H3 hierarchy, fix any issues, add keyword to H2s | ✓ |
| Service pages only | Only audit the 6 service pages | |
| Skip (already done) | Phase 2 handled headings | |

**User's choice:** [auto] Audit all 7 pages — ensure consistency and keyword placement in H2s
**Notes:** Primary keyword must appear in at least one H2 per service page

---

## Keyword Placement

| Option | Description | Selected |
|--------|-------------|----------|
| First 100 words + H2 + CTA | Ensure primary keyword in first 100 words, one H2, and conclusion | ✓ |
| First paragraph only | Only ensure keyword appears early in body copy | |
| Natural only | Don't force keyword placement, rely on Phase 2 content | |

**User's choice:** [auto] First 100 words + H2 + CTA — comprehensive keyword signal without over-optimization
**Notes:** Title tags and meta descriptions already set from Phase 2; verify character limits

---

## Claude's Discretion

- Exact LocalBusiness schema property values (address, hours, phone) — use reasonable SE Florida contractor data
- Which body text links to add and exact anchor text per page
- Specific heading text adjustments for keyword inclusion
- Order of implementation across the 7 files

## Deferred Ideas

None — discussion stayed within phase scope

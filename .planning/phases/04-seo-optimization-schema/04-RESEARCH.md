# Phase 4: SEO Optimization & Schema — Research

## Summary

Phase 4 addresses schema markup, heading hierarchy, keyword placement, and internal linking across all 7 HTML files. The codebase already has a partial LocalBusiness schema on the homepage (incomplete), title tags and meta descriptions set in Phase 2, and a "Related Services" section on each service page. Service pages have NO schema markup. Internal linking from body text is partially implemented on some pages. This phase is mostly additive — insert schema blocks, audit headings, tweak body copy for keyword placement, and strengthen internal links.

## Technical Landscape

### Schema Markup (JSON-LD)
- Google recommends `application/ld+json` in `<head>` for structured data
- **LocalBusiness** schema (homepage): `@type: ConcreteContractor` subclass requires: `name`, `telephone`, `address` (with `streetAddress`, `addressLocality`, `addressRegion`, `postalCode`), `areaServed`, `openingHours`, `priceRange`, `sameAs`
- **Service** schema (6 pages): `name`, `description`, `provider` (organization ref), `areaServed`, `serviceType`
- Google Rich Results Test validates schema before deployment

### Heading Hierarchy
- Every page must have exactly one `<h1>` — already correct across all 7 files
- H2 sections must nest H3 subsections — no skipped levels — already correct
- Primary keyword should appear in at least one H2 per service page — needs audit

### Keyword Placement (SEO best practices)
- Primary keyword in first 100 words of body copy
- Primary keyword in at least one H2 heading
- Natural inclusion in conclusion/CTA section
- Title tag under 60 chars, meta description under 160 chars

### Internal Linking Topology
- Hub-and-spoke model: concrete restoration = hub, all services link back
- Each service links to 2 related services
- Contextual body text links where natural

## Existing Patterns

### Schema Markup
- `index.html:9-25` — **Partial LocalBusiness schema** exists but is incomplete:
  - Missing: `@type` is `LocalBusiness` but should be `ConcreteContractor`
  - Missing: `streetAddress`, `postalCode`, `openingHours`, `sameAs`, `url`
  - Has: `name`, `telephone`, `email`, `address.region`, `address.locality`, `areaServed`, `priceRange`
- **Service pages have NO schema markup** — all 6 need `Service` schema added to `<head>`

### Title Tags & Meta Descriptions (Phase 2 ✓)
- All 7 pages have unique `<title>` tags — verify under 60 chars:
  - `index.html:6` — "Concrete Restoration South Florida | Seacoast Construction" (57 chars ✓)
  - `concrete-restoration.html:6` — Same title as homepage (57 chars — DUPLICATE, needs differentiation)
  - `waterproofing.html:6` — "Waterproofing South Florida | Seacoast Construction" (51 chars ✓)
  - `stucco-repair.html:6` — "Stucco Repair South Florida | Seacoast Construction" (51 chars ✓)
  - `protective-coatings.html:6` — "Protective Coatings South Florida | Seacoast Construction" (56 chars ✓)
  - `balcony-restoration.html:6` — "Balcony Restoration South Florida | Seacoast Construction" (57 chars ✓)
  - `painting.html:6` — "Painting Services South Florida | Seacoast Construction" (55 chars ✓)
- All 7 pages have `<meta name="description">` — verify under 160 chars

### Heading Hierarchy (Audit Results)
- **Homepage**: H1 → H2 (services, why choose, portfolio, testimonials, contact) → H3 (service cards, stats) ✓
- **All 6 service pages**: H1 → H2 (why X matters, process, benefits, before/after, related, contact) → H3 (solution, process steps, benefit items) ✓
- All pages have single H1 ✓
- No heading level skipping detected ✓

### Internal Linking
- **Related Services sections** exist on all 6 service pages — links are text-only `<a>` tags in `.related-grid`
- **Contextual body text links** exist on some pages:
  - `concrete-restoration.html:599` — links to waterproofing and protective-coatings ✓
  - `waterproofing.html:599` — links to concrete-restoration and balcony-restoration ✓
  - `stucco-repair.html:599` — links to concrete-restoration and painting ✓
  - `protective-coatings.html` — needs audit for body text links
  - `balcony-restoration.html` — needs audit for body text links
  - `painting.html` — needs audit for body text links

### Internal Link Topology Map
| Page | Related Services Links | Body Text Links |
|------|----------------------|-----------------|
| concrete-restoration | waterproofing, protective-coatings, stucco-repair | waterproofing, protective-coatings |
| waterproofing | concrete-restoration, balcony-restoration, protective-coatings | concrete-restoration, balcony-restoration |
| stucco-repair | concrete-restoration, painting, protective-coatings | concrete-restoration, painting |
| protective-coatings | concrete-restoration, waterproofing, stucco-repair | (needs audit) |
| balcony-restoration | waterproofing, concrete-restoration, protective-coatings | (needs audit) |
| painting | stucco-repair, protective-coatings, waterproofing | (needs audit) |

## Risks & Open Questions

1. **Duplicate title tag**: `index.html` and `concrete-restoration.html` share the same title "Concrete Restoration South Florida | Seacoast Construction" — the concrete-restoration page should have a unique title or the homepage title should differentiate. D-18 says title tags are already set, but this duplication hurts SEO.

2. **Incomplete homepage schema**: The existing `LocalBusiness` schema is missing critical properties Google requires for rich results (streetAddress, postalCode, openingHours). Using `ConcreteContractor` as `@type` is more specific and better for local SEO.

3. **No service schema on any page**: All 6 service pages need `Service` schema added — this is the biggest gap.

4. **First-100-word keyword placement**: The hero paragraph on service pages does NOT include "concrete restoration south florida" — it uses service-specific language. This is correct for those pages, but the primary keyword needs natural inclusion in body copy somewhere on each page per D-15/D-16.

5. **Keyword in H2s**: Need to audit whether each service page has the primary keyword in at least one H2 (D-13/D-16). Current H2s use service-specific language like "Why Waterproofing Matters" — may need adjustment.

6. **Schema validation**: After adding schema, should validate with Google's Rich Results Test to ensure no errors.

7. **No new files needed**: All changes are modifications to existing 7 HTML files — confirmed.

## Recommendations

### 1. Fix Homepage Schema (`index.html:9-25`)
Replace incomplete LocalBusiness schema with full `ConcreteContractor` schema:
- Add `@type: ConcreteContractor`
- Add `url`, `streetAddress`, `postalCode`, `openingHours`, `sameAs`
- Keep existing `name`, `telephone`, `email`, `areaServed`, `priceRange`

### 2. Add Service Schema to All 6 Service Pages
Insert `<script type="application/ld+json">` block in `<head>` of each page:
- `name` must match H1 exactly
- `description` must match meta description
- `provider` references Seacoast Construction
- `areaServed` = ["Miami-Dade County", "Broward County", "Palm Beach County"]
- `serviceType` = service-specific (e.g., "Concrete Restoration", "Waterproofing")

### 3. Fix Duplicate Title Tag
`concrete-restoration.html:6` needs a unique title — differentiate from homepage (e.g., "Concrete Restoration Services South Florida | Seacoast Construction")

### 4. Keyword Placement in H2s
Add primary keyword to at least one H2 per service page. Options:
- Rename existing H2 (e.g., "Why Waterproofing Matters" → "Concrete Restoration & Waterproofing in South Florida")
- Add a new H2 section if renaming disrupts flow

### 5. Strengthen Internal Links
- Verify all 6 service pages have contextual body text links (protective-coatings, balcony-restoration, painting may be missing)
- Ensure concrete-restoration.html links to all 6 services from body text (currently only links to waterproofing and protective-coatings)

### 6. Validate Schema
After implementation, use Google's Rich Results Test to validate all schema blocks.

## Validation Architecture

### Schema Validation
1. Validate each page's schema using Google's Rich Results Test (search.google.com/test/rich-results)
2. Verify `name` in Service schema matches H1 exactly
3. Verify `description` in Service schema matches meta description
4. Verify all required properties are present for ConcreteContractor and Service types

### Heading Hierarchy Validation
1. Automated check: grep for `<h1>`, `<h2>`, `<h3>` tags in each file
2. Confirm exactly one `<h1>` per page
3. Confirm no heading levels are skipped (no H3 without preceding H2)
4. Confirm primary keyword appears in at least one H2 per service page

### Keyword Placement Validation
1. Check first 100 words of body copy (after `<body>`) for primary keyword
2. Check title tag length (under 60 chars)
3. Check meta description length (under 160 chars)
4. Verify keyword appears in conclusion/CTA section

### Internal Link Validation
1. Verify every service page links back to concrete-restoration.html (hub)
2. Verify each service page links to 2+ related services
3. Verify contextual body text links exist on all service pages
4. Check for broken links (all href targets exist)

### Requirements Coverage
| Requirement | What to Verify | Files |
|-------------|----------------|-------|
| SEO-01 | Unique title tags, under 60 chars | All 7 |
| SEO-02 | Meta descriptions, under 160 chars | All 7 |
| SEO-03 | H1→H2→H3 hierarchy, single H1 | All 7 |
| SEO-04 | LocalBusiness schema on homepage | index.html |
| SEO-05 | Internal linking (hub + related) | All 7 |
| SEO-06 | Image alt text with keywords | All 7 |

---

*Research compiled: 2026-06-20*
*Phase: 4-SEO Optimization & Schema*

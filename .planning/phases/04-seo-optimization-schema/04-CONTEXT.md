# Phase 4: SEO Optimization & Schema - Context

**Gathered:** 2026-06-20
**Status:** Ready for planning

<domain>
## Phase Boundary

Technical SEO audit, schema markup, internal linking optimization, and keyword placement across all 7 pages. This phase ensures the site's technical SEO foundation is solid — structured data for rich snippets, consistent heading hierarchy, keyword-optimized headings/body copy, and a cohesive internal linking topology that establishes concrete restoration as the topical hub.

</domain>

<decisions>
## Implementation Decisions

### LocalBusiness Schema (Homepage)
- **D-01:** Homepage gets `@type: ConcreteContractor` (subclass of LocalBusiness) schema in a `<script type="application/ld+json">` block in `<head>`
- **D-02:** Schema includes: name ("Seacoast Construction"), url, telephone, address (streetAddress, addressLocality, addressRegion, postalCode), serviceArea (array: Miami-Dade, Broward, Palm Beach), openingHours, priceRange, sameAs (placeholder for social profiles)
- **D-03:** Use Google's structured data documentation as the reference — follow their recommended properties for local businesses

### Service Schema (Service Pages)
- **D-04:** Each of the 6 service pages gets `@type: Service` schema in a `<script type="application/ld+json">` block in `<head>`
- **D-05:** Service schema includes: name (matching the H1 exactly), description (matching the meta description), provider (reference to Seacoast Construction), areaServed (array: Miami-Dade, Broward, Palm Beach), serviceType
- **D-06:** Service name in schema MUST match the H1 tag exactly for consistency

### Internal Linking Topology
- **D-07:** Concrete restoration is the hub page — all 6 service pages link back to it
- **D-08:** Each service page links to the 2 most contextually related services (already partially implemented per Phase 2 D-08)
- **D-09:** Add contextual body text links where natural — e.g., "concrete restoration often includes waterproofing" links to waterproofing page
- **D-10:** Homepage "Learn More" links already point to all service pages — no changes needed there
- **D-11:** Verify each service page has a "Related Services" section and that links are bidirectional where appropriate

### Heading Hierarchy Audit
- **D-12:** Every page must have exactly one H1, followed by H2 sections, with H3 subsections under H2s — no skipped levels
- **D-13:** Primary keyword must appear in at least one H2 per service page (e.g., "Our Concrete Restoration Process" as an H2)
- **D-14:** Audit all 7 pages for heading hierarchy consistency. Fix any pages with misordered or missing headings.

### Keyword Placement
- **D-15:** Primary keyword must appear in the first 100 words of body copy on each service page
- **D-16:** Primary keyword must appear in at least one H2 heading per service page
- **D-17:** Primary keyword should appear naturally in the conclusion/CTA section of each page
- **D-18:** Title tags and meta descriptions are already set (Phase 2) — verify they are under 60 and 160 chars respectively

### Claude's Discretion
- Exact LocalBusiness schema property values (address, hours, etc.) — use reasonable placeholder data matching a SE Florida contractor
- Which body text links to add and exact anchor text
- Specific heading text adjustments needed for keyword inclusion
- Order of implementation across the 7 pages

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Project Requirements
- `.planning/ROADMAP.md` — Phase 4 success criteria and canonical refs (Google Search Central documentation reference)
- `.planning/REQUIREMENTS.md` — SEO requirements: SEO-01 through SEO-06
- `.planning/PROJECT.md` — Project context, constraints, and key decisions

### Prior Phase Context
- `.planning/phases/01-site-foundation-homepage/01-CONTEXT.md` — Phase 1 decisions (HTML structure, design patterns)
- `.planning/phases/02-service-landing-pages/02-CONTEXT.md` — Phase 2 decisions (title tags, meta descriptions, H1s, alt text, internal linking)
- `.planning/phases/03-trust-credibility-lead-generation/03-CONTEXT.md` — Phase 3 decisions (trust signals, form optimization)

### Schema Markup Reference
- Google Search Central: structured data documentation — schema types and required/recommended properties for LocalBusiness and Service

### Existing Code
- `index.html` — Homepage (target for LocalBusiness schema)
- `concrete-restoration.html` — Primary keyword page (hub for internal linking)
- `waterproofing.html` — Service page (Service schema + internal links)
- `stucco-repair.html` — Service page (Service schema + internal links)
- `protective-coatings.html` — Service page (Service schema + internal links)
- `balcony-restoration.html` — Service page (Service schema + internal links)
- `painting.html` — Service page (Service schema + internal links)

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- All 7 HTML files already have unique `<title>` tags with primary keywords (SEO-01 ✓)
- All 7 HTML files already have `<meta name="description">` tags (SEO-02 ✓)
- All 7 HTML files have single `<h1>` tags with keywords (SEO-03 ✓)
- All images have descriptive `alt` text with keyword variations (SEO-06 ✓)
- Homepage already links to all service pages in nav, body, and footer

### Established Patterns
- Single-file HTML with inline CSS (no build tools — schema goes in `<head>` as inline `<script>`)
- All pages share identical header/footer/nav structure
- Phase 2 established "Related Services" section on each service page

### Integration Points
- Schema `<script type="application/ld+json">` blocks go in `<head>` of each HTML file
- Internal linking modifications happen in body text and "Related Services" sections
- Heading hierarchy fixes are inline edits to existing `<h2>` and `<h3>` tags
- No new files needed — all changes are modifications to existing 7 HTML files

</code_context>

<specifics>
## Specific Ideas

- Primary keyword: "concrete restoration south florida"
- Target market: Southeast Florida (Miami-Dade, Broward, Palm Beach)
- Company claims: 25+ years, 500+ projects, 4000+ PSI, licensed/insured, OSHA, EPA
- Reference site (bbconceptdesigns.com) for SEO structure — user's own prior work
- Schema markup follows Google's structured data guidelines for rich snippet eligibility

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope

</deferred>

---

*Phase: 4-SEO Optimization & Schema*
*Context gathered: 2026-06-20*

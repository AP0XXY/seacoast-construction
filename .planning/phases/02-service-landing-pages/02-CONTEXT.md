# Phase 2: Service Landing Pages - Context

**Gathered:** 2026-06-20
**Status:** Ready for planning

<domain>
## Phase Boundary

Build all 6 service pages with keyword-targeted content, SEO meta tags, and conversion CTAs — the core SEO engine. Each page targets a specific keyword cluster and drives visitors to the consultation form.

</domain>

<decisions>
## Implementation Decisions

### Page Structure (Standardized)
- **D-01:** All 6 pages follow the same section order: Hero → Problem/Solution → Process Steps → Benefits → Before/After Gallery → CTA → Contact Form
- **D-02:** Each page reuses the header/footer from index.html (Phase 1 established pattern)
- **D-03:** Active nav link highlighted for current page (visual indicator via CSS class)

### Content Depth
- **D-04:** All 6 pages get identical section types with service-specific content. No page gets more or fewer sections — equality ensures consistent SEO crawl structure.
- **D-05:** Concrete restoration page gets slightly more body copy (~150 words extra) since it's the primary keyword target. All others are equal length.

### Before/After Gallery
- **D-06:** Static grid layout (3-4 images per page), no slider/carousel — avoids JavaScript dependencies, keeps page fast, works on all devices
- **D-07:** Stock images with `<!-- SWAP: real photo -->` comments. Image grid uses CSS grid with consistent aspect ratio.

### Internal Linking
- **D-08:** Each service page includes a "Related Services" section linking to 2-3 most related services (contextual, not exhaustive)
- **D-09:** Footer links already cover all 6 pages (Phase 1) — no changes needed there
- **D-10:** Body text includes 1-2 contextual links to related services where natural (e.g., "concrete restoration often includes waterproofing")

### SEO Per Page
- **D-11:** Unique `<title>` tag per page with primary keyword (e.g., "Concrete Restoration South Florida | Seacoast Construction")
- **D-12:** Unique `<meta description>` per page under 160 chars with compelling copy and CTA language
- **D-13:** Single `<h1>` per page with primary keyword, proper H2/H3 hierarchy beneath
- **D-14:** Alt text on all images with keyword variations (e.g., "concrete restoration before and after")

### Template Pattern
- **D-15:** All 6 pages use the same HTML template structure — different content, same CSS classes, same section ordering. Plan as a template + content strategy, not 6 independent pages.

### CTA Strategy
- **D-16:** Each page has the same consultation form (reused from index.html) plus a mid-page CTA button before the gallery section
- **D-17:** Phone number in header and hero CTA on every page (clickable tel: link)

### Claude's Discretion
- Specific copy for each service page's problem/solution and process sections
- Which 2-3 services to link as "Related" on each page
- Hero background image selection from Unsplash (construction-relevant)
- Exact meta description copy per page
- Spacing, padding, and responsive refinements

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### SEO & Content Structure
- `https://bbconceptdesigns.com/luxury-condo-remodeling-in-miami/` — Reference site for SEO page structure (user's own prior work)
- `.planning/PROJECT.md` — Project context, constraints, and key decisions
- `.planning/REQUIREMENTS.md` — 19 service page requirements (REST-01–06, WATR-01–04, STUC-01–04, COAT-01–03, BALC-01–03, PAIN-01–03, ARCH-03)

### Phase Requirements
- `.planning/ROADMAP.md` — Phase 2 success criteria and canonical refs
- `.planning/phases/01-site-foundation-homepage/01-CONTEXT.md` — Phase 1 decisions (color scheme, design patterns, HTML structure)

### Existing Code
- `index.html` — Homepage with established header/footer, nav structure, CSS variables, color scheme, and consultation form (reuse across all service pages)

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `index.html` header/footer/nav: Complete responsive nav with hamburger, phone number, CTA button — copy to all 6 pages
- `index.html` CSS variables: `--navy`, `--blue`, `--white`, `--light-gray`, `--text-dark` — consistent across all pages
- `index.html` consultation form: Full form with name, company, email, phone, service type dropdown, project details — reuse on all service pages
- `index.html` responsive breakpoints: 768px, 1024px, 1440px media queries established

### Established Patterns
- Single-file HTML with inline CSS (project constraint — no build tools)
- System fonts (Arial, Helvetica, sans-serif)
- Unsplash placeholder images with `<!-- SWAP: -->` comments
- Service type dropdown in form already has all 6 services listed

### Integration Points
- Nav links in index.html already point to `concrete-restoration.html`, `waterproofing.html`, etc.
- Footer links already list all 6 service pages
- Form service dropdown already has value options matching page filenames

</code_context>

<specifics>
## Specific Ideas

- Primary keyword: "concrete restoration south florida"
- Secondary keywords per page: "waterproofing contractor south florida", "stucco repair south florida", "protective coatings south florida", etc.
- Target market: Southeast Florida (Miami-Dade, Broward, Palm Beach)
- Reference site (bbconceptdesigns.com) uses keyword-rich H1, problem/solution framing, process sections, and gallery — replicate this playbook
- 6 pages total, each targeting a distinct keyword cluster for SEO topical authority

</specifics>

<deferred>
## Deferred Ideas

None — decisions made via best practices, no scope creep identified.

</deferred>

---

*Phase: 2-Service Landing Pages*
*Context gathered: 2026-06-20*

# Phase 5: Polish, Performance & Launch - Context

**Gathered:** 2026-06-20
**Status:** Ready for planning

<domain>
## Phase Boundary

Final QA, performance optimization, analytics setup, form backend connection, and launch readiness. Deliver a site that scores 90+ on Lighthouse, has a working contact form, analytics tracking, SEO validation, and is deployed to a live hosting platform with proper 404 handling, sitemap, and robots.txt.

</domain>

<decisions>
## Implementation Decisions

### Hosting Platform
- **D-01:** Deploy to **Netlify** — free tier, custom domain, instant deploys, form handling built-in, matches single-file HTML constraint
- **D-02:** Use `netlify.toml` for build config (publish dir: root, no build command needed for static HTML)

### Form Submission Backend
- **D-03:** Use **Netlify Forms** — add `netlify` attribute to the `<form>` tag in `index.html` (and any other page with a form)
- **D-04:** Netlify Forms handles spam filtering, sends email notifications to site owner, requires no third-party service or API key
- **D-05:** Form field names must match existing HTML form fields — no restructuring needed

### Analytics Setup
- **D-06:** **Google Analytics 4 only** (no GTM) — single `<script>` tag in `<head>` of every page
- **D-07:** GA4 measurement ID to be provided by user — placeholder in HTML with comment for swap
- **D-08:** Place analytics snippet in all 7 HTML files for full-site tracking

### 404 Page
- **D-09:** Create **custom 404.html** — matches site design, shows nav and contact info, keeps visitors on-site
- **D-10:** Netlify automatically serves `404.html` from root — no config needed beyond the file existing
- **D-11:** 404 page includes: heading ("Page Not Found"), brief message, link to homepage, phone number, and nav links

### Lighthouse Performance Targets
- **D-12:** All four categories at 90+: Performance, Accessibility, Best Practices, SEO
- **D-13:** Performance optimizations: minify inline CSS, optimize image sizes (Unsplash URLs with `?w=` params), lazy-load below-fold images, minimize DOM size
- **D-14:** No new external dependencies — keep the pure HTML/CSS constraint

### SEO Validation & Sitemap
- **D-15:** Generate `sitemap.xml` with all 8 pages (7 HTML + 404 excluded)
- **D-16:** Generate `robots.txt` allowing all crawlers, pointing to sitemap
- **D-17:** Validate all title tags (under 60 chars), meta descriptions (under 160 chars), heading hierarchy, and schema markup across all pages

### Image Placeholder Audit
- **D-18:** Ensure every `<img>` tag has an `<!-- SWAP: ... -->` comment marking it for replacement
- **D-19:** No real images should be launched — all placeholders clearly marked

### Claude's Discretion
- Specific Lighthouse optimization techniques (image compression strategy, CSS minification approach)
- 404 page exact layout and copy
- robots.txt disallow rules (if any)
- Order of implementation across pages
- Whether to add `favicon.ico` or other static assets

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Project Requirements
- `.planning/ROADMAP.md` — Phase 5 success criteria and canonical refs (Google PageSpeed Insights, Google Search Console)
- `.planning/REQUIREMENTS.md` — All remaining validation requirements
- `.planning/PROJECT.md` — Project context, constraints, and key decisions

### Prior Phase Context
- `.planning/phases/01-site-foundation-homepage/01-CONTEXT.md` — Phase 1 decisions (HTML structure, design patterns, form structure)
- `.planning/phases/02-service-landing-pages/02-CONTEXT.md` — Phase 2 decisions (title tags, meta descriptions, H1s, alt text, internal linking)
- `.planning/phases/03-trust-credibility-lead-generation/03-CONTEXT.md` — Phase 3 decisions (trust signals, form optimization)
- `.planning/phases/04-seo-optimization-schema/04-CONTEXT.md` — Phase 4 decisions (schema markup, heading hierarchy, keyword placement, internal linking)

### Performance & Hosting Reference
- Google PageSpeed Insights — Lighthouse score benchmarks and optimization guidance
- Netlify documentation — form handling, custom domains, 404 pages

### Existing Code
- `index.html` — Homepage (primary form, analytics insertion point)
- `concrete-restoration.html` — Service page (analytics insertion point)
- `waterproofing.html` — Service page (analytics insertion point)
- `stucco-repair.html` — Service page (analytics insertion point)
- `protective-coatings.html` — Service page (analytics insertion point)
- `balcony-restoration.html` — Service page (analytics insertion point)
- `painting.html` — Service page (analytics insertion point)

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- All 7 HTML files already have proper `<title>`, `<meta description>`, single `<h1>`, alt text, and schema markup (Phases 1-4)
- `index.html` consultation form (lines 658-708) — already functional, needs `netlify` attribute for Netlify Forms
- All pages share identical header/footer/nav structure — analytics snippet goes in same position on all
- CSS variables (--navy, --blue, --white) for consistent 404 page styling

### Established Patterns
- Single-file HTML with inline CSS — no build tools, no minification pipeline needed
- Unsplash placeholder images with `<!-- SWAP: -->` comments already in place
- Responsive breakpoints: 768px, 1024px, 1440px
- System fonts (Arial, Helvetica, sans-serif) — no web font loading overhead

### Integration Points
- `<script>` tag for GA4 goes in `<head>` of each HTML file
- `netlify` attribute added to existing `<form>` tag
- `404.html` created as new file in root (Netlify auto-serves)
- `sitemap.xml` and `robots.txt` created as new files in root
- Image `src` attributes may need `?w=` query params for Unsplash optimization

</code_context>

<specifics>
## Specific Ideas

- Company claims: 25+ years, 500+ projects, 4000+ PSI, licensed/insured, OSHA, EPA
- Reference site (bbconceptdesigns.com) for SEO structure
- GA4 measurement ID to be provided — use placeholder for now
- Netlify free tier is sufficient for this static site

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope

</deferred>

---

*Phase: 5-Polish, Performance & Launch*
*Context gathered: 2026-06-20*

# Phase 3: Trust, Credibility & Lead Generation - Context

**Gathered:** 2026-06-20
**Status:** Ready for planning

<domain>
## Phase Boundary

Add project portfolio, testimonials, certifications, and optimize the consultation form for maximum conversion. Enhance the homepage's trust signals and lead generation capabilities while preserving existing design patterns.

</domain>

<decisions>
## Implementation Decisions

### Certifications Display
- **D-01:** Use visual badges/icons for certifications (not text list) — each certification gets an icon with label underneath
- **D-02:** Display all four certifications: State Licensed, Fully Insured, OSHA Compliant, EPA Certified
- **D-03:** Certifications placed below the hero section — first trust signal visitors see after the main CTA
- **D-04:** Merge certifications into existing "Why Choose Us" section rather than creating a separate section — reduces section count, keeps trust signals consolidated

### Trust Content Enhancement
- **D-05:** Enhance the existing "Why Choose Us" section with certification badges alongside the existing 4 trust items (25+ years, licensed/insured, proven process, quality guarantee)
- **D-06:** Update "Licensed & Fully Insured" item to include all four certification badges visually

### Claude's Discretion
- Specific icon/badge design for each certification (shield, checkmark, or industry-standard icons)
- Exact layout within "Why Choose Us" — badges inline with text or stacked below
- Portfolio section layout and categorization
- Testimonials format and placement
- Form optimization details
- Spacing, padding, and responsive refinements

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Project Requirements
- `.planning/ROADMAP.md` — Phase 3 success criteria and canonical refs
- `.planning/REQUIREMENTS.md` — Trust requirements (TRST-01 through TRST-04) and lead gen requirements (LEAD-01 through LEAD-05)
- `.planning/PROJECT.md` — Project context, constraints, and key decisions

### Prior Phase Context
- `.planning/phases/01-site-foundation-homepage/01-CONTEXT.md` — Phase 1 decisions (color scheme, design patterns, HTML structure)
- `.planning/phases/02-service-landing-pages/02-CONTEXT.md` — Phase 2 decisions (no carousel, stock images with swap comments)

### Reference Sites
- `bbconceptdesigns.com` — Portfolio and testimonial patterns (user's own prior work)

### Existing Code
- `index.html` — Homepage with established header/footer, nav, stats section, Why Choose Us section, consultation form, and CSS variables

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `index.html` stats section (lines 613-632): Already displays 25+ years, 500+ projects, 4,000+ PSI, licensed/insured — no changes needed
- `index.html` Why Choose Us section (lines 634-656): 4 trust items with existing CSS grid layout — extend with certification badges
- `index.html` consultation form (lines 658-708): Complete form with all required fields, success message — optimize for conversion
- `index.html` CSS variables (--navy, --blue, --white, --light-gray, --text-dark): Consistent design tokens

### Established Patterns
- Single-file HTML with inline CSS (project constraint — no build tools)
- System fonts (Arial, Helvetica, sans-serif)
- Unsplash placeholder images with `<!-- SWAP: -->` comments
- Responsive breakpoints: 768px, 1024px, 1440px
- Card-based layout with box-shadow and border-radius

### Integration Points
- Certifications integrate into existing Why Choose Us grid (add badges to existing items or extend grid)
- Portfolio section will be new — insert between existing sections
- Testimonials section will be new — insert between existing sections
- Form optimization modifies existing contact section

</code_context>

<specifics>
## Specific Ideas

- Company claims: 25+ years, 500+ projects, 4000+ PSI, licensed/insured, OSHA, EPA
- Reference site (bbconceptdesigns.com) uses portfolio grids and testimonial sections — replicate this pattern
- Certifications should be visually prominent (badges/icons) to build immediate trust
- All trust signals consolidated in one section (Why Choose Us) for scannability

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope

</deferred>

---

*Phase: 3-Trust, Credibility & Lead Generation*
*Context gathered: 2026-06-20*

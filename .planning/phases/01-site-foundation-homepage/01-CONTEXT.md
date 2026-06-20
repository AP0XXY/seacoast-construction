# Phase 1: Site Foundation & Homepage - Context

**Gathered:** 2026-06-19
**Status:** Ready for planning

<domain>
## Phase Boundary

Launch a working homepage with navigation, hero section, and consultation form — the core conversion engine. Expand the user's existing single-page HTML into the homepage, with placeholders linking to future service pages.

</domain>

<decisions>
## Implementation Decisions

### Source Material
- **D-01:** User's existing HTML is the primary source — expand it, don't rebuild from scratch
- **D-02:** Keep the existing navy/blue color scheme, layout structure, and section ordering from the provided HTML

### Design Approach
- **D-03:** Maintain the existing design patterns (sticky nav, hero, services grid, stats, portfolio, credentials, contact form)
- **D-04:** Clean up and professionalize — remove residential division, focus on commercial restoration/concrete restoration

### Claude's Discretion
- Homepage section ordering and spacing
- Specific cleanup of existing HTML (removing residential content, tightening copy)
- Mobile responsiveness refinements
- Sticky header CTA behavior

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### SEO & Content Structure
- `https://bbconceptdesigns.com/luxury-condo-remodeling-in-miami/` — Reference site for SEO page structure (user's own prior work)
- `.planning/PROJECT.md` — Project context, constraints, and key decisions
- `.planning/REQUIREMENTS.md` — 38 v1 requirements across 5 phases

### Phase Requirements
- `.planning/ROADMAP.md` — Phase 1 requirements: ARCH-01, ARCH-02, ARCH-04, ARCH-05, UX-01, UX-02, UX-03, UX-04, UX-05

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- User's original HTML: Complete single-page site with nav, hero, services, stats, portfolio, credentials, contact form — serves as the template for all pages
- Navy/blue color scheme already established in the HTML
- Responsive breakpoints likely already handled

### Established Patterns
- Single-file HTML with inline CSS (project constraint)
- System fonts (Arial, Helvetica, sans-serif)
- Unsplash placeholder images with swap-ready comments

### Integration Points
- Homepage navigation will link to future service pages (Phase 2)
- Contact form will be consistent across all pages
- Header/footer will be shared across the multi-page site

</code_context>

<specifics>
## Specific Ideas

- User referenced BB Concept Designs as the SEO model — "something like i did for this site"
- Primary keyword: "concrete restoration south florida"
- Target market: Southeast Florida (Miami-Dade, Broward, Palm Beach)
- Company claims: 25+ years, 500+ projects, 4000+ PSI, licensed/insured, OSHA, EPA

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope

</deferred>

---

*Phase: 1-Site Foundation & Homepage*
*Context gathered: 2026-06-19*

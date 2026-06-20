# Phase 1: Site Foundation & Homepage - Research

**Researched:** 2026-06-19

## Research Summary

Phase 1 builds the homepage as the primary conversion engine for "concrete restoration south florida" keyword. The user's existing single-page HTML provides the structural template — we expand it into a proper multi-page site with shared header/footer, service page placeholders, and a functional consultation form. The bbconceptdesigns.com reference site demonstrates the SEO playbook: keyword-rich H1, definition/benefits/why-choose-us sections, internal linking, and a contact CTA with form.

## Technical Approach

### Multi-Page HTML Structure

- **Single-file pages** with inline CSS (no build tools, no frameworks)
- **Shared header/footer** across all pages — copy-paste template pattern, no server-side includes needed
- **File structure:** `index.html` (homepage), `contact.html` (standalone form page), placeholder service pages linking to Phase 2 deliverables
- **Navigation:** Sticky nav with links to Home, each service page, and Request Consultation CTA
- **Footer:** Company name, phone (tel: link), email, service area, quick service links, copyright

### Homepage Sections (in order)

1. **Sticky Header/Nav** — Logo/name, nav links, phone number, "Request Consultation" CTA button
2. **Hero Section** — H1 with "concrete restoration south florida", subheadline, two CTAs (primary + secondary)
3. **Services Overview Grid** — 6 service cards (placeholder links to Phase 2 pages)
4. **Stats/Trust Bar** — 25+ years, 500+ projects, 4,000+ PSI, licensed & insured
5. **Why Choose Us** — 4 key differentiators (experience, process, quality, certifications)
6. **Contact/Consultation Form** — RFQ-style form on homepage itself (LEAD-01)
7. **Footer** — NAP data, quick links, copyright

### Mobile Responsiveness Approach

- **Mobile-first CSS** — base styles for mobile, media queries for tablet (768px) and desktop (1024px, 1440px)
- **Sticky header** shrinks on scroll, CTA button remains visible
- **Hamburger menu** on mobile (CSS-only toggle, no JS required)
- **Form** stacks vertically on mobile, two-column on desktop
- **Service cards** — single column mobile, 2-col tablet, 3-col desktop
- **Phone number** uses `tel:` link for click-to-call on mobile

### Form Implementation

- **Method:** POST to `action=""` (self-submit) with JavaScript `onsubmit` handler
- **Fields:** Name (required), Company/Association, Email (required), Phone (required), Service Type (select dropdown), Project Details (textarea)
- **Success state:** Hide form, show confirmation message (no backend needed)
- **CTA:** Blue submit button matching site color scheme
- **Accessibility:** Labels associated with inputs, `required` attributes, `aria` attributes

## Reference Analysis

### What to Learn from bbconceptdesigns.com

The reference site (`/luxury-condo-remodeling-in-miami/`) demonstrates patterns to replicate:

1. **Keyword-Rich H1** — "Luxury Condo Remodeling In Miami" in H1 tag, repeated naturally in subheadings
2. **Definition Section** — Opens with "What is X" content that Google indexes for informational queries
3. **Benefits Section** — Numbered list format (Increased Property Value, Enhanced Living, Modernization, Energy Efficiency)
4. **"Why Choose Us" Section** — 4 numbered points with bold lead-ins (Expertise, Proven Success, Client-Centric, Transparent Pricing)
5. **Project Showcase** — Before/after images with location tags (Williams Island, Palm Bay Towers, etc.)
6. **Internal Linking** — Links to other service pages within content
7. **Contact CTA** — Bottom of page with form, phone, email, Google Maps embed
8. **Footer NAP** — Full business name, address, phone, email, social links

### How to Apply to Concrete Restoration

| BB Concept Pattern | Seacoast Application |
|--------------------|---------------------|
| "What is luxury condo remodeling" | "What is concrete restoration" — problem statement for spalling, deterioration |
| Benefits of remodeling | Benefits of restoration — structural integrity, property value, safety, code compliance |
| Why choose us (4 points) | Why choose Seacoast — 25+ years, licensed/insured, OSHA/EPA, 4,000+ PSI quality |
| Project showcase | Project portfolio section with categorized work (commercial, residential, waterfront) |
| Contact form + phone | Same pattern — form on every page + sticky phone number |
| Service sub-links | 6 service page links in nav and services grid |

## Dependencies & Risks

### Dependencies (Must Be In Place First)

- **None** — this is Phase 1, the foundation. No prior phases needed.
- **User's existing HTML** — the original single-page HTML serves as the starting template. If not available, we build from scratch using the established patterns.

### Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| User's original HTML not found/accessible | Medium | Build homepage from scratch using bbconceptdesigns.com patterns + established conventions |
| Contact form has no backend | Low | Use JavaScript success message; user connects to email/form service in Phase 5 |
| Placeholder images look unprofessional | Low | Use Unsplash with `<!-- SWAP: real photo -->` comments; user replaces post-launch |
| Mobile responsiveness breaks at edge cases | Medium | Test at 320px, 768px, 1024px, 1440px breakpoints during verification |
| Homepage content too thin for SEO | Medium | Ensure 800+ words of keyword-rich content in main sections |

## Recommendations for Planner

### PLAN.md Structure

The PLAN.md should contain 2-3 atomic tasks:

1. **Task 1: Create homepage (index.html)**
   - Build complete homepage with all sections
   - Include shared header/footer that will be copy-pasted to other pages
   - Mobile-responsive CSS
   - Consultation form with JS success handler
   - LocalBusiness schema markup (JSON-LD)
   - Alt text on all images

2. **Task 2: Create contact.html**
   - Standalone consultation form page
   - Same header/footer as homepage
   - Full RFQ form with all fields
   - Phone number and email displayed

3. **Task 3: Create placeholder service page links**
   - Update navigation to link to future service pages
   - Services grid cards link to placeholder pages
   - Footer quick links point to future service pages

### Implementation Order

1. Create homepage first — it defines the shared header/footer template
2. Create contact.html — uses the same template
3. Test mobile responsiveness at all breakpoints
4. Verify form functionality
5. Validate SEO elements (title, meta, H1, schema)

### Key Conventions to Follow

- **Color scheme:** Navy (#0b1426), Blue (#2f80ed), White
- **Fonts:** System fonts only (Arial, Helvetica, sans-serif)
- **Images:** Unsplash placeholders with swap comments
- **CTA style:** Blue buttons, consistent placement
- **Form:** RFQ-style with all 6 fields
- **Schema:** LocalBusiness on homepage, Service on future service pages

### Verification Criteria

- Homepage loads in under 2 seconds (pure HTML/CSS, should be instant)
- Hero H1 contains "concrete restoration south florida"
- Navigation links to all future service pages
- Form captures all required fields
- Mobile responsive at 320px, 768px, 1024px, 1440px
- Phone number and CTA visible without scrolling (sticky header)
- LocalBusiness schema validates

---

*Phase: 1-Site Foundation & Homepage*
*Research completed: 2026-06-19*

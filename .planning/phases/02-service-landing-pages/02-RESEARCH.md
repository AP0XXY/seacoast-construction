# Phase 2: Service Landing Pages - Research

**Researched:** 2026-06-20
**Domain:** Static HTML/CSS landing pages, SEO content structure
**Confidence:** HIGH

## Summary

Phase 2 creates 6 standalone service landing pages for Seacoast Construction. Each page targets a distinct SEO keyword cluster (e.g., "concrete restoration south florida", "waterproofing south florida") and drives visitors to the consultation form. The site is pure HTML/CSS with no build tools — all CSS is inline within `<style>` tags in each file.

The existing `index.html` (Phase 1) serves as the template source: header/nav, footer, consultation form, CSS variables, color scheme, responsive breakpoints, and JavaScript form handler are all copied to each new page. The reference site `bbconceptdesigns.com` demonstrates the SEO page structure pattern: keyword-rich H1 → problem/solution framing → process steps → benefits → before/after gallery → CTA → contact form → related services.

**Primary recommendation:** Build one HTML template file first, then create all 6 service pages by filling in service-specific content (hero H1, problem/solution copy, process steps, benefits, gallery images, meta tags). This eliminates CSS drift between pages and ensures consistency.

<user_constraints>
## User Constraints (from CONTEXT.md)

### Locked Decisions
- **D-01:** All 6 pages follow the same section order: Hero → Problem/Solution → Process Steps → Benefits → Before/After Gallery → CTA → Contact Form
- **D-02:** Each page reuses the header/footer from index.html (Phase 1 established pattern)
- **D-03:** Active nav link highlighted for current page (visual indicator via CSS class)
- **D-04:** All 6 pages get identical section types with service-specific content. No page gets more or fewer sections
- **D-05:** Concrete restoration page gets slightly more body copy (~150 words extra) since it's the primary keyword target. All others are equal length
- **D-06:** Static grid layout (3-4 images per page), no slider/carousel
- **D-07:** Stock images with `<!-- SWAP: real photo -->` comments. Image grid uses CSS grid with consistent aspect ratio
- **D-08:** Each service page includes a "Related Services" section linking to 2-3 most related services
- **D-09:** Footer links already cover all 6 pages (Phase 1) — no changes needed there
- **D-10:** Body text includes 1-2 contextual links to related services where natural
- **D-11:** Unique `<title>` tag per page with primary keyword (e.g., "Concrete Restoration South Florida | Seacoast Construction")
- **D-12:** Unique `<meta description>` per page under 160 chars with compelling copy and CTA language
- **D-13:** Single `<h1>` per page with primary keyword, proper H2/H3 hierarchy beneath
- **D-14:** Alt text on all images with keyword variations
- **D-15:** All 6 pages use the same HTML template structure — different content, same CSS classes, same section ordering
- **D-16:** Each page has the same consultation form (reused from index.html) plus a mid-page CTA button before the gallery section
- **D-17:** Phone number in header and hero CTA on every page (clickable tel: link)

### Claude's Discretion
- Specific copy for each service page's problem/solution and process sections
- Which 2-3 services to link as "Related" on each page
- Hero background image selection from Unsplash (construction-relevant)
- Exact meta description copy per page
- Spacing, padding, and responsive refinements

### Deferred Ideas (OUT OF SCOPE)
None — decisions made via best practices, no scope creep identified.
</user_constraints>

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| ARCH-03 | Each service page has unique URL, meta tags, and keyword-targeted content | Template pattern (D-15) + per-page SEO tags (D-11, D-12, D-13) |
| REST-01 | Dedicated concrete restoration page targeting "concrete restoration south florida" | Primary keyword page — gets extra body copy per D-05 |
| REST-02 | Page includes problem statement (spalling, deterioration, structural concerns) | Problem/Solution section in standardized template |
| REST-03 | Page includes step-by-step process (assessment → preparation → repair → finishing) | Process Steps section in standardized template |
| REST-04 | Page includes benefits section (structural integrity, property value, safety) | Benefits section in standardized template |
| REST-05 | Page includes before/after gallery (3-5 images minimum) | Static grid layout per D-06, D-07 |
| REST-06 | Page includes clear CTA to consultation request | Mid-page CTA + contact form per D-16 |
| WATR-01 | Dedicated waterproofing page targeting "waterproofing contractor south florida" | Template page with service-specific content |
| WATR-02 | Page covers elastomeric coatings, below-grade systems, joint sealing | Problem/Solution and process content for waterproofing |
| WATR-03 | Page includes problem/solution framing | Standardized Problem/Solution section |
| WATR-04 | Page includes CTA to consultation request | Standardized CTA + form |
| STUC-01 | Dedicated stucco repair page targeting "stucco repair south florida" | Template page with service-specific content |
| STUC-02 | Page covers crack remediation, re-application, EIFS systems | Problem/Solution and process content for stucco |
| STUC-03 | Page includes before/after examples | Static grid layout per D-06, D-07 |
| STUC-04 | Page includes CTA to consultation request | Standardized CTA + form |
| COAT-01 | Dedicated coatings page targeting "protective coatings south florida" | Template page with service-specific content |
| COAT-02 | Page covers anti-carbonation, silane/siloxane sealers, traffic coatings | Problem/Solution and process content for coatings |
| COAT-03 | Page includes CTA to consultation request | Standardized CTA + form |
| BALC-01 | Dedicated balcony restoration page | Template page with service-specific content |
| BALC-02 | Page covers deck coating, railing repairs, slope correction | Problem/Solution and process content for balconies |
| BALC-03 | Page includes CTA to consultation request | Standardized CTA + form |
| PAIN-01 | Dedicated painting services page | Template page with service-specific content |
| PAIN-02 | Page covers commercial painting, waterproof painting, elastomeric coatings | Problem/Solution and process content for painting |
| PAIN-03 | Page includes CTA to consultation request | Standardized CTA + form |
</phase_requirements>

## Architectural Responsibility Map

| Capability | Primary Tier | Secondary Tier | Rationale |
|------------|-------------|----------------|-----------|
| Page structure & layout | Browser/Client | — | Static HTML renders client-side |
| SEO meta tags | Browser/Client | — | Tags defined in HTML `<head>`, parsed by crawlers |
| CSS styling | Browser/Client | — | Inline `<style>` in each HTML file |
| Internal linking | Browser/Client | — | Static `<a href>` links in HTML |
| Consultation form | Browser/Client | — | Client-side form with JS submit handler |
| Responsive design | Browser/Client | — | CSS media queries in `<style>` |
| Image placeholders | CDN/Static | — | Unsplash URLs loaded at runtime |
| Content (copywriting) | Browser/Client | — | Static HTML text content |

**Note:** This is a purely static site — all capabilities are Browser/Client tier. There is no backend, API, database, or build pipeline.

## Standard Stack

### Core

| Library | Version | Purpose | Why Standard |
|---------|---------|---------|--------------|
| HTML5 | — | Page structure | Project constraint (pure HTML/CSS) |
| CSS3 | — | Styling with inline `<style>` tags | Project constraint (no build tools) |
| Vanilla JS | — | Form submit handler only | Lightweight, no dependencies |

### Supporting

| Tool | Purpose | When to Use |
|------|---------|-------------|
| Unsplash | Placeholder images with `?w=WIDTH&h=HEIGHT&fit=crop` params | All image sources |
| Google Fonts (optional) | Typography upgrade | Only if user requests — currently using system fonts |

### Alternatives Considered

| Instead of | Could Use | Tradeoff |
|------------|-----------|----------|
| Inline `<style>` per file | Shared CSS file | Project constraint forbids external files — single-file pages |
| System fonts | Google Fonts | Extra HTTP request, slight performance hit — not worth it for this use case |
| CSS Grid gallery | Flexbox gallery | Grid is more natural for fixed-ratio image grids |

**Installation:** None required — this is a static HTML/CSS project with no dependencies to install.

## Package Legitimacy Audit

**SKIPPED** — No external packages are installed in this phase. Pure HTML/CSS/JS with no package manager.

## Recommended Project Structure

```
/Users/rukiverr/
├── index.html                    (Phase 1 — complete)
├── concrete-restoration.html     (Phase 2 — new)
├── waterproofing.html            (Phase 2 — new)
├── stucco-repair.html            (Phase 2 — new)
├── protective-coatings.html      (Phase 2 — new)
├── balcony-restoration.html      (Phase 2 — new)
├── painting.html                 (Phase 2 — new)
└── .planning/
    └── phases/
        └── 02-service-landing-pages/
            ├── 02-CONTEXT.md
            ├── 02-RESEARCH.md
            └── 02-PLAN.md        (planner creates)
```

## Architecture Patterns

### Pattern 1: Single-File HTML Template with Inline CSS

**What:** Each page is a self-contained HTML file with all CSS in a `<style>` tag in `<head>`. No external stylesheets, no build tools.

**When to use:** When the project constraint requires zero dependencies and maximum portability (this project).

**Implementation approach:**
1. Create a "base template" — extract the shared CSS + header + footer + form from `index.html`
2. For each service page: copy the template, swap in service-specific content
3. Each page's `<style>` tag contains the same CSS (duplicated across files — acceptable for 7 files)

**Key CSS variables to preserve across all pages:**
```css
:root {
    --navy: #0b1426;
    --blue: #2f80ed;
    --white: #ffffff;
    --light-gray: #f0f4f8;
    --text-dark: #333333;
}
```

### Pattern 2: Active Nav Highlight

**What:** CSS class `.nav-active` applied to the current page's nav link for visual indicator.

**Implementation:**
```html
<!-- On concrete-restoration.html -->
<li><a href="concrete-restoration.html" class="nav-active">Concrete Restoration</a></li>
```

```css
.nav-links a.nav-active {
    color: var(--blue);
    border-bottom: 2px solid var(--blue);
    padding-bottom: 2px;
}
```

### Pattern 3: Service Page Section Order (from CONTEXT.md D-01)

Each service page follows this exact section order:

1. **Header/Nav** — Same as index.html, with `.nav-active` on current page
2. **Hero** — Gradient overlay + keyword-rich H1 + subtitle + 2 CTAs (consultation + phone)
3. **Problem/Solution** — "Why [service] matters" framing with industry-specific problems
4. **Process Steps** — Numbered steps (e.g., Assessment → Preparation → Repair → Finishing)
5. **Benefits** — 3-4 benefits as card/grid items
6. **Mid-page CTA** — Blue button to consultation form
7. **Before/After Gallery** — CSS grid of 3-4 stock images with `<!-- SWAP: -->` comments
8. **Related Services** — 2-3 links to most related service pages
9. **Contact Form** — Same form as index.html, with service dropdown pre-selected
10. **Footer** — Same as index.html

### Pattern 4: SEO Meta Tags per Page

Each page needs unique `<title>` and `<meta description>` in `<head>`:

| Page | Title (under 60 chars) | Meta Description (under 160 chars) |
|------|------------------------|-------------------------------------|
| concrete-restoration.html | Concrete Restoration South Florida \| Seacoast Construction | Professional concrete restoration services in South Florida. Spalling repair, structural rehabilitation. 25+ years experience. Free consultation. |
| waterproofing.html | Waterproofing South Florida \| Seacoast Construction | Expert waterproofing contractor in South Florida. Elastomeric coatings, below-grade systems, joint sealing. Licensed & insured. Get a free quote. |
| stucco-repair.html | Stucco Repair South Florida \| Seacoast Construction | Professional stucco repair services in South Florida. Crack remediation, EIFS systems, re-application. 25+ years experience. Free estimate. |
| protective-coatings.html | Protective Coatings South Florida \| Seacoast Construction | Anti-carbonation coatings, silane/siloxane sealers, and traffic coatings in South Florida. Protect your concrete investment. Free consultation. |
| balcony-restoration.html | Balcony Restoration South Florida \| Seacoast Construction | Expert balcony restoration in South Florida. Deck coating, railing repairs, slope correction. Licensed contractor. Free consultation. |
| painting.html | Painting Services South Florida \| Seacoast Construction | Commercial painting, waterproof coatings, and elastomeric finishes in South Florida. Quality results guaranteed. Free consultation. |

### Pattern 5: Related Services Mapping

Each page links to 2-3 most contextually related services:

| Page | Related Services |
|------|-----------------|
| concrete-restoration.html | waterproofing, protective-coatings, stucco-repair |
| waterproofing.html | concrete-restoration, balcony-restoration, protective-coatings |
| stucco-repair.html | concrete-restoration, painting, protective-coatings |
| protective-coatings.html | concrete-restoration, waterproofing, stucco-repair |
| balcony-restoration.html | waterproofing, concrete-restoration, protective-coatings |
| painting.html | stucco-repair, protective-coatings, waterproofing |

### Pattern 6: Image Grid CSS

Static grid layout for before/after gallery (from CONTEXT.md D-06):

```css
.gallery-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
    max-width: 1200px;
    margin: 0 auto;
}

.gallery-grid img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 8px;
}

@media (min-width: 768px) {
    .gallery-grid {
        grid-template-columns: 1fr 1fr;
    }
}

@media (min-width: 1024px) {
    .gallery-grid {
        grid-template-columns: 1fr 1fr 1fr;
    }
}
```

### Anti-Patterns to Avoid

- **Don't create 6 completely independent pages** — Use the template pattern (D-15) to ensure CSS consistency
- **Don't add JavaScript frameworks** — Project constraint: pure HTML/CSS/JS only
- **Don't use carousels/sliders** — D-06 explicitly chose static grid for performance
- **Don't skip `<!-- SWAP: -->` comments** — Phase 5 needs to identify all placeholder images
- **Don't add external CSS files** — Project constraint: single-file pages with inline styles

## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| Responsive grid | Custom float layouts | CSS Grid with media queries | Cleaner, less code, better browser support |
| Image aspect ratios | Fixed height + width | `object-fit: cover` with fixed height | Maintains ratio across screen sizes |
| Mobile nav | JS hamburger menu library | CSS checkbox hack (already in index.html) | Zero dependencies, proven pattern |
| Form validation | Custom JS validation | HTML5 `required` attribute + `type="email"` | Built-in browser validation |

**Key insight:** The existing `index.html` already solves responsive design, mobile nav, and form handling. Copy these patterns — don't rebuild them.

## Common Pitfalls

### Pitfall 1: CSS Drift Between Pages
**What goes wrong:** Each page develops slightly different spacing, colors, or responsive behavior because CSS was copied and modified independently.
**Why it happens:** Copy-paste-modify workflow without a reference template.
**How to avoid:** Create one canonical template CSS block first. Copy it identically to all 6 pages. Only add service-specific CSS (like gallery grid) once, then copy that too.
**Warning signs:** Inconsistent padding between pages, different font sizes, varying button styles.

### Pitfall 2: Missing or Duplicate Meta Tags
**What goes wrong:** Pages share identical `<title>` or `<meta description>`, or some pages lack them entirely.
**Why it happens:** Copying the full HTML file and forgetting to update head tags.
**How to avoid:** Make meta tag updates the FIRST thing done when creating each new page, before any content changes.
**Warning signs:** Google Search Console shows duplicate title/description warnings.

### Pitfall 3: Broken Internal Links
**What goes wrong:** Related services section links to wrong filenames or uses wrong relative paths.
**Why it happens:** File naming inconsistency (e.g., `stucco.html` vs `stucco-repair.html`).
**How to avoid:** Use the exact filenames already defined in index.html nav: `concrete-restoration.html`, `waterproofing.html`, `stucco-repair.html`, `protective-coatings.html`, `balcony-restoration.html`, `painting.html`.
**Warning signs:** 404 errors on internal links.

### Pitfall 4: Inconsistent H1/H2 Hierarchy
**What goes wrong:** Multiple H1 tags on a page, or H2/H3 tags used for styling instead of structure.
**Why it happens:** Using heading tags for visual appearance rather than semantic meaning.
**How to avoid:** One H1 per page (service name + keyword). H2 for major sections. H3 for subsections within H2. Never skip levels (no H1 → H3).
**Warning signs:** SEO tools flag heading hierarchy issues.

### Pitfall 5: Forgetting Active Nav State
**What goes wrong:** All pages show no active nav link, or the wrong link is highlighted.
**Why it happens:** Not adding `.nav-active` class to the current page's nav link.
**How to avoid:** When creating each page, immediately add `.nav-active` to the correct `<a>` tag before any other changes.
**Warning signs:** Users can't tell which page they're on from the nav.

## Code Examples

### Service Page Template Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{SERVICE} South Florida | Seacoast Construction</title>
    <meta name="description" content="{UNDER 160 CHARS WITH CTA}">
    <!-- Service schema markup (Phase 4 adds this) -->
    <style>
        /* Copy entire <style> block from index.html */
    </style>
</head>
<body>
    <!-- Header with .nav-active on current page -->
    <header>...</header>

    <!-- Hero with keyword-rich H1 -->
    <section class="hero">
        <h1>{SERVICE} South Florida</h1>
        <p>{service-specific subtitle}</p>
        <div class="hero-ctas">
            <a href="#contact" class="btn btn-primary">Request Free Consultation</a>
            <a href="tel:+15615550192" class="btn btn-secondary">Call (561) 555-0192</a>
        </div>
    </section>

    <!-- Problem/Solution -->
    <section class="problem-solution">
        <div class="container">
            <h2>Why {SERVICE} Matters in South Florida</h2>
            <p>{problem framing with industry-specific issues}</p>
            <h3>Our Solution</h3>
            <p>{how Seacoast solves these problems}</p>
        </div>
    </section>

    <!-- Process Steps -->
    <section class="process">
        <div class="container">
            <h2>Our {SERVICE} Process</h2>
            <div class="process-steps">
                <div class="step"><h3>1. Assessment</h3><p>...</p></div>
                <div class="step"><h3>2. Preparation</h3><p>...</p></div>
                <div class="step"><h3>3. {Service-specific step}</h3><p>...</p></div>
                <div class="step"><h3>4. Final Inspection</h3><p>...</p></div>
            </div>
        </div>
    </section>

    <!-- Benefits -->
    <section class="benefits">
        <div class="container">
            <h2>Benefits of Professional {SERVICE}</h2>
            <div class="benefits-grid">
                <div class="benefit-item">...</div>
                <div class="benefit-item">...</div>
                <div class="benefit-item">...</div>
            </div>
        </div>
    </section>

    <!-- Mid-page CTA -->
    <section class="mid-cta">
        <div class="container">
            <a href="#contact" class="btn btn-primary">Get Your Free {SERVICE} Consultation</a>
        </div>
    </section>

    <!-- Before/After Gallery -->
    <section class="gallery">
        <div class="container">
            <h2>{SERVICE} Before & After</h2>
            <div class="gallery-grid">
                <img src="https://images.unsplash.com/..." alt="{service} before and after">
                <!-- SWAP: real photo -->
                <img src="https://images.unsplash.com/..." alt="{service} restoration result">
                <!-- SWAP: real photo -->
                <img src="https://images.unsplash.com/..." alt="{service} completed project">
                <!-- SWAP: real photo -->
            </div>
        </div>
    </section>

    <!-- Related Services -->
    <section class="related-services">
        <div class="container">
            <h2>Related Services</h2>
            <div class="related-grid">
                <a href="{related1}.html">{Related Service 1}</a>
                <a href="{related2}.html">{Related Service 2}</a>
                <a href="{related3}.html">{Related Service 3}</a>
            </div>
        </div>
    </section>

    <!-- Contact Form (pre-selected service) -->
    <section id="contact" class="contact">
        <div class="container">
            <h2>Request a Free Consultation</h2>
            <!-- Same form as index.html, with service dropdown pre-selected -->
        </div>
    </section>

    <!-- Footer (same as index.html) -->
    <footer>...</footer>

    <script>
        // Same handleSubmit function as index.html
        // Pre-select service dropdown based on page
        document.getElementById('service').value = '{service-slug}';
    </script>
</body>
</html>
```

### CSS for New Sections (add to existing style block)

```css
/* Problem/Solution */
.problem-solution {
    padding: 5rem 2rem;
    background-color: var(--white);
}

.problem-solution h2 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 1.5rem;
    color: var(--navy);
}

.problem-solution h3 {
    color: var(--navy);
    margin: 2rem 0 1rem;
    font-size: 1.3rem;
}

/* Process Steps */
.process {
    padding: 5rem 2rem;
    background-color: var(--light-gray);
}

.process h2 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 3rem;
    color: var(--navy);
}

.process-steps {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    max-width: 1000px;
    margin: 0 auto;
}

.step {
    background: var(--white);
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.step h3 {
    color: var(--blue);
    margin-bottom: 0.75rem;
}

/* Benefits */
.benefits {
    padding: 5rem 2rem;
    background-color: var(--white);
}

.benefits h2 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 3rem;
    color: var(--navy);
}

.benefits-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    max-width: 1000px;
    margin: 0 auto;
}

.benefit-item {
    background: var(--light-gray);
    padding: 1.5rem;
    border-radius: 8px;
}

/* Mid-page CTA */
.mid-cta {
    padding: 4rem 2rem;
    background-color: var(--navy);
    text-align: center;
}

.mid-cta .btn {
    font-size: 1.1rem;
    padding: 1rem 2rem;
}

/* Gallery */
.gallery {
    padding: 5rem 2rem;
    background-color: var(--light-gray);
}

.gallery h2 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 3rem;
    color: var(--navy);
}

.gallery-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
    max-width: 1200px;
    margin: 0 auto;
}

.gallery-grid img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 8px;
}

/* Related Services */
.related-services {
    padding: 4rem 2rem;
    background-color: var(--white);
    text-align: center;
}

.related-services h2 {
    font-size: 1.5rem;
    margin-bottom: 2rem;
    color: var(--navy);
}

.related-grid {
    display: flex;
    gap: 1.5rem;
    justify-content: center;
    flex-wrap: wrap;
}

.related-grid a {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background: var(--light-gray);
    border-radius: 4px;
    color: var(--navy);
    font-weight: bold;
    transition: background 0.3s;
}

.related-grid a:hover {
    background: var(--blue);
    color: var(--white);
}

/* Responsive additions */
@media (min-width: 768px) {
    .process-steps {
        grid-template-columns: 1fr 1fr;
    }
    .benefits-grid {
        grid-template-columns: 1fr 1fr;
    }
    .gallery-grid {
        grid-template-columns: 1fr 1fr;
    }
}

@media (min-width: 1024px) {
    .process-steps {
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
    .benefits-grid {
        grid-template-columns: 1fr 1fr 1fr;
    }
    .gallery-grid {
        grid-template-columns: 1fr 1fr 1fr;
    }
}
```

### JavaScript for Service Pre-Selection

```javascript
// Add to each service page's <script> tag to pre-select the dropdown
document.addEventListener('DOMContentLoaded', function() {
    var serviceSelect = document.getElementById('service');
    if (serviceSelect) {
        serviceSelect.value = 'concrete-restoration'; // Change per page
    }
});
```

## State of the Art

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| External CSS files | Inline `<style>` per page | Project constraint | No build tools needed, but CSS duplicated across 7 files |
| jQuery for interactivity | Vanilla JS | Modern browsers | Zero dependencies, faster load |
| PHP templating | Static HTML files | Project constraint | No server needed, can deploy to any static host |
| Image sliders | Static CSS grid | D-06 decision | Better performance, no JS dependency |

**Deprecated/outdated:**
- Table-based layouts — use CSS Grid/Flexbox instead
- `<center>` tag — use CSS `text-align: center`
- Inline `style=""` attributes — use `<style>` block for maintainability

## Validation Architecture

### Test Framework

| Property | Value |
|----------|-------|
| Framework | Manual validation (static HTML site — no test runner) |
| Config file | none |
| Quick run command | `open index.html` in browser, check all pages visually |
| Full suite command | Visual inspection + Lighthouse audit |

### Phase Requirements → Test Map

| Req ID | Behavior | Test Type | Automated Command | File Exists? |
|--------|----------|-----------|-------------------|-------------|
| ARCH-03 | Unique URL, meta tags, keyword content per page | manual | Visual check + `grep -c "<title>" *.html` | ❌ Wave 0 |
| REST-01 | Concrete restoration page exists | manual | `ls concrete-restoration.html` | ❌ Wave 0 |
| REST-02 | Problem statement present | manual | `grep -c "spalling\|deterioration" concrete-restoration.html` | ❌ Wave 0 |
| REST-03 | Process steps present | manual | `grep -c "Assessment\|Preparation" concrete-restoration.html` | ❌ Wave 0 |
| REST-04 | Benefits section present | manual | `grep -c "Benefits" concrete-restoration.html` | ❌ Wave 0 |
| REST-05 | Gallery images present | manual | `grep -c "SWAP" concrete-restoration.html` | ❌ Wave 0 |
| REST-06 | CTA present | manual | `grep -c "consultation" concrete-restoration.html` | ❌ Wave 0 |
| WATR-01 through WATR-04 | Waterproofing page complete | manual | Same pattern as REST | ❌ Wave 0 |
| STUC-01 through STUC-04 | Stucco repair page complete | manual | Same pattern as REST | ❌ Wave 0 |
| COAT-01 through COAT-03 | Coatings page complete | manual | Same pattern as REST | ❌ Wave 0 |
| BALC-01 through BALC-03 | Balcony page complete | manual | Same pattern as REST | ❌ Wave 0 |
| PAIN-01 through PAIN-03 | Painting page complete | manual | Same pattern as REST | ❌ Wave 0 |

### Sampling Rate
- **Per task commit:** Visual check of the modified page in browser
- **Per wave merge:** Check all modified pages render correctly
- **Phase gate:** All 6 pages load, all nav links work, all forms functional

### Wave 0 Gaps
- [ ] No test framework exists — this is a static HTML site, testing is manual/visual
- [ ] Lighthouse can be run via `npx lighthouse <url>` if installed — verify availability

*(No automated test infrastructure needed for this project — all validation is visual/manual)*

## Security Domain

**SKIPPED** — This is a static HTML site with no server-side code, no authentication, no database, and no user input processing beyond a form that (in Phase 1) only shows a success message client-side. No ASVS categories apply to this phase.

## Environment Availability

| Dependency | Required By | Available | Version | Fallback |
|------------|------------|-----------|---------|----------|
| Web browser | Visual testing | ✓ | any | — |
| Text editor | HTML editing | ✓ | any | — |
| Lighthouse (optional) | Performance audit | ? | — | Manual visual check |

**Missing dependencies with no fallback:** None — this phase requires only a text editor and browser.

**Missing dependencies with fallback:**
- Lighthouse: optional for performance audit. Fallback: manual visual inspection.

## Assumptions Log

| # | Claim | Section | Risk if Wrong |
|---|-------|---------|---------------|
| A1 | index.html CSS can be copied identically to all 6 service pages | Standard Stack | Low — CSS is self-contained in `<style>` tag, no external dependencies |
| A2 | Unsplash images will load reliably as placeholders | Code Examples | Low — Unsplash CDN is highly available; Phase 5 swaps to real photos |
| A3 | The checkbox hamburger nav pattern from index.html works on all pages | Architecture Patterns | Low — proven pattern, already tested in Phase 1 |
| A4 | 6 service pages with inline CSS is maintainable at this scale | Standard Stack | Low — 7 total files is manageable; would need refactor at 20+ pages |

## Open Questions (RESOLVED)

1. **RESOLVED — Service dropdown pre-selection:** Each service page auto-selects its service in the form dropdown via JavaScript. Reduces friction for conversion (one less click). Plan Task 1 action includes JS pre-selection code.

2. **RESOLVED — Unsplash image selection:** Use construction-relevant Unsplash photos with appropriate keywords for each service category. Mark all with `<!-- SWAP: -->` comments for Phase 5 replacement. Exact photo IDs are Claude's discretion during execution.

## Sources

### Primary (HIGH confidence)
- `index.html` — Verified: complete homepage with established patterns (CSS variables, header/nav/footer, form, responsive breakpoints)
- `.planning/REQUIREMENTS.md` — Verified: 19 service page requirements (REST-01–06, WATR-01–04, STUC-01–04, COAT-01–03, BALC-01–03, PAIN-01–03, ARCH-03)
- `.planning/phases/02-service-landing-pages/02-CONTEXT.md` — Verified: 17 locked decisions for this phase

### Secondary (MEDIUM confidence)
- `bbconceptdesigns.com/luxury-condo-remodeling-in-miami/` — CITED: Reference site structure (H1 → problem/solution → process → benefits → gallery → CTA → contact)

### Tertiary (LOW confidence)
- None — all findings are based on verified project files and reference site

## Metadata

**Confidence breakdown:**
- Standard stack: HIGH — pure HTML/CSS/JS, no dependencies to verify
- Architecture: HIGH — single-file template pattern is straightforward
- Pitfalls: MEDIUM — common HTML copy-paste errors well-documented

**Research date:** 2026-06-20
**Valid until:** 2026-07-20 (stable — static HTML project, no fast-moving dependencies)

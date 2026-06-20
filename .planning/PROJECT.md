# Seacoast Construction — Concrete Restoration Website

## What This Is

A multi-page, SEO-optimized marketing website for Seacoast Construction, a Southeast Florida commercial exterior restoration contractor. The site targets "concrete restoration" as the primary keyword, with supporting pages for waterproofing, stucco repair, protective coatings, balcony restoration, and painting. Built to rank AND convert — every page is engineered for search visibility and lead generation.

## Core Value

Rank on page 1 for "concrete restoration south florida" and convert visitors into consultation requests through compelling service pages, social proof, and clear CTAs.

## Current State

**Shipped:** v1.0 MVP (2026-06-20)
**Deployed:** https://seacoast-construction.vercel.app
**Repo:** https://github.com/AP0XXY/seacoast-construction

- 7 HTML pages (homepage + 6 service pages)
- 404.html, sitemap.xml, robots.txt, vercel.json
- Formspree form handling
- GA4 analytics placeholder
- Lazy-loaded images, minified CSS (~41-44% reduction)
- GitHub + Vercel deployment

## Requirements

### Validated

- ✓ Hero section with concrete restoration as primary service offering — v1.0
- ✓ Dedicated service landing pages: Concrete Restoration, Waterproofing, Stucco Repair, Protective Coatings, Balcony Restoration, Painting — v1.0
- ✓ Each service page includes: problem/solution framing, process breakdown, benefits, before/after gallery, CTA — v1.0
- ✓ Company credentials, certifications, and trust signals (licensed, insured, OSHA, EPA) — v1.0
- ✓ Project portfolio with before/after comparisons — v1.0
- ✓ Contact/consultation request form (RFQ-style) — v1.0
- ✓ Mobile-responsive design with sticky CTA — v1.0
- ✓ SEO: meta tags, title tags, heading hierarchy, keyword placement per page — v1.0
- ✓ Local SEO: Southeast Florida service area, Google Business Profile ready — v1.0
- ✓ Page speed optimization (single HTML files, minimal dependencies) — v1.0
- ✓ Analytics-ready structure (Google Analytics placeholder) — v1.0

### Active

- [ ] Replace GA4 placeholder with real measurement ID
- [ ] Replace Formspree placeholder with real form ID
- [ ] Swap placeholder images with real project photos
- [ ] Run Lighthouse audit after deployment
- [ ] Add custom domain in Vercel dashboard

### Out of Scope

- Blog/content hub — defer to v2 (though site structure should support adding one)
- Online booking/scheduling — phone/form consultation only
- Payment processing — not applicable for B2B contracting
- CRM integration — connect form to email for now

## Context

- **Reference site:** BB Concept Designs (bbconceptdesigns.com) ranks for "luxury condo remodeling miami" via service-specific landing pages with keyword-rich content, before/after galleries, and process sections. We're replicating this SEO playbook for "concrete restoration."
- **Competitive landscape:** Capital Contractor Services (capitalserves.com) dominates commercial interior renovation in SE Florida but does NOT specifically target concrete restoration keywords — this is the gap.
- **Technology:** Single-file HTML pages with inline CSS. No frameworks, no build step. Fast, portable, easy to deploy anywhere.
- **Service market:** Southeast Florida (Miami-Dade, Broward, Palm Beach counties) — dense condo/hotel/coastal building market with high demand for exterior restoration.

## Constraints

- **Tech stack:** Pure HTML/CSS/JS — no React, no build tools, no dependencies
- **Performance:** Each page must score 90+ on Lighthouse — fast load, minimal assets
- **SEO:** Must be deployable to any static host with proper meta tags
- **Design:** Professional, credible — conveys 25+ years of experience and $2M+ insurance
- **Mobile:** Mobile-first responsive — many property managers browse on phones
- **Accessibility:** Semantic HTML, proper heading hierarchy, alt text on all images

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Concrete restoration as hero keyword | Highest commercial intent, least competition in SE Florida | ✓ Good |
| Multi-page site over single page | Each service page targets a specific keyword cluster for SEO | ✓ Good |
| Pure HTML/CSS (no framework) | Fast load, easy to deploy, no dependencies, SEO-friendly | ✓ Good |
| Service pages as lead generation | Each page has its own CTA driving to consultation form | ✓ Good |
| Stock images with swap capability | Launch fast with placeholder assets, user replaces with real projects | ✓ Good |
| GitHub + Vercel deployment | Free tier, instant deploys, git-based workflow | ✓ Good |
| Formspree for form handling | Works with static HTML, no backend needed | ✓ Good |
| GA4 only (no GTM) | Lightweight for static site, single script tag | ✓ Good |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd-transition`):
1. Requirements invalidated? → Move to Out of Scope with reason
2. Requirements validated? → Move to Validated with phase reference
3. New requirements emerged? → Add to Active
4. Decisions to log? → Add to Key Decisions
5. "What This Is" still accurate? → Update if drifted

**After each milestone** (via `/gsd:complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-06-20 after v1.0 milestone*

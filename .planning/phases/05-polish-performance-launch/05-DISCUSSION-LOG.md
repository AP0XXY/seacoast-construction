# Phase 5: Polish, Performance & Launch - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-06-20
**Phase:** 5-Polish, Performance & Launch
**Areas discussed:** Hosting Platform, Form Backend, Analytics, 404 Page, Lighthouse Targets

---

## Hosting Platform

| Option | Description | Selected |
|--------|-------------|----------|
| Netlify | Free tier, form handling, instant deploys, custom domain | ✓ |
| GitHub Pages | Free, simple, no form handling | |
| Vercel | Free tier, but overkill for static HTML | |

**Auto choice:** Netlify (Recommended — free tier, form handling built-in, matches single-file HTML constraint)

---

## Form Submission Backend

| Option | Description | Selected |
|--------|-------------|----------|
| Netlify Forms | Zero-backend, spam filtering, email notifications | ✓ |
| Formspree | Third-party form service, free tier available | |
| Custom backend | Requires server setup, overkill for this site | |

**Auto choice:** Netlify Forms (Recommended — zero-backend, handles spam filtering, sends email notifications)

---

## Analytics Setup

| Option | Description | Selected |
|--------|-------------|----------|
| GA4 only | Lightweight, single script tag | ✓ |
| GTM only | Tag manager, more flexibility but heavier | |
| Both GA4 + GTM | Maximum tracking, but unnecessary overhead | |

**Auto choice:** Google Analytics 4 only (Recommended — lightweight, no tag manager overhead for a static site)

---

## 404 Page

| Option | Description | Selected |
|--------|-------------|----------|
| Custom 404.html | Shows nav and contact info, keeps visitors on-site | ✓ |
| Simple redirect to homepage | Quick but poor UX | |
| No 404 handling | Bad UX, lost visitors | |

**Auto choice:** Custom 404 page (Recommended — shows navigation and contact info, keeps visitors on-site)

---

## Lighthouse Targets

| Option | Description | Selected |
|--------|-------------|----------|
| All four at 90+ | Performance, Accessibility, Best Practices, SEO | ✓ |
| Performance + SEO only | Narrower scope | |
| Just performance | Misses accessibility and best practices | |

**Auto choice:** All four at 90+ (Recommended — Phase 5 success criteria already requires this)

---

## Claude's Discretion

- Specific Lighthouse optimization techniques (image compression, CSS minification)
- 404 page exact layout and copy
- robots.txt disallow rules
- Order of implementation across pages
- Whether to add favicon.ico

## Deferred Ideas

None

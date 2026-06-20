# Phase 5: Polish, Performance & Launch

**Created:** 2026-06-20
**Status:** Ready to execute

---

## Wave 1: Create Root Infrastructure Files

### Task 1.1: Create netlify.toml

**read_first:**
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-01, D-02)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §3 (Netlify config)

**acceptance_criteria:**
- File exists at `/Users/rukiverr/netlify.toml`
- Contains `[build]` section with `publish = "."`
- Contains security headers (X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
- Contains cache-control headers for HTML and assets
- Contains www-to-apex redirect

**action:**
Create `netlify.toml` with this exact content:

```toml
[build]
  publish = "."

# Security headers for all pages
[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
    Permissions-Policy = "camera=(), microphone=(), geolocation=()"

# HTML pages — always revalidate
[[headers]]
  for = "*.html"
  [headers.values]
    Cache-Control = "public, max-age=0, must-revalidate"

# Static assets — aggressive cache
[[headers]]
  for = "/assets/*"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"

# Redirect www to apex
[[redirects]]
  from = "https://www.seacoastconstruction.com/*"
  to = "https://seacoastconstruction.com/:splat"
  status = 301
  force = true
```

---

### Task 1.2: Create sitemap.xml

**read_first:**
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §6
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-15)

**acceptance_criteria:**
- File exists at `/Users/rukiverr/sitemap.xml`
- Contains all 7 HTML pages (NOT 404.html)
- Valid XML with `xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"`
- Homepage has priority 1.0, concrete-restoration has 0.9, others have 0.8
- All URLs use `https://seacoastconstruction.com/` base

**action:**
Create `sitemap.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://seacoastconstruction.com/</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/concrete-restoration.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/waterproofing.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/stucco-repair.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/protective-coatings.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/balcony-restoration.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://seacoastconstruction.com/painting.html</loc>
    <lastmod>2026-06-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

---

### Task 1.3: Create robots.txt

**read_first:**
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §6
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-16)

**acceptance_criteria:**
- File exists at `/Users/rukiverr/robots.txt`
- Contains `User-agent: *` and `Allow: /`
- Contains `Sitemap: https://seacoastconstruction.com/sitemap.xml`

**action:**
Create `robots.txt`:

```
User-agent: *
Allow: /

Sitemap: https://seacoastconstruction.com/sitemap.xml
```

---

### Task 1.4: Create 404.html

**read_first:**
- `/Users/rukiverr/index.html` (read header/nav/footer HTML structure, CSS patterns)
- `/Users/rukiverr/.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-09, D-10, D-11)
- `/Users/rukiverr/.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §5

**acceptance_criteria:**
- File exists at `/Users/rukiverr/404.html`
- Has same `<!DOCTYPE html>`, `<head>` structure, viewport meta as other pages
- `<title>Page Not Found | Seacoast Construction</title>`
- `<meta name="robots" content="noindex">`
- Contains identical header/nav with all 7 nav links + phone number + CTA button
- Contains `<h1>Page Not Found</h1>` as the only H1
- Contains "Return to Homepage" button linking to `/`
- Contains "Call (561) 555-0192" button linking to `tel:+15615550192`
- Contains "Popular Pages" section with links to concrete-restoration.html, waterproofing.html, stucco-repair.html, and `/#contact`
- Contains identical footer as other pages (3-column footer with company info, services, contact)
- GA4 placeholder script in `<head>` (same as other pages)
- Inline CSS matches site design (--navy, --blue, --white variables, same font, same header/footer styles)

**action:**
Create `404.html` that is a complete standalone HTML file. Copy the full header/nav structure from `index.html` (lines 710-730), the full footer from `index.html` (lines 983-1010), and the full inline CSS from `index.html` (lines 33-707). Replace the body content between header and footer with:

```html
<section class="error-404">
    <div class="container">
        <h1>Page Not Found</h1>
        <p>Sorry, the page you're looking for doesn't exist or has been moved.</p>
        <div class="error-actions">
            <a href="/" class="btn btn-primary">Return to Homepage</a>
            <a href="tel:+15615550192" class="btn btn-secondary">Call (561) 555-0192</a>
        </div>
        <div class="error-links">
            <h3>Popular Pages</h3>
            <ul>
                <li><a href="concrete-restoration.html">Concrete Restoration</a></li>
                <li><a href="waterproofing.html">Waterproofing</a></li>
                <li><a href="stucco-repair.html">Stucco Repair</a></li>
                <li><a href="/#contact">Request Consultation</a></li>
            </ul>
        </div>
    </div>
</section>
```

Add this CSS to the `<style>` block (before `</style>`):

```css
.error-404 {
    padding: 6rem 2rem;
    text-align: center;
    background-color: var(--light-gray);
}
.error-404 h1 {
    font-size: 4rem;
    color: var(--navy);
    margin-bottom: 1rem;
}
.error-404 p {
    font-size: 1.2rem;
    color: #666;
    max-width: 600px;
    margin: 0 auto 2rem;
}
.error-actions {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3rem;
}
.error-links {
    max-width: 400px;
    margin: 0 auto;
}
.error-links h3 {
    color: var(--navy);
    margin-bottom: 1rem;
}
.error-links ul {
    list-style: none;
}
.error-links li {
    margin-bottom: 0.5rem;
}
.error-links a {
    color: var(--blue);
    font-weight: bold;
}
```

---

## Wave 2: Optimize All 7 HTML Pages

All 7 pages need the same 4 categories of changes. Each task below applies to ALL pages. Execute these edits page-by-page (one full pass per file) to avoid repeated reads.

### Task 2.1: Migrate Forms to Netlify Forms (all 7 pages)

**read_first:**
- `/Users/rukiverr/index.html` lines 936-974 (form structure), lines 1012-1018 (JS)
- `/Users/rukiverr/concrete-restoration.html` lines 707-744 (form), lines 783-794 (JS)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §3 (form migration)
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-03, D-04, D-05)

**acceptance_criteria (per page):**
- `<form>` tag has `name="consultation"` attribute
- `<form>` tag has `method="POST"` attribute
- `<form>` tag has `data-netlify="true"` attribute
- `<form>` tag has `netlify-honeypot="bot-field"` attribute
- `<form>` tag NO LONGER has `onsubmit="handleSubmit(event)"`
- Hidden `<input type="hidden" name="form-name" value="consultation">` is first child of form
- Honeypot `<p>` with `name="bot-field"` input exists (hidden with `display:none`)
- `<script>` block no longer contains `e.preventDefault()` — replaced with fetch-based submission that shows inline success message

**action:**
For each of the 7 HTML files, make these edits:

**Edit A — Form tag (in the `<section id="contact">` section):**
Replace:
```html
<form id="consultation-form" onsubmit="handleSubmit(event)">
```
With:
```html
<form id="consultation-form" name="consultation" method="POST" data-netlify="true" netlify-honeypot="bot-field">
    <input type="hidden" name="form-name" value="consultation">
    <p style="display:none">
        <label>Don't fill this out: <input name="bot-field"></label>
    </p>
```

**Edit B — JavaScript (at the bottom, inside `<script>` tags):**
Replace the entire `<script>` block. For `index.html`, replace:
```javascript
<script>
    function handleSubmit(e) {
        e.preventDefault();
        document.getElementById('consultation-form').style.display = 'none';
        document.getElementById('form-success').style.display = 'block';
    }
</script>
```
With:
```javascript
<script>
    document.getElementById('consultation-form').addEventListener('submit', function(e) {
        e.preventDefault();
        var form = e.target;
        var data = new FormData(form);
        fetch('/', {
            method: 'POST',
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams(data).toString()
        }).then(function() {
            form.style.display = 'none';
            document.getElementById('form-success').style.display = 'block';
        }).catch(function() {
            form.style.display = 'none';
            document.getElementById('form-success').style.display = 'block';
        });
    });
</script>
```

For the 6 service pages (`concrete-restoration.html`, `waterproofing.html`, `stucco-repair.html`, `protective-coatings.html`, `balcony-restoration.html`, `painting.html`), the existing script has extra code after handleSubmit. Replace the entire `<script>` block. For example in `concrete-restoration.html`, replace:
```javascript
<script>
    function handleSubmit(e) {
        e.preventDefault();
        document.getElementById('consultation-form').style.display = 'none';
        document.getElementById('form-success').style.display = 'block';
    }
    document.addEventListener('DOMContentLoaded', function() {
        var serviceSelect = document.getElementById('service');
        if (serviceSelect) {
            serviceSelect.value = 'concrete-restoration';
        }
    });
</script>
```
With:
```javascript
<script>
    document.getElementById('consultation-form').addEventListener('submit', function(e) {
        e.preventDefault();
        var form = e.target;
        var data = new FormData(form);
        fetch('/', {
            method: 'POST',
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: new URLSearchParams(data).toString()
        }).then(function() {
            form.style.display = 'none';
            document.getElementById('form-success').style.display = 'block';
        }).catch(function() {
            form.style.display = 'none';
            document.getElementById('form-success').style.display = 'block';
        });
    });
    document.addEventListener('DOMContentLoaded', function() {
        var serviceSelect = document.getElementById('service');
        if (serviceSelect) {
            serviceSelect.value = 'REPLACE-WITH-SERVICE-SLUG';
        }
    });
</script>
```
Where `REPLACE-WITH-SERVICE-SLUG` is: `concrete-restoration`, `waterproofing`, `stucco-repair`, `protective-coatings`, `balcony-restoration`, `painting` respectively.

---

### Task 2.2: Add GA4 Analytics to All 7 Pages

**read_first:**
- `/Users/rukiverr/index.html` lines 1-8 (head section)
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-06, D-07, D-08)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §4

**acceptance_criteria (per page):**
- GA4 script tag exists in `<head>` section, after `</script>` closing tag of schema markup and before `<style>` tag
- Script uses placeholder `G-XXXXXXXXXX` measurement ID
- Script includes async gtag.js loader and config call

**action:**
For each of the 7 HTML files, insert this block in `<head>` after the closing `</script>` of the schema markup and BEFORE the `<style>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Insertion point for each file:
- `index.html`: after line 31 (`</script>` closing schema), before line 33 (`<style>`)
- `concrete-restoration.html`: after line 22 (`</script>` closing schema), before line 24 (`<style>`)
- `waterproofing.html`: after line 22, before line 24
- `stucco-repair.html`: after line 22, before line 24
- `protective-coatings.html`: after line 22, before line 24
- `balcony-restoration.html`: after line 22, before line 24
- `painting.html`: after line 22, before line 24

---

### Task 2.3: Optimize Images — Lazy Loading & Dimensions (all 7 pages)

**read_first:**
- `/Users/rukiverr/index.html` lines 749-760 (service card img examples)
- `/Users/rukiverr/concrete-restoration.html` lines 640-690 (gallery img examples)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §2 (image optimization)

**acceptance_criteria (per page):**
- Every `<img>` tag has `loading="lazy"` attribute
- Every `<img>` tag has `width` and `height` attributes matching the Unsplash URL params
- Every `<img>` tag has `decoding="async"` attribute
- Hero background images in CSS are NOT modified (they're above-fold, CSS backgrounds can't be lazy-loaded)
- All `<!-- SWAP: real photo -->` comments preserved

**action:**
For each of the 7 HTML files, add `loading="lazy" decoding="async" width="W" height="H"` to every `<img>` tag.

**Pattern for service card images (index.html, lines ~749-810):**
Replace:
```html
<img src="https://images.unsplash.com/photo-1581094794329-c8112c4e5190?w=600&h=400&fit=crop" alt="Concrete restoration work on commercial building">
```
With:
```html
<img src="https://images.unsplash.com/photo-1581094794329-c8112c4e5190?w=600&h=400&fit=crop" alt="Concrete restoration work on commercial building" loading="lazy" decoding="async" width="600" height="400">
```

**Pattern for portfolio images (index.html, lines ~820-880):**
Same transformation — add `loading="lazy" decoding="async" width="W" height="H"`.

**Pattern for gallery images (service pages, lines ~640-690):**
Replace:
```html
<img src="https://images.unsplash.com/photo-XXX?w=800&h=500&fit=crop" alt="...">
```
With:
```html
<img src="https://images.unsplash.com/photo-XXX?w=800&h=500&fit=crop" alt="..." loading="lazy" decoding="async" width="800" height="500">
```

**Key rule:** Extract `w=` and `h=` values from the Unsplash URL and use them as the `width` and `height` attribute values. Do NOT lazy-load the hero background (it's a CSS `background-image`, not an `<img>` tag).

**Files and approximate img counts:**
- `index.html`: ~10 img tags (6 service cards + 3 portfolio + 1 other)
- `concrete-restoration.html`: ~5 img tags (1 hero-related + 4 gallery)
- `waterproofing.html`: ~5 img tags
- `stucco-repair.html`: ~5 img tags
- `protective-coatings.html`: ~5 img tags
- `balcony-restoration.html`: ~5 img tags
- `painting.html`: ~5 img tags

---

### Task 2.4: CSS Minification (all 7 pages)

**read_first:**
- `/Users/rukiverr/index.html` lines 33-707 (full CSS block)
- `/Users/rukiverr/concrete-restoration.html` lines 24-500 (full CSS block)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §2B

**acceptance_criteria (per page):**
- CSS comments removed (except `<!-- SWAP -->` HTML comments which are outside `<style>`)
- Leading/trailing whitespace inside CSS rules removed
- Blank lines between rules removed
- CSS still renders correctly (no syntax errors introduced)

**action:**
For each of the 7 HTML files, minify the CSS inside the `<style>` tag:

1. Remove all CSS comments (lines starting with `/*`)
2. Remove blank lines between CSS rules
3. Collapse multiple spaces to single spaces
4. Remove spaces after `{` and before `}`
5. Remove spaces around `:` in property declarations (keep space after colon for readability)

**Example transformation:**
Before:
```css
/* Header */
header {
    position: sticky;
    top: 0;
    z-index: 1000;
    background-color: var(--navy);
    color: var(--white);
    padding: 1rem 2rem;
}
```
After:
```css
header{position:sticky;top:0;z-index:1000;background-color:var(--navy);color:var(--white);padding:1rem 2rem}
```

**Important:** Do NOT minify the `:root` variables block — keep custom properties readable. Focus on removing comments and collapsing whitespace. The goal is ~30-40% CSS size reduction without breaking anything.

---

## Wave 3: Validation

### Task 3.1: SEO Audit — Title Tags, Meta Descriptions, Headings, Schema

**read_first:**
- All 7 HTML files (check `<title>`, `<meta name="description">`, `<h1>`, heading hierarchy, `<script type="application/ld+json">`)
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-17)

**acceptance_criteria:**
- Every page has `<title>` under 60 characters
- Every page has `<meta name="description">` under 160 characters
- Every page has exactly ONE `<h1>` tag
- Heading hierarchy is H1 → H2 → H3 (no skipped levels)
- `index.html` has LocalBusiness/ConcreteContractor schema
- All 6 service pages have Service schema
- All `<img>` tags have descriptive `alt` text

**action:**
Read each HTML file and verify all SEO elements. Fix any issues found:
- If a title exceeds 60 chars, shorten it
- If a meta description exceeds 160 chars, shorten it
- If any page has multiple H1s, change extras to H2
- If heading hierarchy skips levels, fix nesting
- If schema is missing or malformed, fix it

---

### Task 3.2: Image Placeholder Audit

**read_first:**
- All 7 HTML files
- `.planning/phases/05-polish-performance-launch/05-CONTEXT.md` (D-18, D-19)

**acceptance_criteria:**
- Every `<img>` tag has a `<!-- SWAP: real photo -->` comment immediately after it
- Every CSS `background-image: url(...)` has a `<!-- SWAP: real photo -->` comment nearby
- No Unsplash images are missing the SWAP comment
- Count matches: index.html=10, each service page=5

**action:**
Search all 7 HTML files for `<img` tags and verify each has a `<!-- SWAP` comment on the next line. Search CSS for `url('https://images.unsplash.com` and verify SWAP comments exist. Add any missing SWAP comments.

---

### Task 3.3: Mobile-Friendly Validation

**read_first:**
- All 7 HTML files (check viewport meta, responsive CSS, tap targets)
- `.planning/phases/05-polish-performance-launch/05-RESEARCH.md` §8

**acceptance_criteria:**
- Every page has `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- All interactive elements (buttons, links) have minimum 44px tap targets
- Form inputs have `min-height` of at least 44px
- No horizontal overflow at any breakpoint
- Font sizes readable on mobile (minimum 16px base)

**action:**
Verify viewport meta exists on all pages. Check CSS for tap target sizes. If any buttons or links are too small, add `min-height: 44px; min-width: 44px` or adjust padding. Verify form inputs have adequate touch targets.

---

## must_haves

Goal-backward verification — these MUST be true when Phase 5 is complete:

1. `netlify.toml` exists at project root with build config, security headers, and redirects
2. `sitemap.xml` exists with all 7 page URLs (no 404)
3. `robots.txt` exists with Allow: / and sitemap reference
4. `404.html` exists with site header/nav, "Page Not Found" heading, homepage link, phone link, popular pages, and footer
5. All 7 HTML forms have `data-netlify="true"`, honeypot field, and no `onsubmit="handleSubmit(event)"`
6. All 7 HTML forms submit via fetch to Netlify with inline success message
7. GA4 placeholder script (`G-XXXXXXXXXX`) present in `<head>` of all 7 HTML files
8. All `<img>` tags have `loading="lazy"`, `decoding="async"`, `width`, `height` attributes
9. All `<img>` tags have `<!-- SWAP: ... -->` comments
10. CSS in all 7 files is minified (comments removed, whitespace collapsed)
11. All title tags under 60 chars, meta descriptions under 160 chars
12. Every page has exactly one H1, proper heading hierarchy
13. Schema markup present on all pages (LocalBusiness on homepage, Service on service pages)

---

## Verification

After executing all tasks:

1. **File check:** Verify all 4 new root files exist (netlify.toml, sitemap.xml, robots.txt, 404.html)
2. **Form check:** Grep all 7 HTML files for `data-netlify="true"` — should match 7 times
3. **Form check:** Grep all 7 HTML files for `onsubmit` — should match 0 times
4. **GA4 check:** Grep all 7 HTML files for `G-XXXXXXXXXX` — should match 14 times (2 per file)
5. **Image check:** Grep all 7 HTML files for `loading="lazy"` — count should match total img tags
6. **Image check:** Grep all 7 HTML files for `<!-- SWAP` — count should match total img tags
7. **SEO check:** Verify each `<title>` tag length < 60 chars
8. **SEO check:** Verify each `<meta name="description">` length < 160 chars
9. **Schema check:** Verify LocalBusiness schema in index.html, Service schema in all 6 service pages
10. **404 check:** Verify 404.html has header, nav, h1, homepage link, phone link, footer

---

*Plan created: 2026-06-20*

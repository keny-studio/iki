## $${\color{red}SEO \ Cheat \ Sheet}$$

SEO - Search Engine Optimization - practice of optimizing a website’s structure, content, performance, and authority to improve its visibility in organic (non-paid) search engine results.

🎯 SEO goal is to increase:
- Organic traffic
- Rankings for relevant queries
- Click-through rate (CTR)
- Conversions

🧩 Core Areas

- Technical SEO - Crawlability, indexability, site architecture, performance, structured data.

- On-Page SEO - Content quality, keyword targeting, headings, internal linking, metadata.

- Off-Page SEO - Backlinks, brand authority, external signals.

- UX & Performance - Core Web Vitals, mobile usability, accessibility.

---

## SEO Checklist 

* Page returns 200
* HTTPS enabled
* Canonical correct
* One H1
* Title optimized
* Meta description present
* Structured data valid
* Core Web Vitals optimized
* XML sitemap updated
* Robots.txt correct
* No broken internal links
* Mobile-friendly

---

## 1️⃣ Core Technical Foundations

### ✅ HTTP Status Codes

* `200` – OK
* `301` – Permanent redirect (preserves SEO value)
* `302` – Temporary redirect
* `404` – Not found
* `410` – Gone (better than 404 for removed content)
* `503` – Maintenance (temporary downtime)

**Rule:** Avoid 302 for permanent changes. Use 301.

---

### ✅ Canonicalization

```html
<link rel="canonical" href="https://example.com/page/" />
```

Prevents duplicate content issues.

Use when:

* Pagination
* Query parameters
* Sorting/filter URLs
* HTTP vs HTTPS
* www vs non-www

---

### ✅ Robots.txt

```
User-agent: *
Disallow: /admin/
Allow: /
Sitemap: https://example.com/sitemap.xml
```

Blocks crawling, NOT indexing.

---

### ✅ Meta Robots

```html
<meta name="robots" content="noindex, nofollow">
```

Options:

* `index`
* `noindex`
* `follow`
* `nofollow`
* `noarchive`
* `nosnippet`

---

### ✅ XML Sitemap

* Must return `200`
* UTF-8 encoded
* < 50MB
* < 50,000 URLs per file
* Submit to Google Search Console

---

## 2️⃣ On-Page SEO Essentials

### ✅ Title Tag

```html
<title>Primary Keyword – Secondary Keyword | Brand</title>
```

* 50–60 characters
* Unique per page

---

### ✅ Meta Description

```html
<meta name="description" content="Compelling summary for CTR.">
```

* 150–160 characters
* Impacts CTR, not ranking

---

### ✅ Headings Structure

```html
<h1>Main Topic</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

Rules:

* One H1 per page
* Hierarchical structure
* No skipping levels

---

### ✅ Clean URLs

Good:

```
/seo-cheatsheet/
```

Bad:

```
/index.php?id=123&cat=9
```

---

## 3️⃣ Performance & Core Web Vitals

### 🚀 Core Metrics

* **LCP** – Largest Contentful Paint (<2.5s)
* **CLS** – Cumulative Layout Shift (<0.1)
* **INP** – Interaction to Next Paint (<200ms)

---

### ⚡ Performance Best Practices

* Use HTTP/2 or HTTP/3
* Enable compression (Brotli > Gzip)
* Minify CSS/JS
* Use CDN
* Lazy load images
* Preload critical assets

```html
<link rel="preload" as="image" href="hero.webp">
```

---

## 4️⃣ Structured Data (Schema.org)

Use JSON-LD:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "SEO Cheat Sheet",
  "author": {
    "@type": "Person",
    "name": "John Doe"
  }
}
</script>
```

Common Types:

* Article
* Product
* FAQPage
* BreadcrumbList
* Organization

Test:

* Google Rich Results Test

---

## 5️⃣ JavaScript SEO

### ⚠️ Key Rules

* Server-Side Rendering (SSR) preferred
* Avoid client-only rendering for core content
* Ensure crawlable links:

Bad:

```html
<div onclick="location.href='/page'">
```

Good:

```html
<a href="/page">Link</a>
```

* Avoid hash routing:

```
/page#section
```

---

## 6️⃣ Mobile SEO

* Responsive design (not m.example.com)
* Viewport meta:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* No intrusive popups

---

## 7️⃣ Security & Indexing

* HTTPS required
* HSTS enabled
* No mixed content
* Avoid orphan pages
* Internal linking strategy

---

## 8️⃣ Internal Linking Rules

* Descriptive anchor text
* Avoid "click here"
* Keep crawl depth < 3 clicks
* Fix broken links regularly

---

## 9️⃣ Log File & Crawl Budget Basics

Check:

* Crawl frequency
* Status codes
* Bot user agents
* Wasted crawl (404s, params)

Large sites:

* Manage faceted navigation
* Block infinite filters


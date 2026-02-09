## $${\color{red}Website \ Migration \ Cheat \ Sheet}$$

## 1️⃣ Pre-Migration

### 📋 Audit & Inventory

* [ ] Current URLs (crawl with Screaming Frog / Sitebulb)
* [ ] Page types (static, dynamic, CMS, ecommerce)
* [ ] Media assets (images, videos, PDFs)
* [ ] Forms & integrations (CRM, email, payments)
* [ ] Third-party scripts (analytics, ads, chat)
* [ ] SEO data (meta titles, descriptions, H1s)
* [ ] Redirect rules already in place

### 🧠 Migration Type

* ☐ Domain change
* ☐ Hosting change
* ☐ CMS change (e.g. custom → WordPress)
* ☐ Framework rewrite (PHP → JS / React / Next)
* ☐ HTTP → HTTPS
* ☐ URL structure change

---

## 2️⃣ Backups (Non-Negotiable)

* [ ] Full **database dump**
* [ ] Full **files backup**
* [ ] Server config (NGINX / Apache / `.htaccess`)
* [ ] Environment variables
* [ ] DNS records (A, AAAA, CNAME, MX, TXT)

```bash
mysqldump -u user -p db_name > backup.sql
tar -czf site_files.tar.gz public_html/
```

---

## 3️⃣ Environment Setup

### 🧪 Staging / Dev

* [ ] Separate staging domain or subdomain
* [ ] Password protected / noindex
* [ ] Same PHP / Node / DB versions as prod
* [ ] Same folder structure

```html
<meta name="robots" content="noindex,nofollow">
```

---

## 4️⃣ URL Mapping & Redirects (SEO Lifeline)

### 🔀 Redirect Rules

* [ ] Create **old → new URL mapping**
* [ ] Prefer **301 redirects**
* [ ] Avoid redirect chains (301 → 301 → 200 ❌)
* [ ] Handle trailing slashes, case sensitivity

#### Apache

```apache
Redirect 301 /old-page https://example.com/new-page
```

#### NGINX

```nginx
rewrite ^/old-page$ https://example.com/new-page permanent;
```

---

## 5️⃣ Content & Data Migration

### 🧱 Content

* [ ] Pages & posts
* [ ] Custom post types
* [ ] Taxonomies / categories / tags
* [ ] Slugs preserved
* [ ] Internal links updated

### 🗄️ Data

* [ ] Users & roles
* [ ] Orders / customers (ecommerce)
* [ ] Comments / reviews
* [ ] Media paths verified

---

## 6️⃣ SEO Checklist (Don’t Nuke Rankings)

* [ ] Titles & meta descriptions preserved
* [ ] Canonical URLs correct
* [ ] H1–H6 structure intact
* [ ] Alt attributes on images
* [ ] XML sitemap regenerated
* [ ] Robots.txt verified

```txt
User-agent: *
Disallow:
Sitemap: https://example.com/sitemap.xml
```

---

## 7️⃣ Performance & Frontend

* [ ] Page load times compared (before vs after)
* [ ] Images optimized
* [ ] CSS / JS minified
* [ ] Cache headers working
* [ ] CDN configured (if used)

```bash
curl -I https://example.com
```

---

## 8️⃣ Forms, Auth & Integrations

* [ ] Contact forms submit correctly
* [ ] Emails sent & received
* [ ] OAuth / login works
* [ ] Payment gateways tested
* [ ] Webhooks firing

---

## 9️⃣ Analytics & Tracking

* [ ] GA / GA4 installed
* [ ] Google Tag Manager working
* [ ] Conversion events firing
* [ ] Search Console verified (new domain if needed)
* [ ] Old Search Console kept for monitoring

---

## 🔟 DNS & Go-Live

### 🌍 DNS

* [ ] TTL lowered before migration
* [ ] A / AAAA records updated
* [ ] SSL certificate valid
* [ ] HTTPS forced

```bash
dig example.com
```

### 🚀 Launch

* [ ] Remove noindex
* [ ] Remove auth from staging
* [ ] Clear caches
* [ ] Smoke test critical paths

---

## 1️⃣1️⃣ Post-Migration Monitoring

### 🔍 First 24–72h

* [ ] 404 errors
* [ ] Redirect accuracy
* [ ] Server error logs
* [ ] Search Console coverage
* [ ] Analytics traffic anomalies

```bash
tail -f /var/log/nginx/error.log
```

---

## 1️⃣2️⃣ Rollback Plan 

* [ ] Old site still accessible
* [ ] DNS rollback documented
* [ ] Backup restore tested
* [ ] Emergency contact list ready

---

## 🧠 Pro Tips

* Migrate **mid-week**, not Friday 🙃
* Freeze content during migration window
* Keep redirects **at least 12 months**
* Document everything — future you will thank you

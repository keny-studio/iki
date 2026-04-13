## $${\color{red}Website \ Audit \ Cheat \ Sheet}$$

from designer and developer point of view


**(Strategy → UX → Dev → SEO → Performance → Conversion)**

---

### 🎯 1. STRATEGY (FOUNDATION FIRST)

**Goal: Align website with business outcomes**

#### ✅ What to Check

* Clear primary goal (sales / leads / traffic)
* Strong value proposition above the fold
* Clear CTA hierarchy (primary vs secondary)
* Each page has a single purpose
* Funnel logic (TOFU → MOFU → BOFU) is visible

#### ⚡ How to Audit

1. Open homepage (first 5 seconds):

   * What is this?
   * Who is it for?
   * What should I do?
2. Map pages to funnel stages:

   * Blog → TOFU
   * Case study → MOFU
   * Landing page → BOFU
3. Remove mixed-intent pages

---

### 🎨 2. UI DESIGN AUDIT

**Goal: Visual clarity + consistency**

#### ✅ Checklist

* Clear visual hierarchy (headings, sections)
* Consistent spacing system (8pt grid)
* Typography readable (≥16px, good line-height)
* Max 2–3 font families
* Consistent button styles
* Consistent color system
* High contrast (WCAG)
* Visual consistency across pages

#### ⚡ How to Audit

* Blur test (does structure still make sense?)
* Compare pages side-by-side
* Identify inconsistent components → unify into design system

---

### ⚙️ 3. UX / USABILITY AUDIT

**Goal: Reduce friction, improve flow**

#### ✅ Checklist

* Navigation simple (≤7 items)
* Logical menu structure
* ≤3 clicks to key pages
* Clear CTA in each section
* No dead ends
* Forms short + simple
* Inline validation
* Helpful error messages

#### ⚡ How to Audit

1. Perform key task (e.g. “buy / contact”)
2. Track friction points:

   * Confusion
   * Extra steps
3. Fix:

   * Navigation
   * CTA placement
   * Form UX

---

### 📱 4. MOBILE / RESPONSIVE AUDIT

**Goal: Perfect mobile experience**

#### ✅ Checklist

* Fully responsive layout
* No horizontal scroll
* Tap targets ≥48px
* Mobile-friendly navigation
* Readable text (no zoom)
* Proper image scaling

#### ⚡ How to Audit

* Test on real phone + DevTools
* Thumb test (can you use with one hand?)

---

### 🚀 5. PERFORMANCE AUDIT

**Goal: Speed = rankings + conversions**

#### ✅ Checklist

* Load time < 3s
* LCP < 2.5s
* CLS < 0.1
* Images optimized (WebP/AVIF)
* Lazy loading enabled
* CSS/JS minified
* Unused code removed
* Fonts optimized

#### ⚡ How to Audit

1. Run Lighthouse / PageSpeed
2. Fix biggest issues first:

   * Images
   * JS blocking
   * Fonts

---

### 💻 6. DEVELOPMENT AUDIT

**Goal: Clean, scalable, maintainable code**

#### ✅ Checklist

* Semantic HTML
* No console errors
* Modular code
* No excessive inline styles
* Accessibility attributes
* Cross-browser tested

#### ⚡ How to Audit

* Inspect DOM structure
* Check console
* Review CSS/JS structure

---

### 🔐 7. SECURITY AUDIT

**Goal: Protect site + users**

#### ✅ Checklist

* HTTPS enabled
* Input validation & sanitization
* XSS / CSRF protection
* CMS/plugins updated
* Backup system active

#### ⚡ How to Audit

* Run vulnerability scan
* Test forms manually
* Verify backups

---

### 🔍 8. SEO AUDIT (TECHNICAL + ON-PAGE)

#### ✅ Checklist

* Unique meta titles/descriptions
* Proper heading structure (H1–H6)
* sitemap.xml exists
* robots.txt configured
* Canonical tags set
* Internal linking
* Alt text on images
* No duplicate content

#### ⚡ How to Audit

1. Crawl site (Screaming Frog)
2. Fix:

   * Missing tags
   * Duplicate pages
   * Broken links

---

### ♿ 9. ACCESSIBILITY (WCAG)

#### ✅ Checklist

* Keyboard navigation works
* Visible focus states
* Alt text for images
* Labels for inputs
* Proper contrast
* No autoplay with sound

#### ⚡ How to Audit

* Tab through entire site
* Run WAVE / Axe
* Fix manual issues

---

### 📊 10. ANALYTICS AUDIT

#### ✅ Checklist

* GA4 installed
* Events tracked (clicks, forms)
* Conversion goals set
* No duplicate tracking
* Cookie consent implemented

#### ⚡ How to Audit

* Use DebugView (GA4)
* Trigger events manually
* Verify conversions

---

### ✍️ 11. CONTENT AUDIT

#### ✅ Checklist

* Benefit-driven headlines
* No placeholder text
* Grammar + consistency
* Strong CTAs (“Get Quote”)
* Matches user intent

#### ⚡ How to Audit

* Compare with top competitors
* Remove fluff
* Improve clarity

---

### 🧩 12. CMS (WORDPRESS, ETC.)

#### ✅ Checklist

* Lightweight theme
* Minimal plugins
* SEO plugin configured
* Security plugin active
* Regular backups

#### ⚡ How to Audit

* List all plugins → remove unnecessary
* Check performance impact

---

### 🧠 13. CRO (CONVERSION RATE OPTIMIZATION)

#### ✅ What to Check

* CTA placement & clarity
* Funnel drop-offs
* Trust signals
* Landing page focus

#### ⚡ How to Audit

1. Analyze funnel (Analytics)
2. Identify drop-offs
3. A/B test:

   * Headlines
   * CTAs
   * Layout

---

### 🔗 14. OFF-PAGE / BACKLINK AUDIT

#### ✅ What to Check

* Backlink quality
* Toxic links
* Anchor text

#### ⚡ How to Audit

* Use Ahrefs / SEMrush
* Disavow spam links

---

### 🧪 QUICK AUDIT FLOW (YOUR + IMPROVED)

#### ⏱ 50–60 MIN RAPID AUDIT

1. **First impression (5 min)**
2. **Strategy + messaging (5 min)**
3. **Key pages UX/UI (10 min)**
4. **Mobile check (10 min)**
5. **Performance + SEO scan (10 min)**
6. **Technical + dev check (10 min)**
7. **Final notes + priorities (10 min)**

---

### 🚨 PRIORITIZATION FRAMEWORK

#### 🔴 Critical (Fix immediately)

* Broken checkout / forms
* Slow load (>5s)
* No CTA / unclear offer
* Mobile broken

#### 🟡 Medium

* UX friction
* SEO gaps
* Content improvements

#### 🟢 Low

* Visual polish
* Minor consistency issues

---

### 📋 MASTER COPY CHECKLIST

```
STRATEGY
[ ] Clear goal
[ ] Strong value prop
[ ] CTA hierarchy
[ ] Single page purpose
[ ] Funnel structure

UI / UX
[ ] Visual hierarchy
[ ] Consistent spacing
[ ] Readable typography
[ ] Simple navigation
[ ] No dead ends
[ ] Clear CTAs
[ ] Good forms

MOBILE
[ ] Responsive
[ ] No scroll issues
[ ] Tap targets OK

PERFORMANCE
[ ] <3s load
[ ] Optimized assets

DEV
[ ] Clean code
[ ] No errors

SEO
[ ] Meta tags
[ ] Headings
[ ] Sitemap
[ ] No duplicates

ACCESSIBILITY
[ ] Keyboard usable
[ ] Contrast OK

SECURITY
[ ] HTTPS
[ ] Safe forms

ANALYTICS
[ ] GA4 + events

CONTENT
[ ] Clear messaging
[ ] Strong CTAs

CMS
[ ] Clean plugins
[ ] Backups
```

---

### 💡 FINAL INSIGHT

Most audits fail because they:

* Focus on tools instead of **business goals**
* List issues instead of **prioritizing impact**
* Ignore **conversion + UX**

👉 Real audit =
**Revenue impact > technical perfection**


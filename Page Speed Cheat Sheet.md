## $${\color{red}Page \ Speed \ Cheat \ Sheet}$$

### 1️⃣ Core Web Vitals (Google 👑)

These directly affect **SEO & UX**.

| Metric                              | What it Measures                | Good        | Needs Improvement | Poor    |
| ----------------------------------- | ------------------------------- | ----------- | ----------------- | ------- |
| **LCP** (Largest Contentful Paint)  | Time to render the main content | ≤ **2.5s**  | 2.5–4.0s          | > 4.0s  |
| **INP** (Interaction to Next Paint) | Responsiveness to user input    | ≤ **200ms** | 200–500ms         | > 500ms |
| **CLS** (Cumulative Layout Shift)   | Visual stability                | ≤ **0.1**   | 0.1–0.25          | > 0.25  |

👉 Replace old **FID** — INP is the new standard.

---

### 2️⃣ Loading & Rendering Metrics

| Metric                           | Meaning                  | Target      |
| -------------------------------- | ------------------------ | ----------- |
| **TTFB** (Time to First Byte)    | Server + network latency | < **800ms** |
| **FCP** (First Contentful Paint) | First visible content    | < **1.8s**  |
| **FP** (First Paint)             | First pixel rendered     | ASAP        |
| **DOMContentLoaded**             | HTML parsed              | < **2s**    |
| **Load Event**                   | All resources loaded     | < **3–4s**  |

---

### 3️⃣ JavaScript Performance

| Indicator                     | Why it Matters       | Good        |
| ----------------------------- | -------------------- | ----------- |
| **Total Blocking Time (TBT)** | Main thread blocked  | < **200ms** |
| **Long Tasks**                | Tasks >50ms          | Minimize    |
| **JS Execution Time**         | Delays interactivity | < **1s**    |
| **Unused JS**                 | Wasted bytes         | < **20%**   |

📌 Heavy JS = bad INP + bad UX.

---

### 4️⃣ Network & Asset Metrics

| Metric                | Ideal                  |
| --------------------- | ---------------------- |
| **Total Page Weight** | < **2 MB**             |
| **Requests Count**    | < **70**               |
| **Image Size**        | Compressed, responsive |
| **Font Files**        | ≤ 2 families           |
| **CSS Size**          | < **100 KB (gzipped)** |
| **JS Size**           | < **300 KB (gzipped)** |

---

### 5️⃣ Image Performance Indicators

| Indicator         | Best Practice     |
| ----------------- | ----------------- |
| Image format      | WebP / AVIF       |
| Responsive images | `srcset`, `sizes` |
| Lazy loading      | `loading="lazy"`  |
| Dimensions set    | Prevent CLS       |
| LCP image         | Preloaded         |

---

### 6️⃣ Caching & Delivery

| Indicator         | Target                     |
| ----------------- | -------------------------- |
| **Browser cache** | Long TTL for static assets |
| **CDN usage**     | Yes                        |
| **Compression**   | Gzip / Brotli              |
| **HTTP Version**  | HTTP/2 or HTTP/3           |
| **Cache-Control** | `immutable` for assets     |

---

### 7️⃣ Mobile-Specific Metrics 📱

| Metric        | Goal        |
| ------------- | ----------- |
| Mobile LCP    | ≤ **2.5s**  |
| CPU blocking  | Minimal     |
| Touch latency | < **200ms** |
| Layout shifts | Near zero   |

📌 Always test on **throttled CPU + 4G**.

---

### 8️⃣ Lab vs Real-User Data

| Type           | Tools                    |
| -------------- | ------------------------ |
| **Lab data**   | Lighthouse, WebPageTest  |
| **Field data** | CrUX, PageSpeed Insights |
| **RUM**        | Web Vitals JS, GA4       |

---

### 9️⃣ Key Tools for Developers 🛠️

* **Chrome DevTools → Performance / Lighthouse**
* **PageSpeed Insights**
* **WebPageTest**
* **Lighthouse CI**
* **CrUX Dashboard**
* **@web-vitals JS**

---

### 🔥 Speed Optimization Priority Order

1. Fix **LCP** (images, fonts, server)
2. Reduce **JS blocking**
3. Eliminate **CLS**
4. Optimize **images**
5. Improve **TTFB**
6. Cache everything possible

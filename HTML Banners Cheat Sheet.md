## $${\color{red}HTML \ Banners \ Cheat \ Sheet}$$

### 1. What Is an HTML5 Banner?

An **HTML5 banner** is a lightweight web creative using:

* **HTML** – structure
* **CSS** – layout & animation
* **JavaScript** – interaction & logic

Used for **display advertising** instead of Flash.

---

### 2. Standard Banner Sizes (IAB standrads)

| Name              | Size    |
| ----------------- | ------- |
| Leaderboard       | 728×90  |
| Large Leaderboard | 970×90  |
| Billboard         | 970×250 |
| Medium Rectangle  | 300×250 |
| Large Rectangle   | 336×280 |
| Half Page         | 300×600 |
| Skyscraper        | 160×600 |
| Mobile Banner     | 320×50  |
| Mobile Large      | 320×100 |

---

### 3. File & Weight Limits (Typical)

* **Total ZIP size**: 150–300 KB
* **Initial load**: ≤ 200 KB
* **Animation length**: max **15–30 sec**
* **Loop count**: 1–3
* **No audio autoplay**

> Always check the ad platform specs.

---

### 4. Required Files

```
banner.zip
 ├── index.html   (entry file)
 ├── styles.css
 ├── script.js
 └── images/
```

---

### 5. Minimal HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="ad.size" content="width=300,height=250">
  <title>HTML5 Banner</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <a href="javascript:void(0)" id="clickTag">
    <div id="banner">
      <img src="images/bg.jpg" alt="">
      <div class="cta">Buy Now</div>
    </div>
  </a>
  <script src="script.js"></script>
</body>
</html>
```

---

### 6. Click Handling

**Google Ads / Studio**

```js
document.getElementById("clickTag").onclick = function () {
  window.open(window.clickTag);
};
```

Or newer:

```js
window.open(clickTag, "_blank");
```

> Never hardcode URLs inside the banner.

---

### 7. CSS Animation Best Practices

✔ Use:

* `transform`
* `opacity`

❌ Avoid:

* `top / left`
* `width / height`

Example:

```css
.cta {
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.1); }
}
```

---

### 8. JavaScript Rules

* No external JS unless allowed
* No tracking scripts
* No inline JS in HTML (some networks reject it)
* ES5 preferred for compatibility

---

### 9. Fonts

✔ Allowed:

* System fonts
* Converted text → SVG
* Embedded webfonts (WOFF, WOFF2)

❌ Avoid:

* Google Fonts CDN
* External font loading

---

### 10. Images & Media

* Use **JPG / PNG / SVG**
* Compress images aggressively
* Use **sprite sheets** when possible
* No video unless explicitly allowed

---

### 11. Common Rejection Reasons

🚫 Hardcoded links
🚫 Missing `meta ad.size`
🚫 Too large ZIP
🚫 Infinite animation
🚫 External assets
🚫 Autoplay sound

---

### 12. Testing Checklist

* ✔ Click works
* ✔ Correct dimensions
* ✔ Loads under size limit
* ✔ Animations stop
* ✔ Works in Chrome / Firefox / Edge

---

### 13. Platforms & Specs to Know

* **Google Ads / Display & Video 360**
* **Google Web Designer**
* **Adform**
* **Sizmek**
* **CM360**

---

### 14. Pro Tips

* Use **GSAP (if allowed)** for smooth animations
* Export from **Google Web Designer** for faster approvals
* Keep **background static**, animate foreground
* Design mobile-first for performance

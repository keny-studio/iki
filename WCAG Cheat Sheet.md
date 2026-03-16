## $${\color{red}WCAG \ Cheat \ Sheet}$$

**Web Content Accessibility Guidelines** used to build accessible websites and apps.

---

### 1. WCAG Principles (POUR)

WCAG is based on **4 core principles**.

| Principle          | Meaning                                        | Developer Focus                       |
| ------------------ | ---------------------------------------------- | ------------------------------------- |
| **Perceivable**    | Users must be able to perceive content         | Provide text alternatives, captions   |
| **Operable**       | Interface must be usable with different inputs | Keyboard support, no traps            |
| **Understandable** | UI and content must be clear                   | Predictable navigation, readable text |
| **Robust**         | Works with assistive technologies              | Semantic HTML, ARIA where needed      |

---

### 2. Accessibility Levels

| Level   | Meaning                              |
| ------- | ------------------------------------ |
| **A**   | Minimum accessibility requirements   |
| **AA**  | Standard level required by most laws |
| **AAA** | Highest accessibility standard       |

Most organizations target **WCAG 2.1/2.2 Level AA**.

---

### 3. Semantic HTML (Always First)

Use **native HTML elements before ARIA**.

| Element     | Purpose                |
| ----------- | ---------------------- |
| `<header>`  | Page or section header |
| `<nav>`     | Navigation region      |
| `<main>`    | Main content           |
| `<section>` | Content grouping       |
| `<article>` | Independent content    |
| `<button>`  | Interactive button     |
| `<label>`   | Form field label       |

Example:

```html
<label for="email">Email</label>
<input id="email" type="email" required>
```

---

### 4. Images

Always provide alternative text.

| Case              | Example                        |
| ----------------- | ------------------------------ |
| Informative image | `alt="Team working in office"` |
| Decorative image  | `alt=""`                       |
| Complex image     | use description in text        |

Example:

```html
<img src="chart.png" alt="Sales increased 40 percent in 2025">
```

---

### 5. Keyboard Accessibility

All interactive elements must work with keyboard.

Checklist:

✔ Tab navigation
✔ Visible focus state
✔ No keyboard traps
✔ Logical tab order

Example focus style:

```css
:focus {
  outline: 3px solid #005fcc;
}
```

---

### 6. Color & Contrast

Minimum contrast ratios:

| Text Type     | Ratio       |
| ------------- | ----------- |
| Normal text   | **4.5 : 1** |
| Large text    | **3 : 1**   |
| UI components | **3 : 1**   |

Never rely on **color alone**.

Bad:

```
Red text = error
```

Good:

```
Icon + text + color
```

---

### 7. Forms Accessibility

Best practices:

✔ Label every input
✔ Provide error messages
✔ Use fieldsets for groups
✔ Describe required fields

Example:

```html
<label for="password">Password</label>
<input id="password" type="password" aria-describedby="pwd-help">

<p id="pwd-help">Must contain at least 8 characters</p>
```

---

### 8. ARIA (Accessible Rich Internet Applications)

Entity reference: **WAI-ARIA**

Use ARIA **only when HTML is insufficient**.

Common attributes:

| Attribute       | Purpose                  |
| --------------- | ------------------------ |
| `role`          | Defines element type     |
| `aria-label`    | Accessible name          |
| `aria-hidden`   | Hide from screen readers |
| `aria-expanded` | Toggle state             |
| `aria-live`     | Dynamic content updates  |

Example:

```html
<button aria-expanded="false" aria-controls="menu">
  Menu
</button>
```

---

### 9. Headings Structure

Use proper hierarchy.

Correct:

```
h1
 ├─ h2
 │   └─ h3
 └─ h2
```

Bad:

```
h1
 ├─ h4
 └─ h2
```

Rule: **Do not skip heading levels**.

---

### 10. Accessible Links

Links must describe their destination.

Bad:

```
Click here
```

Good:

```
Download accessibility report
```

Example:

```html
<a href="/report.pdf">Download accessibility report</a>
```

---

### 11. Media Accessibility

Videos must include:

✔ Captions
✔ Transcripts
✔ Audio descriptions (AAA)

Example:

```html
<track kind="captions" src="captions.vtt" srclang="en">
```

---

### 12. Common Developer Accessibility Tests

Quick checklist:

* Navigate entire page using **Tab**
* Test with **screen reader**
* Disable CSS
* Zoom to **200%**
* Test color contrast
* Validate HTML

Tools:

| Tool       | Purpose                  |
| ---------- | ------------------------ |
| Axe        | Accessibility testing    |
| Lighthouse | Accessibility audit      |
| WAVE       | Accessibility evaluation |
| NVDA       | Screen reader            |

---

### 13. Frequent Accessibility Mistakes

❌ Missing alt text
❌ Div buttons instead of `<button>`
❌ No keyboard support
❌ Placeholder instead of labels
❌ Low color contrast
❌ Incorrect heading structure

---

### 14. Developer Accessibility Workflow

1. Use semantic HTML
2. Add accessibility during development
3. Test keyboard navigation
4. Validate contrast
5. Test with screen reader
6. Run automated tools

---

✅ **Key Rule**

> “Accessibility should be built-in, not added later.”

---

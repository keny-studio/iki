## $${\color{red}BEM \ Cheat \ Sheet}$$


**BEM** = **Block – Element – Modifier** <br>
A CSS naming methodology created by Yandex to build scalable, maintainable UI components.

```
Block = Component
Element = Part of component
Modifier = Variation/state
```

---

### 1️⃣ Core Concepts

### 🧱 Block

Standalone, reusable component.

```html
<div class="card"></div>
```

* Represents a meaningful UI component
* Can be nested inside other blocks
* No dependency on parent

Examples:

```
.header
.menu
.card
.button
.form
```

---

### 🧩 Element

A part of a block. Cannot exist independently.

```html
<div class="card">
  <h2 class="card__title"></h2>
</div>
```

Syntax:

```
block__element
```

Examples:

```
.card__title
.card__image
.menu__item
.form__input
```

Rules:

* Always tied to a block
* No element of element ❌
  `card__header__title` → WRONG

---

### 🎛 Modifier

Defines variation or state.

```html
<button class="button button--primary"></button>
```

Syntax:

```
block--modifier
block__element--modifier
```

Examples:

```
.button--large
.card--featured
.menu__item--active
.form__input--error
```

---

### 2️⃣ Naming Rules

| Type     | Format                 | Example             |
| -------- | ---------------------- | ------------------- |
| Block    | `.block`               | `.card`             |
| Element  | `.block__element`      | `.card__title`      |
| Modifier | `.block--modifier`     | `.card--dark`       |
| Elem Mod | `.block__el--modifier` | `.card__title--big` |

✔ Use lowercase
✔ Use hyphen for multi-words
✔ Use double underscore `__` for elements
✔ Use double dash `--` for modifiers

Example:

```
.user-profile
.user-profile__avatar
.user-profile__avatar--large
```

---

### 3️⃣ Example Component

### HTML

```html
<div class="card card--featured">
  <img class="card__image" src="image.jpg">
  <h2 class="card__title">Title</h2>
  <p class="card__description">Description</p>
  <button class="card__button card__button--primary">Buy</button>
</div>
```

### CSS

```css
.card {
  border: 1px solid #ddd;
}

.card--featured {
  border-color: gold;
}

.card__title {
  font-size: 1.2rem;
}

.card__button--primary {
  background: blue;
  color: white;
}
```

---

### 4️⃣ Good vs Bad

### ❌ Bad

```css
.card .title {}
.card.active {}
```

* Depends on nesting
* Not reusable
* Hard to refactor

---

### ✅ Good

```css
.card__title {}
.card--active {}
```

* Independent
* Predictable
* Scalable

---

### 5️⃣ States in BEM

Instead of:

```css
.is-active {}
```

Prefer:

```
.menu__item--active
.button--disabled
.modal--open
```

If using JS frameworks:

```
.is-loading  (utility state class)
```

---

### 6️⃣ When to Create a New Block?

Create new block when:

* Component can exist independently
* It has its own logic
* It can be reused elsewhere

Example:

```
.card__button   ❌ if reusable everywhere
.button         ✅ separate block
```

---

### 7️⃣ BEM + SCSS Example

```scss
.card {
  padding: 1rem;

  &__title {
    font-weight: bold;
  }

  &--featured {
    border: 2px solid gold;
  }
}
```

Compiles to:

```
.card {}
.card__title {}
.card--featured {}
```

---

### 8️⃣ Architecture Tips

✔ Keep blocks small
✔ Avoid deep nesting
✔ Don’t chain selectors
✔ One responsibility per block
✔ Avoid styling by tag name inside block

---

### 9️⃣ BEM vs Utility CSS

| BEM                      | Utility (e.g., Tailwind) |
| ------------------------ | ------------------------ |
| Semantic                 | Atomic                   |
| Component-based          | Utility-based            |
| Structured               | Fast prototyping         |
| Great for design systems | Great for speed          |

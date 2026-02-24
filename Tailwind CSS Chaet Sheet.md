## $${\color{red}Tailwind \ CSS \ Cheat \ Sheet}$$

**Tailwind CSS** is a utility-first CSS framework for rapidly building modern UIs directly in your markup.

---

### 1️⃣ Core Syntax

```html
<div class="p-4 bg-blue-500 text-white rounded-lg shadow-md">
  Hello Tailwind
</div>
```

Structure:

```
[property]-[value]
```

Examples:

```
p-4          → padding
mt-2         → margin-top
text-lg      → font-size
bg-red-500   → background color
flex         → display:flex
```

---

### 2️⃣ Spacing (Margin & Padding)

### Margin

```
m-4     → all sides
mt-4    → top
mr-4    → right
mb-4    → bottom
ml-4    → left
mx-4    → left & right
my-4    → top & bottom
```

### Padding

```
p-4
pt-4
px-4
py-2
```

Scale (default):

```
0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 56, 64
```

---

### 3️⃣ Layout

### Display

```
block
inline-block
inline
flex
grid
hidden
```

### Flexbox

```
flex
flex-row / flex-col
flex-wrap
items-center
justify-between
gap-4
```

### Grid

```
grid
grid-cols-3
col-span-2
gap-4
```

---

### 4️⃣ Sizing

```
w-full
w-1/2
w-screen
h-full
h-screen
max-w-lg
min-h-screen
```

---

### 5️⃣ Typography

```
text-sm / text-lg / text-xl
font-light / font-bold
text-center / text-left
text-gray-700
leading-tight
tracking-wide
uppercase
```

---

### 6️⃣ Colors

Format:

```
color-shade
```

Example palette:

```
bg-blue-500
text-red-600
border-gray-300
```

Shades:

```
50 → lightest
100–900 → darkest
```

---

### 7️⃣ Backgrounds & Borders

```
bg-cover
bg-center
bg-no-repeat

border
border-2
border-red-500
rounded
rounded-lg
rounded-full
```

---

### 8️⃣ Effects

```
shadow
shadow-md
shadow-lg

opacity-50

transition
duration-300
ease-in-out
```

---

### 9️⃣ Positioning

```
relative
absolute
fixed
sticky

top-0
left-0
z-10
```

---

### 🔟 Responsive Design

Prefix with breakpoints:

```
sm:
md:
lg:
xl:
2xl:
```

Example:

```html
<div class="text-sm md:text-lg lg:text-xl">
```

Default breakpoints:

```
sm  → 640px
md  → 768px
lg  → 1024px
xl  → 1280px
2xl → 1536px
```

---

### 1️⃣1️⃣ State Variants

```
hover:
focus:
active:
disabled:
group-hover:
```

Example:

```html
<button class="bg-blue-500 hover:bg-blue-700">
```

---

### 1️⃣2️⃣ Dark Mode

```
dark:bg-gray-900
dark:text-white
```

Enable in config:

```js
darkMode: 'class'
```

---

### 1️⃣3️⃣ Common Patterns

### Center with Flex

```html
<div class="flex items-center justify-center min-h-screen">
```

### Card

```html
<div class="max-w-sm p-6 bg-white rounded-lg shadow-md">
```

### Button

```html
<button class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600 transition">
```

---

### 1️⃣4️⃣ Customization (tailwind.config.js)

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#1e40af',
      },
    },
  },
}
```

---

### 🚀 Pro Tips

* Use `@apply` for reusable components
* Extract repeated patterns into components
* Use `container` for layout wrapper
* Use `prose` (Typography plugin) for article content
* Combine with frameworks (React, Vue, Laravel, etc.)

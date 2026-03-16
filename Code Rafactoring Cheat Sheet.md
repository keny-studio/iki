  ## $${\color{red}🔧 \ Code \ Refactoring \ Cheat \ Sheet}$$

Code refactoring is the systematic process of restructuring existing computer code - improving its internal structure, readability, and maintainability—without changing its external behavior or adding new functionality. 

---

### 1️⃣ Core Refactoring Principles

#### ✔ Preserve Behavior

Refactoring ≠ rewriting.
All tests must pass before & after.

#### ✔ Small Steps

Refactor incrementally. Commit often.

#### ✔ Red–Green–Refactor

From **Refactoring** and **Test Driven Development: By Example** philosophy:

1. Red – failing test
2. Green – make it pass
3. Refactor – improve structure

---

### 2️⃣ Code Smells → Refactoring Techniques

| Code Smell                   | Fix                        |
| ---------------------------- | -------------------------- |
| Long method                  | Extract Method             |
| Large class                  | Extract Class              |
| Duplicate code               | Extract Method / DRY       |
| Long parameter list          | Introduce Parameter Object |
| Primitive obsession          | Replace with Value Object  |
| Switch statements everywhere | Replace with Polymorphism  |
| Feature envy                 | Move Method                |
| Data clumps                  | Introduce Object           |
| Shotgun surgery              | Move Responsibilities      |
| God object                   | Split by Responsibility    |

---

### 3️⃣ Common Refactoring Techniques

#### 🔹 Extract Method

**Before**

```php
function processOrder($order) {
    // validate
    if (!$order->isValid()) {
        throw new Exception("Invalid");
    }

    // calculate total
    $total = 0;
    foreach ($order->items as $item) {
        $total += $item->price;
    }

    return $total;
}
```

**After**

```php
function processOrder($order) {
    $this->validate($order);
    return $this->calculateTotal($order);
}
```

---

#### 🔹 Rename for Clarity

Bad:

```js
let d;
```

Good:

```js
let deliveryDate;
```

---

#### 🔹 Replace Conditional with Polymorphism

**Before**

```php
if ($user->type === 'admin') {
    return 0.2;
}
if ($user->type === 'customer') {
    return 0.1;
}
```

**After**

```php
$user->getDiscount();
```

Each class implements its own logic.

---

#### 🔹 Introduce Value Object

**Before**

```php
$user->email = "test@example.com";
```

**After**

```php
$user->email = new Email("test@example.com");
```

Encapsulates validation + behavior.

---

#### 🔹 Replace Magic Numbers with Constants

Bad:

```js
if (timeout > 3000)
```

Good:

```js
const REQUEST_TIMEOUT_MS = 3000;
```

---

#### 🔹 Guard Clauses (Reduce Nesting)

**Before**

```php
if ($user) {
    if ($user->isActive()) {
        return true;
    }
}
return false;
```

**After**

```php
if (!$user) return false;
if (!$user->isActive()) return false;

return true;
```

---

### 4️⃣ Structural Refactoring

#### 🧱 Split Large Class

* Separate read vs write logic
* Separate domain vs infrastructure
* Apply Single Responsibility Principle

#### 🧩 Move Method

If a method uses another class more than its own → move it.

#### 📦 Extract Module

Group related logic into:

* Service
* Helper
* Domain class
* Custom hook (React)

---

### 5️⃣ Naming Refactoring

| Bad       | Better                 |
| --------- | ---------------------- |
| getData() | getUserById()          |
| handle()  | handlePaymentWebhook() |
| data      | userProfile            |
| temp      | formattedDate          |

Rules:

* Be explicit
* Prefer domain language
* Avoid abbreviations

---

### 6️⃣ Dependency Refactoring

#### ❌ Before (Tight Coupling)

```php
$mailer = new SmtpMailer();
```

#### ✅ After (Dependency Injection)

```php
function __construct(MailerInterface $mailer)
```

---

### 7️⃣ Functional Refactoring

#### Replace Loop with Collection Methods

**Before**

```js
let active = [];
for (let user of users) {
    if (user.active) active.push(user);
}
```

**After**

```js
const active = users.filter(u => u.active);
```

---

### 8️⃣ Architecture-Level Refactoring

#### ➜ Layer Separation

* Controller → Application → Domain → Infrastructure

#### ➜ Remove Business Logic from:

* Controllers
* React components
* WordPress templates

Move into:

* Services
* Domain objects
* Hooks

---

### 9️⃣ Safe Refactoring Checklist

✔ Tests exist
✔ Small commits
✔ Remove dead code
✔ Remove commented code
✔ Remove unused imports
✔ Improve names
✔ Flatten conditionals
✔ Remove duplication
✔ Improve cohesion
✔ Reduce coupling

---

### 🔟 Refactoring vs Rewriting

| Refactoring        | Rewriting          |
| ------------------ | ------------------ |
| Improves structure | Replaces system    |
| Low risk           | High risk          |
| Incremental        | Big bang           |
| Keeps tests green  | Often resets tests |

---

### ⚡ High-Impact Quick Wins

* Rename unclear variables
* Extract 20+ line methods
* Remove nested conditionals
* Replace booleans with enums
* Remove static dependencies
* Replace arrays with objects
* Introduce DTO instead of raw arrays

---

### 🧠 Mental Models

* Code should read like a sentence
* Every function should do ONE thing
* If you need comments → improve naming
* If change is painful → design is wrong
* Make illegal states unrepresentable

---


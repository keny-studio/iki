## $${\color{red}💩 \ Code \ Smells}$$

A **code smell** is a symptom in the source code that may indicate a deeper problem in design, architecture, or maintainability.

---

### 🔴 1. Bloaters (Too Big / Too Much)

#### 🧱 Long Method

* Method does too many things
* Hard to read, test, reuse

**Fix:**

* Extract Method
* Break into smaller functions

---

#### 🏗 Large Class

* Too many fields/methods
* Violates Single Responsibility Principle

**Fix:**

* Extract Class
* Apply SRP

---

#### 📦 Primitive Obsession

* Using primitives instead of value objects
* `string email`, `string currency`, etc.

**Fix:**

* Introduce Value Objects
* Use enums / small domain models

---

#### 📚 Long Parameter List

* Too many function arguments
* Hard to understand call sites

**Fix:**

* Introduce Parameter Object
* Use builder pattern

---

### 🟡 2. Object-Oriented Smells

#### 🔁 Switch Statements Everywhere

* Same `switch` or `if` chain in multiple places
* Violates Open/Closed Principle

**Fix:**

* Replace with Polymorphism
* Strategy Pattern

---

#### 💤 Lazy Class

* Class does almost nothing

**Fix:**

* Inline Class
* Merge with related class

---

#### 👨‍👩‍👧 Feature Envy

* Method uses another class more than its own

**Fix:**

* Move Method

---

#### 🔗 Inappropriate Intimacy

* Classes know too much about each other

**Fix:**

* Reduce coupling
* Introduce interface

---

#### 🧬 Refused Bequest

* Subclass doesn't use parent behavior

**Fix:**

* Replace inheritance with composition

---

### 🟠 3. Change Preventers

#### 🎯 Divergent Change

* One class changes for many different reasons

**Fix:**

* Split responsibilities

---

#### 🔄 Shotgun Surgery

* One change requires editing many files

**Fix:**

* Improve cohesion
* Centralize logic

---

### 🔵 4. Dispensables (Unnecessary Code)

#### 🧟 Dead Code

* Unused variables, methods, classes

**Fix:**

* Delete it
* Use static analysis tools

---

#### 💬 Comments Explaining Bad Code

* Comments used to justify complex logic

**Fix:**

* Refactor to self-documenting code

---

#### 🧩 Duplicate Code

* Same logic in multiple places

**Fix:**

* Extract method
* Create shared abstraction

---

#### 🪶 Speculative Generality

* Code added “just in case”

**Fix:**

* Remove unused abstractions
* YAGNI principle

---

### 🟣 5. Coupling & Architecture Smells

#### 🧵 Tight Coupling

* Classes directly depend on concrete implementations

**Fix:**

* Dependency Injection
* Depend on interfaces

---

#### 🌊 God Object / God Class

* One class controls everything

**Fix:**

* Split into smaller domain-focused services

---

#### 🏛 Anemic Domain Model

* Classes with only getters/setters
* Logic placed in services instead

**Fix:**

* Move behavior into domain objects

---

#### 🕸 Cyclic Dependencies

* Module A depends on B, B depends on A

**Fix:**

* Introduce abstraction layer
* Redesign module boundaries

---

### ⚫ 6. Naming Smells

#### ❓ Vague Names

* `data`, `manager`, `util`, `helper`

**Fix:**

* Use intention-revealing names

---

#### 🔤 Inconsistent Naming

* Mixed conventions
* Similar concepts named differently

**Fix:**

* Standardize naming conventions

---

### 🟢 7. Testing Smells

#### 🧪 Hard-to-Test Code

* Hidden dependencies
* Static/global state

**Fix:**

* Dependency injection
* Remove global state

---

#### 🧱 Massive Setup in Tests

* Complicated object graphs

**Fix:**

* Test builders
* Mock dependencies

---

## 🚀 Quick Recognition Table

| Smell               | Root Problem            | Quick Fix           |
| ------------------- | ----------------------- | ------------------- |
| Long Method         | Too much responsibility | Extract method      |
| Large Class         | Violates SRP            | Split class         |
| Duplicate Code      | DRY violation           | Extract abstraction |
| Shotgun Surgery     | Poor cohesion           | Centralize logic    |
| God Object          | Poor design             | Decompose           |
| Primitive Obsession | Weak domain modeling    | Value objects       |
| Tight Coupling      | Low flexibility         | DI + interfaces     |

---

## 🧠 Rule of Thumb

If code is:

* Hard to read → Naming or bloat issue
* Hard to change → Architecture problem
* Hard to test → Coupling problem
* Hard to extend → OCP violation



## $${\color{red}Software \ Design \ Patterns \ Cheat \ Sheet}$$

Design patterns - **reusable solutions to common software design problems**. They help you write code that is **flexible, maintainable, and scalable**.

---

## 🏗️ Creational Patterns

**Concern:** How objects are created

### 1. Singleton

**Purpose:** Ensure only one instance exists
**Use when:** Shared resource (logger, config, cache)


```text
One instance
Global access point
```

⚠️ Beware of overuse (testability issues)

---

### 2. Factory Method

**Purpose:** Create objects without specifying exact class
**Use when:** Object creation depends on input or context

```text
Interface → Concrete implementations
```

Example: Payment method factory (Card, PayPal, Crypto)

---

### 3. Abstract Factory

**Purpose:** Create families of related objects
**Use when:** Multiple product types must work together

Example: UI kits (Windows buttons + inputs vs Mac)

---

### 4. Builder

**Purpose:** Construct complex objects step-by-step
**Use when:** Many optional parameters

Example: HTTP request builder

---

### 5. Prototype

**Purpose:** Clone existing objects
**Use when:** Object creation is expensive

Example: Duplicating preconfigured objects

---

## 🧱 Structural Patterns

**Concern:** Object composition & structure

### 6. Adapter

**Purpose:** Make incompatible interfaces work together
**Use when:** Integrating legacy or third-party code

```text
Old API → Adapter → New API
```

---

### 7. Decorator

**Purpose:** Add behavior without modifying class
**Use when:** Need flexible feature combinations

Example: Coffee + milk + sugar pricing

---

### 8. Facade

**Purpose:** Simplified interface to complex system
**Use when:** Hiding complexity

Example: `OrderService.placeOrder()`

---

### 9. Composite

**Purpose:** Treat individual objects and groups the same
**Use when:** Tree structures

Example: Files & folders

---

### 10. Proxy

**Purpose:** Control access to object
**Use when:** Lazy loading, access control, caching

Example: Image loading proxy

---

### 11. Bridge

**Purpose:** Separate abstraction from implementation
**Use when:** Avoid class explosion

Example: Shape + Renderer

---

## 🔁 Behavioral Patterns

**Concern:** Communication between objects

### 12. Observer

**Purpose:** Notify dependents on state change
**Use when:** Event-driven systems

Example: UI updates, pub/sub

---

### 13. Strategy

**Purpose:** Switch algorithms at runtime
**Use when:** Multiple ways to do the same thing

Example: Sorting strategies, payment methods

---

### 14. Command

**Purpose:** Encapsulate a request as an object
**Use when:** Undo/redo, queues, macros

Example: Editor actions

---

### 15. State

**Purpose:** Change behavior based on internal state
**Use when:** Object has many conditional behaviors

Example: Order status (New → Paid → Shipped)

---

### 16. Template Method

**Purpose:** Define algorithm skeleton
**Use when:** Steps are fixed, details vary

Example: Data import workflow

---

### 17. Chain of Responsibility

**Purpose:** Pass request along handler chain
**Use when:** Multiple possible handlers

Example: Middleware, validation pipeline

---

### 18. Mediator

**Purpose:** Centralize complex communications
**Use when:** Many objects interact tightly

Example: Chat room logic

---

### 19. Iterator

**Purpose:** Traverse collection without exposing structure
**Use when:** Custom collections

---

### 20. Memento

**Purpose:** Capture and restore object state
**Use when:** Undo functionality

---

### 21. Visitor

**Purpose:** Add operations without modifying objects
**Use when:** Stable structure, changing behavior

Example: AST operations

---

## 🧩 Architectural / Modern Patterns (Bonus)

### MVC

**Model – View – Controller**
Separation of concerns (classic web apps)

---

### MVVM

**Model – View – ViewModel**
Two-way data binding (frontend frameworks)

---

### Repository

Abstracts data access
Used heavily in DDD

---

### Dependency Injection (DI)

Objects receive dependencies instead of creating them
Improves testability

---

### Service Layer

Encapsulates business logic
Keeps controllers thin

---

## 🧪 Anti-Patterns

* God Object
* Spaghetti Code
* Over-engineering
* Singleton everywhere
* Premature abstraction

---

## 🗺️ Quick Pattern Selection Guide

| Problem                  | Pattern           |
| ------------------------ | ----------------- |
| One shared instance      | Singleton         |
| Many object types        | Factory           |
| Add behavior dynamically | Decorator         |
| Event handling           | Observer          |
| Switch algorithms        | Strategy          |
| Simplify complex system  | Facade            |
| Undo/redo                | Command / Memento |


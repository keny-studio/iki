## $${\color{red}Object-Oriented \ Programming \ Cheat \ Sheet}$$

OOP - programming approach where software is structured as interacting objects that contain both data and behavior.

### OOP Core principles:

### 1️⃣ Encapsulation

**Definition:** Bundle data + behavior together and restrict direct access to internal state.

**Goal:** Protect object integrity.

```php
class User {
    private string $email;

    public function setEmail(string $email): void {
        if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
            throw new InvalidArgumentException();
        }
        $this->email = $email;
    }

    public function getEmail(): string {
        return $this->email;
    }
}
```

**Key Points**

* Use `private` / `protected`
* Validate inside setters
* Avoid exposing raw internal state

---

### 2️⃣ Abstraction

**Definition:** Hide implementation details, expose only essential behavior.

**Goal:** Reduce complexity.

```php
interface PaymentGateway {
    public function charge(float $amount): bool;
}

class StripePayment implements PaymentGateway {
    public function charge(float $amount): bool {
        // Stripe logic here
        return true;
    }
}
```

**Key Points**

* Use interfaces / abstract classes
* Code against contracts, not implementations

---

### 3️⃣ Inheritance

**Definition:** Create new classes from existing ones.

**Goal:** Reuse behavior.

```php
class Animal {
    public function speak() {
        return "Sound";
    }
}

class Dog extends Animal {
    public function speak() {
        return "Bark";
    }
}
```

**Use carefully**

* Prefer composition over deep inheritance trees
* Avoid fragile base class problem

---

### 4️⃣ Polymorphism

**Definition:** Same interface, different behavior.

```php
function makeSpeak(Animal $animal) {
    echo $animal->speak();
}
```

Works for `Dog`, `Cat`, etc.

**Types**

* Method overriding (runtime)
* Method overloading (compile-time, language-dependent)

---

### 🔥 SOLID Principles

---

### S — Single Responsibility Principle (SRP)

> A class should have only one reason to change.

❌ Bad:

```php
class Report {
    public function generate() {}
    public function saveToFile() {}
}
```

✅ Good:

```php
class ReportGenerator {}
class ReportStorage {}
```

---

### O — Open/Closed Principle (OCP)

> Open for extension, closed for modification.

Add new behavior via new classes — not by editing old ones.

Use:

* Interfaces
* Strategy pattern
* Dependency injection

---

### L — Liskov Substitution Principle (LSP)

> Subtypes must be replaceable for their base types.

If `Dog` extends `Animal`, it must behave like an `Animal`.

🚨 Red flag:

* Throwing "Not implemented"
* Breaking parent contract

---

### I — Interface Segregation Principle (ISP)

> Don’t force classes to implement methods they don’t use.

❌ Fat interface:

```php
interface Worker {
    public function work();
    public function eat();
}
```

✅ Split:

```php
interface Workable { public function work(); }
interface Eatable { public function eat(); }
```

---

### D — Dependency Inversion Principle (DIP)

> Depend on abstractions, not concretions.

❌

```php
class Order {
    private StripePayment $payment;
}
```

✅

```php
class Order {
    private PaymentGateway $payment;
}
```

Inject dependency via constructor.

---

### 🧩 Composition Over Inheritance

Prefer:

```php
class Car {
    private Engine $engine;
}
```

Instead of:

```php
class Car extends Engine {}
```

**Why?**

* More flexible
* Less coupling
* Easier testing

---

### ⚙️ OOP Design Best Practices

* Favor immutability when possible
* Keep classes small
* Avoid god objects
* Use dependency injection
* Program to interfaces
* Follow DRY (Don’t Repeat Yourself)
* Apply KISS (Keep It Simple, Stupid)

---

### 🏗️ Common OOP Patterns

* Strategy
* Factory
* Singleton (use carefully)
* Observer
* Decorator
* Adapter

---

### 🧠 OOP Mental Model

| Concept     | Think Of    |
| ----------- | ----------- |
| Class       | Blueprint   |
| Object      | Instance    |
| Interface   | Contract    |
| Method      | Behavior    |
| Property    | State       |
| Constructor | Setup logic |

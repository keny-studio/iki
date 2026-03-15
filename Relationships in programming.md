## $${\color{red}Relationships \ in \ programming}$$ - how things are linked


> **Relationship** - defined connection between entities (such as objects, classes, modules, or data records) that determines how they reference, use, or affect each other.

---

### **Common Types of Relationships**

### 1. Association

A **loose connection** where one entity uses or knows about another.

* Objects can exist independently.
* Often represented by variables, method parameters, or references.

**Example**

```java
class Teacher {
    Student student;
}
```

---

### 2. Aggregation (Has-a)

A **whole–part relationship** where parts can exist independently of the whole.

* Weak ownership
* Represented by collections or references

**Example**

```java
class Team {
    List<Player> players;
}
```

---

### 3. Composition (Strong Has-a)

A **strong whole–part relationship** where parts cannot exist without the whole.

* Strong ownership
* Lifecycle is tied together

**Example**

```java
class House {
    private Room room = new Room();
}
```

---

### 4. Inheritance (Is-a)

One entity **extends or inherits** from another.

* Reuse of behavior
* Strong coupling

**Example**

```java
class Dog extends Animal {}
```

---

### 5. Dependency (Uses-a)

One entity **temporarily relies** on another to perform a task.

* Often via method arguments
* Short-lived relationship

**Example**

```java
class ReportService {
    void generate(PDFGenerator generator) {}
}
```

---

### 6. Data Relationships (Databases)

Used to define how data records relate to each other.

* **One-to-One**
* **One-to-Many**
* **Many-to-Many**

**Example**

```sql
User → Orders (one-to-many)
```

---

### 7. Functional Relationships

How functions interact or depend on each other.

* Function calls
* Higher-order functions
* Callbacks

**Example**

```js
processData(validateData);
```

---

## Why Relationships Matter

* Define **system structure**
* Control **coupling and cohesion**
* Improve **maintainability**
* Help with **scalability and testing**
* Fundamental for **OOP, databases, APIs, and architecture**


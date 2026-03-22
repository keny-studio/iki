## $${\color{red}Code \ Review \ Cheat \ Sheet}$$


Code review is a software quality assurance process where developers systematically examine and evaluate a peer's source code before it is integrated into a main codebase.

### 🎯 1. Core Goals

* ✅ Improve code quality
* ✅ Catch bugs early
* ✅ Ensure consistency
* ✅ Share knowledge
* ✅ Maintain long-term maintainability

---

### 🔍 2. High-Level Checks

#### 🧩 Functionality

* Does the code **work as intended**?
* Are **edge cases handled**?
* Are **error states covered**?

#### 📖 Readability

* Is the code **easy to understand**?
* Are names **clear and meaningful**?
* Can a new dev understand it quickly?

#### 🧱 Architecture

* Does it follow **project patterns**?
* Any **tight coupling / bad dependencies**?
* Is responsibility **well separated**?

---

### ⚙️ 3. Code Quality

#### 🧼 Clean Code

* Small, focused functions
* No duplication (**DRY**)
* No dead code
* No magic numbers / hardcoded values

#### 🧾 Naming

* Variables → descriptive (`userEmail` > `ue`)
* Functions → verbs (`getUserData`)
* Booleans → `is`, `has`, `can`

#### 🧩 Structure

* Logical file/module organization
* Consistent formatting
* Proper abstraction levels

---

### 🧪 4. Testing

* Are **tests included**?
* Do tests cover:

  * Happy path
  * Edge cases
  * Failure cases
* Are tests:

  * Readable
  * Deterministic
  * Fast

---

### ⚡ 5. Performance

* Any **unnecessary loops or computations**?
* Avoid **N+1 queries**
* Efficient data structures used?
* Any **blocking operations**?

---

### 🔐 6. Security

* Input validation & sanitization
* Protection against:

  * XSS
  * SQL Injection
  * CSRF
* Sensitive data handling (tokens, passwords)
* Proper auth & permissions

---

### 🌐 7. API & Data Handling

* Consistent API contracts
* Proper status codes
* Error handling:

  * Clear messages
  * No sensitive leaks
* Data validation on both ends

---

### 🧵 8. Concurrency & State

* Race conditions?
* Proper async handling (`await`, promises)
* No shared mutable state issues
* Idempotency where needed

---

### 📦 9. Dependencies

* Are new deps necessary?
* Any **heavy / risky libraries**?
* Version compatibility
* Security vulnerabilities

---

### 📝 10. Documentation

* Clear PR description
* Comments explain **why**, not what
* README / docs updated if needed

---

### 🧰 11. Style & Standards

* Linting passes
* Follows team conventions
* Consistent formatting (Prettier, ESLint, etc.)

---

### 🚨 12. Red Flags (Quick Scan)

* ❌ Huge pull request (>500 lines)
* ❌ Mixed concerns (UI + logic + API)
* ❌ Commented-out code
* ❌ Duplicate logic
* ❌ Hardcoded values
* ❌ No tests
* ❌ Vague naming (`data`, `stuff`, `temp`)

---

### 💬 13. Review Feedback Tips

#### ✅ Good Feedback

* Be **specific**
* Suggest improvements
* Ask questions:

  * “What happens if…?”
  * “Can this be simplified?”

#### ❌ Avoid

* Personal criticism
* Vague comments (“bad code”)
* Over-engineering suggestions

---

### ⚡ 14. Quick pull request Checklist

* [ ] Works correctly
* [ ] Readable & clean
* [ ] No duplication
* [ ] Proper error handling
* [ ] Tests included
* [ ] No security risks
* [ ] Performance OK
* [ ] Follows standards
* [ ] Docs updated

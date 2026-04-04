## $${\color{red}Software \ Quality \ Principles}$$

### 🎯 1. Correctness

* Software does what it is supposed to do
* Meets **functional requirements**
* Produces expected outputs for valid inputs

**Quick checks:**

* Unit tests pass ✅
* Acceptance criteria satisfied
* Edge cases handled

---

### ⚡ 2. Reliability

* Works consistently over time
* Handles failures gracefully

**Key ideas:**

* Fault tolerance
* Error handling
* Retry mechanisms

**Metrics:**

* MTBF (Mean Time Between Failures)
* Error rate

---

### 🚀 3. Performance & Efficiency

* Uses resources optimally
* Responds quickly

**Focus areas:**

* Response time (latency)
* Throughput
* CPU / memory usage

**Tips:**

* Avoid premature optimization
* Profile before optimizing

---

### 🔒 4. Security

* Protects data and systems from threats

**Core practices:**

* Input validation
* Authentication & authorization
* Encryption (in transit & at rest)

**Watch for:**

* OWASP Top 10 vulnerabilities

---

### 🧩 5. Maintainability

* Easy to modify, fix, and extend

**Principles:**

* Clean code
* Modular design
* Low coupling, high cohesion

**Practices:**

* Refactoring regularly
* Code reviews
* Consistent naming

---

### 🔄 6. Testability

* Easy to test and verify

**Enabled by:**

* Dependency injection
* Small, isolated components
* Clear interfaces

**Tools:**

* Unit / integration / e2e tests
* Mocking & stubbing

---

## 📦 7. Scalability

* Handles growth (users, data, traffic)

**Strategies:**

* Horizontal scaling (add more nodes)
* Load balancing
* Stateless services

---

### 🌐 8. Usability

* Easy and intuitive for users

**Focus:**

* UX/UI clarity
* Accessibility (WCAG)
* Minimal learning curve

---

### 🔌 9. Interoperability

* Works with other systems

**Enabled by:**

* Standard protocols (REST, GraphQL)
* APIs
* Data format consistency (JSON, XML)

---

### 📊 10. Portability

* Runs in different environments

**Examples:**

* Cross-platform apps
* Cloud-agnostic deployments
* Containerization (Docker)

---

### 🧱 11. Robustness

* Handles invalid input and unexpected situations

**Includes:**

* Graceful degradation
* Defensive programming
* Fail-safe defaults

---

### 🔍 12. Observability

* Easy to monitor and debug

**Pillars:**

* Logs
* Metrics
* Traces

**Tools:**

* Monitoring systems (Prometheus, Grafana)

---

### ⚖️ 13. Consistency

* Predictable behavior and structure

**Applies to:**

* UI patterns
* API design
* Code style

---

### 🧬 14. Reusability

* Components can be reused across projects

**Achieved by:**

* Abstraction
* Libraries / shared modules
* DRY principle

---

### 🧩 Quality Models (Quick Reference)

#### ISO/IEC 25010

* Functional suitability
* Reliability
* Performance efficiency
* Usability
* Security
* Compatibility
* Maintainability
* Portability

#### FURPS

* **F**unctionality
* **U**sability
* **R**eliability
* **P**erformance
* **S**upportability

---

### 🛠️ Golden Rules

* ✅ “Make it work → Make it right → Make it fast”
* ✅ Test early, test often
* ✅ Automate everything possible
* ✅ Measure before improving
* ✅ Keep it simple (KISS)
* ✅ Avoid duplication (DRY)
* ✅ Design for change

## 🧪 $${\color{red}Testing \ Cheat \ Sheet}$$

### Testing Levels
- **Unit Testing**
  - Tests individual functions/classes
  - Fast, isolated, no external dependencies
- **Integration Testing**
  - Tests interaction between modules/services
  - DB, APIs, external services involved
- **System Testing**
  - Tests whole application as a system
- **Acceptance Testing (UAT)**
  - Verifies business requirements
  - Often written in business language (BDD)

---

### Testing Types
- **Functional Testing** – correctness of features
- **Non-Functional Testing**
  - Performance
  - Security
  - Usability
  - Accessibility
- **Regression Testing** – ensures existing functionality still works
- **Smoke Testing** – critical path verification
- **Sanity Testing** – quick verification after changes
- **Exploratory Testing** – unscripted, manual testing
- **Mutation Testing** – validates test quality

---

### Test Design Techniques
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Tables
- State Transition Testing
- Pairwise Testing
- Error Guessing

---

### Unit Test Best Practices
- **AAA Pattern**
  - Arrange
  - Act
  - Assert
- One assertion per test (recommended)
- Tests should be:
  - Deterministic
  - Independent
  - Fast
- Avoid:
  - Shared state
  - Real network calls
  - Real databases

---

### Mocking & Stubbing
- **Mock** – verifies behavior (method calls)
- **Stub** – returns predefined data
- **Fake** – lightweight implementation
- Common tools:
  - Jest
  - Mockito
  - Sinon
  - PHPUnit mocks

---

### Test Coverage
- Statement coverage
- Branch coverage
- Function/method coverage
- Line coverage
- ⚠ High coverage ≠ good tests
- Focus on:
  - Critical logic
  - Edge cases
  - Business rules

---

### Common Test Smells 🚨
- Flaky tests
- Over-mocking
- Testing implementation details
- Large setup blocks
- Order-dependent tests

---

### BDD (Behavior-Driven Development)
- **Given** – context
- **When** – action
- **Then** – expected outcome
- Tools:
  - Cucumber
  - Behat
  - SpecFlow

---

### Performance Testing
- Load Testing
- Stress Testing
- Spike Testing
- Tools:
  - JMeter
  - k6
  - Gatling

---

### Security Testing
- Input validation
- Authentication & authorization
- CSRF / XSS / SQL Injection
- Dependency vulnerability scanning
- Tools:
  - OWASP ZAP
  - Snyk
  - Dependabot

---

### CI/CD Testing Flow
1. Linting
2. Unit tests
3. Integration tests
4. Build
5. End-to-end tests
6. Deployment
7. Monitoring

---

### End-to-End (E2E) Testing
- Tests real user flows
- High confidence, slower execution
- Tools:
  - Cypress
  - Playwright
  - Selenium

---

### Test Case Structure
- Test ID
- Preconditions
- Steps
- Expected Result
- Actual Result
- Status
- Priority

---


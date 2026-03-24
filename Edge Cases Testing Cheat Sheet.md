## $${\color{red}Edge \ Cases \ Testing \ Cheat \ Sheet}$$

 Edge case is a problem or situation that occurs only at an extreme (maximum or minimum) operating parameter.

### 🔹 1. Input Validation Edge Cases

Test boundaries and unexpected input.

**Numbers**

* `0`, `-1`, `1`
* `INT_MAX`, `INT_MIN`
* Very large numbers (overflow)
* Floating precision (`0.1 + 0.2`)
* Division by zero

**Strings**

* Empty: `""`
* Whitespace: `" "`, `"\n"`
* Very long strings (10k+ chars)
* Special chars: `!@#$%^&*()`
* Unicode / emojis: `"你好"`, `"💥"`
* SQL injection: `' OR 1=1 --`
* XSS: `<script>alert(1)</script>`

**Booleans / Null**

* `null`, `undefined`
* Missing fields
* Wrong types (`"true"` vs `true`)

---

### 🔹 2. Boundary Value Analysis (BVA)

Test **just below, at, and above limits**.

```txt
If valid range = 1–100:
Test → 0, 1, 2, 99, 100, 101
```

Use for:

* Age, price, quantity
* Pagination limits
* String length validation

---

### 🔹 3. Collections & Arrays

* Empty array `[]`
* One item `[x]`
* Max size array
* Duplicate values
* Null values inside array
* Mixed types

---

### 🔹 4. Date & Time Edge Cases

* Leap year (`Feb 29`)
* Timezones differences
* DST changes (missing/repeated hours)
* End/start of:

  * Day (`23:59:59 → 00:00`)
  * Month
  * Year
* Invalid dates (`2025-02-30`)
* Unix epoch (`1970-01-01`)
* Far future dates

---

### 🔹 5. API & Network Edge Cases

* Timeout / slow response
* 4xx / 5xx errors
* Empty response
* Partial data
* Wrong schema
* Rate limiting (429)
* Retry logic
* Duplicate requests (idempotency)

---

### 🔹 6. Authentication & Security

* Invalid credentials
* Expired tokens
* Missing tokens
* Role/permission mismatch
* Session expiration
* CSRF / XSS / injection attempts
* Brute force attempts

---

### 🔹 7. UI / UX Edge Cases

* Empty states (no data)
* Loading states (slow API)
* Error states
* Long text overflow
* Small screens / responsiveness
* Disabled buttons / invalid forms
* Double-click / rapid actions

---

### 🔹 8. Concurrency & Race Conditions

* Multiple users editing same resource
* Simultaneous requests
* Duplicate submissions
* Deadlocks
* Event ordering issues

---

### 🔹 9. File Handling

* Empty file
* Max file size
* Unsupported formats
* Corrupted files
* Same filename upload
* Special characters in filename

---

### 🔹 10. Database Edge Cases

* Null values
* Unique constraint violations
* Large datasets
* Transaction rollback
* Missing relations (foreign keys)
* Migration inconsistencies

---

### 🔹 11. Performance Edge Cases

* High traffic (load testing)
* Large payloads
* Memory leaks
* Slow queries
* Cold start (serverless)

---

### 🔹 12. Business Logic Edge Cases

* Invalid state transitions
* Conflicting rules
* Edge workflows (cancel/refund loops)
* Rounding issues (money 💸)
* Partial completion scenarios

---

### 🔹 13. Localization & Internationalization

* RTL languages
* Long translations
* Currency formats
* Date formats (`MM/DD` vs `DD/MM`)
* Unicode normalization

---

### 🔹 14. Error Handling

* Unexpected exceptions
* Fallback logic
* Logging correctness
* User-friendly messages
* Silent failures

---

### 🔹 15. Common “Forgotten” Edge Cases

* Double form submission
* Browser back button behavior
* Offline mode
* Cache inconsistencies
* Feature flags toggling mid-session
* Version mismatches (API/client)

---

### ⚡ Quick Mental Checklist

Before shipping, ask:

* ❓ What happens if input is **empty / huge / invalid**?
* ❓ What happens at **boundaries**?
* ❓ What if **API fails or is slow**?
* ❓ What if **user clicks twice**?
* ❓ What if **two users act at the same time**?
* ❓ What if **data is missing or corrupted**?

---

### 🧠 Pro Tips

* Use **property-based testing** (e.g., fuzzing)
* Automate edge cases in unit + integration tests
* Log and monitor real-world edge cases (Sentry, logs)
* Reproduce bugs → convert into test cases

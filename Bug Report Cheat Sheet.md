## $${\color{red}🐞 \ Bug \ Report \ Cheat \ Sheet}$$


### **Title**

Short, precise, technical summary of the defect. Should describe *what* is broken and *where*.

---

### **Description / Summary**

High-level explanation of the problem, including its impact on the system or user.

---

### **Steps to Reproduce (STR)**

Clear, ordered, and deterministic steps required to reproduce the issue from a clean state.

---

### **Expected Result (ER)**

How the system is supposed to behave according to requirements or specifications.

---

### **Actual Result (AR)**

What the system actually does when the steps are executed.

---

### **Environment**

Context in which the issue occurs:

* OS
* Browser / device
* Application version
* Runtime (Node, PHP, JVM, etc.)
* Database / API version

---

### **Error Details / Logs**

Technical diagnostics:

* error messages
* stack traces
* console output
* HTTP status codes

---

### **Reproducibility**

Frequency and conditions of occurrence:

* always
* intermittent
* specific edge cases only

---

### **Severity**

Technical impact on the system:

* **Blocker** – prevents further testing or usage
* **Critical** – data loss or system crash
* **Major** – core functionality broken
* **Minor** – limited impact
* **Trivial** – cosmetic issue

---

### **Priority**

Business urgency of the fix:

* **P0** – immediate fix required
* **P1** – high priority
* **P2** – medium priority
* **P3/P4** – low priority

---

### **Affected Component / Module**

Specific subsystem, service, feature, or layer involved.

---

### **Regression**

Indicates whether the issue appeared after a change:

* Yes / No / Unknown
  (Optional: reference version or commit)

---

### **Workaround**

Temporary method to avoid or mitigate the issue until fixed.

---

### **Attachments**

Supporting materials:

* screenshots
* screen recordings
* HAR files
* request/response dumps

---

### **Related Issues / References**

Links to:

* related tickets
* pull requests
* commits
* documentation

---

### Quality Check

A bug report is complete if:

* the issue can be reproduced without clarification
* expected vs actual behavior is unambiguous
* enough technical context is provided to debug


### 🐞 Universal Bug Report Template (Copy-Paste)

```md
## Title
[Clear, technical summary of the issue]

## Description
[Brief explanation of what is broken and its impact]

## Steps to Reproduce (STR)
1.
2.
3.

## Expected Result
[What should happen]

## Actual Result
[What actually happens]

## Environment
- OS:
- Browser / Device:
- App Version:
- Runtime (Node/PHP/JVM/etc.):
- Database / API:

## Error Details / Logs
[Error messages, stack traces, HTTP status codes]

## Reproducibility
[Always / Intermittent / Specific conditions]

## Severity
[Blocker / Critical / Major / Minor / Trivial]

## Priority
[P0 / P1 / P2 / P3 / P4]

## Affected Component
[Module / Feature / Service]

## Regression
[Yes / No / Unknown | Version / Commit]

## Workaround
[Temporary solution if available]

## Attachments
[Screenshots / Videos / HAR / Dumps]

## Related Issues / References
[Linked tickets, PRs, commits, docs]
```

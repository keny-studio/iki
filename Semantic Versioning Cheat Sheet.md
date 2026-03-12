## $${\color{red}SemVer \ - \ Semantic \ Versioning \ Cheat Sheet}$$

SemVer is a widely adopted, standardized 3-part numbering system used to communicate the nature of software changes.

### 1️⃣ Version Format

```
MAJOR.MINOR.PATCH
```

Example:

```
2.4.1
```

| Part      | When It Changes  | Meaning                           |
| --------- | ---------------- | --------------------------------- |
| **MAJOR** | Breaking changes | Incompatible API changes          |
| **MINOR** | New features     | Backward-compatible functionality |
| **PATCH** | Bug fixes        | Backward-compatible fixes         |

---

### 2️⃣ Version Increment Rules

| Change Type     | Example                      | Version Change  |
| --------------- | ---------------------------- | --------------- |
| Bug fix         | Fix typo or small bug        | `1.2.3 → 1.2.4` |
| New feature     | Add new function             | `1.2.3 → 1.3.0` |
| Breaking change | Remove function / change API | `1.2.3 → 2.0.0` |

---

### 3️⃣ Pre-Release Versions

Used for testing before stable release.

Format

```
MAJOR.MINOR.PATCH-identifier
```

Examples

```
1.0.0-alpha
1.0.0-beta
1.0.0-rc.1
```

Common identifiers:

| Tag                        | Meaning                               |
| -------------------------- | ------------------------------------- |
| **alpha**                  | Early development                     |
| **beta**                   | Feature complete but may contain bugs |
| **rc** (release candidate) | Almost ready for production           |

Example flow:

```
1.0.0-alpha → 1.0.0-beta → 1.0.0-rc.1 → 1.0.0
```

---

### 4️⃣ Build Metadata

Extra build information (ignored when comparing versions).

Format

```
MAJOR.MINOR.PATCH+metadata
```

Example

```
1.4.2+20260310
1.4.2+build.45
```

---

### 5️⃣ Dependency Version Constraints

Common in **npm, composer, pip**.

| Symbol | Meaning          | Example   |
| ------ | ---------------- | --------- |
| `=`    | Exact version    | `=1.2.3`  |
| `>`    | Greater than     | `>1.2.3`  |
| `>=`   | Greater or equal | `>=1.2.3` |
| `<`    | Less than        | `<2.0.0`  |
| `<=`   | Less or equal    | `<=1.2.3` |

---

### 6️⃣ Caret (^) — Compatible Updates

Allows **non-breaking updates**.

```
^1.2.3
```

Allows:

```
1.2.3 → 1.9.9
```

But NOT:

```
2.0.0
```

Rule:

```
^MAJOR.MINOR.PATCH → <(MAJOR+1).0.0
```

---

### 7️⃣ Tilde (~) — Patch Updates

```
~1.2.3
```

Allows:

```
1.2.3 → 1.2.9
```

But NOT:

```
1.3.0
```

Rule:

```
~1.2.3 → <1.3.0
```

---

### 8️⃣ Version Ranges

Example:

```
>=1.2.0 <2.0.0
```

Meaning:

```
1.2.0 up to but not including 2.0.0
```

---

### 9️⃣ Real Examples

#### npm

```json
"react": "^18.2.0"
```

#### Composer (PHP)

```json
"laravel/framework": "^10.0"
```

#### Docker tags

```
node:20.11.0
node:20
```

---

### 🔟 Release Strategy Example

```
0.9.0   Initial beta
1.0.0   First stable release
1.1.0   New feature
1.1.1   Bug fix
2.0.0   Breaking API change
```

---

### 1️⃣1️⃣ Quick Decision Guide

| Situation           | Version                  |
| ------------------- | ------------------------ |
| Bug fix             | PATCH                    |
| New feature         | MINOR                    |
| Breaking change     | MAJOR                    |
| Pre-release testing | `-alpha`, `-beta`, `-rc` |

---

### 1️⃣2️⃣ Common Developer Rules

- Start development with `0.x.x`
- Release `1.0.0` when API is stable
- Never modify a released version
- Always bump version when publishing


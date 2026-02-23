## $${\color{red}Changelog \ Cheat \ Sheet}$$

A **changelog** is a structured, chronological list of notable changes for each version of a project.

---

### 🧱 Standard Format

Most projects follow the format from:

* Keep a Changelog
* Semantic Versioning (SemVer)

---

### 🏷️ Versioning (SemVer)

Format:

```
MAJOR.MINOR.PATCH
```

Example:

```
2.4.1
```

### Rules

| Version   | When to bump                       |
| --------- | ---------------------------------- |
| **MAJOR** | Breaking changes                   |
| **MINOR** | New features (backward compatible) |
| **PATCH** | Bug fixes                          |

---

### 📝 Changelog Structure

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog.
This project adheres to Semantic Versioning.

## [1.4.0] - 2026-02-19

### Added
- New payment gateway integration
- Dark mode support

### Changed
- Updated validation logic for forms

### Deprecated
- Old REST v1 endpoints

### Removed
- Legacy jQuery dependency

### Fixed
- Login race condition bug

### Security
- Patched XSS vulnerability in comments
```

---

### 📂 Standard Sections

Use these headings consistently:

### ➕ Added

New features.

### 🔄 Changed

Changes in existing functionality.

### ⚠️ Deprecated

Soon-to-be removed features.

### ❌ Removed

Removed features.

### 🐛 Fixed

Bug fixes.

### 🔐 Security

Vulnerability fixes.

---

### 🚀 Pre-release Tags

Examples:

```
1.5.0-alpha
1.5.0-beta
1.5.0-rc.1
```

Used for:

* Testing releases
* CI builds
* Staging deployments

---

### 🧠 Best Practices

### ✅ Be human-readable

Write for developers and stakeholders.

Bad:

```
fix issue
```

Good:

```
Fixed memory leak in image processing pipeline
```

---

### ✅ Group logically

Do not mix fixes with features.

---

### ✅ One version per release

Do not edit old versions — append new ones.

---

### ✅ Link issues / PRs

Example:

```markdown
- Fixed crash on login (#342)
- Added caching layer (#410)
```

---

### ✅ Keep Unreleased Section

```markdown
## [Unreleased]
### Added
- Experimental GraphQL endpoint
```

Move items to a version on release.

---

### 🛠️ Automation Tips

You can generate changelogs using:

* Conventional Commits
* commitlint
* release-it
* semantic-release
* GitHub Releases auto-generation

---

### 🧾 Conventional Commit Mapping

| Commit Prefix    | Changelog Section  |
| ---------------- | ------------------ |
| feat:            | Added              |
| fix:             | Fixed              |
| refactor:        | Changed            |
| perf:            | Changed            |
| docs:            | Documentation only |
| chore:           | Internal changes   |
| BREAKING CHANGE: | Major version bump |

Example:

```
feat(auth): add OAuth2 login
fix(api): prevent null pointer crash
```

---

### 📦 Git Tagging

```bash
git tag -a v1.4.0 -m "Release 1.4.0"
git push origin v1.4.0
```

---

### 🏗️ Monorepo Strategy

Options:

* Single global changelog
* Per-package changelogs
* Auto-generated per workspace

Tools:

* Lerna
* Nx
* Changesets

---

### 📄 Where to Put It?

* Root directory
* File name: `CHANGELOG.md`
* Keep it version-controlled

---

### 🎯 Enterprise Tip

For production systems:

* Add migration notes
* Document DB changes
* Mention API contract updates
* Mark breaking changes clearly

Example:

```markdown
### BREAKING CHANGES
- Renamed `/users` endpoint to `/accounts`
- Removed support for API v1
```

---

### ⚡ Minimal Template (Copy-Paste)

```markdown
# Changelog

## [Unreleased]

### Added
-
### Changed
-
### Fixed
-

---

## [1.0.0] - YYYY-MM-DD

### Added
- Initial release
```


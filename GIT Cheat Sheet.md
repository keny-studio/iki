## $${\color{red}GIT \ Cheat \ Sheet}$$

Git = Distributed Version Control System 


### 🔹 1. Setup & Config

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list
```

Set default branch name:

```bash
git config --global init.defaultBranch main
```

---

### 🔹 2. Repository Basics

### Initialize repo

```bash
git init
```

### Clone repo

```bash
git clone <url>
git clone <url> <folder-name>
```

---

### 🔹 3. File Lifecycle

Working Directory → Staging Area → Repository

### Check status

```bash
git status
```

### Add files

```bash
git add file.txt
git add .
git add -A
```

### Remove file

```bash
git rm file.txt
```

### Move/Rename

```bash
git mv old.txt new.txt
```

---

### 🔹 4. Commits

### Commit staged changes

```bash
git commit -m "Message"
```

### Commit all tracked changes

```bash
git commit -am "Message"
```

### Amend last commit

```bash
git commit --amend
```

---

### 🔹 5. Viewing History

```bash
git log
git log --oneline
git log --graph --all --decorate
git show <commit>
```

---

### 🔹 6. Branching

### List branches

```bash
git branch
git branch -a
```

### Create branch

```bash
git branch feature/login
```

### Switch branch

```bash
git checkout feature/login
```

Modern alternative:

```bash
git switch feature/login
git switch -c feature/new
```

### Delete branch

```bash
git branch -d branch-name
git branch -D branch-name
```

---

### 🔹 7. Merging

```bash
git merge branch-name
```

Abort merge:

```bash
git merge --abort
```

---

### 🔹 8. Rebasing

```bash
git rebase main
git rebase -i HEAD~3
```

Abort rebase:

```bash
git rebase --abort
```

---

### 🔹 9. Remote Repositories

### Add remote

```bash
git remote add origin <url>
```

### View remotes

```bash
git remote -v
```

### Push

```bash
git push origin main
```

Set upstream:

```bash
git push -u origin main
```

### Pull

```bash
git pull
git pull origin main
```

### Fetch

```bash
git fetch
```

---

### 🔹 10. Undoing Things

### Restore working directory file

```bash
git restore file.txt
```

### Unstage file

```bash
git restore --staged file.txt
```

### Reset commit (soft/mixed/hard)

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

### Revert commit (safe for shared history)

```bash
git revert <commit>
```

---

### 🔹 11. Stashing

```bash
git stash
git stash list
git stash pop
git stash apply
git stash drop
```

---

### 🔹 12. Tags

```bash
git tag
git tag v1.0.0
git tag -a v1.0.0 -m "Release"
git push origin v1.0.0
```

---

### 🔹 13. .gitignore

Ignore files:

```
node_modules/
.env
dist/
*.log
```

---

### 🔹 14. Useful Power Commands

```bash
git diff
git diff --staged
git blame file.txt
git reflog
git cherry-pick <commit>
git clean -fd
```

---

### 🔹 15. Typical Workflow

```bash
git clone <repo>
git checkout -b feature/xyz
git add .
git commit -m "Add feature"
git push -u origin feature/xyz
```

---

### 🔹 16. Common Aliases

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.cm commit
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --decorate --all"
```

---

### 🧩 Git Concepts (Quick Definitions)

| Term   | Meaning                    |
| ------ | -------------------------- |
| HEAD   | Current commit pointer     |
| Index  | Staging area               |
| Commit | Snapshot of changes        |
| Branch | Movable pointer to commits |
| Merge  | Combine histories          |
| Rebase | Reapply commits            |
| Origin | Default remote name        |

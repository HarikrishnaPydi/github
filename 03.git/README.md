## 🔁 Q1: What is the difference between `git add .` and `git add *`?

| Command | Behavior |
|--------|----------|
| `git add .` | Adds all changes (new + modified files) **recursively** from the current directory |
| `git add *` | Adds all files in the current directory (non-hidden), **but skips** deleted files and subdirectories |

> ✅ Use `git add .` in most DevOps scenarios — it’s safer and includes everything recursively.

---

## 🧹 Q2: How to remove **untracked files** from the working directory?

```bash
git clean -n    # Dry run – shows which files will be deleted
git clean -f    # Forcefully deletes untracked files
```

> ⚠️ This **only removes untracked (new) files**, not modified tracked files.

---

## 🔄 Q3: Is it possible to move files from staging area to working directory?

```bash
git reset              # Moves all staged files back to working area
git reset <filename>   # Moves only the specified file
```

> 🔙 Useful when you staged something by mistake and want to edit again.

---

## ⏪ Q4: Due to a bad commit, the application is not working. How to revert it?

```bash
git revert <commit-id>
```

- This creates a **new commit** that reverses the changes of the given commit.
- ✅ **Safe for remote repos** (does not delete history).

---

## 🚫 Q5: How to delete updated code in the **remote repository**?

- First delete or roll back changes in your **local repository**
- Then push to remote to overwrite:

```bash
git push origin master
```

> ✅ This works only if the local branch reflects the correct state.

---

## ⚖️ Q6: Difference between `git reset` and `git revert`?

| Command | Description |
|---------|-------------|
| `git reset` | Moves files from **staging → working** area (does not affect history) |
| `git revert` | Creates a **new commit** that cancels the effect of a bad commit (history-safe) |

---

## 🚫 Q7: What is a `.gitignore` file?

A `.gitignore` file tells Git **which files or patterns to ignore** (not track).

### Example:
```
*.log
.env
backup/
```

> 💡 Useful to skip config files, secrets, IDE files, etc.

---

## 🔍 Bonus Real-Time Git Tips

### ✔️ View status of working and staged files:
```bash
git status
```

### ✔️ See commit history:
```bash
git log --oneline --graph --all
```

### ✔️ Undo last local commit but keep changes:
```bash
git reset --soft HEAD~1
```

### ✔️ Remove a file from staging:
```bash
git reset HEAD <file>
```

---

## 💼 Real-Time Use Case

**Scenario**: You committed credentials to GitHub by mistake.

### Solution:
```bash
git reset --soft HEAD~1
vi filename     # remove sensitive info
git commit -am "remove credentials"
git push --force
```

> ⚠️ Use `--force` carefully. Never do this on shared branches unless you know what you're doing.

---


```

---


Here’s your content formatted as a clean, professional **`.md` (Markdown)** file, with headings, subheadings, and code blocks for clarity:

---

```markdown
# Git Best Practices

- ❌ Don't commit your code in the middle of work.
- ✅ Commit your code **only when everything is ready**.
- ✅ **Test your code** before committing.
- ✅ Use **clear, meaningful commit messages**, e.g.:
```

JIRA-165: Updated pom.xml to include new plugin

````
- 🤝 Avoid merge conflicts by **communicating with your team**.
- 🚫 Avoid blind merging — **always raise a Pull Request (PR)**.
- 👀 Monitor branches closely — if a branch is not needed, **delete it with proper lead approval**.
- 🧹 **Delete stashes** if they are no longer required.

---

# Git Clone Command

The `git clone` command creates a local copy of a remote Git repository and sets up a tracking connection.

### Steps:
1. Create a folder on the Desktop.
2. Navigate into the folder.
3. Run:  
 ```bash
 git clone <repo-url>
````

✅ This will bring both the **code** and **Git config**.
4\. Create a staging branch and start working.

**Note:** The default remote alias is `origin`.

Check remotes:

```bash
git remote -v
```

---

# Git Merging Strategy

## 1. Fast-Forward Merge

### Description:

If no new commits are made to the target branch, Git moves the branch pointer forward.

### Before:

```
A --- B --- C  (master)
         \
          D --- E  (feature)
```

### After:

```
A --- B --- C --- D --- E  (master, feature)
```

> ✅ Simple linear history. No merge commit.

---

## 2. Recursive Merge (Three-Way Merge)

### Description:

Used when both branches have diverged. Git creates a new merge commit.

### Before:

```
A --- B --- C  (master)
         \
          D --- E  (feature)
```

### After:

```
A --- B --- C --------- M  (master)
         \           /
          D --- E ---   (feature)
```

> 🧠 Merge commit `M` combines both changes and preserves branch history.

---

## 3. Rebase

### Description:

Rewrites history by placing feature commits on top of the latest master commit.

### Before:

```
A --- B --- C  (master)
         \
          X --- Y --- Z  (feature)
```

### After (after `git rebase master` on feature branch):

```
A --- B --- C --- X' --- Y' --- Z'  (feature)
```

> 📜 Cleaner, linear history — **use with care** to avoid history rewriting issues.

---

# Git Cherry-Pick

Use this to **apply a specific commit** from one branch to another:

```bash
git cherry-pick <commit-hash>
```

> Useful for merging **only selected changes**.

---

# Git Pull vs Git Fetch

## Git Fetch

Fetches changes from remote without merging.

```bash
git fetch origin test
git merge origin/test
```

## Git Pull

Fetches and merges in one command:

```bash
git pull origin test
```

> `git pull = git fetch + git merge`

---

# How to Change the Most Recent Commit Message?

### Option 1 (Inline):

```bash
git commit --amend -m "New commit message"
```

### Option 2 (Opens editor):

```bash
git commit --amend
```

Then update and save the message.

> ⚠️ To reflect this on the remote:

```bash
git push --force
```

---

```

Would you like me to generate a PDF version of this Markdown as well?
```

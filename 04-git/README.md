Here's your content formatted into a clean and professional `.md` (Markdown) file. You can use this in your GitHub README, documentation, or blog post:

---

````markdown
# Git Branching and Merging Guide

## Environments and Branch Mapping

| Branch Name      | Environment      |
|------------------|------------------|
| `dev`            | Development      |
| `stg`            | QA (Staging)     |
| `master`         | Production       |
| `release`        | Production       |
| `feature/*`      | Feature/Dev Work |

> **Note:** By default, we have a `master` branch. Do **not** push code directly to the `master` branch.

---

## Common Git Branch Commands

### How to list branch names
```bash
git branch
````

### How to create a branch

```bash
git branch <branch-name>
```

### How to switch branches

```bash
git checkout <branch-name>
```

### Create and switch to a new branch in one command

```bash
git checkout -b <branch-name>
```

---

## Merging Concept Explained

1. **Checkout to `development` from `master`:**

   ```bash
   git checkout development
   ```

   > Dev branch usually has all files from `master` if created from `master`.

2. **Update a file in `development`, then commit:**

   ```bash
   git add <file>
   git commit -m "Updated file in dev"
   ```

3. **Switch back to `master` and verify changes:**

   ```bash
   git checkout master
   ```

4. **See differences between `master` and `development`:**

   ```bash
   git diff development
   ```

5. **Merge `development` into `master`:**

   ```bash
   git merge development
   ```

6. **Verify that the file is merged.**

---

## Merge Conflict

**Occurs when two developers update the same file and the same line.**

### Steps:

1. Update and commit a file in `master`.
2. Update the same file in `development` and commit.
3. Switch to `master` and merge `development`:

   ```bash
   git merge development
   ```
4. Resolve the conflict manually, remove unused lines, then:

   ```bash
   git add <conflicted-file>
   git commit -m "Resolved merge conflict"
   ```

---

## Remote Branch Operations

### Push specific branches to remote

```bash
git push <alias> branch1 branch2
```

### Push all branches to remote

```bash
git push <alias> --all
```

### Create a remote branch

> Go to your remote repository (e.g., GitHub/GitLab) and create it manually.

### Pull latest changes from a remote branch

```bash
git pull <alias> <branch-name>
```

### View remote branches

```bash
git branch -r
```

### View all branches (local + remote)

```bash
git branch -a
```

---

## Branch Management

### Rename a local branch

```bash
git branch -m old-name new-name
```

### Delete a local branch

```bash
git branch -d <branch-name>
```

> Note: You cannot delete the branch you're currently on.

### Delete a remote branch from local

```bash
git push <alias> :<branch-name>
```

> Example:
>
> ```bash
> git push origin :feature-xyz
> ```

---

```

Would you like a downloadable `.md` file version of this?
```

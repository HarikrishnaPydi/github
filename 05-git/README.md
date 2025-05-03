Here's your content in clean and well-structured **Markdown (.md)** format, suitable for documentation, blogs, or GitHub README files:

---

````markdown
# Git: Branch vs Tag, Stash Usage, and Cleanup Tips

## 🔀 Branch vs Tag

### 📌 Branch
- **Mutable**: Can be updated or deleted.
- **Used during development.**
- **Branches can be created from other branches.**

#### 🔧 Common Branch Commands
```bash
# List all branches
git branch

# Create a new branch
git branch <branch-name>

# Push branch to remote
git push <remote-alias> <branch-name>

# Push all branches to remote
git push <remote-alias> --all

# Delete a local branch
git branch -d <branch-name>
````

---

### 🏷️ Tag

* **Immutable**: Once created, it doesn’t change.
* **Usually created after production deployment.**
* **Tags are typically created from the `master/main` branch.**

#### 🔧 Common Tag Commands

```bash
# List all tags
git tag

# Create a new tag
git tag <tag-name>  # Example: git tag Airtel_V1.0.0

# Push a specific tag to remote
git push <remote-alias> <tag-name>

# Push all tags
git push <remote-alias> --tags

# Delete a tag
git tag -d <tag-name>
```

### Example Tag Workflow

```bash
# Step 1: Check existing tags
git tag

# Step 2: Create a tag from master
git tag Airtel_V1.0.0  # Format: major.minor.patch

# Step 3: Confirm the tag
git tag

# Step 4: Push to remote
git push airtel Airtel_V1.0.0
```

> 💡 NOTE: Tags show up as downloadable `.zip` and `.tar.gz` files in most Git GUIs like GitHub or GitLab.

---

## ❓ IQ: How to Create a Tag in Remote Repository (via GitHub/GitLab UI)?

1. Go to **Tags → Create Release**.
2. Enter the **tag name**, e.g., `V1.0.0`.
3. Select the target branch (e.g., `main`).
4. Add optional release notes.
5. Click **Publish/Save**.

---

## 🧰 Git Stash – Real-Time Use Case

> You’re working on the `dev` branch, and suddenly need to switch to `master` to fix a production issue.

### ✅ Steps:

```bash
# Step 1: Backup current changes with a name
git stash save "login feature"

# Step 2: View all stash entries
git stash list
# Output: stash@{0}: On dev: login feature

# Step 3: Switch to master, fix the issue
git checkout master
# Make and commit changes

# Step 4: Switch back to dev and reapply the stash
git checkout dev
git stash apply stash@{0}
```

---

## ❓ IQ: My Local Repo Size is Increasing. What Should I Do?

### 🧹 Clean Up Old or Unused Stashes

```bash
# Delete the most recent stash
git stash drop

# Delete a specific stash by index
git stash drop stash@{5}

# Apply and delete at once
git stash pop

# Clear all stash entries
git stash clear
```

---

## 🔄 How to Restore Changes in the Working Area?

> Scenario: You made unwanted changes to a file in your working area.

### ✅ Steps:

```bash
# Restore the original file from last commit
git restore <file-name>
```

---

```

Would you like this exported as a downloadable `.md` file or need a PDF version as well?
```

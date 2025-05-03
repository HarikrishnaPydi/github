Here's your Git interview questions document in **Markdown (.md)** format:

```markdown
# Git Interview Questions

These questions cover various aspects of Git and GitHub and test knowledge about handling common scenarios. They also evaluate the depth of understanding of workflows, problem-solving techniques, and best practices.

---

### 1. What is the difference between `git pull` and `git fetch`?

**Explanation:**  
- `git fetch` retrieves new data from a remote repository without merging it into your working directory.  
- `git pull` fetches the data and automatically merges it into your current branch.

---

### 2. What does `git merge` do and how is it different from `git rebase`?

**Explanation:**  
- `git merge` combines the histories of two branches, creating a new commit.  
- `git rebase` moves or combines a sequence of commits to a new base commit, resulting in a linear history.

---

### 3. How would you handle a conflict during a merge?

**Explanation:**  
- Git marks files with conflicts. Manually resolve conflicts by editing the files, removing conflict markers, and staging them using `git add <file>`. Then commit the merge.

---

### 4. You’ve committed some code, but now you want to change the commit message. How can you do that?

**Explanation:**  
- Use `git commit --amend` to change the most recent commit message. If the commit was pushed, use `git push --force`.

---

### 5. How would you revert a commit that has already been pushed to the remote repository?

**Explanation:**  
- Use `git revert <commit>` to create a new commit that undoes the changes. This is safe for shared repositories.

---

### 6. Explain what a fast-forward merge is.

**Explanation:**  
- A fast-forward merge happens when the current branch is directly ahead of the branch being merged, so no new merge commit is needed.

---

### 7. What does `git reset --hard` do?

**Explanation:**  
- Resets the working directory and staging area to a specified commit, discarding all changes.

---

### 8. How would you undo a commit that has been added to the staging area but not yet committed?

**Explanation:**  
- Use `git reset` to unstage. `git reset <file>` for specific files or `git reset` to unstage all.

---

### 9. What’s the difference between `git stash` and `git commit`?

**Explanation:**  
- `git stash` temporarily stores uncommitted changes.  
- `git commit` saves changes permanently in the local repository.

---

### 10. How would you undo a `git pull`?

**Explanation:**  
- Use `git reset --hard HEAD~1` to reset to the commit before the pull (if it's a single merge commit).

---

### 11. What are the differences between a Git branch and a Git tag?

**Explanation:**  
- A branch tracks development, while a tag marks a specific point in history (e.g., a release).

---

### 12. How do you create a new branch in Git?

**Explanation:**  
- Use `git branch <branch-name>` to create.  
- Or `git checkout -b <branch-name>` to create and switch.

---

### 13. What is the purpose of `.gitignore`?

**Explanation:**  
- Specifies files and directories to ignore in version control (e.g., logs, temp files).

---

### 14. How can you see which files have been modified in your working directory?

**Explanation:**  
- Use `git status`.

---

### 15. What is a pull request in GitHub?

**Explanation:**  
- A pull request proposes changes for review and merge into the main branch.

---

### 16. How would you merge a pull request on GitHub?

**Explanation:**  
- Go to the pull request, review, and click "Merge pull request".

---

### 17. Explain how you can squash commits in Git.

**Explanation:**  
- Use `git rebase -i <commit-hash>` and change `pick` to `squash` or `fixup`.

---

### 18. What is a GitHub fork?

**Explanation:**  
- A fork creates a personal copy of another user’s repository on GitHub.

---

### 19. Explain the difference between `git clone` and `git fork`.

**Explanation:**  
- `git clone` creates a local copy.  
- `git fork` creates a copy on GitHub you can freely edit and later clone.

---

### 20. How would you delete a branch both locally and remotely?

**Explanation:**  
- Local: `git branch -d <branch-name>`  
- Remote: `git push origin --delete <branch-name>`

---

### 21. How would you create a remote repository on GitHub and link it to your local repository?

**Explanation:**  
- Create on GitHub → `git remote add origin <url>` → `git push -u origin <branch-name>`

---

### 22. What is the difference between `git diff` and `git status`?

**Explanation:**  
- `git diff` shows file differences.  
- `git status` shows the state of the working directory and staging area.

---

### 23. How do you handle a situation where a pull request has conflicts that cannot be automatically resolved?

**Explanation:**  
- Pull changes, manually resolve conflicts, commit, and push updates to the pull request.

---

### 24. What are submodules in Git?

**Explanation:**  
- A submodule is a repository embedded inside another. Useful for managing dependencies.

---

### 25. What is the difference between `git log` and `git reflog`?

**Explanation:**  
- `git log` shows commit history.  
- `git reflog` shows reference history (e.g., HEAD movements).

---

### 26. What happens when you run `git push --force`?

**Explanation:**  
- It forcefully updates the remote, potentially overwriting others' work.

---

### 27. What are Git tags and when would you use them?

**Explanation:**  
- Tags mark specific points in history, typically used for releases (e.g., v1.0.0).

---

### 28. What is the difference between `git pull` and `git fetch` in terms of the local repository?

**Explanation:**  
- `git fetch` updates references without modifying files.  
- `git pull` fetches and merges into the working directory.

---

### 29. How do you undo the last commit in Git?

**Explanation:**  
- `git reset --soft HEAD~1` keeps changes in staging.  
- `git reset --hard HEAD~1` discards changes.

---

### 30. How can you manage multiple remotes in Git?

**Explanation:**  
- Add with `git remote add <name> <url>`  
- View with `git remote -v`  
- Push with `git push <remote> <branch>`
```

Would you like this saved as a downloadable `.md` file?

Here's your cleaned-up and organized version of the notes in `.md` (Markdown) format, suitable for a GitHub `README.md` or internal documentation:

---

````markdown
# Git and SSH Key Guide

## Where Are Credentials Stored?

- **Windows**: Credential Manager  
- **Mac**: Keychain Access  
- **Linux**: `~/.ssh/`, environment variables, or credential helpers

---

## SSH Keys

### How to Generate SSH Keys?

```bash
ssh-keygen
````

Keys are stored in:

* `~/.ssh/id_rsa` → Private key
* `~/.ssh/id_rsa.pub` → Public key

### How to Change the Algorithm?

```bash
ssh-keygen -t dsa       # Generates DSA key: id_dsa, id_dsa.pub
ssh-keygen -t rsa       # Generates RSA key: id_rsa, id_rsa.pub
ssh-keygen -t rsa -f ~/.ssh/my_rsa_key  # Custom file name
```

---

### Step-by-Step: SSH Key Generation

```bash
Step 1: ls -la ~/.ssh/             # Check if keys exist
Step 2: cat ~/.ssh/known_hosts     # Display known hosts
Step 3: rm -rf ~/.ssh/known_hosts  # Delete if required
Step 4: ssh-keygen                 # Generate default keys
Step 5: ssh-keygen -t rsa          # Regenerate using RSA
Step 6: ssh-keygen -t rsa -f ~/.ssh/my_rsa_key  # Custom file
Step 7: cat ~/.ssh/id_rsa.pub      # Copy public key
```

### Add SSH Key to GitHub

1. Go to your GitHub **Profile → Settings → SSH and GPG keys**
2. Click **"New SSH key"**
3. Paste the copied public key
4. Click **Save**

### Verify SSH Connection

```bash
ssh -T git@github.com
```

You might be prompted to trust the host because the `known_hosts` file was deleted.

---

## Switching Remote URL to SSH

```bash
Step 10: cd <your-project>
         git remote -v      # Check if it points to HTTPS
Step 11: git remote set-url origin git@github.com:your-org/your-repo.git
```

### Clear Saved GitHub Credentials

* **Windows**: Open *Credential Manager* → Remove GitHub entries
* **Mac**: Open *Keychain Access* → Search and remove GitHub keys

### Push Your Code

```bash
git push <alias> <branch-name>
```

---

## Branching Strategy

### Create a New Branch from Master Without Switching

```bash
# While on 'stage' branch
git checkout -b uat master
```

---

## Pull Request (PR)

* Always raise a PR for merging.
* Avoid direct (blind) merges.
* Ensure PR is reviewed and approved.

---

## Best Practices

* ✅ **Do not commit incomplete code**

* ✅ **Commit only when the work is complete and tested**

* ✅ **Write meaningful commit messages**

  Example:

  ```
  JIRA-165: Updated pom.xml for dependency fix
  ```

* ✅ **Coordinate with team to avoid merge conflicts**

* ✅ **Use feature branches and raise PRs for merging**

* ✅ **Monitor and clean up stale branches (with lead approval)**

* ✅ **Delete stashes that are no longer needed**

---

## README.md File

Maintain a well-structured `README.md` file for every repository with:

* Project overview
* Installation steps
* Usage instructions
* Contributing guidelines
* License info (if any)

---

```

Would you like a visual flowchart for the SSH setup and branching workflow?
```

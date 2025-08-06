# 🛠️ Git & GitHub Setup on macOS (SSH Workflow)

✅ This project documents the full process of setting up Git and GitHub over SSH on **macOS High Sierra (10.13)** using Terminal. It includes both successful steps and mistakes encountered along the way — making it a helpful guide for troubleshooting older systems or understanding Git/GitHub deeper.

---

## ✅ What This Covers

- Checking for existing Git installation
- Generating a secure SSH key
- Adding the SSH key to GitHub
- Setting Git remote URL to SSH
- Handling permission issues
- **Deactivating GitHub branch protection**
- Making local commits
- Pushing directly to GitHub (no pull request needed)

---

## 🔧 Tools & Environment

- 💻 macOS 10.13 High Sierra
- 💬 Terminal (bash)
- 🧰 Git preinstalled (`2.17.2`)
- 🔐 SSH key pair (`ed25519`)
- ☁️ GitHub (public repo)

---

## ⚠️ What Went Wrong

### ❌ 1. Tried Installing Git with Homebrew
- Git was already available (`2.17.2`)
- `brew install git` failed due to unsupported macOS version
- Resolved by using the preinstalled version

### ❌ 2. SSH Key Creation Errors
- Entered command text into the prompt by mistake
- Fixed by deleting malformed files and rerunning `ssh-keygen`

### ❌ 3. GitHub Push Blocked by Branch Protection
- `git push` to `main` failed due to rule:


- Solved by **disabling the branch protection rule**
- **No pull request needed**

---

## ✅ What Worked

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "user@example.com"

# Copy public key
cat ~/.ssh/id_ed25519.pub

# Add it to GitHub: https://github.com/settings/keys

# Point repo remote to SSH
git remote set-url origin git@github.com:username/repo-name.git

# Stage and commit a file
git add somefile.txt
git commit -m "Add somefile.txt"

# Push to GitHub (after disabling branch protection)
git push
  ```

## ✅ Lessons Learned
- macOS often comes with Git already — check git --version first
- Homebrew may not support older macOS versions
- SSH keys must be handled carefully — but are the best long-term solution
- GitHub will block pushes to protected branches unless rules are removed or followed
- Direct push to main is fine for solo projects 

## ✅ Outcome
- Git and GitHub were successfully connected via SSH on an unsupported macOS version.
- This proves that even older systems can be used for secure modern development workflows.

## ✅ Why this repo
This repo can be used as:
- A personal checklist for setting up Git on macOS
- A guide for others working with older Macs
- A public demo of Git/GitHub/SSH workflow mastery 





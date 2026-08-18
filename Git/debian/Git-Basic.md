# Git Basics

## Table Of Contents
- [1. Create / Sign in to GitHub Account](#1-create--sign-in-to-github-account)
- [2. Set Up SSH Connection (Recommended Way)](#2-set-up-ssh-connection-recommended-way)
    * [Step 2.1 – Generate an SSH key (if you don't have one)](#step-21--generate-an-ssh-key-if-you-dont-have-one)
    * [Step 2.2 – Copy your public key to clipboard](#step-22--copy-your-public-key-to-clipboard)
    * [Step 2.3 – Add the public key to GitHub](#step-23--add-the-public-key-to-github)
    * [Step 2.4 – Test the SSH connection](#step-24--test-the-ssh-connection)
    * [Step 2.5 – Switch your repository to use SSH (if it's currently HTTPS)](#step-25--switch-your-repository-to-use-ssh-if-its-currently-https)
- [3. How to Safely Push Changes](#3-how-to-safely-push-changes)
    * [Step 3.1 – Pull latest changes first (very important!)](#step-31--pull-latest-changes-first-very-important)
    * [Step 3.2 – If there are conflicts](#step-32--if-there-are-conflicts)
    * [Step 3.3 – Normal push](#step-33--normal-push)
---

This guide explains how to set up Git, connect to GitHub using **SSH** (recommended), and safely push your changes.

## 1. Create / Sign in to GitHub Account

- Go to https://github.com
- If you don't have an account → click **Sign up** and create one
- If you already have one → **Sign in** using your username/email and password

**Tip**: Enable **two-factor authentication (2FA)** in Settings → Password and authentication for better security.

***[🔝 Table Of Contents](#table-of-contents)***

---

## 2. Set Up SSH Connection (Recommended Way)

Using SSH is better than HTTPS because:
- No need to enter username/token every time
- More secure
- Faster

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 2.1 – Generate a Public SSH key (if you don't have one)

Run this command in your terminal:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Press Enter to accept the default file location (~/.ssh/id_ed25519)

Enter a passphrase (recommended for extra security) or press Enter for none

**Note:** ed25519 is the modern, secure, and recommended key type in 2025–2026. GitHub fully supports it.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 2.2 – Copy your public key to clipboard

#### On Linux / macOS:
```bash
cat ~/.ssh/id_ed25519.pub
```

#### On Windows (Git Bash or WSL):
```bash
cat ~/.ssh/id_ed25519.pub | clip
```

Copy the entire output (starts with ssh-ed25519 ... and ends with your email).

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 2.3 – Add the public key to GitHub

Go to GitHub → click your profile picture (top right) → Settings

In the left sidebar: SSH and GPG keys

Click New SSH key (or Add SSH key)

Give it a descriptive title (e.g. "My Ubuntu Laptop 2026")

Paste the key into the "Key" field

Click Add SSH key

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 2.4 – Test the SSH connection
```bash
ssh -T git@github.com
```
You should see something like:
```bash
Hi NimaAthari99! You've successfully authenticated, but GitHub does not provide shell access.
```
If you see this → SSH is working correctly!

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 2.5 – Switch your repository to use SSH (if it's currently HTTPS)
Check current remote URLs:
```bash
git remote -v
```
If you see https://github.com/... → change it to SSH:
```bash
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

Example:
```bash
git remote set-url origin git@github.com:NimaAthari99/Linux.git
```
Verify again:
```bash
git remote -v
```
You should now see sothing like this:
```bash
origin  git@github.com:NimaAthari99/Linux.git (fetch)
origin  git@github.com:NimaAthari99/Linux.git (push)
```

***[🔝 Table Of Contents](#table-of-contents)***

---

## 3. How to Safely Push Changes
### Step 3.1 – Pull latest changes first (very important!)
Before pushing, always bring your local branch up to date:
```bash
git pull --rebase origin main
```
What does this do?
Downloads the latest commits from GitHub (git fetch); Replays your local commits on top of the newest remote commits; Keeps history clean and linear (no unnecessary merge commits)

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 3.2 – If there are conflicts
If Git says there are conflicts during rebase:

```bash 
Open the conflicting files → fix them manually
Mark them as resolved:

Bashgit add <file>
# or
git add .
```

Continue the rebase:

```bash
git rebase --continue
```

Repeat until finished.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Step 3.3 – Normal push
When everything is ready:
```bash
git push -v
```

The -v (verbose) flag shows more details — very useful when learning.

***[🔝 Table Of Contents](#table-of-contents)***

---

***`NOTE: If want to add current directory as a  project to your gitlab:`***
```bash
git push --set-upstream git@GITLAB_URL:USER/$(git rev-parse --show-toplevel | xargs basename).git $(git rev-parse --abbrev-ref HEAD)                                                         # For example mine is: git push --set-upstream git@gitlab.domain.local:root/$(git rev-parse --show-toplevel | xargs basename).git $(git rev-parse --abbrev-ref HEAD)
```

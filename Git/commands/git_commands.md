# Debian Git Commands

## Git Global

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git config --local user.name "YOUR USER NAME"`                      | Configure your Git identity locally to use it only for this project                           | Git local setup                                     |
| `git config --local user.email "YOUR_EMAIL@gmail.com`                | Configure your Git identity locally to use it only for this project                           | Git local setup                                     |
| `git status`                                                         | Shows which files are changed, staged, or untracked                                           | **Always** — before every commit                    |
| `git log --oneline --graph --all`                                    | Show beautiful history of all branches                                                        | To see the full picture of your project             |
| `git clone git@git.nima.local:voting-app/monorepo-voting-app.git`    | Clone remote repo to your current local directory                                             | Setting up project on local device                  |
| `git commit -m "Clear message"`                                      | Save your staged changes with a message                                                       | After `git add`                                     |
| `git init`                                                           |                                                                                               |                                                     |
| `git init --initial-branch=main --object-format=sha1"`               |                                                                                               |                                                     |
| `git checkout`                                                       |                                                                                               |                                                     |
| `git tag`                                                            |                                                                                               |                                                     |
| `git rebase`                                                         |                                                                                               |                                                     |
| `git reset`                                                          |                                                                                               |                                                     |
| `git reset --hard`                                                   |                                                                                               |                                                     |
| `git reset --mix`                                                    |                                                                                               |                                                     |
| `git reset --soft`                                                   |                                                                                               |                                                     |
| `git revert`                                                         |                                                                                               |                                                     |

## Git Add

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git add .`                                                          | Stage (prepare) **all** new and modified files in current folder                              | Most common way to stage changes                    |
| `git add -u`                                                         | Stage only **modified and deleted** files (ignores completely new files)                      | When you edited or deleted files only               |
| `git add -A`                                                         | Stage **everything** (new, modified, deleted files — even in subfolders)                      | When you added new folders or deleted files         |
| `git add README.md`                                                  | Stage only **`README.md`** file                                                               | Staging only specific file                          |

## Git Remote

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git remote`                                                         | Show git remotes in current git config                                                        | When you want to see git remotes                    |
| `git remote -v`                                                      | Show git remotes in current git config                                                        | When you want to see git remotes                    |
| `git remote add origin git@github.com:USERNAME/REPO.git`             | Add the URL of your "origin" remote (e.g. switch from HTTPS to SSH)                           | When you want to change from HTTPS to SSH           |
| `git remote set-url origin git@github.com:USERNAME/REPO.git`         | Change the URL of your "origin" remote (e.g. switch from HTTPS to SSH)                        | When you want to change from HTTPS to SSH           |
| `git remote rename origin old-origin`                                | Rename a git remote usage name                                                                | Renaming a git remote and clarify it                |

## Git Switch

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git switch main`                                                    | Switch to the main branch                                                                     | Before creating a new branch or pulling             |
| `git switch -c feature/name`                                         | Create a new branch and switch to it                                                          | Every time you start a new task                     |
| `git switch --create main`                                           | Create a new branch and switch to it                                                          | Every time you start a new task                     |

## Git Push

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git push`                                                           | Upload your commits to GitHub (to the current branch)                                         | After commit — sends your work online               |
| `git push origin --delete feature/name`                              | Delete a branch from GitHub (remote)                                                          | Clean up after merging                              |
| `git push nima_projects-github --delete old-production`              | Push changes aand delete old branch                                                           | Changing and deleting old branch                    |
| `git push --set-upstream nima-projects-github main`                  | Try pushing with the specific remote name you used and change main remote                     | Push changes and change git remote                  |
| `git push --set-upstream monorepo-voting-app_gitlab --all`           | Temporarily disable branch protection                                                         | Push to spescific remote                            |
| `git push --set-upstream monorepo-voting-app_gitlab main-force -f`   | Create and push a new branch instead                                                          | Push a new branch                                   |
| `git push --set-upstream origin --tags`                              | Push items with spescific tags                                                                | Push items with spescific tags                      |

## Git Pull

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git pull`                                                           | Download latest changes from GitHub and merge them                                            | Before starting new work                            |
| `git pull --rebase origin main`                                      | Download latest changes and **replay** your commits on top (cleaner history)                  | When you want a very clean linear history           |

## Git Branch

| Command                                                              | What it does                                                                                  | When to use it                                      |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------|
| `git branch`                                                         | List all local branches                                                                       | To see what branches you have                       |
| `git branch -a`                                                      | List all branches (local + remote)                                                            | To see remote branches too                          |
| `git branch -vv`                                                     | Show current branch and changed on it                                                         | To see remote branche and changes                   |
| `git branch -d feature/name`                                         | Delete a local branch **safely** (only if already merged)                                     | After your Pull Request is merged                   |
| `git branch -D feature/name`                                         | Force delete a local branch (even if not merged)                                              | When you want to throw away a branch                |
| `git branch --show-current`                                          | Shows current woorking braanch                                                                | Shows current woorking braanch                      |

## Create a new repository

git clone git@git.nima.local:voting-app/monorepo-voting-app.git
cd monorepo-voting-app
git switch --create main
touch README.md
git add README.md
git commit -m "add README"
git push --set-upstream origin main

## Push an existing Git folder

### Configure the Git repository

git init --initial-branch=main --object-format=sha1
git remote add origin git@git.nima.local:voting-app/monorepo-voting-app.git
git add .
git commit -m "Initial commit"
git push --set-upstream origin main

## Push an existing Git repository

git remote rename origin old-origin
git remote add origin git@git.nima.local:voting-app/monorepo-voting-app.git
git push --set-upstream origin --all
git push --set-upstream origin --tags

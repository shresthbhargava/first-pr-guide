# Git Basics — Commands You Actually Need

> This is not an exhaustive Git reference. It's the commands you'll use in 90% of your open-source contributions, explained in plain language.

---

## Before You Start: Configure Git

Run these once on your machine. Git uses this info for every commit you make.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# Verify your config
git config --list
```

---

## `git clone`

Downloads a repository from GitHub to your local machine.

```bash
git clone https://github.com/USERNAME/REPO_NAME.git
```

This creates a folder called `REPO_NAME` in your current directory with all the files inside.

**Clone into a specific folder name:**
```bash
git clone https://github.com/USERNAME/REPO_NAME.git my-folder
```

**After cloning, move into the folder:**
```bash
cd REPO_NAME
```

> **Common mistake:** Forgetting to `cd` into the cloned folder before running other Git commands.

---

## `git branch`

Branches let you work on changes without affecting the main codebase.

```bash
# See all local branches (current branch has * next to it)
git branch

# See all branches including remote
git branch -a

# Create a new branch
git branch feature/my-new-feature

# Delete a branch (after it's merged)
git branch -d feature/my-new-feature

# Force delete (use carefully)
git branch -D feature/my-new-feature
```

---

## `git checkout`

Switch between branches or create a new branch and switch to it.

```bash
# Switch to an existing branch
git checkout main

# Create a new branch AND switch to it (most common usage)
git checkout -b fix/broken-link-in-readme

# Go back to previous branch
git checkout -
```

> **Modern alternative:** `git switch` does the same thing and is easier to read:
> ```bash
> git switch main
> git switch -c fix/broken-link   # -c = create
> ```
> Both work — use whichever you prefer.

---

## `git add`

Stages your changes — tells Git "include these in my next commit."

```bash
# Stage a specific file
git add README.md

# Stage multiple files
git add README.md CONTRIBUTING.md

# Stage all changed files in current directory
git add .

# Stage parts of a file interactively
git add -p filename
```

**Check what's staged before committing:**
```bash
git status
```

You'll see:
- **Green** = staged (will be included in commit)
- **Red** = modified but not staged (won't be included yet)

---

## `git commit`

Saves a snapshot of your staged changes with a message describing what changed.

```bash
# Basic commit
git commit -m "fix: correct typo in installation guide"

# Add and commit in one step (only for already-tracked files)
git commit -am "fix: correct typo in installation guide"

# Open editor for a longer commit message
git commit
```

**Commit message format:**
```
type: short description (under 72 characters)

Optional longer explanation if the change needs context.
Closes #42
```

**Good commit messages:**
```bash
git commit -m "docs: add Windows installation steps"
git commit -m "fix: handle null response in API call"
git commit -m "feat: add dark mode to settings page"
```

**Bad commit messages:**
```bash
git commit -m "update"          # What was updated? Why?
git commit -m "fix"             # Fix what?
git commit -m "stuff"           # Not useful to anyone
git commit -m "WIP"             # Don't commit work-in-progress to a PR
```

---

## `git push`

Uploads your local commits to GitHub.

```bash
# Push your branch to your fork
git push origin your-branch-name

# First time pushing a new branch (sets tracking):
git push -u origin your-branch-name

# After -u is set, you can just use:
git push
```

> **Note:** You push to YOUR fork (`origin`), not the original repo (`upstream`). You don't have write access to the original.

---

## `git pull`

Downloads and applies the latest changes from a remote branch.

```bash
# Pull latest changes from main
git pull origin main

# Pull from the branch you're currently on
git pull
```

**Safe practice — always pull before starting new work:**
```bash
git checkout main
git pull upstream main
```

---

## `git remote`

Manages connections to remote repositories.

```bash
# See your current remotes
git remote -v

# Add the original repo as "upstream"
git remote add upstream https://github.com/ORIGINAL_OWNER/REPO_NAME.git

# Verify it was added
git remote -v
# origin    https://github.com/YOUR_USERNAME/REPO_NAME.git (fetch)
# origin    https://github.com/YOUR_USERNAME/REPO_NAME.git (push)
# upstream  https://github.com/ORIGINAL_OWNER/REPO_NAME.git (fetch)
# upstream  https://github.com/ORIGINAL_OWNER/REPO_NAME.git (push)
```

---

## `git fetch`

Downloads changes from remote without applying them to your branch.

```bash
# Fetch all changes from upstream
git fetch upstream

# Fetch from a specific branch
git fetch upstream main
```

Use `git fetch` when you want to see what changed remotely before merging.

---

## `git merge`

Combines changes from one branch into another.

```bash
# Merge upstream/main into your current branch
git merge upstream/main

# Merge a feature branch into main
git checkout main
git merge feature/my-feature
```

---

## Resolving Merge Conflicts

A conflict happens when two people changed the same part of the same file. Git doesn't know which version to keep — you have to decide.

**When a conflict happens, you'll see this in the file:**

```
<<<<<<< HEAD
Your version of the line
=======
Their version of the line (from upstream)
>>>>>>> upstream/main
```

**Steps to resolve:**

```bash
# Step 1: See which files have conflicts
git status

# Step 2: Open each conflicted file and edit it
# Remove the conflict markers (<<<<<<<, =======, >>>>>>>)
# Keep the correct version (or combine both)

# Step 3: Stage the resolved file
git add filename.md

# Step 4: Complete the merge
git commit -m "fix: resolve merge conflict in README"
```

**Tools that make conflict resolution easier:**
- VS Code — shows conflicts visually with "Accept Current", "Accept Incoming" buttons
- `git mergetool` — opens a visual diff tool

> **Best prevention:** Sync your fork frequently. The longer you wait, the more likely a conflict.

---

## `git log`

See your commit history.

```bash
# Full log
git log

# Compact one-line view
git log --oneline

# See last 5 commits
git log --oneline -5

# Visual branch graph
git log --oneline --graph --all
```

---

## `git diff`

See what changed before committing.

```bash
# See unstaged changes
git diff

# See staged changes (what's about to be committed)
git diff --staged

# Compare two branches
git diff main feature/my-feature
```

---

## `git stash`

Temporarily saves your uncommitted changes so you can switch branches without losing work.

```bash
# Save your current changes
git stash

# Apply your stashed changes back
git stash pop

# See all stashes
git stash list

# Apply a specific stash
git stash apply stash@{0}
```

**When to use it:** You're in the middle of something, need to quickly fix a bug on another branch, and don't want to commit unfinished work.

---

## `git reset`

Undo commits or unstage changes.

```bash
# Unstage a file (keeps changes in working directory)
git reset HEAD filename.md

# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo last commit and unstage changes
git reset --mixed HEAD~1

# ⚠️ Danger: Undo last commit AND discard all changes
git reset --hard HEAD~1
```

> **Warning:** Never use `git reset --hard` on commits that have already been pushed to a shared branch. This rewrites history and causes problems for everyone else.

---

## Quick Reference Card

| Command | What It Does |
|---|---|
| `git clone <url>` | Download repo locally |
| `git checkout -b <name>` | Create and switch to branch |
| `git status` | See what's changed |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Save snapshot with message |
| `git push origin <branch>` | Upload branch to GitHub |
| `git pull upstream main` | Sync with original repo |
| `git fetch upstream` | Download without merging |
| `git merge upstream/main` | Apply upstream changes |
| `git log --oneline` | See commit history |
| `git diff` | See unstaged changes |
| `git stash` | Temporarily save changes |

---

*Next: [`first-contribution.md`](first-contribution.md) — Put these commands to use in a real contribution.*

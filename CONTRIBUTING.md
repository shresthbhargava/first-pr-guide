# Contributing to first-pr-guide

First off — thank you for taking the time to contribute. 🎉

This repository exists to help beginners enter open source. That means **this repo is itself a great place to make your first contribution.** The bar is intentionally accessible. You don't need to write code — improving a sentence, fixing a typo, or adding a useful resource all count.

---

## 📋 Table of Contents

- [Who Can Contribute](#who-can-contribute)
- [What You Can Contribute](#what-you-can-contribute)
- [Before You Start](#before-you-start)
- [How to Contribute](#how-to-contribute)
- [Issue Guidelines](#issue-guidelines)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Commit Message Standards](#commit-message-standards)
- [Code of Conduct Expectations](#code-of-conduct-expectations)

---

## Who Can Contribute

Everyone. Seriously.

- You've never opened a PR before? Start here.
- You're an experienced developer? Help us improve the advanced sections.
- English isn't your first language? Help us with translations.
- You found something confusing in this guide? Tell us — that's valuable feedback.

---

## What You Can Contribute

| Type | Examples |
|---|---|
| **Fix** | Typos, broken links, outdated commands |
| **Improve** | Clarify confusing explanations, add missing steps |
| **Add** | New tips, resources, diagrams, examples |
| **Translate** | Translate sections into other languages |
| **Report** | Open an issue for something that seems wrong or unclear |

---

## Before You Start

1. **Read the README** — understand what this project is trying to do
2. **Check open issues** — someone may already be working on what you have in mind
3. **Check open PRs** — same reason
4. **If in doubt, open an issue first** — don't spend hours on a PR that might not be accepted

---

## How to Contribute

```bash
# Step 1: Fork this repository (click Fork on GitHub)

# Step 2: Clone your fork
git clone https://github.com/YOUR_USERNAME/first-pr-guide.git
cd first-pr-guide

# Step 3: Add upstream remote
git remote add upstream https://github.com/ORIGINAL_OWNER/first-pr-guide.git

# Step 4: Sync with upstream (always do this before starting)
git fetch upstream
git checkout main
git merge upstream/main

# Step 5: Create a branch
git checkout -b docs/improve-git-basics-section

# Step 6: Make your changes

# Step 7: Stage and commit
git add .
git commit -m "docs: clarify git rebase explanation in git-basics.md"

# Step 8: Push
git push origin docs/improve-git-basics-section

# Step 9: Open a Pull Request on GitHub
```

---

## Issue Guidelines

**Before opening an issue:**
- Search existing issues to avoid duplicates
- Be specific — vague issues are hard to act on

**When creating an issue, use the provided templates:**
- `bug_report.md` — for errors, broken links, incorrect information
- `content_suggestion.md` — for new content ideas
- `resource_request.md` — to suggest external resources to add

**Issue title format:**
```
[BUG] Broken link in git-basics.md
[SUGGESTION] Add section on rebasing
[RESOURCE] Add link to learngitbranching.js.org
```

---

## Pull Request Guidelines

**A good PR:**
- Addresses one thing (one issue, one improvement)
- Has a clear title describing what changed
- References the issue it closes (if applicable): `Closes #42`
- Includes a brief description of what you changed and why

**PR title format:**
```
fix: correct broken link in resources section
docs: add rebase explanation to git-basics.md
feat: add Korean translation of first-contribution.md
```

**PR checklist (included in the PR template):**
- [ ] I have read CONTRIBUTING.md
- [ ] My changes are focused (not mixing multiple unrelated changes)
- [ ] I have tested that links work (if I added any)
- [ ] My commit messages follow the convention
- [ ] I have referenced the related issue (if one exists)

**What happens after you open a PR:**
1. A maintainer will review within a few days
2. You may receive feedback — this is normal
3. Make requested changes and push to the same branch
4. Once approved, your PR will be merged

---

## Commit Message Standards

Follow the **Conventional Commits** format:

```
type: short description in present tense
```

| Type | When to use |
|---|---|
| `fix` | Correcting something wrong |
| `docs` | Documentation changes |
| `feat` | Adding new content or sections |
| `style` | Formatting only (whitespace, punctuation) |
| `chore` | Maintenance (file moves, renaming) |

**Examples:**
```bash
# ✅ Good
git commit -m "fix: remove outdated GitHub Desktop instructions"
git commit -m "docs: add explanation for git stash command"
git commit -m "feat: add Spanish translation of README"

# ❌ Bad
git commit -m "update"
git commit -m "fix stuff"
git commit -m "changes to file"
```

---

## Code of Conduct Expectations

This is a welcoming space. We hold contributors to these standards:

**We expect:**
- Respectful, constructive communication
- Patience with beginners — everyone starts somewhere
- Honest feedback given kindly
- Giving credit where it's due

**We do not tolerate:**
- Harassment, discrimination, or personal attacks
- Dismissing someone's contribution because it's "too small"
- Spam PRs or low-effort contributions submitted for program points
- Claiming others' work as your own

**Enforcement:**
Violations will result in removal from the project. If you experience or witness a code of conduct violation, open a private issue or contact the maintainer directly.

---

## Questions?

If you're unsure about anything, open an issue with the label `question`. There are no stupid questions here — if something in this guide confused you, that's actually useful information for us.

---

Thank you for making open source more welcoming. 🙌

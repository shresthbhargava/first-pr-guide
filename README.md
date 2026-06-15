# 🚀 first-pr-guide

> **A practical, community-maintained guide to making your first open-source contribution.**
> From zero to merged PR — no fluff, just real steps.

[![Contributors](https://img.shields.io/github/contributors/YOUR_USERNAME/first-pr-guide?color=brightgreen)](https://github.com/shresthbhargava/first-pr-guide/graphs/contributors)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/shresthbhargava/first-pr-guide?style=social)](https://github.com/shresthbhargava/first-pr-guide/stargazers)
[![Open Issues](https://img.shields.io/github/issues/shresthbhargava/first-pr-guide)](https://github.com/shresthbhargava/first-pr-guide/issues)

---

## 💡 Why Does This Exist?

When I started contributing to open source, I didn't struggle with coding — I struggled with **everything around it**.

- Which repository should I pick?
- What does "good first issue" actually mean?
- How do I write a commit message that won't embarrass me?
- What do I say when a maintainer requests changes?

No single resource answered these clearly. I pieced it together over months across dozens of tabs, Stack Overflow threads, and Discord servers.

This guide is what I wish had existed on Day 1.

---

## 👥 Who Is This For?

| You are... | This guide helps you... |
|---|---|
| A student entering open source for the first time | Navigate the process without feeling lost |
| A GSSoC / Hacktoberfest participant | Understand contribution workflows that programs expect |
| A self-taught developer | Fill the gaps that tutorials and courses skip |
| Someone who tried and failed their first PR | Understand what went wrong and how to fix it |

**You do not need to be an expert. You just need to be willing to try.**

---

## 🗺️ Complete Beginner Roadmap

```
STAGE 1 — Understand the Ecosystem
   └── What is open source?
   └── How does GitHub work?
   └── What is a fork, branch, PR?

STAGE 2 — Set Up Your Environment
   └── Install Git
   └── Configure your identity
   └── Connect Git to GitHub

STAGE 3 — Find Your First Issue
   └── Browse beginner-friendly repos
   └── Read contribution guidelines
   └── Understand issue labels

STAGE 4 — Make Your Contribution
   └── Fork → Clone → Branch → Change → Commit → Push → PR

STAGE 5 — Handle the Review Process
   └── Respond to feedback
   └── Make requested changes
   └── Get it merged 🎉

STAGE 6 — Keep Growing
   └── Find harder issues
   └── Help others
   └── Build your open-source profile
```

---

## ⚡ Quick Contribution Workflow

For those who just want the workflow at a glance:

```bash
# 1. Fork the repo on GitHub (click the Fork button)

# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
cd REPO_NAME

# 3. Add the original repo as upstream
git remote add upstream https://github.com/ORIGINAL_OWNER/REPO_NAME.git

# 4. Sync with upstream before you start
git fetch upstream
git checkout main
git merge upstream/main

# 5. Create a new branch for your work
git checkout -b fix/your-descriptive-branch-name

# 6. Make your changes, then stage them
git add .

# 7. Commit with a clear message
git commit -m "fix: correct typo in installation docs"

# 8. Push to your fork
git push origin fix/your-descriptive-branch-name

# 9. Open a Pull Request on GitHub
```

---

## 🔖 Understanding GitHub Issue Labels

Labels are how maintainers communicate what kind of help they need and who it's for.

| Label | What It Means | Should You Pick It? |
|---|---|---|
| `good first issue` | Low complexity, well-scoped, newcomer-friendly | ✅ Yes — start here |
| `help wanted` | Maintainer needs external help, any skill level | ✅ Yes — if you understand the issue |
| `documentation` | Improve or write docs, no deep code needed | ✅ Great for beginners |
| `beginner` | Explicitly tagged for newcomers | ✅ Yes |
| `bug` | Something is broken | ⚠️ Only if you can reproduce and fix it |
| `enhancement` | New feature request | ⚠️ Discuss in the issue before coding |
| `wontfix` | Maintainer won't address this | ❌ Don't work on this |
| `duplicate` | Already reported elsewhere | ❌ Skip |

---

## 🍴 Forking a Repository

**Forking** creates your own copy of someone else's repository under your GitHub account.

1. Navigate to the repository on GitHub
2. Click the **Fork** button (top right corner)
3. Select your account as the destination
4. GitHub creates `YOUR_USERNAME/REPO_NAME` — this is your fork

> **Why fork?** You don't have write access to the original repo. Your fork is your personal sandbox where you make changes before proposing them back.

---

## 🌿 Creating Branches

Never work directly on `main`. Always create a dedicated branch for each contribution.

```bash
# See all branches
git branch -a

# Create and switch to a new branch
git checkout -b type/short-description

# Examples of good branch names:
git checkout -b fix/navbar-alignment
git checkout -b docs/add-docker-setup
git checkout -b feat/add-search-filter
```

**Branch naming convention:**
- `fix/` — bug fixes
- `feat/` — new features
- `docs/` — documentation changes
- `chore/` — maintenance, dependency updates

---

## 💬 Writing Good Commits

Your commit messages are communication. They tell maintainers (and future you) *what* changed and *why*.

**Format:**
```
type: short description in present tense

Optional longer explanation if needed.
Closes #issue_number
```

**Types:**
| Type | Use for |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no logic change |
| `refactor` | Code restructure, no behavior change |
| `test` | Adding or fixing tests |
| `chore` | Build process, tooling |

**Good vs Bad:**
```bash
# ❌ Bad
git commit -m "fixed stuff"
git commit -m "changes"
git commit -m "asdfgh"

# ✅ Good
git commit -m "fix: resolve null pointer in user login flow"
git commit -m "docs: add Windows setup instructions to README"
git commit -m "feat: add dark mode toggle to settings page"
```

---

## 🔍 Finding Beginner-Friendly Repositories

**Search GitHub with these filters:**

```
label:"good first issue" language:javascript is:open
label:"good first issue" language:python is:open
label:"good first issue" label:"documentation" is:open
```

**Beginner-friendly programs:**
- [GSSoC (GirlScript Summer of Code)](https://gssoc.girlscript.tech/)
- [Hacktoberfest](https://hacktoberfest.com/)
- [Google Summer of Code](https://summerofcode.withgoogle.com/)
- [MLH Fellowship](https://fellowship.mlh.io/)

**Curated lists:**
- [goodfirstissue.dev](https://goodfirstissue.dev/)
- [up-for-grabs.net](https://up-for-grabs.net/)
- [firsttimersonly.com](https://www.firsttimersonly.com/)

---

## 🔄 Handling Review Feedback

Getting review comments is **normal and expected**. It is not rejection — it is collaboration.

**When a maintainer requests changes:**

1. Read every comment carefully before replying
2. If something is unclear, ask a specific question — don't guess
3. Make the requested changes in your branch (not a new branch)
4. Push the changes — the PR updates automatically
5. Reply to each comment to let the reviewer know it's addressed

```bash
# After making changes based on review:
git add .
git commit -m "fix: address review feedback - refactor auth logic"
git push origin your-branch-name
```

**What NOT to do:**
- Don't argue defensively about feedback
- Don't close and reopen a new PR
- Don't go silent for weeks

---

## ⚠️ Common Mistakes Beginners Make

See the full guide → [`docs/common-mistakes.md`](docs/common-mistakes.md)

Quick overview:
- Working on `main` directly instead of creating a branch
- Not reading the `CONTRIBUTING.md` before starting
- Submitting a PR without testing the changes
- Writing vague commit messages like "update" or "fix"
- Opening a massive PR that changes 15 files for one issue
- Not syncing your fork before starting new work

---

## 📚 Resources

**Git & GitHub:**
- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Skills](https://skills.github.com/)
- [Pro Git Book (free)](https://git-scm.com/book/en/v2)
- [Learn Git Branching (interactive)](https://learngitbranching.js.org/)

**Finding Contributions:**
- [goodfirstissue.dev](https://goodfirstissue.dev/)
- [up-for-grabs.net](https://up-for-grabs.net/)
- [GitHub Explore](https://github.com/explore)

**More Guides in This Repo:**
- [`docs/git-basics.md`](docs/git-basics.md) — Every Git command you need, explained simply
- [`docs/first-contribution.md`](docs/first-contribution.md) — Full walkthrough of your first PR
- [`docs/common-mistakes.md`](docs/common-mistakes.md) — What to avoid
- [`docs/understanding-labels.md`](docs/understanding-labels.md) — Deep dive on GitHub labels

---

## 🤝 Contributing to This Guide

This guide improves because of contributors like you.

Found a mistake? Have a tip that helped you? Want to translate a section?

Read [`CONTRIBUTING.md`](CONTRIBUTING.md) to get started. Even fixing a typo counts — this repo is intentionally beginner-friendly so your first PR can happen *here*.

---

## 📄 License

MIT License — see [`LICENSE`](LICENSE) for details.

---

<div align="center">

**Built with ❤️ for the open-source community**

If this helped you, consider giving it a ⭐ and sharing it with someone who's just getting started.

</div>

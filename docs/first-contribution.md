# Your First Contribution — Step by Step

> This guide walks you through a complete contribution from finding an issue to getting your PR merged. Follow every step in order.

---

## Step 1: Find a Repository

Don't pick randomly. A good first repository:

- Has a `CONTRIBUTING.md` file (they care about contributors)
- Has issues labeled `good first issue` or `beginner`
- Has recent activity (last commit within a few weeks)
- Has a maintainer who responds to issues and PRs

**Where to look:**

- [goodfirstissue.dev](https://goodfirstissue.dev/) — filtered list of beginner issues
- [up-for-grabs.net](https://up-for-grabs.net/) — community-curated beginner projects
- GitHub search: `label:"good first issue" is:open language:python`
- GSSoC / Hacktoberfest participating repositories

**Check before you commit to a repo:**
```
- When was the last commit?           → Recent = active project
- Are issues being responded to?      → Check if maintainers reply
- Are PRs being reviewed and merged?  → Check the "Closed" PRs tab
- Is there a CONTRIBUTING.md?        → Good sign
```

---

## Step 2: Read the Contribution Guidelines

Before anything else, read `CONTRIBUTING.md`.

Every project has its own rules. Some require you to:
- Comment on an issue before working on it
- Follow a specific branch naming convention
- Sign a Contributor License Agreement (CLA)
- Run a specific test suite before submitting

**Skipping this step is the most common beginner mistake.**

If there's no `CONTRIBUTING.md`, check the README for a "Contributing" section.

---

## Step 3: Select an Issue

Find an issue labeled `good first issue`, `beginner`, `documentation`, or `help wanted`.

**Before selecting, check:**
- Is anyone already assigned to it?
- Are there recent comments saying someone is working on it?
- Do you actually understand what needs to be done?

**If the issue description is vague, ask for clarification before starting.** Post a comment like:

> "Hi, I'd like to work on this. Before I start, could you clarify what the expected behavior should be after the fix? I want to make sure I'm solving the right problem."

---

## Step 4: Comment on the Issue

Most projects expect you to claim an issue before working on it. This prevents two people doing the same work.

**Post a comment like:**

> "Hi! I'd like to work on this issue. I'm thinking of [brief description of your approach]. Could you assign it to me? I expect to have a draft PR ready within [timeframe]."

Wait for acknowledgment if the project requires it. Some maintainers will assign the issue to you. Others will just reply "go ahead."

---

## Step 5: Fork the Repository

1. Go to the repository on GitHub
2. Click the **Fork** button (top right)
3. Select your account
4. GitHub creates `YOUR_USERNAME/REPO_NAME`

You now have your own copy to work on.

---

## Step 6: Clone Your Fork Locally

```bash
# Clone your fork (not the original repo)
git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
cd REPO_NAME

# Add the original repo as upstream
git remote add upstream https://github.com/ORIGINAL_OWNER/REPO_NAME.git

# Verify both remotes
git remote -v
```

You should see:
```
origin    https://github.com/YOUR_USERNAME/REPO_NAME.git (fetch)
origin    https://github.com/YOUR_USERNAME/REPO_NAME.git (push)
upstream  https://github.com/ORIGINAL_OWNER/REPO_NAME.git (fetch)
upstream  https://github.com/ORIGINAL_OWNER/REPO_NAME.git (push)
```

---

## Step 7: Sync Before You Start

Your fork might already be out of date. Always sync before creating a branch.

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main   # Keep your fork's main updated too
```

---

## Step 8: Create a Branch

Never work on `main`. Create a branch specifically for this issue.

```bash
git checkout -b fix/issue-42-broken-link
```

**Naming convention:**
```
fix/short-description       → bug fixes
docs/short-description      → documentation
feat/short-description      → new features
chore/short-description     → maintenance
```

Use the issue number if it helps: `fix/42-broken-link`

---

## Step 9: Make Your Changes

Now actually do the work.

**While working:**
- Make small, focused changes — don't fix unrelated things
- Follow the existing code style (indentation, naming, structure)
- If you change a function, check if it affects other parts of the codebase
- For documentation changes, re-read your edits for clarity

**Check your changes at any time:**
```bash
git status          # What's changed
git diff            # See the actual line changes
```

---

## Step 10: Test Locally

Before submitting, verify your changes work.

**For documentation:**
- Re-read everything you changed
- Check all links work
- Make sure formatting renders correctly (preview in VS Code or GitHub)

**For code:**
```bash
# Run existing tests
npm test           # Node.js projects
pytest             # Python projects
mvn test           # Java/Maven projects

# Run the project locally and test manually
npm run dev        # React/Next.js
python app.py      # Python apps
```

**If you broke a test — fix it before submitting the PR.**

---

## Step 11: Stage and Commit

```bash
# Stage your changes
git add .

# Check what you're about to commit
git diff --staged

# Commit with a clear message
git commit -m "fix: correct broken link in resources section

The link to learngitbranching.js.org was pointing to an
outdated URL. Updated to the current working URL.

Closes #42"
```

**If you have multiple logical changes, make multiple commits:**
```bash
git commit -m "fix: update outdated installation commands"
git commit -m "docs: add note about Windows path requirements"
```

---

## Step 12: Push to Your Fork

```bash
git push origin fix/issue-42-broken-link
```

---

## Step 13: Open the Pull Request

1. Go to your fork on GitHub
2. You'll see a yellow banner: **"Compare & pull request"** — click it
3. If the banner isn't there, click **"Pull requests"** → **"New pull request"**

**Fill out the PR:**

**Title:**
```
fix: correct broken link in resources section
```

**Description (follow the PR template):**
```
## What does this PR do?
Fixes a broken link in the resources section of README.md.
The link to learngitbranching.js.org was pointing to an outdated URL.

## Related Issue
Closes #42

## Changes Made
- Updated URL in README.md line 87
- Verified the new URL loads correctly

## Testing
- Manually verified the link opens in browser
- No code changes — documentation only
```

4. Click **Create pull request**

---

## Step 14: Respond to Review Feedback

The maintainer will review your PR. This usually takes 1–7 days.

**If they request changes:**

1. Read every comment carefully
2. Ask a clarifying question if something isn't clear
3. Make the changes in your local branch
4. Commit and push — the PR updates automatically

```bash
# Make changes...
git add .
git commit -m "fix: address review feedback - use relative URL"
git push origin fix/issue-42-broken-link
```

5. Reply to each review comment on GitHub: "Done — updated in the latest commit."
6. If you disagree with feedback, explain your reasoning respectfully. Maintainers are usually open to discussion.

**Stay patient.** Maintainers are often volunteers with full-time jobs.

---

## Step 15: Your PR Gets Merged 🎉

When the maintainer merges your PR:

1. Delete your branch (GitHub will prompt you — it's good hygiene)
2. Sync your fork

```bash
git checkout main
git pull upstream main
git push origin main
git branch -d fix/issue-42-broken-link
```

3. Celebrate. You're an open-source contributor.

---

## What Next?

- Find another issue in the same repo — you already know the codebase
- Try a slightly harder issue
- Help someone else who's stuck
- Write about your experience and share it

See [`after-your-first-pr.md`](after-your-first-pr.md) for what to do next.

---

## Troubleshooting Common Issues

**"I can't push to upstream"**
You don't have write access to the original repo. Push to `origin` (your fork), not `upstream`.

**"My PR shows merge conflicts"**
Your branch is out of sync. Run:
```bash
git fetch upstream
git merge upstream/main
# Resolve conflicts, then push
```

**"The maintainer isn't responding"**
Wait at least 1–2 weeks. Then you can politely comment: "Hi, just checking in on this PR. Let me know if any changes are needed."

**"My PR was closed without merging"**
This happens. Sometimes the issue was already fixed elsewhere, or the approach wasn't right. It's not personal. Ask for feedback if none was given, and move on.

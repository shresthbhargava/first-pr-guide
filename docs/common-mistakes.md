# Common Mistakes Beginners Make (And How to Avoid Them)

> These aren't meant to shame anyone. Every single one of these was made by someone experienced before they knew better — including the person who wrote this guide.

---

## Mistake 1: Jumping Into Code Without Reading the README

**What happens:**
You find an issue, immediately fork and start coding, then submit a PR that doesn't match the project's structure, style, or requirements.

**Why it happens:**
Excitement. You want to contribute. Reading feels like a delay.

**The cost:**
Your PR gets closed. You wasted hours. The maintainer spends time explaining something that was already documented.

**The fix:**
Before touching any code, read in this order:
1. `README.md` — what is this project?
2. `CONTRIBUTING.md` — how does this project want contributions?
3. The specific issue — what exactly needs to be done?
4. Related code files — how does the existing code work?

This takes 15 minutes and saves hours.

---

## Mistake 2: Not Syncing Your Fork Before Starting

**What happens:**
You fork a repo, start working immediately, and a week later your PR shows "merge conflicts" because the original repo moved forward without you.

**Why it happens:**
Forks don't auto-update. Most beginners don't know about `upstream`.

**The cost:**
Merge conflicts you have to resolve. Sometimes a messy PR history that's hard to review.

**The fix:**
Every single time you start new work:
```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

Set up `upstream` once after cloning:
```bash
git remote add upstream https://github.com/ORIGINAL_OWNER/REPO_NAME.git
```

---

## Mistake 3: Working Directly on `main`

**What happens:**
You make changes directly on your fork's `main` branch. This makes it hard to sync with upstream, hard to manage multiple contributions, and creates a messy history.

**Why it happens:**
It feels simpler. You don't understand why branches exist yet.

**The cost:**
When you try to sync with upstream, you'll get conflicts on `main` itself. You also can't work on two issues simultaneously.

**The fix:**
Always create a branch for every single contribution:
```bash
git checkout -b fix/descriptive-name
```

Treat your fork's `main` as read-only. Only update it by merging from upstream.

---

## Mistake 4: Writing Vague Commit Messages

**What happens:**
Your commit history looks like: "update", "fix", "changes", "final", "final2", "ok now it works"

**Why it happens:**
Commit messages feel unimportant in the moment. You're focused on the code.

**The cost:**
Maintainers can't understand what changed. Reviewers have to read every line diff instead of getting context from messages. It looks unprofessional.

**The fix:**
Use the format `type: what changed`:
```bash
# ❌
git commit -m "fix"
git commit -m "update readme"

# ✅
git commit -m "fix: resolve null pointer exception in auth middleware"
git commit -m "docs: add Windows setup instructions to README"
```

Ask yourself: "If I read this commit message in 6 months, will I understand what it does?"

---

## Mistake 5: Submitting a Giant PR

**What happens:**
You find one issue, but while fixing it you "clean up" other things, add a feature you wanted, refactor some code, and update the docs. Your PR touches 20 files.

**Why it happens:**
Good intentions. You see things that could be better and want to help.

**The cost:**
Maintainers are much less likely to review and merge a huge PR. It's harder to review, harder to test, and if one part is wrong, the whole thing stalls.

**The fix:**
One PR = one purpose.

If you find other issues while working, open separate issues for them. Maybe even separate PRs. A small focused PR that gets merged is infinitely more valuable than a large PR that sits in review for weeks.

A good PR can be as small as fixing one typo, adding one missing step, or correcting one broken link.

---

## Mistake 6: Commenting "Can I work on this?" Without Context

**What happens:**
You comment "Can I work on this?" or "Assign me please" on an issue without explaining your approach or background.

**Why it happens:**
You've seen others do it. It seems like the right move.

**The cost:**
Many maintainers will ignore these comments, especially on popular repos. It gives them no information to work with.

**The fix:**
Show that you've thought about it:
```
"Hi! I'd like to work on this. My approach would be to [brief description].
I'm familiar with [relevant tech]. Could you assign this to me?
I can have a draft PR ready by [timeframe]."
```

This takes 3 minutes and dramatically increases your chances of getting assigned.

---

## Mistake 7: Going Silent After Opening a PR

**What happens:**
You open a PR, a reviewer asks for changes, and you don't respond for 2-3 weeks (or ever).

**Why it happens:**
Life gets busy. You moved on to other things. The feedback felt discouraging.

**The cost:**
Your PR gets closed. The maintainer wasted time reviewing something that goes nowhere.

**The fix:**
- Check your PR notifications at least every few days
- If you can't work on it right now, comment: "I'll have time to address this by [date]"
- If you've abandoned it, comment: "I won't be able to finish this — feel free to close or reassign"

Being communicative even when you're stuck builds trust. Disappearing burns it.

---

## Mistake 8: Not Testing Changes Before Submitting

**What happens:**
You make a change, push it, open the PR, and then the CI fails or the maintainer finds a bug you would have caught in 2 minutes of testing.

**Why it happens:**
Eagerness to submit. Assuming small changes can't break anything.

**The cost:**
Multiple round trips of feedback. Maintainer frustration. Your PR takes longer.

**The fix:**
Before every PR:
- Run the test suite: `npm test`, `pytest`, `mvn test`
- Run the project locally and test your change manually
- For documentation: preview it and read it out loud
- For code: try to break your own change

A 5-minute check before submitting saves everyone time.

---

## Mistake 9: Ignoring Review Feedback (or Taking It Personally)

**What happens:**
A reviewer points out issues. You either get defensive, argue without good reason, or reopen a new PR "starting fresh" to avoid the feedback.

**Why it happens:**
It can feel like criticism of you, not just your code. Imposter syndrome is real.

**The cost:**
The PR stalls. The relationship with the maintainer gets awkward. You miss out on learning.

**The fix:**
Treat review feedback as what it is: collaboration, not judgment.

When you disagree:
- Explain your reasoning calmly: "I chose this approach because..."
- Ask if there's a better way: "Would you suggest an alternative?"
- Accept that maintainers have context about the codebase that you don't

Most reviewers want your PR to succeed. Their job is to keep the codebase healthy, not to reject you.

---

## Mistake 10: Submitting PRs to Win Program Points, Not to Help

**What happens:**
During Hacktoberfest, GSSoC, or similar programs, some people spam repositories with low-effort PRs — fixing single character typos, adding random blank lines, or making meaningless changes just to get contribution credit.

**Why it happens:**
Program incentives can attract the wrong behavior.

**The cost:**
Maintainers have to spend time rejecting these. It damages the reputation of genuine contributors. Many repositories now mark themselves as "spam-prevention" and won't count these contributions.

**The fix:**
Ask yourself before every PR: "Does this genuinely improve the project?"

If the answer is unclear, find something else to work on. A single genuinely useful contribution is worth more than ten spam PRs — for your reputation, your learning, and the community.

---

## The Meta-Mistake: Thinking You Need to Be an Expert

The belief that stops most people from contributing is: "I'm not good enough yet."

You don't need to be an expert. The best contributions often come from beginners — because beginners notice the things experts stopped seeing. Confusing documentation, missing setup steps, assumptions that aren't explained.

If you noticed something and thought "this could be clearer" — that thought is a contribution waiting to happen.

---

*Next: [`first-contribution.md`](first-contribution.md) — Now that you know what to avoid, here's exactly what to do.*

# Module 06 — Git Best Practices (Summary)
**Source:** Mariot Tsitoara — *Beginning Git and GitHub* (Chapter: Git Best Practices)
## High-level topics
- Why good commit messages matter
- Commit message guidelines and examples
- Dos and don'ts when using Git
- Short review of how Git works (three states)
---
## Commit messages — why they matter
- Commit messages explain why a change was made; diffs show what changed.
- Each commit should be atomic, complete, and self-contained (it must make sense on its own).
- If a task is too big, split it into smaller commits that each perform a single logical change.
---
## Commit message best practices (practical rules)
- Keep the subject line ≤ 50 characters.
- Start with a capital letter.
- Do not end the subject with a period.
- Use imperative present tense (e.g., "Fix typo in DB call", "Add user validation").
- Keep the subject concise; if needed, use a body paragraph to explain *why* (not *what*).
- Be consistent in language and style across the project.
### Example good vs bad
- Good: `[login] Fix typo in DB call`  
  Bad: `Fixed typo in DB call`  
  Worst: `Fix typo`
- Good: `Refactor login function for reuse`  
  Bad: `Changing login function by moving declarations to parameters`
- Good: `Add new API for user program check`  
  Bad: `New user API`
---
## Dos
- Keep commits small and independent.
- Write messages that explain why the change was made.
- Use `git diff --staged` to review staged changes before committing.
- Use branches when working on features or experiments.
- Prefer new commits over rewriting history for fixes that can be recorded.
## Don'ts
- Don’t cram unrelated changes into one commit.
- Don’t use Git as a daily backup for meaningless checkpoints.
- Avoid large `git commit --amend` changes for important modifications — amends should be for tiny fixes (typos, forgotten files).
- Never rewrite shared history (avoid `git push --force` on shared branches).
- Don’t write vague messages like “updates”, “fixes”, “stuff”.
---
## Quick review: the three Git states (Three Trees)
- **Working Directory:** where you edit files.
- **Staging Area (Index):** where you place files you want to include in the next snapshot.
- **Repository (.git):** where commits (snapshots + metadata) are stored.
Typical workflow:
1. Edit files (Working Directory)
2. Stage with `git add` (Staging Area)
3. Commit with `git commit` (Repository)
---
## Useful commands & checks
- View staged vs unstaged:
git status
git diff # unstaged changes vs last commit
git diff --staged # staged changes vs last commit
- Review what will be committed:
git add <file>
git diff --staged
git commit -m "Subject line" -m "Optional body explaining why"
- See short log:
git log --oneline --graph -n 20
- Show a commit in detail:
git show <commit-id>
---
## Practical checklist
- [ ] Commits are atomic and focused
- [ ] Subject ≤ 50 chars, capitalized, no trailing period, imperative tense
- [ ] Use `git diff --staged` before commits
- [ ] Use branches for new features/experiments
- [ ] Avoid rewriting published history
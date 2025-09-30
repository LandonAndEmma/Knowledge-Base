
# Module 12 — Better Project Management: Pull Requests (Summary)

**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: Better Project Management: Pull Requests)

## High-level topics

- Why use Pull Requests
- Pull vs Push operations
- Creating Pull Requests
- Code review process
- Updating Pull Requests
- Merging and closing PRs

---

## Why Pull Requests

- A formal process for proposing changes to a repository.
- Enables structured code review and quality control.
- Reduces bugs through peer review and discussion.
- Allows contributors to work in parallel while awaiting review.
- Standard workflow for open source and most professional teams.

---

## Pull vs Push operations

```bash
# Pull changes from remote into your local branch
git pull origin branch-name
```

- `pull` is the opposite of `push`: it brings remote commits into your local branch.
- Keep your branch up-to-date with the target branch before opening a PR to minimize conflicts.
- Regular `pull`/`fetch` is essential for smooth collaboration.

---

## Creating Pull Requests

**Typical process**

1.  Create and work on a feature branch.
2.  Push the branch to the remote:
    `bashgit push origin feature-branch`
3.  On GitHub, open a Pull Request (feature → target branch).
4.  Add a clear title and descriptive body.
5.  Reference related issues (use closing keywords if appropriate).

PR contents

- Title: concise summary of what the PR does.
- Description: motivation, what changed, how to test, any limitations.
- Included commits and the diff of modified files.

---

## Code review process

- Use the **Files changed** tab to review diffs line-by-line.
- Add inline comments or file-level comments to give feedback.
- Submit a review with one of three states:
  - **Comment** — general feedback without approving.
  - **Approve** — ready to merge.
  - **Request Changes** — changes required before merging.
- Discuss comments in-thread and iterate on the branch until reviewers are satisfied.

---

## Updating Pull Requests

- Push additional commits to the same branch; GitHub will update the PR automatically.
- Only the new changes appear in subsequent reviews, keeping review scope focused.
- Use meaningful commit messages for updates to help reviewers follow progress.
- Continue iterating until all review feedback is addressed.

---

## Merging and closing PRs

- Merge the PR using GitHub’s **Merge pull request** button once approvals are in place.
- Typical post-merge actions:
  - Optionally delete the source branch to keep the repo tidy.
  - Issues referenced with closing keywords will automatically close when merged to the default branch.
- All PR discussion, review history, and commits are preserved for auditability.

---

## PR best practices

- Open PRs early to get feedback sooner rather than later.
- Use clear, descriptive titles and a helpful description.
- Reference related issues to provide context.
- Keep PRs focused on a single purpose or concern.
- Respond to review feedback promptly and courteously.
- Avoid merging your own PR without at least one independent review when possible.

---

## Quick checklist

- [ ] Create a PR for every branch merge
- [ ] Write a clear PR title and descriptive body
- [ ] Reference related issues and use closing keywords when appropriate
- [ ] Participate in the code review process (comment, approve, request changes)
- [ ] Update the PR by pushing commits until reviewers are satisfied
- [ ] Merge only after required approvals
- [ ] Delete the source branch after merge to keep the repo clean

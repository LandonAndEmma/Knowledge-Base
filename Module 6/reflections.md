# Module 06 — Reflections

## What I learned
- Commit messages should answer *why* — they are critical for team understanding and future debugging.
- Keep commits atomic and focused; split work into logical, independent commits.
- Avoid using Git as a daily/automatic backup and avoid rewriting shared history.
- Use `git diff --staged` as a pre-commit sanity check.

## How I applied it (actions I will / did take)
- Practiced writing concise commit messages (≤50 chars, imperative).
- Broke a sample change into three atomic commits (e.g., add endpoint, add tests, update docs).
- Used:
git diff
git add file1 file2
git diff --staged
git commit -m "Add user-email validation" -m "Ensure emails are normalized and validated to prevent X issue"

- Avoided `--amend` except to correct a single missing file or typo in the previous commit.

## Questions for instructor
- None

## Personal takeaways
- Good commit hygiene saves time and reduces friction in collaboration. I’ll be strict about commit scope and message clarity going forward.
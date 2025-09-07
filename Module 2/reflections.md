# Module 02 — Reflections

## What I learned
- Installing Git is straightforward on all platforms; defaults are safe and recommended for learners.
- The most important post-install steps are setting `user.name` and `user.email` so commits have the correct identity.
- PATH choice matters: adding Git to PATH makes it usable from any terminal and by other tools.
- Line ending settings can create confusing diffs if misconfigured across OSes; stick with sensible defaults.
- It's better to learn the Git CLI before using GUI clients to avoid “mystery” behavior.

## How I applied it (actions I will/ did take)
- Installed Git on my system (or verified Git is present).
- Ran:
git --version
git config --global user.name "My Name"
git config --global user.email "my.email@example.com"
git config --global core.editor "code" # or "nano" or preferred editor

- Confirmed `~/.gitconfig` exists and contains my settings.

## Questions for instructor
- None

## Personal takeaways
- The installation process is short; the important part is forming the habit of configuring Git correctly and committing frequently so the commit log becomes a usable history of progress.
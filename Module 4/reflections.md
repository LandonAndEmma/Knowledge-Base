# Module 04 — Reflections

## What I learned
- `.gitignore` is essential to keep generated files, secrets, and local config out of commits.
- Pattern rules are flexible (wildcards, directories, recursive patterns) — but order matters for exceptions.
- `git log`, `git show`, and `git diff` are the core tools for reading project history and inspecting changes.
- `git diff` shows **unstaged** changes; `git diff --staged` shows what will be committed.

## How I applied it (actions I will / did take)
- Created `Module-04/.gitignore` with common patterns and committed it.
- Tested ignoring files and using an exception (`!`) to include one specific file.
- Ran:
git log --graph --oneline -n 10
git show <commit-id-prefix>
git diff
git diff --staged

to review commit history and changes.

## Example `.gitignore` I used
Ignore OS files
.DS_Store
Thumbs.db

Node modules
node_modules/

Build outputs
build/
dist/

Logs
*.log

Editor temp files
*.swp
*.swo
.vscode/
.idea/

Ignore all exe but include output.exe
*.exe
!output.exe

## Questions for instructor
- None

## Personal takeaways
- Small, consistent `.gitignore` maintenance prevents accidental commits of secrets or large generated files.
- Reading history (log/show) helps me understand project evolution and makes debugging regressions easier.
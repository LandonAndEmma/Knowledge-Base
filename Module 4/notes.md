# Module 04 — Diving into Git (Summary)

**Source:** Mariot Tsitoara — *Beginning Git and GitHub* (Chapter: Diving into Git)

## High-level topics
- Ignoring files using `.gitignore`
- `.gitignore` patterns and exceptions
- Viewing history with `git log`
- Inspecting commits with `git show`
- Checking local and staged changes with `git diff` and `git diff --staged`

---

## Ignoring files: `.gitignore`
- Create a file named `.gitignore` at the **root** of the repo.
- Each line describes a filename, directory, wildcard pattern, or exception to ignore.
- The `.gitignore` file **itself is tracked** — add & commit it so everyone uses the same rules.

### Basic examples
- `config.txt` → ignore any `config.txt` in any directory
- `build/` → ignore any directory named `build` and its contents
- `*.exe` → ignore all `.exe` files
- `bin/*.exe` → ignore `.exe` only in `bin/`
- `temp*` → ignore files starting with `temp`
- `**/configs` → ignore any directory named `configs` anywhere
- `**/configs/local.py` → ignore a `local.py` in any `configs` directory
- `output/**/result.exe` → ignore `result.exe` in any subdirectory under `output`

### Exceptions
- Use `!` to un-ignore a previously ignored **file**: *.exe !output.exe

> Important: exception lines must come **after** the rule they override.
- Note: exceptions do **not** work for files ignored by a directory match in all situations — use specific rules carefully.

### Where to get templates
- GitHub maintains many language/framework `.gitignore` templates:  
`https://github.com/github/gitignore`

---

## Inspecting history & commits
- `git log` — list commits (most recent first). Useful flags:
- `git log --reverse` — oldest first
- `git log -n 10` — last 10 commits
- `git log --since=YYYY/MM/DD` — commits after date
- `git log --author="Name"` — commits by author
- `git log --stat` — show files changed/statistics
- `git log --graph --oneline` — compact graphical view
- Navigation inside `git log` pager:
- up/down (or `j`/`k`), `f`/`b` page, `g` start, `G` end, `q` quit

- `git show <commit>` — show changes introduced by a commit.
- You can type only the first 7 (or fewer) commit characters.

---

## Comparing changes
- `git diff` — differences between working directory and the last commit (unstaged changes).
- `git diff --staged` — differences for staged files (what will be committed).
- `git diff <file>` — changes for a single file.

**Tip:** Always `git diff --staged` before committing to review what's going to be recorded.

---

## Exercises (practice)
1. Create several files and directories; write `.gitignore` patterns that match them; confirm `git status` doesn't show ignored files.
2. Add a rule and an exception (using `!`) and verify the exception file **is** tracked while others remain ignored.
3. Make some commits; then:
 - View the full `git log`.
 - Run `git show <commit>` for an older commit.
 - Modify files and run `git diff` and `git diff --staged`.

---

## Short checklist
- [ ] `.gitignore` created at repo root and committed
- [ ] Confirmed sensitive / generated files are ignored (e.g., `node_modules/`, secret files)
- [ ] Demonstrated `git log`, `git show <id>`, `git diff`, `git diff --staged`
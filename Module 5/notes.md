
# Module 5 — Working with Commits (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_
## High-level topics
-   The three states of Git
-   Navigating between versions
-   Undoing commits with revert
-   Modifying and amending commits
-   Commit safety and best practices
---
## The Three States of Git
### File States in Git:
-   **Modified:** File is changed in Working Directory but not staged
-   **Staged:** File is changed and prepared to be snapshotted
-   **Committed:** File is part of a project snapshot in the Git database
### Key Concepts:
-   Git tracks **snapshots**, not changes
-   Each commit saves the state of the entire project
-   Unchanged files are referenced, not duplicated (efficient storage)
-   Untracked files remain so until staged/committed or ignored
### Workflow Areas:
1.  **Working Directory:** Where you read/edit files directly
2.  **Staging Area:** Where you select which changed files to include in next snapshot
3.  **Git Directory (`.git`):** Where all snapshots (commits) are stored
> **Remember:** You stage individual files, but commit the entire project.
---
## Navigating Between Versions
### Checking Out Previous Commits:
```bash
# View project state at specific commit
git checkout <commit-name>

# Return to current branch
git checkout master
```
### Important Terminology:
-   **head:** A reference to any commit
-   **HEAD:** The currently checked-out commit (current head)
### Golden Rules of Time Travel:
1.  **Only travel back when present is clean** - No unstaged changes in Working Directory
2.  **Don't change the past** - Avoid modifying historical commits
> **Caution:** Always ensure Working Directory is clean (`git status` shows no changes) before checking out other commits.
---
## Undoing a Commit
### Safe Method: `git revert`
-   Creates a new commit that is the exact opposite of the target commit
-   Preserves history and follows time travel rules
-   Can revert any commit, even old ones
### Revert Process:
```bash
# Ensure working directory is clean
git status

# View commit history
git log --oneline

# Create reverse commit
git revert <commit-name>
```
### Revert Characteristics:
-   Reverting a revert reapplies the original changes
-   All commits remain in history (no history rewriting)
-   Default commit message clearly indicates what was reverted
> **Note:** Use `git log --oneline` for cleaner history view.
---
## Modifying and Amending Commits
### Amending Commits:
```bash
# Modify the most recent commit
git commit --amend
```
### When to Amend:
-   Forgot to stage a file
-   Need to fix commit message
-   Minor corrections to recent commit
### What Actually Happens:
-   Creates a new commit that replaces the current one
-   Commit hash changes (since content changes)
-   Only for recent commits, not historical ones
### Dangerous Method: `git reset`
	# Remove last commit, keep changes staged
	git reset --soft HEAD~1
	
	# Unstage a specific file
	git reset HEAD <filename>
> **Warning:**  `git reset` can be dangerous - double-check commands before executing.
---
## Practical Workflow Examples
### Fixing a Bad Commit:
1.  **Reset** the problematic commit:
	```bash
	git reset --soft HEAD~1
	```
2.  **Unstage** incorrect files:
	```bash
	git reset HEAD wrong-file.txt
	```
3.  **Stage** correct files:
	```bash
	git add correct-file.txt
	```
4.  **Commit** with proper message:
	```bash
	git commit -m "Proper commit message"
	```
### Amending Commit Message:
```bash
git commit --amend    # Opens editor to modify commit message
```
---
## Commit Safety and Best Practices
### Do:
-   Use `git revert` for undoing changes
-   Use `git commit --amend` for recent minor fixes
-   Keep Working Directory clean before time traveling
-   Write clear, descriptive commit messages
### Don't:
-   Modify historical commits (changes the past)
-   Abuse amending for major changes
-   Use `git reset` without understanding consequences
-   Check out other commits with unstaged changes
### Philosophy:
-   Mistakes are learning opportunities - keeping them in history can be valuable
-   Clean history is good, but authentic history has value too
-   When in doubt, create new commits rather than modifying old ones
---
## Quick Checklist
- [ ] Understand the three Git states (modified, staged, committed)
- [ ] Know how to navigate between commits using `git checkout`
- [ ] Be able to safely undo commits with `git revert`
- [ ] Understand when and how to use `git commit --amend`
- [ ] Recognize the dangers of `git reset`
- [ ] Always check `git status` before time traveling
- [ ] Follow the golden rules: clean working directory, don't change the past
- [ ] Practice the exercise: cleanly amend a commit with proper workflow
---
## Exercise: Cleanly Amend a Commit
1.  Edit some files and stage them
2.  Commit with intentional grammatical error in message
3.  Unstage one file using `git reset HEAD <file>`
4.  Stage another file
5.  Amend the commit with corrected message using `git commit --amend`

This reinforces proper amendment workflow while maintaining commit integrity.
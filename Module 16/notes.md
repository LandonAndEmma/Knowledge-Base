# Module 16 — Advanced Git (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: Advanced Git)
## High-level topics
-   Reverting individual files
-   Stashing changes for context switching
-   Hard resetting for destructive rollbacks
-   Advanced workflow techniques
---
## Reverting Individual Files
### Problem:
-   Need to discard changes to a single file without affecting others
-   Common when realizing a coding approach was wrong
-   Alternative to multiple undo operations
### Solution:
```bash
# Discard changes in working directory
git checkout -- <filename>
```
### Process:
1.  Make unwanted changes to a file
2.  Check status: `git status` shows revert instructions
3.  Execute: `git checkout -- README.md`
4.  Verify: File returns to last committed state
### Safety Considerations:
-   **Destructive operation** - changes are permanently lost
-   **Review changes first** using GUI or `git diff` before reverting
-   Use when certain changes are unwanted
---
## Stashing Changes
### Problem:
-   Need to switch branches with uncommitted changes
-   Changes aren't ready for commit but need to be preserved
-   Working directory is "dirty" (has uncommitted changes)
### Solution: Git Stash
```bash
# Save changes to stash
git stash push

# View stashed changes
git stash list

# Show details of latest stash
git stash show

# Apply and remove latest stash
git stash pop
```
### Stash Characteristics:
-   **Temporary storage** for unfinished work
-   **LIFO (Last-In, First-Out)** database
-   Preserves both modified and staged files
-   Creates temporary commits in separate "stash" repository
### Typical Workflow:
1.  Working on feature with uncommitted changes
2.  Urgent task requires branch switch
3.  `git stash push` to save current work
4.  Working directory becomes clean
5.  Switch branches and complete urgent task
6.  Return to original branch and `git stash pop`
### Advanced Stash Commands:
```bash
# Apply stash without removing it
git stash apply

# Remove specific stash
git stash drop

# Clear all stashes
git stash clear
```
> **Caution:** Frequent stashing may indicate workflow or priority issues
---
## Hard Resetting
### Problem:
-   Need to completely discard recent commits and changes
-   Want to return project to previous known good state
-   Last resort when reverting isn't sufficient
### Solution:
```bash
# Destructive reset
git reset --hard <commit-or-branch>

# Reset to match remote
git reset --hard origin/branch-name
```
### Reset Characteristics:
-   **Extremely destructive** - permanently removes commits and changes
-   **--hard option** overwrites working directory, staging area, and commit history
-   Moves HEAD and branch pointer to specified commit
-   All subsequent commits are lost
### Example Scenario:
```bash
# Make bad commits
git add .
git commit -m "Bad changes"
# Reset to match remote branch (destroys bad commit)
git reset --hard origin/feature-branch
```
### Dangers and Alternatives:
-   **Data loss** - commits and changes cannot be recovered
-   **Prefer revert** for safe undoing: `git revert <commit>`
-   **Create new branch** instead of resetting when possible
-   **Team impact** - never reset pushed commits others may depend on
### When to Use Reset:
-   Only on local branches that haven't been shared
-   When you're certain you want to permanently remove work
-   As absolute last resort after considering all alternatives
---
## Advanced Workflow Strategies
### Context Switching:
-   Use **stashing** for temporary task switching
-   Maintain **clean working directory** for flexibility
-   **Commit often** to avoid excessive stashing
### Error Recovery Hierarchy:
1.  **Revert file** (`git checkout -- file`) - single file mistakes
2.  **Stash changes** (`git stash`) - preserve work temporarily
3.  **Revert commit** (`git revert`) - safely undo published changes
4.  **Hard reset** (`git reset --hard`) - nuclear option for local branches
### Productivity Tips:
-   Use **GUI tools** to visualize changes before reverting
-   **Communicate** with team before destructive operations
-   **Regular commits** reduce need for complex recovery operations
-   **Branch liberally** to isolate experimental work
---
## Command Reference
### Safe Operations:
```bash
# Revert single file
git checkout -- <file>

# Temporary save
git stash push

# Restore stashed work
git stash pop

# Safe commit undoing
git revert <commit>
```
### Dangerous Operations:
```bash
# Destructive history rewrite
git reset --hard <commit>
```
### Inspection Commands:
```bash
# Check current state
git status

# View stashed changes
git stash list

# Check commit history
git log --oneline

# Review changes before reverting
git diff
```
---
## Summary & Best Practices
### Reverting Files:
-   Quick way to discard unwanted changes to specific files
-   Always review changes before executing
-   Use when confident changes are incorrect
### Stashing:
-   Essential for **context switching** without committing
-   Preserves work in progress safely
-   Ideal for handling interruptions and urgent tasks
### Resetting:
-   **Last resort option** for local branch cleanup
-   Never use on shared or published branches
-   Consider alternatives before resorting to reset
### Professional Guidelines:
-   **Prefer safe methods** over destructive ones
-   **Communicate changes** that affect teammates
-   **Use version control proactively** to minimize recovery needs
-   **Understand consequences** before executing destructive commands
---
## Quick Checklist
- [ ] Know how to revert individual files using `git checkout -- file`
- [ ] Understand when and how to use git stash for context switching
- [ ] Be able to list, view, and apply stashed changes
- [ ] Recognize the extreme danger of `git reset --hard`
- [ ] Know safer alternatives to resetting (revert, new branches)
- [ ] Use inspection commands before destructive operations
- [ ] Communicate with team before operations that affect shared history
- [ ] Prefer committing often to avoid complex recovery scenarios
- [ ] Use GUI tools to visualize changes before reverting
- [ ] Reserve hard reset only for local, unshared branches
# Module 18 — Common Git Problems (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: Common Git Problems)
## High-level topics
-   Repository management issues
-   Working directory problems
-   Commit errors and solutions
-   Branch-related challenges
-   Best practices for avoiding common pitfalls
---
## Repository Problems
### Starting Over Completely:
**When to use:**
-   Changing work computers
-   Corrupted `.git` directory
-   Unrecoverable errors
**Solution:**
```bash
# Fresh clone from remote
git clone <repository_location>
```
**Benefits:**
-   Copies all history and commits
-   Sets up remote origin automatically
-   Clean slate without legacy issues
### Changing Remote Origin:
**When needed:**
-   Switching between HTTPS and SSH
-   Repository transferred to new host
-   Adding dedicated repositories
**Commands:**
```bash
# View current remotes
git remote -v

# Change remote URL
git remote set-url origin <new_url>
```
**Authentication Options:**
-   **SSH:** Private/public key pairs (no password typing)
-   **HTTPS with caching:** Credential helpers store passwords
-   Choose based on security needs and convenience
> **Caution:** Remember to use new remote name for all push/pull operations after changing.
---
## Working Directory Issues
### Empty git diff:
**Problem:**  `git diff` shows nothing but you know files changed  
**Cause:** Files are already staged  
**Solution:**
```bash
# View changes in staged files
git diff --staged
```
**Recommendation:** Use GUI tools for easier change visualization
### Undoing File Changes:
**Scenario:** Want to revert a file to previous state without affecting other files  
**Solution:**
```bash
# Revert specific file
git checkout <commit_name> -- <file_name>
```
**Warning:** This overwrites current changes - review first!
---
## Commit Problems
### Fixing Commit Errors:
**Types of errors:**
-   Typos in commit message
-   Forgot to stage files
-   Committed to wrong branch (if not pushed)
**Safe Solution (Amend):**
```bash
# Modify most recent commit
git commit --amend
```
**When to use amend:**
-   Only for most recent commit
-   Before pushing to remote
-   When working alone on branch
### Dangerous Solutions (Use Carefully):
**Force Push After Amend:**
```bash
# Overwrites remote history
git push <remote> <branch> -f
```
**Soft Reset to Undo Commit:**
```bash
# Remove commit but keep changes
git reset HEAD~ --soft
```
> **Critical Rule:** Never rewrite history on branches others are using!
---
## Branch Problems
### Detached HEAD State:
**What happens:**
-   Checking out specific commits instead of branches
-   New commits won't belong to any branch
-   Changes can be lost
**Solution:**
```bash
# Create branch from current state
git checkout -b <new_branch_name>
```
**Prevention:** Always verify you're on a branch before committing
### Worked on Wrong Branch:
**Scenario:** Made changes on master instead of feature branch  
**Solution (if not committed):**
```bash
# Move changes to new branch
git checkout -b <correct_branch>
```
**Solution (if committed but not pushed):**
```bash
# Undo commit
git reset HEAD~ --soft

# Move to correct branch
git checkout -b <correct_branch>

# Re-commit
git commit
```
> **Warning:** If already pushed, must use revert - live with the history!
### Keeping Current with Parent Branch:
**Problem:** Base branch (master) has new commits you need  
**Solution (Rebase):**
```bash
git checkout master
git pull origin master
git checkout <feature_branch>
git rebase master
```
**Rebase Process:**
1.  Temporarily removes your commits
2.  Applies new commits from base branch
3.  Re-applies your commits on top
4.  May require conflict resolution
**Conflict Resolution During Rebase:**
```bash
git add <resolved_files>

git rebase --continue

# Cancel if conflicts too complex
git rebase --abort
```
**Benefits of Regular Rebasing:**
-   Smaller, manageable conflicts
-   Cleaner history
-   Avoids massive merge conflicts later
### Diverged Branches:
**Cause:** Both local and remote branches have new commits  
**Error:** "Updates were rejected because the tip of your current branch is behind"
**Safe Solution (Merge):**
```bash
# Fetch and merge remote changes
git pull origin <branch_name>

# Now push successfully
git push origin <branch_name>
```
**Dangerous Solution (Avoid):**
```bash
# Force push - destroys others' work
git push origin <branch_name> -f
```
**Prevention:** Use proper workflow - one person per branch
---
## Conflict Resolution Patterns
### During Rebase/Merge:
1.  **Identify conflicted files** from Git output
2.  **Edit files** to resolve marker conflicts (`<<<<<<<`, `=======`, `>>>>>>>`)
3.  **Stage resolved files**: `git add <file>`
4.  **Continue operation**: `git rebase --continue` or complete commit
### Abort Options:
```bash
# Cancel merge
git merge --abort
```
git rebase --abort   # Cancel rebase
---
## Prevention Strategies
### Repository Management:
-   **Regular pushes** to remote for backup
-   **Clear remote URLs** documentation for team
-   **SSH keys** for easier authentication
### Commit Hygiene:
-   **Review changes** before committing
-   **Use amend sparingly** and only locally
-   **Never rewrite shared history**
### Branch Discipline:
-   **Always create feature branches** for new work
-   **Regularly rebase** on parent branch
-   **Verify branch** before starting work
-   **One person per branch** rule
### Team Coordination:
-   **Clear communication** about who works where
-   **Pull before pushing** to avoid diverged branches
-   **Code reviews** before merging to main branches
---
## Emergency Recovery
### When All Else Fails:
1.  **Stash current work**: `git stash push`
2.  **Return to known good state**: `git checkout master`
3.  **Fresh start**: `git pull origin master`
4.  **Recover work**: `git stash pop` (if safe)
### Nuclear Options (Last Resort):
-   **Fresh clone** from remote
-   **Branch deletion** and recreation
-   **Complete workflow restart**
---
## Summary & Golden Rules
### Safe Practices:
-   **Commit often, push regularly**
-   **One feature per branch**
-   **Pull before push**
-   **Communicate with team**
-   **Review before committing**
### Dangerous Operations:
-   **Amend pushed commits**
-   **Force push to shared branches**
-   **Reset shared history**
-   **Work directly on main branches**
### Problem Prevention:
-   **Good workflow** eliminates most issues
-   **Regular synchronization** prevents divergence
-   **Clear team agreements** on branch usage
-   **Backup strategy** with remote repository
---
## Quick Checklist
- [ ] Know how to completely restart with fresh clone
- [ ] Understand when and how to change remote URLs
- [ ] Be able to fix commit messages with amend (before push)
- [ ] Recognize detached HEAD state and recover from it
- [ ] Know how to move work to correct branch
- [ ] Understand rebase process and conflict resolution
- [ ] Know safe solution for diverged branches (pull then push)
- [ ] Recognize dangerous operations and avoid them
- [ ] Use stashing for emergency context switching
- [ ] Follow team workflow to prevent most problems
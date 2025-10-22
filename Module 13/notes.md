# Module 13 — Managing Conflicts (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: Conflicts)
## High-level topics
-   How merging works in Git
-   Pulling and fast-forward merges
-   Understanding merge conflicts
-   Resolving conflicts step by step
-   Conflict prevention strategies
----------
## How a Merge Works
### Basic Merge Concept:
-   A merge takes commits from one branch and applies them to another
-   **Distributed nature:** Every contributor has their own copy and can change any file
-   **No file locking:** Multiple people can modify the same files simultaneously
-   Merging brings these parallel changes together
### Golden Rule of Merging:
-   Only merge branches when you're sure the commits are final
-   Merging unfinished work defeats the purpose of clear history
-   Pull Requests for unfinished work are okay, but actual merges should be complete
---
## Pulling from Remote
### What is Pulling:
-   Copies a remote branch to your local repository
-   Updates your local branch with commits from the remote
-   Essential when you're "behind" in the history timeline
### Pull Command:
```bash
# Switch to target branch
git checkout master

# Ensure clean working directory
git status

# Pull latest changes from remote
git pull origin master
```
### Behind vs Ahead Concept:
-   "Behind" is a convention, not a Git requirement
-   All repositories are independent in Git's distributed model
-   Remote servers are social constructs for team convenience
---
## Fast-Forward Merge
### What is Fast-Forward:
-   Occurs when branches are on the same timeline
-   Git simply moves the branch pointer forward
-   Cleanest merge type for history logs
-   No merge commit created in simple cases
### Characteristics:
-   Fast and efficient - only pointer movement
-   Preserves linear history
-   Always strive for fast-forward when possible
### History Visualization:
```bash
# Shows branch relationships visually
git log --oneline --graph
```
### Branch Management:
```bash
# Delete merged branches (optional)
git branch -D branch-name
```
-   Delete branches you're sure you won't need again
-   Keep branches if you might need to revisit work
---
## Merge Conflicts
### What Causes Conflicts:
-   Multiple contributors change the same parts of the same files
-   Target branch changes while you work on your feature
-   Reality "changes" by the time you finish your work
### Conflict Scenario:
1.  Check out your working branch: `git checkout develop`
2.  Make changes to files that others have also modified
3.  Attempt to pull remote changes: `git pull origin develop`
4.  Git detects overlapping changes and stops the merge
### Conflict Detection:
-   Git attempts auto-merge for different files/different file sections
-   Merge fails when same code regions are modified in both branches
-   Repository enters "merging" state until conflicts are resolved
---
## Resolving Merge Conflicts
### Step 1: Identify Conflict Files
```bash
# Shows files with conflicts under "Unmerged paths"
git status
```
### Step 2: Examine Conflict Markers
Conflict markers in files:
text
<<<<<<< HEAD
// Your local changes (current branch)
=======
// Incoming changes (remote branch)
>>>>>>> commit-hash
### Step 3: Resolve Conflicts
-   Edit the file to choose which changes to keep
-   Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
-   You can combine changes from both versions
-   Ensure the final code is syntactically correct
### Step 4: Complete the Merge
```bash
# Stage the resolved file
git add filename

# Complete the merge (pre-filled message)
git commit
```
-   Git provides a default merge commit message
-   Repository returns to normal state after commit
### Abort Option:
```bash
# Cancel the merge and return to pre-merge state
git merge --abort
```
----------
## Conflict Resolution Workflow
### Complete Process:
1.  **Pull** remote changes: `git pull origin branch-name`
2.  **Encounter** conflicts during merge
3.  **Check status**: `git status` to see conflicted files
4.  **Open conflicted files** and resolve marker sections
5.  **Stage resolved files**: `git add filename`
6.  **Commit** the merge: `git commit` (uses pre-filled message)
7.  **Verify**: `git log --oneline --graph` to see merge in history
### Best Practices:
-   **Communicate** with team members about conflicting changes
-   **Test** the merged code thoroughly
-   **Keep** the default merge message unless guidelines specify otherwise
-   **Consider aborting** if conflicts are too complex to resolve immediately
---
## Advanced Conflict Concepts
### Merge Commits:
-   Created when merging branches with divergent history
-   Have two parents (from both merged branches)
-   Contain merger information separate from original authors
### Pull Command Breakdown:
-   **Fetch**: Copies remote branch to temporary storage (FETCH_HEAD)
-   **Merge**: Merges FETCH_HEAD with current branch
-   These are two separate operations combined in `git pull`
### Visualizing Complex History:
```bash
# Complete project history with visuals
git log --oneline --graph --all
```
---
## Summary & Key Takeaways
### Conflict Philosophy:
-   Conflicts are annoying but inevitable in team development
-   Git provides clear tools to identify and resolve conflicts
-   The process is manual by design - you decide what to keep
### Essential Commands:
```bash
# Trigger potential conflicts
git pull origin branch-name

# Identify conflicted files
git status

# Mark conflicts as resolved
git add filename

# Complete the merge
git commit

# Cancel merge operation
git merge --abort
```
### Prevention Strategies:
-   **Pull frequently** to stay updated with target branch
-   **Communicate** with teammates about overlapping work
-   **Keep features small** and focused to minimize overlap
-   **Coordinate** on who works on which files
---
## Quick Checklist
- [ ] Understand what causes merge conflicts
- [ ] Know how to pull changes from remote repositories
- [ ] Recognize fast-forward vs. merge commits
- [ ] Be able to identify conflict markers in code
- [ ] Know how to resolve conflicts by editing files
- [ ] Understand the complete conflict resolution workflow
- [ ] Be able to abort a merge if needed
- [ ] Use `git log --graph` to visualize branch history
- [ ] Communicate with team members to prevent unnecessary conflicts
- [ ] Test thoroughly after resolving conflicts
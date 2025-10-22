# Module 14 — More About Conflicts (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: More About Conflicts)
## High-level topics
-   Pushing after conflict resolution
-   Reviewing changes before merging
-   Understanding merge types
-   Strategies to reduce conflicts
-   Workflow best practices
---
## Pushing After Conflict Resolution
### How Pushing Works:
-   **Push operation** copies local commits to a remote branch
-   Similar to pull but in reverse direction
-   **Two parts:** Copy local branch to remote + merge branches
-   Under normal circumstances, uses **fast-forward** merge
### Normal Push Scenario:
```bash
# Push local develop branch to remote
git push origin develop
```
### Fast-Forward Conditions:
-   Possible when local commits can be directly linked to remote commits
-   Occurs when simply adding commits sequentially
-   **No merge commit** created in fast-forward scenarios
### Post-Conflict Push:
-   Pushing after resolving conflicts and merging should proceed normally
-   No unexpected behavior unless history was changed (avoid this!)
---
## Review Changes Before Merge
### Critical Pre-Merge Steps:
#### 1. Check Branch Location
```bash
# Always checkout target branch first
git checkout target-branch

# Then merge source into target
git merge source-branch
```
#### 2. Review Branch Differences
```bash
# Compare two branches
git diff branch1..branch2

# Example: compare develop to master
git diff master..develop
```
### GitHub Alternative:
-   Push your branch and open a **Pull Request** for visual comparison
-   GitHub provides rich diff viewing interface
-   Easier for large changesets
---
## Understanding Merge Types
### Fast-Forward Merge:
-   **Scenario:** Parent branch unchanged since child branch creation
-   **Mechanism:** Git simply moves branch pointer forward
-   **Result:** Linear history, no merge commit
-   **Frequency:** Most common when working alone
### Three-Way Merge (True Merge):
-   **Scenario:** Both parent and child branches have new commits
-   **Mechanism:** Creates new **merge commit** with two parents
-   **Result:** Non-linear history, merge commit created
-   **Conflict Potential:** High when same code regions modified
### Merge Commit Characteristics:
-   Has **two parent commits** (from both merged branches)
-   Contains all changes from the child branch
-   Appended to the parent branch history
---
## Reducing Conflicts - Strategies
### 1. Adopt a Good Workflow
#### Branch Protection:
-   **Never commit directly** to main branches (master/develop)
-   **All changes** should come through merge operations
-   **Use Pull Requests** for every change, even when working alone
#### Pull Request Guidelines:
-   **Single purpose:** One PR = one issue/bugfix/feature
-   **Avoid "do-it-all" PRs** - they're conflict magnets
-   **Clear goals** make reviews easier and conflicts less likely
### 2. Standardize Code Formatting
#### Line Endings:
-   **Unix-style** (LF) most common in teams
-   Windows users should configure Git: `git config core.autocrlf true`
-   **Team agreement** essential for consistency
#### Formatting Standards:
-   **Indentation:** Spaces vs. Tabs (choose one!)
-   **Line returns:** Consistent trailing whitespace handling
-   **Team discussion** required to establish standards
> **Caution:** Tabs vs. Spaces debates can get heated - prepare your arguments!
### 3. Know When to Abort
#### Merge Abort Scenarios:
-   **Formatting conflicts** (whitespace, indentation)
-   **Trailing space differences**
-   **Non-code changes** causing unnecessary conflicts
#### Abort Command:
```bash
# Safely cancel merge, preserve all commits
git merge --abort
```
#### Recovery Process:
1.  Abort problematic merge
2.  Fix formatting differences
3.  Reattempt merge
### 4. Use Visual Tools
-   **IDE extensions** for better conflict visualization
-   **Specialized Git tools** for complex scenarios
-   **Color-coded interfaces** to distinguish changes clearly
---
## Workflow Best Practices
### Conflict Prevention:
-   **Pull frequently** to stay updated with target branch
-   **Small, focused PRs** with single responsibilities
-   **Clear communication** with team about overlapping work
-   **Consistent formatting** across the team
### PR Management:
-   **One issue per PR** - avoid combinatorial conflicts
-   **Early PR creation** - get feedback while working
-   **Clear descriptions** - help reviewers understand changes
### Team Coordination:
-   **Discuss formatting** standards before project begins
-   **Establish workflows** that everyone follows
-   **Use PR templates** for consistent information
---
## Summary & Key Takeaways
### Merge Understanding:
-   **Fast-forward:** Linear history, pointer movement only
-   **Three-way merge:** Creates merge commit, handles divergent history
-   **Conflict resolution:** Manual intervention required for overlapping changes
### Conflict Reduction:
-   **Good workflows** prevent most conflicts
-   **Standardized formatting** eliminates trivial conflicts
-   **Strategic aborting** saves time on non-essential conflicts
-   **Visual tools** make resolution easier
### Professional Habits:
-   **Always review** changes before merging
-   **Use PRs consistently** even for solo work
-   **Communicate early** about potential overlaps
-   **Test thoroughly** after conflict resolution
---
## Quick Checklist
- [ ] Understand the difference between fast-forward and three-way merges
- [ ] Know how to push safely after conflict resolution
- [ ] Always review branch differences before merging
- [ ] Use Pull Requests for all changes to main branches
- [ ] Keep PRs focused on single issues
- [ ] Establish team formatting standards early
- [ ] Know when to abort and retry problematic merges
- [ ] Consider using visual Git tools for complex conflicts
- [ ] Communicate with teammates about overlapping work
- [ ] Pull frequently to minimize divergence
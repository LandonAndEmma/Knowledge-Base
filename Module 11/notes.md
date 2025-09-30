# Module 11 — Diving into Project Management: Branches (Summary)
**Source:** Mariot Tsitoara — *Beginning Git and GitHub* (Chapter: Diving into Project Management: Branches)
## High-level topics
- GitHub workflow with branches
- What branches are and why use them
- Branch types and strategies
- Creating, switching, and deleting branches
- Merging branches
- Pushing branches to remote
---
## GitHub workflow (standard)
1. Create an issue.
2. Create a branch from the development branch.
3. Make commits on the feature branch.
4. Push the branch and open a Pull Request (PR).
5. Code review and discussion.
6. Merge via PR and delete the branch.
**Benefits**
- Isolates changes until reviewed.
- Reduces production bugs.
- Enables parallel work on multiple issues.
- Keeps project history clean and traceable.
---
## What are branches
- Branches are independent pointers to specific commits — effectively independent copies of the project at a point in time.
- They allow parallel development without interfering with other work.
- `HEAD` points to the current branch/commit.
- Common branch types:
  - **Production** (`main`/`master`): stable release code.
  - **Development** (`develop`): integration and testing.
  - **Patching**: short-lived branches for fixes or hotpatches.
---
## Branch commands
```bash
# Create a branch
git branch branch-name

# Switch to a branch
git checkout branch-name

# Create and switch
git checkout -b branch-name

# List branches (local)
git branch

# Delete a local branch
git branch -d branch-name
```
## Branch creation strategy
-   Create patch/feature branches from the development branch (not from production).
-   Never commit directly to protected production/development branches.
-   Use one branch per issue/task for clarity and traceability.
-   Delete branches after successful merge to keep the repository tidy.
-   Avoid large “do-it-all” commits that address multiple issues.
---
## Merging branches
`# Switch to the target branch (e.g., develop) git checkout develop # Merge the feature branch into the target git merge feature-branch` 
-   Merging brings commits from one branch into another and can create a merge commit with multiple parents.
-   Fast-forward merges happen when there is no divergence.
-   Merge conflicts occur when the same code was changed differently — resolve carefully.
## Pushing branches
`# Push a branch to the remote (origin) git push origin branch-name` 
-   Pushing makes the branch available on the remote and enables PR creation and code review.
-   After pushing, GitHub typically offers a quick link to create a Pull Request.
---
## Branch visualization (conceptual)
```
* (main)       - production releases
| \
|  * (develop) - development integration
|  |\
|  | * (feature-A) - feature work
|  | * (feature-B)
|  |/
|  * 
| / *          - initial commit
```
---
## Quick checklist
- [ ] Understand the standard GitHub branch workflow
- [ ] Create branches for all feature/bug work
- [ ] Use descriptive branch names (issue-123/feature-name)
- [ ] Merge via Pull Requests, not by direct commits to main/develop
- [ ] Delete merged branches to keep repository clean
- [ ] Push branches to enable collaboration and review

# Module 1 — Introduction to Version Control and Git (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_
## High-level topics
-   What is Version Control and why it's needed
-   Types of Version Control Systems (Local, Centralized, Distributed)
-   What is Git and its history
-   Key features and capabilities of Git
-   How Git works internally (Snapshots, Three States)
-   Typical Git workflow
---
## What is Version Control?
-   **Definition:** The management of multiple versions of a project. It tracks every change (addition, edition, removal) to files.
-   **Purpose:** Allows you to navigate between changes, undo or roll back changes, and see the history of a project.
-   **Teamwork:** Enables multiple people to work on their own copy of the project (branches) and merge changes safely, preventing overwrites.
> **Note:** While often used by developers, Version Control applies to any text files and can even track changes to many non-text files like images.
---
## Why do you need a VCS?
Common, inefficient methods of version tracking include:
-   Duplicate files with suffixes like "final," "reviewed," leading to confusion.
-   Compressed files with timestamps, which lack change descriptions.
-   A separate changelog file, which still doesn't allow for easy file comparison.
A Version Control System (VCS) solves these problems by:
-   Tracking each change to every file.
-   Providing a way to compare and roll back changes.
-   Showing who edited what and when.
-   Saving time by letting you focus on writing, not tracking.
---
## Types of Version Control Systems
### Local Version Control Systems (LVCS)
-   **How it works:** A single database stored locally on one computer.
-   **Drawbacks:** High risk of total loss, no team collaboration, typically tracked only one file at a time.
-   **Examples:** SCCS, RCS.
### Centralized Version Control Systems (CVCS)
-   **How it works:** A single server holds the change history, and clients connect to it.
-   **Advantages:** Enables teamwork, easy to set up and understand.
-   **Drawbacks:** Server failure can mean total loss of history, requires network connection, file locking can slow down development.
-   **Examples:** CVS, Apache Subversion (SVN).
### Distributed Version Control Systems (DVCS)
-   **How it works:** Every client has a full copy of the repository, including its entire history.
-   **Advantages:** No single point of failure, enables "forking," much faster as most operations are local.
-   **Concept:** Tracks changes as "patches" that can be freely exchanged between repositories.
-   **Examples:** BitKeeper SCM, Git.
---
## What is Git?
-   **Origin:** Created in 2005 by Linus Torvalds and the Linux community after the proprietary BitKeeper SCM became non-free.
-   **Type:** A free, open-source, Distributed Version Control System (DVCS).
-   **Goal:** Designed to be fast, efficient with large projects, and a direct replacement for BitKeeper SCM.
---
## What can Git do?
-   **Tracking Changes:**
    -   Move between versions.
    -   Review differences between versions.
    -   Check a file's change history.
    -   Tag specific versions.
-   **Teamwork:**
    -   Exchange changes between repositories.
    -   Review changes made by others.
-   **Key Features:**
    -   **Branching & Merging:** Work on isolated copies of a project and integrate changes back.
    -   **Stashing:** Temporarily save unfinished changes to work on something else.
### Common Git Commands
```bash
# Initialize a new repository
git init

# Copy an existing repository
git clone

# Check the status of files
git status

# Stage changed files for commit
git add

# Save the staged snapshot to the history
git commit

# Upload local commits to a remote repository
git push

# Download commits from a remote repository
git pull

# Check the project history
git log

# List, create, or delete branches
git branch

# Merge branches together
git merge
```
git stash      # Temporarily stash away changes
---
## How does Git work?
-   **Snapshots, Not Differences:** Unlike other VCS, Git takes a "snapshot" of the entire project state for each commit, making it very fast.
-   **Checksumming:** Every file and commit is checksummed, so Git can detect changes and file corruption.
-   **The Three States:** A file in a Git project can be in one of three main states:
    1.  **Modified:** Changed but not committed to the database.
    2.  **Staged:** A modified file has been marked to go into the next commit snapshot.
    3.  **Committed:** The data is safely stored in the local database.
---
## Typical Git Workflow
1.  **Clone** the remote repository: `git clone <repository-url>`
2.  **Create a new branch** for your work: `git branch <new-branch>`
3.  **Switch to your branch:**  `git checkout <new-branch>`
4.  **Make changes** to your files.
5.  **Stage** the changed files: `git add <file>`
6.  **Commit** the changes to your local history: `git commit -m "Descriptive message"`
7.  **Switch back** to the main branch (e.g., `master`): `git checkout master`
8.  **Pull** the latest changes from the remote: `git pull origin master`
9.  **Merge** your branch into the main branch: `git merge <your-branch>`
10.  **Push** the merged changes to the remote server: `git push`
---
## Summary & Key Takeaways
-   Distributed VCS (like Git) is more powerful and safer than Centralized VCS.
-   Git's workflow is the standard for professional and open-source teams.
-   The main concept is the Three States: working directory, staging area, and git directory.
-   The core workflow involves making changes, staging (`git add`), and committing (`git commit`).
---
## Quick checklist
- [ ] Understand the problem that Version Control solves
- [ ] Know the difference between Local, Centralized, and Distributed VCS
- [ ] Understand Git's origin and that it is a Distributed VCS
- [ ] Grasp the core concept of Git's Three States
- [ ] Familiarize yourself with the basic Git commands (`clone`, `add`, `commit`, `push`, `pull`)
- [ ] Understand the standard workflow of branching, committing, and merging
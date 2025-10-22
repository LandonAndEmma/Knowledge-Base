# Module 3 — Getting Started with Git (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_
## High-level topics
-   Repositories and initialization
-   Working Directory
-   Staging Area
-   Commits and commit messages
-   Basic Git workflow
-   Practical exercises
---
## Repositories
-   **Definition:** A storage location where all project files and their change history are kept. Essentially a "change database" that appears as a normal folder on your system.
-   **Initialization:** Create a repository by navigating to your project directory and running `git init`.
-   **Structure:** Git creates a hidden `.git` directory that contains all snapshots, changesets, and Git's internal database.
-   **Default Branch:** The initial branch is called "master" (just a convention).
### Creating a Repository
```bash
# Create project directory
mkdir mynewproject

# Navigate into directory
cd mynewproject/

# Initialize Git repository
git init
```
> **Note:**  `mkdir` and `cd` are system commands, while `init` is a Git command (all Git commands begin with "git").
---
## Working Directory
-   **Definition:** The area outside the `.git` directory where you directly work with your project files.
-   **Purpose:** Contains your most recent version of files that you can modify directly.
-   **Tracking:** Git detects any new files placed in the Working Directory.
-   **Status Check:** Use `git status` to see the current state of files in the Working Directory.
### Typical `git status` output shows:
-   Current branch (master)
-   Files that are untracked (new files)
-   Files that are modified but not staged
-   Files that are staged and ready to commit
> **Warning:** Never modify files directly inside the `.git` directory!
---
## Staging Area
-   **Purpose:** A preparatory area where you select which file changes should be included in the next snapshot.
-   **Workflow:** Only files placed in the Staging Area will be included in the commit snapshot.
-   **Adding Files:** Use `git add <filename>` to stage files.
-   **Removing Files:** Use `git rm --cached <filename>` to unstage files.
### Staging Commands
```bash
#Stage a single file
git add README.md

# Stage multiple files
git add file1.txt file2.txt

# Unstage a file (keeps it in Working Directory)
git rm --cached README.md
```
> **Caution:** Always use `--cached` when unstaging to avoid deleting your file!
---
## Commits
-   **Definition:** A snapshot of the entire project at a specific point in time.
-   **Identification:** Each commit has a unique 40-character SHA1 hash.
-   **Parentage:** Commits form a chain where each commit points to its parent (except the first commit).
-   **Information:** Contains author, committer, timestamp, and commit message.
### Creating Commits
```bash
# Opens editor for commit message
git commit

# Commits with inline message
git commit -m "Your message"
```
### Commit Message Guidelines:
-   First line: Short summary (50 characters or less)
-   Additional lines: More detailed explanation (if needed)
-   Lines starting with `#` are treated as comments and ignored
### Commit Summary shows:
-   Branch name
-   Commit hash (first 7 characters)
-   Commit message
-   Number of files changed and operations performed
---
## Basic Git Workflow
The fundamental Git workflow follows three stages:
1.  **Modify** files in the Working Directory
2.  **Stage** specific changes using `git add`
3.  **Commit** the staged snapshot using `git commit`
### Key Principles:
-   Modified but unstaged files won't be included in commits
-   Unmodified files from previous commits are automatically included
-   You must explicitly stage files before committing
---
## Practical Exercises
### Exercise 1: Create an Empty Repository
```bash
mkdir myproject
cd myproject
git init
```
### Exercise 2: Create and Track Files
-   Create files in your project directory
-   Use `git status` to see untracked files
-   Stage files using `git add`
-   Commit changes with descriptive messages
### Exercise 3: Versioned TODO App
1.  Create new repository
2.  Create `TODO.txt` with some text
3.  Stage and commit `TODO.txt`
4.  Create `DONE.txt` and `WORKING.txt`
5.  Stage and commit both new files
6.  Rename `WORKING.txt` to `IN PROGRESS.txt`
7.  Add text to `DONE.txt`
8.  Check status, stage `IN PROGRESS.txt`, unstage `DONE.txt`
9.  Commit changes
10.  Check final status
---
## Summary & Key Concepts
### The Three File States in Git:
1.  **Modified:** File is changed in Working Directory but not staged
2.  **Staged:** File is added to Staging Area and ready for commit
3.  **Committed:** File is safely stored in the Git database as part of a snapshot
### Core Workflow:
-   Work on files → Stage changes → Commit snapshots
-   Use `git status` frequently to understand current state
-   Write clear, descriptive commit messages
-   Commit early and often to maintain project history
---
## Quick Checklist
- [ ]  Understand what a Git repository is and how to create one
- [ ]  Know the difference between Working Directory, Staging Area, and Commits
- [ ]  Be able to stage and unstage files using `git add` and `git rm --cached`
- [ ]  Understand how to create commits with meaningful messages
- [ ]  Practice the basic modify → stage → commit workflow
- [ ] Complete the TODO app exercise to reinforce concepts
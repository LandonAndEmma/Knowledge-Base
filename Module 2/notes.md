
# Module 02 — Installation & Setup (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_
## Quick overview
This chapter covers:
- Installing Git on Windows, macOS, and Linux.
- Recommended installation options (use defaults unless you have a reason).
- Initial Git setup: user name, email, and default editor.
- Important cautions about PATH, line endings, and GUI clients.
## Installation — high level
**Official downloads:** https://git-scm.com/downloads
### Windows
- Visit: https://git-scm.com/download/win (download should begin automatically).
- During install, recommended defaults:
  - Leave default components checked (including Windows Explorer integration).
  - Choose a default editor (Vim is default; choose whichever you prefer).
  - Add Git to PATH (recommended) so Git is available from any console.
  - Use the default HTTPS transport (unless corporate policy requires otherwise).
  - Use the default line ending conversion for Windows.
  - Keep MinTTY terminal (default) for Git Bash.
  - Leave extra options (Git Credential Manager, etc.) enabled.
**Windows tips/caution**
- If you skip Explorer integration, use `Shift + Right-click` to open a console in a folder.
- Be careful with line ending settings — incorrect choices can create noise in diffs.
### macOS
- Git may already be installed (via Xcode CLI). Check:
$ git --version
If not present, download from https://git-scm.com/download/mac or use Homebrew:
$ brew install git
### Linux
- Use your distribution package manager:
- Debian/Ubuntu:
  ```
  $ sudo apt update
  $ sudo apt install git
  ```
- Fedora (dnf):
  ```
  $ sudo dnf install git
  ```
- Or check https://git-scm.com/download/linux for distro-specific instructions.
## Initial configuration (do this once per system)
Open your terminal (Git Bash on Windows or system terminal) and run:
$ git config --global user.name "Your Full Name"
$ git config --global user.email "your.email@example.com"
Optional: change default editor (example — use nano):
$ git config --global core.editor "nano"
## Useful checks & files
- Check Git version: $ git --version
- Global config file locations:
- Windows: `C:\Users\YourName\.gitconfig`
- macOS/Linux: `/home/yourname/.gitconfig` or `~/.gitconfig`
- You may also have a `~/.bash_history` containing typed commands.
## GUI clients and timing
- GUI clients exist, but the author strongly recommends learning the CLI first to avoid confusion.
- Git ships with two simple GUI tools: `gitk` (history viewer) and `git-gui` (basic GUI).
- Explore GUIs after you are comfortable with commands.
## Short checklist to confirm installation & setup
- [ ] `git --version` returns a version
- [ ] `git config --global user.name` is set
- [ ] `git config --global user.email` is set
- [ ] `~/.gitconfig` exists
- [ ] You chose a default editor or set one with `git config`
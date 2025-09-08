# Module 08 — GitHub Primer (Summary)

**Source:** Mariot Tsitoara — *Beginning Git and GitHub* (Chapter: GitHub Primer)

## High-level topics
- What GitHub is and why use it
- GitHub’s role in Open Source and contribution workflow (fork → work → pull request)
- Project documentation: README, Wiki, and Markdown
- GitHub Pages (hosted project websites)
- Personal use (public vs private repos, profile & contribution graph)
- GitHub for businesses / enterprise options
- Social and project-management features (stars, watch, follow, news feed)

---

## What is GitHub
- GitHub is a development platform that hosts Git repositories and adds tools to plan, review, and release software.
- Beyond code hosting, it includes features for issue tracking, PR code review, documentation (READMEs, wikis), CI/CD integrations, and Pages for hosting sites.

---

## Open Source on GitHub
- Forking is the typical workflow for contributing:
  1. Fork the repository (makes personal copy).
  2. Clone your fork and create a branch.
  3. Make changes, commit, push to your fork.
  4. Open a Pull Request (PR) from your branch to the upstream project.
  5. Maintain ers review and request changes; when accepted, your changes are merged.
- Contributions are not limited to code: docs, translations, test reports, issue triage, and community support are all valuable.

---

## Project documentation: README and Wiki
- `README.md` is the canonical, front-line project document: what the project does, how to install/run, how to contribute.
- For larger projects, use the GitHub **Wiki** for longer, structured docs (tutorials, FAQs). Wikis are themselves backed by Git.
- Markdown is the standard format for READMEs and wikis; it supports headings, lists, links, code blocks, and images.

---

## GitHub Pages
- GitHub Pages hosts static websites directly from a repository (useful for docs, portfolios, blogs).
- Pages live in a separate part of the repo and can be maintained by different contributors than the code.

---

## Personal use & profile
- Repos can be public or private; free accounts allow many private repos (contributor limits may apply for advanced features).
- Use your GitHub profile and repos to showcase work; GitHub Pages can host a portfolio or résumé.
- Contribution graph shows commit activity across repositories and is visible on your profile.

---

## Social/project features
- **Stars**: bookmark/endorse projects.
- **Follow** repositories or users to see updates in your feed.
- **Issues & Projects**: track tasks and project planning directly in the repo.
- **Pull Requests**: built-in review and discussion system for proposed changes.

---

## GitHub for businesses
- Enterprise plans add features like self-hosting, enhanced security, and paid support for teams.
- For course work and personal projects, the Free plan is usually sufficient.

---

## Basic GitHub workflow (commands + web steps)
- Fork → clone:
git clone https://github.com/<your-username>/<fork>.git
cd <repo>
git checkout -b my-feature

edit -> git add -> git commit -m "Short message"
git push origin my-feature

- Open a Pull Request on GitHub from `your-username:my-feature` → `upstream:main`.
- Keep your fork up to date:
git remote add upstream https://github.com/original-owner/repo.git
git fetch upstream
git merge upstream/main

---

## Quick checklist
- [ ] Create repository README.md that explains purpose and how to run the project
- [ ] Consider a Wiki for long-form docs or guides
- [ ] Optionally enable GitHub Pages for documentation/portfolio
- [ ] Use forks + PRs for contributing to external projects
- [ ] Keep profile contributions (and privacy settings) configured as desired
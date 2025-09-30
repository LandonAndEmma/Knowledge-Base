
# Module 10 — Beginning Project Management: Issues (Summary)

**Source:** Mariot Tsitoara — *Beginning Git and GitHub* (Chapter: Beginning Project Management: Issues)

## High-level topics
- What Issues are and why use them
- Creating and managing Issues
- Labels for organization and filtering
- Assigning issues to team members
- Linking commits to issues
- Closing issues with commit messages

---

## Issues overview
- Issues track features, bugs, discussions, and ideas.
- Every development action should relate to an issue when possible.
- Issues provide project history and planning transparency.
- They replace ad-hoc methods like email chains and scattered meetings.

---

## Creating and managing issues
- Only a **title** is required; a description is optional but recommended.
- Each issue receives a unique, non-recyclable **issue number**.
- Issues include a comment thread for discussion and emoji reactions.
- Users can **subscribe** to an issue to receive notifications.
- **Close** completed issues (do not delete) to preserve project history.

---

## Labels
- Labels are text tags used to organize and filter issues.
- Repositories include default labels (e.g., `bug`, `enhancement`, `documentation`) which are fully customizable.
- Use labels for quick filtering, prioritization, and categorization.
- Multiple labels can be applied to a single issue.

---

## Assignees
- Assign issues to specific team members to make responsibilities explicit (GitHub supports multiple assignees; commonly limited to up to 10).
- Assignees make it easy to filter and report on ownership.
- Combine assignees with labels for powerful project organization.

---

## Linking commits to issues
- Structure commit messages for traceability:
- Title (imperative mood)
- Body (optional — detailed explanation)
- Footer: #issue-number
- Reference issues in the commit footer using `#123` to link code changes to issues.
- GitHub will automatically link commits to the referenced issue, improving traceability.

---

## Closing issues with keywords
- Closing keywords (used in commit messages or PR descriptions):
- `close`, `closes`, `closed`
- `fix`, `fixes`, `fixed`
- `resolve`, `resolves`, `resolved`
- Example commit message that closes an issue:
- Add user authentication
- Implements login with password hashing and session tokens.
- Resolves #123
- Use the imperative form in the commit title/body and a closing keyword + issue number in the footer.
- Be certain before closing an issue — reopening can cause confusion.

---

## Workflow best practices
- Create an issue for every task, bug, or feature proposal.
- Apply appropriate labels and assign owners.
- Reference the related issue(s) in commits and pull requests.
- Use closing keywords only when the issue is truly resolved.
- Keep issues open until work and verification are complete to preserve history.

---

## Quick checklist
- [ ] Create issues for all planned work
- [ ] Use labels consistently for organization
- [ ] Assign issues to appropriate team members
- [ ] Reference issues in commit messages and PRs
- [ ] Use closing keywords when work is complete
- [ ] Maintain issue history rather than deleting

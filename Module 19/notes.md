# Module 19 — Git and GitHub Workflow (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: Git and GitHub Workflow)
## High-level topics
-   GitHub as a project management tool
-   Essential GitHub workflow rules
-   Git best practices and rituals
-   Team collaboration guidelines
-   Workflow adaptation strategies
---
## Workflow Philosophy
### Purpose:
-   **Comprehensive guide** for successful project management
-   **Best practices** compilation from previous chapters
-   **Adaptable framework** for teams and individuals
-   **Foundation** for building efficient development habits
### Implementation Approach:
-   **Beginners:** Follow religiously to build proper habits
-   **Experienced:** Modify carefully while maintaining security
-   **Experts:** Create custom workflows that enhance team efficiency
### Core Principle:
**Never forfeit security for time** - shortcuts lead to more bugs and conflicts
---
## GitHub Workflow Rules
### 1. Every Project Starts with a Project
-   **Create Project Boards immediately** after repository creation
-   **Minimum:** One Kanban board for "to do" tracking
-   **Additional boards** for user feedback, ideas, releases
-   **Document everything** - ideas are easily forgotten
### 2. Every Action Starts with an Issue
-   **Bugs:** Create Issue first, then fix code
-   **Features:** Document ideas as Issues immediately
-   **Small tasks:** Always create Issues, no matter how minor
-   **Question to ask:** "What Issue does this resolve?"
### 3. No Direct Push to Master
-   **Absolute rule:** Never push directly to master branch
-   **All changes** must go through feature branches
-   **"Ready" means:** Properly reviewed and tested
-   **Exception:** None - this is non-negotiable
### 4. Any Merge into Master Needs a PR
-   **Pull Requests required** for all merges to master
-   **Code review** by team members mandatory
-   **Reference Issues** in PR descriptions for automatic closing
-   **Discussion and approval** before merging
### 5. Use Wiki to Document Your Code
-   **README.md insufficient** for comprehensive documentation
-   **Write documentation concurrently** with code development
-   **Small, frequent updates** prevent documentation debt
-   **Preserve crucial information** that code alone doesn't convey
---
## Git Workflow Rules
### 1. Always Know Where You Are
-   **Verify current branch** before making changes
-   **Modern IDEs** show branch in status bar
-   **Fallback:**  `git status` or `git branch`
-   **Prevention:** Avoid working on wrong branches
### 2. Pull Remote Changes Before Any Action
-   **Update local master** before creating new branches
-   **Regular rebasing** from parent branch during development
-   **Benefits:** Fewer conflicts, cleaner history graphs
-   **Frequency:** Before starting work and periodically during development
### 3. Take Care of Your Commit Messages
-   **Follow Chapter 5 guidelines** for quality messages
-   **Clear, descriptive messages** are historical records
-   **Bad messages cost time** during bug investigations
-   **Investment:** Few minutes now saves hours later
### 4. Don't Rewrite History
-   **Never amend pushed commits** on shared branches
-   **Force push destroys** others' work and causes conflicts
-   **Exception:** Only if working alone on a branch
-   **Team impact:** Others must discard and reset their work
---
## Complete Development Workflow
### Issue-Driven Development:
1.  **Identify need** (bug, feature, improvement)
2.  **Create Issue** on GitHub with clear description
3.  **Discuss and plan** with team if needed
### Local Development:
1.  **Pull latest** from master: `git pull origin master`
2.  **Create feature branch**: `git checkout -b feature/issue-description`
3.  **Make changes** and commit with clear messages
4.  **Regularly rebase** from master: `git rebase master`
5.  **Push branch**: `git push origin feature/issue-description`
### Collaboration Phase:
1.  **Create Pull Request** referencing the Issue
2.  **Team review** with discussions and suggestions
3.  **Make requested changes** and push updates
4.  **Approval and testing** by team members
### Completion:
1.  **Merge PR** to master (squash or regular merge)
2.  **Close referenced Issues** automatically
3.  **Delete feature branch** (optional but recommended)
4.  **Update documentation** in wiki if needed
---
## Team Collaboration Guidelines
### Communication:
-   **Clear Issue descriptions** with acceptance criteria
-   **Descriptive PR titles** and detailed descriptions
-   **Regular team syncs** on Project Board status
-   **Transparent decision making** documented in Issues
### Code Quality:
-   **PR reviews** are learning opportunities, not criticism
-   **Consistent coding standards** across the team
-   **Testing requirements** defined per project
-   **Documentation updates** part of definition of done
### Conflict Prevention:
-   **One person per branch** rule
-   **Regular communication** about overlapping work
-   **Early PR creation** for visibility
-   **Continuous integration** for automatic testing
---
## Workflow Benefits
### For Individuals:
-   **Clear focus** on specific Issues
-   **Reduced context switching**
-   **Better time management**
-   **Professional habit development**
### For Teams:
-   **Transparent progress** tracking
-   **Knowledge sharing** through reviews
-   **Quality assurance** through multiple eyes
-   **Historical context** for future maintenance
### For Projects:
-   **Comprehensive documentation**
-   **Clean, understandable history**
-   **Stable main branch**
-   **Scalable processes**
---
## Common Pitfalls to Avoid
### GitHub Missteps:
-   **Skipping Issue creation** for "quick fixes"
-   **Direct commits to master** for urgency
-   **Incomplete PR descriptions** without Issue references
-   **Neglected documentation** until it's overwhelming
### Git Mistakes:
-   **Working on wrong branch** due to inattention
-   **Infrequent pulling** leading to massive conflicts
-   **Vague commit messages** that obscure intent
-   **History rewriting** that disrupts team workflow
### Team Dysfunctions:
-   **Skipping reviews** for speed
-   **Poor communication** about blocking Issues
-   **Inconsistent standards** across contributors
-   **Documentation as afterthought**
---
## Summary & Golden Rules
### GitHub Commandments:
1.  **Project Boards first** - track everything
2.  **Issues drive development** - document all work
3.  **Protect master** - no direct pushes
4.  **PRs for all changes** - review and discuss
5.  **Document as you go** - wiki alongside code
### Git Principles:
1.  **Branch awareness** - know where you work
2.  **Stay updated** - pull and rebase regularly
3.  **Meaningful commits** - clear historical record
4.  **Preserve history** - never rewrite shared branches
### Success Mindset:
-   **Discipline over speed** - quality trumps haste
-   **Communication over assumption** - clarity prevents errors
-   **Documentation over memory** - written records endure
-   **Collaboration over isolation** - team strength multiplies output
---
## Quick Checklist
- [ ] Create Project Boards for every new project
- [ ] Always create Issues before starting work
- [ ] Never push directly to master branch
- [ ] Use Pull Requests for all merges to master
- [ ] Reference Issues in PR descriptions
- [ ] Maintain wiki documentation alongside code
- [ ] Always verify current branch before working
- [ ] Pull latest changes before creating branches
- [ ] Write clear, descriptive commit messages
- [ ] Never rewrite history on shared branches
- [ ] Use meaningful branch names
- [ ] Regular rebasing during feature development
- [ ] Delete merged branches to reduce clutter
- [ ] Communicate with team about overlapping work
- [ ] Treat PR reviews as collaborative learning
----------
## Final Recommendation
**Start strict, then adapt** - Follow this workflow exactly until the practices become second nature, then carefully customize based on proven experience and team needs while maintaining the core principles that ensure project success.
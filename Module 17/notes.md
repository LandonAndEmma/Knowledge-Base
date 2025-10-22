# Module 17 — More with GitHub (Summary)
**Source:** Mariot Tsitoara — _Beginning Git and GitHub_ (Chapter: More with GitHub)
## High-level topics
-   Wikis for project documentation
-   GitHub Pages for project hosting
-   Releases for software distribution
-   Project Boards for project management
---
## Wikis
### Purpose:
-   Provide **in-depth documentation** for projects
-   Explain what the project does, how it works, and how to contribute
-   Similar to Wikipedia but for your specific project
### Creating Wiki Pages:
1.  Navigate to your project → Click "Wiki" tab
2.  Click "Create the first page" button
3.  Fill in:
    -   **Title:** Clear and descriptive page title
    -   **Content:** Written in Markdown (recommended)
    -   **Edit message:** Description of changes (like commit messages)
### Best Practices:
-   Use **Markdown** for consistency with README files
-   Create multiple pages for different topics
-   Include **images and relevant links**
-   Focus on **comprehensible and useful** content
### Example Wiki Structure:
```markdown
# What is this
Project description and purpose
# Why this project
Explanation of project's value
# How does it work
Usage instructions and technical details
# How to contribute
Contribution guidelines and links to issues
```
---
## GitHub Pages
### What are GitHub Pages:
-   **Free static website hosting** provided by GitHub
-   Can be used for **project showcases, portfolios, or documentation**
-   Available for both **personal accounts** and **individual projects**
### Setting Up Pages:
1.  Go to project → **Settings** → **Pages** (scroll down)
2.  Choose source:
    -   **Master branch** - root directory
    -   **Master branch/docs folder** - recommended for clarity
3.  Create `docs/index.html` with your content
4.  Save and access via provided GitHub Pages URL
### Technical Details:
-   **Static sites only** (HTML, CSS, JavaScript)
-   Can use **Jekyll** for easier site generation
-   Project's own HTML files can serve as the Page content
-   Automatic publishing after configuration
### Use Cases:
-   **Project documentation** sites
-   **Personal portfolios** and resumes
-   **Project showcases** and demos
-   **Team information** pages
---
## Releases
### Purpose:
-   **Formal software distribution** and version management
-   Package and distribute **application binaries**
-   Mark significant project milestones
### Creating Releases:
1.  Navigate to project → **Releases** → **Create a new release**
2.  Fill release form:
    -   **Tag version:** Version number (e.g., v1.0.0)
    -   **Release title:** Descriptive name
    -   **Description:** Release notes and changes
    -   **Attach binaries:** Drag and drop distributable files
3.  Choose **target** (branch or specific commit)
4.  **Publish** release
### Release Components:
-   **Source code** (automatically included)
-   **Compiled binaries** (manually attached)
-   **Release notes** with change descriptions
-   **Version tags** for reference
### Best Practices:
-   **Test thoroughly** before releasing
-   Include **clear release notes**
-   Attach **all necessary binaries**
-   Use **semantic versioning** (v1.0.0, v1.1.0, v2.0.0)
---
## Project Boards
### Purpose:
-   **Visual project management** and progress tracking
-   Organize and prioritize **issues, PRs, and notes**
-   Kanban-style workflow visualization
### Creating Project Boards:
1.  Navigate to project → **Projects** → **Create a project**
2.  Choose template:
    -   **Basic Kanban** (recommended for beginners)
    -   **Automated Kanban** (auto-moves cards)
    -   **Blank** (custom setup)
### Basic Kanban Structure:
-   **To do:** Planned but not started work
-   **In progress:** Currently being worked on
-   **Done:** Completed items
### Using Project Boards:
-   **Drag and drop** issues between columns
-   Track **progress visually** with colored bars
-   Include **notes and PRs** alongside issues
-   Use for various purposes beyond issue tracking
### Advanced Features:
-   **Automated Kanban:** Automatically moves cards based on status
-   **Multiple boards:** Different boards for releases, meetings, ideas
-   **Progress tracking:** Visual indicators of project completion
### Use Cases:
-   **Development workflow** tracking
-   **Release planning** and tracking
-   **Meeting notes** organization
-   **Feature brainstorming** and prioritization
-   **User feedback** management
---
## GitHub Ecosystem Integration
### Connected Features:
-   **Issues** automatically link to Project Boards
-   **Releases** connect to specific commits/tags
-   **Wikis** provide documentation alongside code
-   **Pages** offer public-facing project information
### Workflow Benefits:
-   **Centralized project management** in one platform
-   **Transparent progress** tracking for teams
-   **Comprehensive documentation** alongside code
-   **Professional release** management
---
## Professional Usage Tips
### Documentation Strategy:
-   Use **Wikis** for detailed technical documentation
-   Keep **[README.md](https://readme.md/)** for quick start guides
-   Use **GitHub Pages** for user-facing documentation
-   Maintain **consistent formatting** across all documentation
### Release Management:
-   Create **releases for major versions**
-   Include **comprehensive release notes**
-   Attach **all distribution formats** needed
-   Use **meaningful version numbers**
### Project Management:
-   Start with **Basic Kanban** and evolve as needed
-   **Regularly update** Project Board status
-   Use **Automated Kanban** to reduce manual updates
-   Create **multiple boards** for complex projects
### Team Collaboration:
-   **Wikis** for shared knowledge base
-   **Project Boards** for coordinated workflow
-   **Releases** for synchronized deployment
-   **Pages** for unified public presence
---
## Summary & Best Practices
### Documentation Excellence:
-   **Wikis** for deep technical details
-   **README** for quick onboarding
-   **Pages** for public documentation
-   **Consistent** formatting and style
### Professional Releases:
-   **Regular, versioned** releases
-   **Clear release notes** with changes
-   **Tested binaries** and source code
-   **Semantic versioning** standards
### Effective Project Management:
-   **Visual workflow** with Project Boards
-   **Regular updates** and maintenance
-   **Appropriate templates** for your needs
-   **Progress tracking** for motivation
### Platform Integration:
-   Leverage **all GitHub features** together
-   Create **comprehensive project ecosystem**
-   Maintain **consistent quality** across all areas
-   Use **automated features** to save time
---
## Quick Checklist
- [ ] Create project Wiki with essential documentation
- [ ] Set up GitHub Pages for project showcase
- [ ] Create formal releases with version tags
- [ ] Establish Project Boards for workflow management
- [ ] Use Markdown consistently across all documentation
- [ ] Test thoroughly before creating releases
- [ ] Choose appropriate Project Board templates
- [ ] Link issues to Project Boards for tracking
- [ ] Maintain clear release notes with each version
- [ ] Use GitHub features as integrated ecosystem rather than separate tools
# GitHub Onboarding Documentation

## 1. Introduction

Welcome to the team! This document will guide you through setting up GitHub, understanding our workflows, and following best practices to collaborate efficiently. GitHub is a powerful platform for version control and collaboration, allowing multiple developers to work on projects simultaneously.

## 2. Access & Setup

### a. Creating a GitHub Account
- Go to [GitHub.com](https://github.com/).
- Sign up using your work email.
- Set up your profile with your name, avatar, and company details.
- Configure your notification preferences to stay updated on project activities.

### b. Getting Access to the Organization
- Request access from the team lead or administrator.
- Accept the invitation email sent by GitHub.
- Verify that you can see the repositories under the organization’s GitHub page.
- Configure organization-level settings like team membership and permissions.

### c. Installing Required Tools
- Install Git for command-line access.
- Install GitHub Desktop for a graphical interface (optional).
- Set up SSH keys ([Guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)) for secure authentication.
- Install a code editor such as VS Code or JetBrains IntelliJ.

## 3. Understanding Git & GitHub Basics

### Common Git Commands
```sh
git clone <repository-url>
git branch <branch-name>
git checkout <branch-name>
git add .
git commit -m "commit message"
git push origin <branch-name>
git pull origin main  # Sync with main branch
git merge <branch-name>  # Merge changes
```

### GitHub Concepts
- **Repositories**: Storage for project files, including code, documentation, and configurations.
- **Branches**: Isolated environments for development, used for new features and fixes.
- **Pull Requests (PRs)**: Proposed changes before merging into the main branch, allowing for review and discussion.
- **Issues**: Used to track bugs, enhancements, and tasks for the project.
- **Forking**: Creating a personal copy of a repository to make independent changes before contributing back.

## 4. GitHub Workflows & Best Practices

### a. Branching Strategy

A clear branching strategy is crucial for organized development.

**Feature Branch Workflow (Recommended for Teams)**
- Developers create separate branches for each feature or bug fix.
- All work is done in isolated branches to avoid disrupting the main codebase.

**Example branch names:**
- `main` → Production-ready code, stable and deployable.
- `develop` → Active development, staging area before merging into main.
- `feature/xyz` → Feature-specific branches for individual contributions.
- `bugfix/xyz` → Fix-specific branches for resolving issues.

### b. Commit Message Guidelines

Clear and meaningful commit messages help maintain a readable history.

#### Format:
```
[Feature] Implement user authentication
[Bugfix] Fix login button issue
[Docs] Update README file
[Refactor] Improve code structure
```
✅ **Follow Guidelines:**
- Keep messages clear and concise.
- Use present-tense verbs (e.g., “Add”, “Fix”, “Update”).
- Reference issue numbers if applicable (e.g., Fix #42).

❌ **Avoid Generic Messages:**
```
Fixed it
Updated stuff
Some changes
```

### c. Pull Request (PR) Process

A structured PR process ensures quality and maintainability.

#### Steps to Create a PR:
1. **Create a feature branch:**
   ```sh
   git checkout -b feature/add-user-auth
   ```
2. **Make changes and commit:**
   ```sh
   git add .  
   git commit -m "[Feature] Add JWT-based authentication"
   ```
3. **Push to the remote repository:**
   ```sh
   git push origin feature/add-user-auth
   ```
4. **Open a Pull Request:**
   - Compare against `main` or `develop` (depending on workflow).
   - Add a descriptive title and summary.
   - Request code reviews.
   - Assign labels and link related issues.

✅ **Best Practice:**
- Keep PRs small, focused, and well-documented.
- **Avoid:** Merging without reviews or large PRs with multiple unrelated changes.

### d. Code Review Guidelines

- Read the PR description first – Understand the context.
- Check for logic errors, security issues, and best practices.
- Test locally if needed.
- Ensure tests are included and pass before merging.
- Provide constructive feedback – Use inline comments to suggest improvements.
- Approve or request changes with explanations.

✅ **Best Practice:**
Encourage team members to review each other’s code before merging.

## 5. Issue & Project Management

- **Creating Issues:** Clearly describe bugs or feature requests, assign priorities, and add labels.
- **Assigning Issues:** Assign tasks to the relevant team members.
- **Using Labels & Milestones:** Categorize issues for better tracking (e.g., bug, enhancement, documentation).
- **Project Boards**: Use GitHub Projects or Jira for task management and sprint planning.
   - **Kanban Boards** – Organize tasks in "To Do," "In Progress," and "Done."  
   - **Milestones** – Track major feature releases or deadlines.  
   - **Automations** – Move issues automatically based on PR merges.  

## 6. Security & Compliance

- Enable **Two-Factor Authentication (2FA)** for account security.
- Never commit credentials (use environment variables instead).
- Use GitHub’s security tools to scan for vulnerabilities.
- Use SSH keys instead of passwords for authentication.
- Enable **branch protection rules** to prevent accidental merges to `main`.
- Use **GitHub Code Scanning** to detect vulnerabilities.

## 7. Automation & CI/CD

- **GitHub Actions:** Automate build and deployment workflows.
- **Automated Testing:** Ensure all code passes tests before merging.
- **Deployment Pipelines:** Use CI/CD tools like Jenkins, GitHub Actions, or CircleCI for automated deployments.

### Example GitHub Actions Workflow (.github/workflows/test.yml):
```yaml
name: Run Tests
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install Dependencies
        run: npm install

      - name: Run Tests
        run: npm test
```

## 8. Documentation & Knowledge Sharing

- Maintain a **README.md** with installation/setup instructions.
- Use **CONTRIBUTING.md** for guidelines on contributing to the project.
- Document API endpoints using OpenAPI or Swagger.
- Keep changelogs updated (**CHANGELOG.md**).

✅ **Best Practice:**
Encourage a culture of documentation to help new developers onboard quickly.

## 9. Additional Resources & Support

- **GitHub Docs:** [https://docs.github.com/](https://docs.github.com/)
- **Internal Wiki:** Refer to the company wiki for project-specific guidelines.
- **Support Contact:** Reach out to `dev-support@company.com` for assistance.

Welcome aboard! Happy coding! 🚀

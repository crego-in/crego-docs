# Git Rules and Standards

This document outlines the mandatory Git workflow rules and standards for our development team. These rules ensure consistency, maintainability, and quality across all repositories.

## Core Branching Rules

### Main Branch
- The default branch must always be set to `main`
- The `main` branch should always contain production-ready, deployable code
- **Never commit directly to the `main` branch**

### Branch Creation and Naming
- Always create new branches from the latest `main` branch
- Use descriptive branch names following this structure:
  - **Features**: `feat/featureName` (e.g., `feat/user-authentication`, `feat/payment-gateway`)
  - **Bug fixes**: `fix/fixName` (e.g., `fix/login-error`, `fix/memory-leak`)
  - **Other types**: `chore/taskName`, `docs/updateName`, `build/configName`

### Branch Lifecycle
- **Never reuse merged branches** - always create unique branches for new work
- Delete branches after successful merge to keep the repository clean
- Keep branches short-lived - merge frequently to avoid conflicts

## Pull Request (PR) Rules

### Mandatory PR Process
- **All changes must go through Pull Requests** - no exceptions
- Every PR must be reviewed by at least one other team member before merging
- Exception: Life and death situations only (must be documented and justified)

### PR Requirements
- **One commit per PR at merge time** - squash multiple commits during merge
- **Always use "Rebase and merge" strategy** - never use regular merge commits
- Include JIRA card link in PR description (mandatory)
- For multi-repository features: all related PRs must reference each other and include the same JIRA card link

### PR Description Template
```
## Description
Brief description of changes made

## JIRA Link
[TICKET-123](link-to-jira-ticket)

## Related PRs (if applicable)
- [Repo Name PR #XX](link)
- [Another Repo PR #YY](link)

## Testing
- [ ] Manual testing completed
- [ ] All existing tests pass
```

## Commit Message Standards

We follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification for all commit messages.

### Commit Message Format
```
<type>(subject): <description>
```

### Common Types (Most Used)
- **feat**: New feature implementation
  - Example: `feat(auth): add user login functionality`
- **fix**: Bug fixes
  - Example: `fix(payment): resolve checkout validation error`

### Additional Types
- **chore**: Maintenance tasks, dependency updates
- **docs**: Documentation changes
- **build**: Build system or dependency changes
- **style**: Code formatting (no functional changes)
- **refactor**: Code refactoring (no functional changes)
- **test**: Adding or modifying tests

### Commit Message Rules
- Write in **present tense** and keep it concise
- Use **lowercase** for the description
- No period at the end of the description
- Be specific about what was changed
- Reference JIRA ticket in commit body if needed

### Examples
```bash
feat(user): add password reset functionality
fix(api): handle null response in user service
chore(deps): update React to version 18.2
docs(readme): add installation instructions
```

## Repository Maintenance

### README.md Requirements
- Every repository **must maintain** a README.md file at all times
- Keep README updated with:
  - Project description
  - Installation instructions
  - Usage examples
  - Contributing guidelines
  - Contact information

### File Management
- Use `.gitignore` to exclude unnecessary files
- Never commit sensitive information (API keys, passwords, etc.)
- Keep repository clean and organized

## Workflow Summary

1. **Create branch**: `git checkout main && git pull && git checkout -b feat/new-feature`
2. **Make changes**: Edit, add, commit following conventional commit format
3. **Push branch**: `git push -u origin feat/new-feature`
4. **Create PR**: Include JIRA link and proper description
5. **Code review**: At least one approval required
6. **Merge**: Use "Rebase and merge" with single commit
7. **Cleanup**: Delete merged branch

## Quality Standards

### Code Review Focus
- Functionality and logic correctness
- Code readability and maintainability
- Adherence to project coding standards
- Security considerations
- Performance implications

### Best Practices
- Keep PRs small and focused (single responsibility)
- Write clear, descriptive commit messages
- Test thoroughly before creating PR
- Respond promptly to review feedback
- Be constructive in code review comments

---

**Remember**: These rules help maintain code quality, enable better collaboration, and ensure project maintainability. When in doubt, err on the side of more communication and documentation rather than less.
# Git Best Practices

Professional Git workflows, commit standards, and collaboration guidelines for maintainable projects and effective teamwork.

## Commit Best Practices

### Writing Good Commit Messages

#### Format Structure
```bash
# Basic format
<type>: <subject>

<body>

<footer>
```

#### Conventional Commits
```bash
# Feature additions
git commit -m "feat: add user authentication system"
git commit -m "feat(api): add user registration endpoint"

# Bug fixes
git commit -m "fix: resolve login validation bug"
git commit -m "fix(ui): correct button alignment on mobile"

# Documentation
git commit -m "docs: update API documentation"
git commit -m "docs(readme): add installation instructions"

# Code style/formatting
git commit -m "style: format code according to style guide"
git commit -m "style(css): fix indentation in header component"

# Refactoring
git commit -m "refactor: simplify authentication logic"
git commit -m "refactor(utils): extract common validation functions"

# Tests
git commit -m "test: add unit tests for user service"
git commit -m "test(integration): add API endpoint tests"

# Chores/maintenance
git commit -m "chore: update dependencies to latest versions"
git commit -m "chore(build): configure webpack for production"
```

#### Message Guidelines
```bash
# Good commit messages
git commit -m "feat: add password reset functionality via email"
git commit -m "fix: prevent crash when user has no profile image"
git commit -m "docs: add code examples to authentication guide"

# Bad commit messages
git commit -m "fix stuff"
git commit -m "WIP"
git commit -m "updated files"
git commit -m "changes"
git commit -m "asdf"
```

### Commit Frequency and Size

#### Make Small, Focused Commits
```bash
# Good: One logical change per commit
git add auth.js
git commit -m "feat: add login validation"

git add auth.js
git commit -m "feat: add logout functionality"

# Bad: Multiple unrelated changes
git add .
git commit -m "add login, fix css, update readme"
```

#### Commit Often
```bash
# Good workflow: commit frequently
git add login-form.html
git commit -m "feat: create login form structure"

git add styles.css
git commit -m "style: add login form styling"

git add validation.js
git commit -m "feat: add client-side form validation"

git add auth-service.js
git commit -m "feat: add authentication service"
```

## Branch Management

### Branch Naming Conventions
```bash
# Feature branches
feature/user-authentication
feature/payment-integration
feature/mobile-responsive-design

# Bug fix branches
bugfix/login-validation-error
bugfix/memory-leak-in-dashboard
fix/critical-security-vulnerability

# Hotfix branches (for production)
hotfix/security-patch-v1.2.1
hotfix/payment-gateway-timeout

# Release branches
release/v1.2.0
release/2023-Q4-launch

# Documentation branches
docs/api-documentation
docs/user-manual-update

# Experiment branches
experiment/new-ui-framework
poc/performance-optimization
```

### Branch Workflow
```bash
# 1. Always start from updated main
git checkout main
git pull origin main

# 2. Create descriptive feature branch
git checkout -b feature/user-profile-edit

# 3. Work in small commits
git add profile-component.js
git commit -m "feat: create user profile edit component"

git add profile-api.js
git commit -m "feat: add profile update API endpoint"

# 4. Push branch regularly
git push -u origin feature/user-profile-edit

# 5. Keep branch updated with main
git checkout main
git pull origin main
git checkout feature/user-profile-edit
git rebase main  # or git merge main

# 6. Clean up after merge
git checkout main
git pull origin main
git branch -d feature/user-profile-edit
```

## Repository Structure

### .gitignore Best Practices
```bash
# Language-specific ignores
node_modules/
*.pyc
__pycache__/
.env
.venv/
*.class
target/

# OS-specific ignores
.DS_Store
Thumbs.db
*.swp
*.swo

# IDE ignores
.vscode/
.idea/
*.sublime-*

# Build artifacts
dist/
build/
*.min.js
*.map

# Sensitive files
.env
.env.local
config/secrets.yml
*.pem
*.key

# Logs
*.log
logs/
npm-debug.log*
```

### Repository Organization
```bash
# Good repository structure
project/
├── .gitignore
├── README.md
├── package.json
├── src/
│   ├── components/
│   ├── services/
│   └── utils/
├── tests/
├── docs/
└── config/

# Include essential files
README.md        # Project overview and setup
LICENSE          # Open source license
.gitignore       # Ignore patterns
CONTRIBUTING.md  # Contribution guidelines
CHANGELOG.md     # Version history
```

## Collaboration Workflows

### Pull Request Best Practices

#### Before Creating PR
```bash
# 1. Update your branch
git checkout feature-branch
git rebase main

# 2. Run tests
npm test  # or your test command

# 3. Review your changes
git diff main..feature-branch

# 4. Push updated branch
git push --force-with-lease origin feature-branch
```

#### PR Description Template
```markdown
## Summary
Brief description of what this PR does.

## Changes Made
- Added user authentication system
- Updated login form validation
- Fixed responsive design issues

## Testing
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed
- [ ] Cross-browser testing done

## Screenshots (if applicable)
[Add screenshots for UI changes]

## Breaking Changes
None / [List any breaking changes]

## Related Issues
Closes #123
Related to #456
```

### Code Review Guidelines

#### For Authors
```bash
# Keep PRs small and focused
# Good: 50-200 lines of changes
# Bad: 1000+ lines mixing multiple features

# Self-review before requesting review
git diff main..feature-branch

# Respond to feedback constructively
# Make requested changes in new commits
# Don't force-push until review is complete
```

#### For Reviewers
```bash
# Check out the branch locally for testing
git fetch origin
git checkout feature-branch

# Run tests and verify functionality
npm test
npm start

# Look for:
# - Code quality and readability
# - Security issues
# - Performance implications
# - Test coverage
# - Documentation updates
```

## Security Best Practices

### Never Commit Secrets
```bash
# Use environment variables
# Good:
const apiKey = process.env.API_KEY;

# Bad:
const apiKey = "sk_live_abc123...";

# Use .env files (and .gitignore them)
echo ".env" >> .gitignore
echo "API_KEY=your_key_here" > .env
```

### SSH Keys Setup
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your-email@example.com"

# Add to SSH agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy public key to clipboard
# macOS:
pbcopy < ~/.ssh/id_ed25519.pub
# Linux:
xclip -sel clip < ~/.ssh/id_ed25519.pub

# Add to GitHub: Settings > SSH and GPG keys
```

### Signing Commits
```bash
# Generate GPG key
gpg --full-generate-key

# List GPG keys
gpg --list-secret-keys --keyid-format LONG

# Configure Git to use GPG key
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true

# Sign commits
git commit -S -m "feat: add secure authentication"
```

## Performance and Maintenance

### Keep Repository Clean
```bash
# Remove merged branches regularly
git branch --merged | grep -v "main\|master" | xargs git branch -d

# Clean up remote tracking branches
git remote prune origin

# Garbage collect to optimize repository
git gc

# Show repository size
git count-objects -vH
```

### Large File Management
```bash
# Use Git LFS for large files
git lfs install
git lfs track "*.psd"
git lfs track "*.zip"
git lfs track "videos/*"

git add .gitattributes
git commit -m "chore: configure Git LFS for large files"

# Check LFS status
git lfs ls-files
```

### Useful Aliases
Add to `.gitconfig`:
```bash
[alias]
    # Status and log shortcuts
    st = status -s
    lg = log --oneline --graph --all
    ll = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    
    # Branch management
    br = branch
    co = checkout
    cb = checkout -b
    
    # Commit shortcuts
    ci = commit
    ca = commit -a
    cm = commit -m
    cam = commit -am
    
    # Remote shortcuts
    pl = pull
    ps = push
    pso = push origin
    psu = push --set-upstream origin
    
    # Useful shortcuts
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
    
    # Cleanup
    cleanup = "!git branch --merged | grep -v '\\*\\|main\\|master' | xargs -n 1 git branch -d"
    
    # Show files ignored by git
    ignored = !git status --ignored --short | grep "^!!" | cut -c4-
```

## Team Workflows

### Gitflow Workflow
```bash
# Main branches
main/master     # Production code
develop         # Integration branch

# Supporting branches
feature/*       # New features (from develop)
release/*       # Release preparation (from develop)
hotfix/*        # Emergency fixes (from main)

# Example workflow
git checkout develop
git checkout -b feature/new-feature
# ... develop feature ...
git checkout develop
git merge --no-ff feature/new-feature
git branch -d feature/new-feature
```

### GitHub Flow (Simpler)
```bash
# Simple workflow
main            # Always deployable
feature/*       # Feature branches from main

# Workflow
git checkout main
git pull origin main
git checkout -b feature/new-feature
# ... develop feature ...
git push -u origin feature/new-feature
# ... create pull request ...
# ... after review and merge ...
git checkout main
git pull origin main
git branch -d feature/new-feature
```

## Continuous Integration

### Pre-commit Hooks
```bash
# Install pre-commit framework
pip install pre-commit

# Create .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.4.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-added-large-files

# Install hooks
pre-commit install

# Run on all files
pre-commit run --all-files
```

### GitHub Actions Example
```yaml
# .github/workflows/ci.yml
name: CI
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm ci
      - run: npm test
      - run: npm run lint
```

## Documentation Standards

### README Template
```markdown
# Project Name

Brief description of what this project does.

## Installation

```bash
git clone https://github.com/username/project.git
cd project
npm install
```

## Usage

```bash
npm start
```

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'feat: add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## License

This project is licensed under the MIT License - see LICENSE file.
```

### Changelog Format
```markdown
# Changelog

## [1.2.0] - 2023-12-01

### Added
- User authentication system
- Password reset functionality

### Changed
- Updated UI design for better accessibility

### Fixed
- Fixed memory leak in dashboard
- Resolved login validation bug

### Security
- Updated dependencies to patch security vulnerabilities
```

## Next Steps

- **[Git Troubleshooting](Git%20Troubleshooting.md)** - Solve common Git problems
- **[Git Security](Git%20Security.md)** - Advanced security practices
- **[Git Submodules](Git%20Submodules.md)** - Manage complex project structures

---

*Last Updated: 2025-07-27*
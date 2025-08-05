# Git Remote Repositories

Remote repositories allow you to collaborate with others and backup your code. This guide covers working with GitHub, GitLab, and other remote Git services.

## Understanding Remotes

A remote is a version of your repository hosted somewhere else (like GitHub). You can have multiple remotes and push/pull changes between them.

### Common Remote Names
- **origin**: Default name for the main remote (usually where you cloned from)
- **upstream**: Often used for the original repository when working with forks
- **deploy**: Sometimes used for deployment repositories

## Remote Management

### Adding Remotes
```bash
# Add remote repository
git remote add origin https://github.com/username/repository.git

# Add additional remote
git remote add upstream https://github.com/original-owner/repository.git

# Add remote with SSH
git remote add origin git@github.com:username/repository.git
```

### Viewing Remotes
```bash
# List remotes
git remote

# List remotes with URLs
git remote -v

# Show detailed remote information
git remote show origin
```

### Modifying Remotes
```bash
# Change remote URL
git remote set-url origin https://github.com/username/new-repository.git

# Rename remote
git remote rename origin upstream

# Remove remote
git remote remove origin
```

## Pushing Changes

### Basic Push Commands
```bash
# Push current branch to origin
git push

# Push specific branch
git push origin main

# Push new branch and set upstream
git push -u origin feature-branch
git push --set-upstream origin feature-branch

# Push all branches
git push --all origin

# Push tags
git push --tags origin
```

### Force Pushing (Use Carefully)
```bash
# Force push (overwrites remote history)
git push --force origin main

# Safer force push (fails if others have pushed)
git push --force-with-lease origin main

# Force push specific branch
git push --force origin feature-branch
```

## Pulling Changes

### Basic Pull Commands
```bash
# Pull from default remote/branch
git pull

# Pull from specific remote/branch
git pull origin main

# Pull with rebase instead of merge
git pull --rebase origin main

# Pull all branches
git pull --all
```

### Fetch vs Pull
```bash
# Fetch downloads changes but doesn't merge
git fetch origin

# See what was fetched
git log HEAD..origin/main

# Merge fetched changes
git merge origin/main

# Pull = fetch + merge
git pull origin main
```

## Working with Branches

### Tracking Remote Branches
```bash
# Create local branch tracking remote
git checkout -b main origin/main

# Set existing branch to track remote
git branch --set-upstream-to=origin/main main

# Push and set upstream in one command
git push -u origin feature-branch
```

### Managing Remote Branches
```bash
# List all branches (local and remote)
git branch -a

# List only remote branches
git branch -r

# Delete remote branch
git push origin --delete feature-branch

# Prune deleted remote branches locally
git remote prune origin

# Auto-prune when fetching
git fetch --prune origin
```

## Collaboration Workflows

### Fork and Pull Request Workflow
```bash
# 1. Fork repository on GitHub

# 2. Clone your fork
git clone https://github.com/yourusername/repository.git
cd repository

# 3. Add upstream remote
git remote add upstream https://github.com/originalowner/repository.git

# 4. Create feature branch
git checkout -b feature/new-feature

# 5. Make changes and commit
git add .
git commit -m "Add new feature"

# 6. Push to your fork
git push origin feature/new-feature

# 7. Create pull request on GitHub

# 8. Keep your fork updated
git checkout main
git pull upstream main
git push origin main
```

### Direct Collaboration
```bash
# Daily workflow with shared repository
git pull origin main          # Get latest changes
git checkout -b feature/task  # Create feature branch
# ... make changes ...
git add .
git commit -m "Implement feature"
git push -u origin feature/task  # Push branch
# ... create pull request ...
# ... after merge ...
git checkout main
git pull origin main          # Get merged changes
git branch -d feature/task    # Clean up local branch
```

## Syncing Forks

### Keeping Fork Updated
```bash
# Add upstream remote (original repository)
git remote add upstream https://github.com/original-owner/repository.git

# Fetch upstream changes
git fetch upstream

# Merge upstream changes into your main
git checkout main
git merge upstream/main

# Push updated main to your fork
git push origin main
```

### Resolving Conflicts with Upstream
```bash
# When your main conflicts with upstream
git fetch upstream
git checkout main
git merge upstream/main
# ... resolve conflicts ...
git add .
git commit
git push origin main
```

## Advanced Remote Operations

### Multiple Remotes
```bash
# Add multiple remotes
git remote add origin https://github.com/you/repo.git
git remote add gitlab https://gitlab.com/you/repo.git
git remote add bitbucket https://bitbucket.org/you/repo.git

# Push to multiple remotes
git push origin main
git push gitlab main
git push bitbucket main

# Or create alias to push to all
git config alias.pushall '!git push origin && git push gitlab && git push bitbucket'
git pushall
```

### Working with Different URLs
```bash
# Use HTTPS for fetching, SSH for pushing
git remote set-url origin https://github.com/username/repo.git
git remote set-url --push origin git@github.com:username/repo.git

# Verify URLs
git remote -v
```

## Troubleshooting Remote Issues

### Authentication Problems
```bash
# Check current remote URL
git remote -v

# Switch to SSH (if you have SSH keys set up)
git remote set-url origin git@github.com:username/repository.git

# Switch to HTTPS (will prompt for credentials)
git remote set-url origin https://github.com/username/repository.git

# Clear stored credentials (Windows)
git config --global --unset credential.helper

# Clear stored credentials (macOS)
git credential-osxkeychain erase
```

### Push/Pull Issues
```bash
# Push rejected (non-fast-forward)
git pull --rebase origin main  # Get latest changes
git push origin main           # Try push again

# Or merge instead of rebase
git pull origin main
git push origin main

# Force push (only if you're sure)
git push --force-with-lease origin main
```

### Branch Tracking Issues
```bash
# Branch not tracking remote
git branch --set-upstream-to=origin/main main

# See tracking information
git branch -vv

# Reset branch to match remote exactly
git reset --hard origin/main
```

## Best Practices

### Before Pushing
```bash
# Always pull before pushing
git pull origin main

# Check what you're about to push
git log origin/main..HEAD --oneline

# Make sure tests pass
npm test  # or your test command

# Push when ready
git push origin main
```

### Security
- Use SSH keys instead of HTTPS when possible
- Never commit sensitive information (passwords, API keys)
- Use `.gitignore` to exclude sensitive files
- Consider using Git hooks for pre-commit checks

### Collaboration
- Write clear commit messages
- Keep feature branches focused and short-lived
- Use pull requests for code review
- Delete merged branches to keep repository clean
- Communicate with team about major changes

## GitHub-Specific Features

### GitHub CLI
```bash
# Install GitHub CLI
# macOS: brew install gh
# Windows: Download from github.com/cli/cli

# Login
gh auth login

# Create repository
gh repo create my-new-repo

# Create pull request
gh pr create --title "Add new feature" --body "Description"

# List pull requests
gh pr list

# Checkout pull request
gh pr checkout 123
```

### Common GitHub Workflows
```bash
# Clone with GitHub CLI
gh repo clone username/repository

# Fork repository
gh repo fork username/repository

# Create issue
gh issue create --title "Bug report" --body "Description"

# View repository in browser
gh repo view --web
```

## Next Steps

- **[Git Security](Git%20Security.md)** - Set up SSH keys and secure authentication
- **[Git Advanced Commands](Git%20Advanced%20Commands.md)** - Learn powerful Git features
- **[Git Best Practices](Git%20Best%20Practices.md)** - Develop good Git habits

---

*Last Updated: 2025-07-27*
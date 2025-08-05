# Git Branching and Merging

Working with branches allows you to develop features, fix bugs, and experiment without affecting the main codebase. This guide covers branch management, merging, and rebasing.

## Understanding Branches

Branches are parallel versions of your code. The default branch is usually called `main` (formerly `master`). Each branch represents an independent line of development.

### Why Use Branches?
- **Isolate features**: Work on new features without breaking main code
- **Collaborate safely**: Multiple developers can work simultaneously
- **Experiment freely**: Try ideas without risk
- **Organize work**: Separate different types of changes (features, bugs, experiments)

## Branch Management

### Creating Branches
```bash
# Create new branch (stays on current branch)
git branch feature-name

# Create and switch to new branch
git checkout -b feature-name
git switch -c feature-name  # Git 2.23+

# Create branch from specific commit
git checkout -b feature-name abc1234

# Create branch from another branch
git checkout -b feature-branch main
```

### Switching Between Branches
```bash
# Switch to existing branch
git checkout branch-name
git switch branch-name  # Git 2.23+ (preferred)

# Switch to previous branch
git checkout -
git switch -

# Switch and create if branch doesn't exist
git checkout -b feature-name
git switch -c feature-name
```

### Viewing Branches
```bash
# List local branches (* shows current)
git branch

# List all branches (local and remote)
git branch -a

# List branches with last commit info
git branch -v

# List merged branches
git branch --merged

# List unmerged branches
git branch --no-merged
```

### Deleting Branches
```bash
# Delete merged branch (safe)
git branch -d branch-name

# Force delete branch (even if unmerged)
git branch -D branch-name

# Delete remote branch
git push origin --delete branch-name
```

## Merging

Merging combines changes from one branch into another. There are different merge strategies depending on your needs.

### Basic Merging
```bash
# Switch to target branch (usually main)
git checkout main

# Merge feature branch into main
git merge feature-name

# Merge with commit message
git merge feature-name -m "Merge feature: user authentication"
```

### Merge Types

#### Fast-Forward Merge
When the target branch hasn't changed since you created your feature branch:
```bash
# This will fast-forward (no merge commit)
git merge feature-name
```

#### Three-Way Merge
When both branches have new commits:
```bash
# Creates a merge commit
git merge feature-name

# Force merge commit even for fast-forward
git merge --no-ff feature-name
```

#### Squash Merge
Combines all feature branch commits into one:
```bash
# Squash all commits into one
git merge --squash feature-name
git commit -m "Add complete user authentication feature"
```

### Handling Merge Conflicts

When Git can't automatically merge changes:
```bash
# Git will show conflict status
git status

# Edit conflicted files (look for conflict markers)
# <<<<<<< HEAD
# Your changes
# =======
# Their changes
# >>>>>>> branch-name

# After resolving conflicts, stage files
git add filename.txt

# Complete the merge
git commit

# Or abort the merge
git merge --abort
```

## Rebasing

Rebasing rewrites commit history to create a cleaner, linear history.

### Basic Rebase
```bash
# Rebase current branch onto main
git rebase main

# Rebase specific branch
git rebase main feature-branch
```

### Interactive Rebase
Clean up commits before merging:
```bash
# Rebase last 3 commits interactively
git rebase -i HEAD~3

# Rebase from specific commit
git rebase -i abc1234
```

Interactive rebase options:
- `pick`: Keep commit as-is
- `reword`: Change commit message
- `edit`: Stop to modify commit
- `squash`: Combine with previous commit
- `drop`: Remove commit completely

### Rebase Workflow
```bash
# Start rebase
git rebase main

# If conflicts occur, resolve them and continue
git add .
git rebase --continue

# Or abort rebase
git rebase --abort

# Or skip problematic commit
git rebase --skip
```

## Branch Workflows

### Feature Branch Workflow
```bash
# 1. Start from main
git checkout main
git pull origin main

# 2. Create feature branch
git checkout -b feature/user-login

# 3. Work and commit
git add .
git commit -m "Add login form"
git commit -m "Add validation"

# 4. Push feature branch
git push -u origin feature/user-login

# 5. Create pull request (on GitHub/GitLab)

# 6. After merge, clean up
git checkout main
git pull origin main
git branch -d feature/user-login
```

### Gitflow Workflow
```bash
# Main branches
main        # Production-ready code
develop     # Integration branch

# Supporting branches
feature/*   # New features
release/*   # Prepare releases
hotfix/*    # Emergency fixes

# Example feature workflow
git checkout develop
git checkout -b feature/new-feature
# ... work and commit ...
git checkout develop
git merge --no-ff feature/new-feature
git branch -d feature/new-feature
```

## Best Practices

### Branch Naming
```bash
# Good branch names
feature/user-authentication
bugfix/login-validation
hotfix/security-patch
release/v1.2.0
docs/api-documentation

# Avoid
feature
bugfix
new-feature
fix
```

### Before Merging
```bash
# Always pull latest changes first
git checkout main
git pull origin main

# Rebase feature branch to get latest changes
git checkout feature-branch
git rebase main

# Run tests before merging
npm test  # or your test command

# Merge when everything passes
git checkout main
git merge feature-branch
```

### Keep Branches Focused
- One feature per branch
- Small, focused commits
- Regular commits with good messages
- Keep branches short-lived
- Delete merged branches

## Common Scenarios

### Update Feature Branch with Latest Main
```bash
# Option 1: Rebase (cleaner history)
git checkout feature-branch
git rebase main

# Option 2: Merge (preserves branch structure)
git checkout feature-branch
git merge main
```

### Undo a Merge
```bash
# If merge hasn't been pushed
git reset --hard HEAD~1

# If merge has been pushed (creates new commit)
git revert -m 1 abc1234
```

### Work on Multiple Features
```bash
# Switch between feature branches
git stash                    # Save current work
git checkout other-feature   # Switch branches
# ... work on other feature ...
git checkout feature-1       # Switch back
git stash pop               # Restore work
```

## Troubleshooting

### Common Issues
```bash
# Branch not showing up
git fetch origin

# Can't switch branches (uncommitted changes)
git stash
git checkout other-branch
git stash pop

# Accidentally committed to wrong branch
git log --oneline -3        # Find commit hash
git checkout correct-branch
git cherry-pick abc1234     # Copy commit
git checkout wrong-branch
git reset --hard HEAD~1     # Remove from wrong branch
```

## Next Steps

- **[Git Remote Repositories](Git%20Remote%20Repositories.md)** - Work with GitHub/GitLab
- **[Git History and Logs](Git%20History%20and%20Logs.md)** - Track changes over time
- **[Git Best Practices](Git%20Best%20Practices.md)** - Develop good Git habits

---

*Last Updated: 2025-07-27*
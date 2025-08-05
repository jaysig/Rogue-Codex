# Git Worktrees Overview

Git worktrees allow you to check out multiple branches from the same repository into separate directories, creating isolated working environments while sharing the same Git history.

## What are Git Worktrees?

Git worktrees enable you to have multiple working copies of the same repository checked out to different directories simultaneously. Each worktree can be on a different branch, allowing you to work on multiple features, bug fixes, or experiments without switching branches or stashing changes.

## Key Benefits

### Isolation
- Each worktree has completely independent file state
- No conflicts between simultaneous work on different branches
- Changes in one worktree don't affect others

### Efficiency
- Shared Git history and object database (saves disk space)
- No need to clone repository multiple times
- Instant branch switching without affecting other work

### Parallel Development
- Work on multiple features simultaneously
- Compare different implementations side by side
- Test changes across different branches easily

## Basic Commands

### Creating Worktrees
```bash
# Create a new worktree with a new branch
git worktree add ../project-feature-a -b feature-a

# Create a worktree with an existing branch
git worktree add ../project-bugfix bugfix-123

# Create a worktree for a specific commit
git worktree add ../project-hotfix abc1234
```

### Managing Worktrees
```bash
# List all worktrees
git worktree list

# Remove a worktree when finished
git worktree remove ../project-feature-a

# Remove a worktree directory that was manually deleted
git worktree prune
```

### Working with Worktrees
```bash
# Navigate to a worktree
cd ../project-feature-a

# Normal git operations work in each worktree
git status
git add .
git commit -m "Feature implementation"
git push origin feature-a
```

## Best Practices

### Directory Organization
- Use descriptive directory names that clearly indicate the purpose
- Consider using a consistent naming pattern (e.g., `../repo-feature-name`, `../repo-bugfix-123`)
- Keep worktrees organized in a parent directory for easy management

### Workflow Tips
- Initialize development environment in each new worktree (install dependencies, set up config)
- Each worktree can have its own development server running on different ports
- Use relative paths (../) to keep worktrees organized near your main repository

### Cleanup
- Remove worktrees when finished to avoid cluttering your filesystem
- Use `git worktree prune` periodically to clean up references to manually deleted worktrees
- Consider automating cleanup as part of your development workflow

## Common Use Cases

### Feature Development
```bash
# Start work on a new feature
git worktree add ../myapp-user-auth -b feature/user-auth
cd ../myapp-user-auth
# Work on feature implementation
```

### Bug Fixes
```bash
# Quick hotfix on main branch
git worktree add ../myapp-hotfix main
cd ../myapp-hotfix
# Fix critical bug while continuing feature work elsewhere
```

### Code Review
```bash
# Check out PR branch for review
git worktree add ../myapp-review pr/123
cd ../myapp-review
# Review and test changes without affecting current work
```

### Experimentation
```bash
# Try different approach
git worktree add ../myapp-experiment -b experiment/new-approach
cd ../myapp-experiment
# Experiment freely without risk to main development
```

## Limitations and Considerations

### Branch Restrictions
- The same branch cannot be checked out in multiple worktrees simultaneously
- HEAD cannot be detached in multiple worktrees at the same time

### Shared Resources
- Git hooks, configuration, and refs are shared between all worktrees
- Changes to .git/config affect all worktrees
- Submodules work but require careful management across worktrees

### Storage
- While Git objects are shared, working directory files are duplicated
- Each worktree needs space for its complete working directory
- Large repositories with many worktrees can consume significant disk space

## Advanced Usage

### Sparse Checkout
Combine with sparse checkout to only include relevant files in each worktree:
```bash
git worktree add ../myapp-frontend -b frontend-only
cd ../myapp-frontend
git config core.sparseCheckout true
echo "frontend/*" > .git/info/sparse-checkout
git read-tree -m -u HEAD
```

### Automation Scripts
Create scripts to automate worktree creation with environment setup:
```bash
#!/bin/bash
# create-worktree.sh
BRANCH_NAME=$1
WORKTREE_DIR="../myapp-$BRANCH_NAME"

git worktree add "$WORKTREE_DIR" -b "$BRANCH_NAME"
cd "$WORKTREE_DIR"
npm install
cp ../main/.env.example .env
echo "Worktree $BRANCH_NAME ready at $WORKTREE_DIR"
```

## IDE and Tool Integration

Most modern IDEs and development tools work well with git worktrees:
- **VS Code**: Can open each worktree as a separate workspace
- **JetBrains IDEs**: Support multiple project windows for different worktrees
- **Terminal multiplexers**: tmux/screen sessions for each worktree
- **Development servers**: Each worktree can run on different ports

---

*Last Updated: 2025-08-05*
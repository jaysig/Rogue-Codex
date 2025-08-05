# Git Setup Guide

A comprehensive guide to setting up and using Git for version control, including essential commands and best practices.

## Overview

Git is a distributed version control system that helps you track changes in your code, collaborate with others, and manage different versions of your projects.

## Installation

### Prerequisites
- Windows 10+, macOS 10.15+, or Linux
- Internet connection for downloading

### Step 1: Install Git
```bash
# macOS (using Homebrew)
brew install git

# Ubuntu/Debian
sudo apt update
sudo apt install git

# Windows
# Download from https://git-scm.com/download/win
```

### Step 2: Initial Configuration
```bash
# Set your name and email
git config --global user.name "Your Name"
git config --global user.email "your-email@domain.com"

# Set default branch name
git config --global init.defaultBranch main

# Set default editor
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "vim"          # Vim
```

### Step 3: Verify Installation
```bash
git --version
git config --list
```

## Essential Commands

### Repository Management

#### Initialize Repository
```bash
# Create new repository
git init

# Clone existing repository
git clone https://github.com/username/repository.git
git clone https://github.com/username/repository.git my-folder-name

# Clone specific branch
git clone -b develop https://github.com/username/repository.git
```

#### Repository Status
```bash
# Check repository status
git status

# Check status in short format
git status --short
git status -s

# Check what branch you're on
git branch
git branch -v  # Shows last commit on each branch
```

### File Management

#### Adding Files
```bash
# Add specific file
git add filename.txt

# Add all files
git add .

# Add all files with specific extension
git add *.js

# Add files interactively
git add -i

# Add files with pattern matching
git add "*.{js,jsx,ts,tsx}"
```

#### Removing Files
```bash
# Remove file from staging area and working directory
git rm filename.txt

# Remove file from staging area only
git rm --cached filename.txt

# Remove directory
git rm -r directory/

# Remove files with pattern
git rm "*.log"
```

### Committing Changes

#### Basic Commits
```bash
# Commit with message
git commit -m "Add new feature"

# Commit all staged changes
git commit -am "Update existing files"

# Commit with detailed message
git commit

# Amend last commit
git commit --amend -m "Updated commit message"
```

#### Commit Best Practices
```bash
# Conventional commit format
git commit -m "feat: add user authentication"
git commit -m "fix: resolve login bug"
git commit -m "docs: update README"
git commit -m "style: format code"
git commit -m "refactor: simplify function"
git commit -m "test: add unit tests"
git commit -m "chore: update dependencies"
```

### Branching and Merging

#### Branch Management
```bash
# Create new branch
git branch feature-name

# Create and switch to new branch
git checkout -b feature-name
git switch -c feature-name  # Git 2.23+

# Switch between branches
git checkout branch-name
git switch branch-name  # Git 2.23+

# List all branches
git branch -a

# Delete branch
git branch -d branch-name
git branch -D branch-name  # Force delete
```

#### Merging
```bash
# Merge branch into current branch
git merge feature-name

# Merge with no fast-forward
git merge --no-ff feature-name

# Abort merge
git merge --abort

# Squash merge
git merge --squash feature-name
```

#### Rebasing
```bash
# Rebase current branch onto another
git rebase main

# Interactive rebase
git rebase -i HEAD~3

# Abort rebase
git rebase --abort

# Continue rebase after resolving conflicts
git rebase --continue
```

### History and Logs

#### Viewing History
```bash
# View commit history
git log

# View history in one line
git log --oneline

# View history with graph
git log --graph --oneline --all

# View history for specific file
git log -- filename.txt

# View history with changes
git log -p

# View history with statistics
git log --stat
```

#### Comparing Changes
```bash
# Compare working directory with staging area
git diff

# Compare staging area with last commit
git diff --staged
git diff --cached

# Compare with specific commit
git diff HEAD~1

# Compare between branches
git diff main..feature-branch

# Compare specific files
git diff file1.txt file2.txt
```

### Remote Repositories

#### Remote Management
```bash
# Add remote repository
git remote add origin https://github.com/username/repository.git

# List remotes
git remote -v

# Remove remote
git remote remove origin

# Rename remote
git remote rename origin upstream
```

#### Pushing and Pulling
```bash
# Push to remote
git push origin main

# Push new branch
git push -u origin feature-branch

# Pull from remote
git pull origin main

# Fetch from remote
git fetch origin

# Fetch all remotes
git fetch --all
```

## Advanced Commands

### Stashing
```bash
# Stash changes
git stash

# Stash with message
git stash push -m "Work in progress"

# List stashes
git stash list

# Apply stash
git stash apply
git stash pop  # Apply and remove

# Apply specific stash
git stash apply stash@{1}

# Drop stash
git stash drop stash@{0}

# Clear all stashes
git stash clear
```

### Cherry-picking
```bash
# Cherry-pick specific commit
git cherry-pick abc1234

# Cherry-pick range of commits
git cherry-pick abc1234..def5678

# Cherry-pick without auto-commit
git cherry-pick --no-commit abc1234
```

### Reset and Revert
```bash
# Soft reset (keep changes in staging)
git reset --soft HEAD~1

# Mixed reset (keep changes in working directory)
git reset --mixed HEAD~1
git reset HEAD~1  # Default

# Hard reset (discard all changes)
git reset --hard HEAD~1

# Reset to specific commit
git reset --hard abc1234

# Revert commit (create new commit)
git revert abc1234

# Revert without commit
git revert --no-commit abc1234
```

### Tags
```bash
# Create lightweight tag
git tag v1.0.0

# Create annotated tag
git tag -a v1.0.0 -m "Release version 1.0.0"

# List tags
git tag

# Push tags
git push origin --tags

# Delete tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0
```

## Best Practices

### Commit Messages
```bash
# Good commit messages
git commit -m "feat: add user authentication system"
git commit -m "fix: resolve login validation bug"
git commit -m "docs: update API documentation"
git commit -m "style: format code according to style guide"
git commit -m "refactor: simplify authentication logic"
git commit -m "test: add unit tests for user service"
git commit -m "chore: update dependencies to latest versions"

# Bad commit messages
git commit -m "fix"
git commit -m "updated stuff"
git commit -m "WIP"
```

### Branch Naming
```bash
# Good branch names
feature/user-authentication
bugfix/login-validation
hotfix/security-patch
release/v1.2.0
docs/api-documentation

# Bad branch names
feature
bugfix
new-feature
fix
```

### Workflow
```bash
# 1. Always pull before starting work
git pull origin main

# 2. Create feature branch
git checkout -b feature/new-feature

# 3. Make changes and commit frequently
git add .
git commit -m "feat: implement new feature"

# 4. Push branch to remote
git push -u origin feature/new-feature

# 5. Create pull request (on GitHub/GitLab)

# 6. After merge, clean up
git checkout main
git pull origin main
git branch -d feature/new-feature
```

## Troubleshooting

### Common Issues

#### Undo Last Commit
```bash
# Undo commit but keep changes
git reset --soft HEAD~1

# Undo commit and discard changes
git reset --hard HEAD~1

# Undo commit with new commit
git revert HEAD
```

#### Fix Merge Conflicts
```bash
# During merge conflict
# 1. Edit conflicted files
# 2. Add resolved files
git add filename.txt

# 3. Complete merge
git commit

# Or abort merge
git merge --abort
```

#### Recover Deleted Branch
```bash
# Find commit hash
git reflog

# Recreate branch
git checkout -b recovered-branch abc1234
```

#### Clean Working Directory
```bash
# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd

# Preview what will be removed
git clean -n
```

### Useful Aliases
```bash
# Add to ~/.gitconfig
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    ca = commit -a
    cm = commit -m
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
    lg = log --graph --oneline --all
    ll = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

## Security Best Practices

### SSH Keys
```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your-email@domain.com"

# Add SSH key to agent
ssh-add ~/.ssh/id_ed25519

# Copy public key
cat ~/.ssh/id_ed25519.pub
```

### Credential Management
```bash
# Store credentials
git config --global credential.helper store

# Cache credentials temporarily
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'
```

## Resources

### Documentation
- [Git Documentation](https://git-scm.com/doc)
- [Git Book](https://git-scm.com/book/en/v2)
- [GitHub Guides](https://guides.github.com/)

### Interactive Learning
- [GitHub Learning Lab](https://lab.github.com/)
- [Git Branching](https://learngitbranching.js.org/)
- [Oh My Git!](https://ohmygit.org/)

### Community
- [Stack Overflow Git](https://stackoverflow.com/questions/tagged/git)
- [GitHub Community](https://github.community/)
- [Reddit r/git](https://reddit.com/r/git)

---

*Last Updated: July 27, 2025* 
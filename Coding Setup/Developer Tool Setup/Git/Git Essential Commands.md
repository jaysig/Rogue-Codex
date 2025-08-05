# Git Essential Commands

Basic Git commands for daily development work including repository management, file operations, and committing changes.

## Repository Management

### Initialize Repository
```bash
# Create new repository in current directory
git init

# Create new repository in specific directory
git init my-project

# Clone existing repository
git clone https://github.com/username/repository.git

# Clone into specific folder name
git clone https://github.com/username/repository.git my-folder-name

# Clone specific branch
git clone -b develop https://github.com/username/repository.git
```

### Repository Status
```bash
# Check repository status (essential command)
git status

# Short status format
git status --short
git status -s

# Check current branch
git branch

# Show last commit on each branch
git branch -v
```

## File Management

### Adding Files
```bash
# Add specific file
git add filename.txt

# Add all files in current directory
git add .

# Add all files with specific extension
git add *.js

# Add multiple files with pattern
git add "*.{js,jsx,ts,tsx}"

# Add files interactively (lets you choose what to add)
git add -i

# Add only part of a file (patch mode)
git add -p filename.txt
```

### Removing Files
```bash
# Remove file from Git and file system
git rm filename.txt

# Remove file from Git but keep on file system
git rm --cached filename.txt

# Remove directory and all contents
git rm -r directory/

# Remove files matching pattern
git rm "*.log"

# Remove all files in directory but keep directory
git rm directory/*
```

### Moving Files
```bash
# Move/rename file
git mv old-filename.txt new-filename.txt

# Move file to directory
git mv filename.txt directory/

# Rename directory
git mv old-directory/ new-directory/
```

## Committing Changes

### Basic Commits
```bash
# Commit with message
git commit -m "Add new feature"

# Commit all tracked files (skip git add)
git commit -am "Update existing files"

# Open editor for detailed commit message
git commit

# Add more files to the last commit
git add forgotten-file.txt
git commit --amend --no-edit

# Change the last commit message
git commit --amend -m "Better commit message"
```

### Commit Message Best Practices
```bash
# Use conventional commit format
git commit -m "feat: add user authentication"
git commit -m "fix: resolve login bug"
git commit -m "docs: update README"
git commit -m "style: format code"
git commit -m "refactor: simplify function"
git commit -m "test: add unit tests"
git commit -m "chore: update dependencies"
```

## Checking What's Changed

### View Changes
```bash
# See what's changed but not staged
git diff

# See what's staged for commit
git diff --staged
git diff --cached

# See changes in specific file
git diff filename.txt

# See changes between commits
git diff HEAD~1
git diff abc1234..def5678
```

### Check File Status
```bash
# See which files are tracked/untracked
git status

# See what files have been modified
git diff --name-only

# See what files are staged
git diff --cached --name-only
```

## Quick Reference

### Most Used Commands
```bash
git status          # Check what's changed
git add .           # Stage all changes
git commit -m "msg" # Commit with message
git pull            # Get latest changes
git push            # Send your changes
git log --oneline   # See commit history
```

### Daily Workflow
```bash
# Start of day
git status          # See current state
git pull            # Get latest changes

# During work
git add .           # Stage your changes
git commit -m "descriptive message"

# End of day
git push            # Share your work
```

## Common Scenarios

### Undo Changes
```bash
# Undo changes to a file (not staged)
git checkout filename.txt
git restore filename.txt  # Git 2.23+

# Unstage a file
git reset filename.txt
git restore --staged filename.txt  # Git 2.23+

# Undo all local changes
git reset --hard HEAD
```

### Work with Specific Files
```bash
# See history of specific file
git log filename.txt

# See who changed what in a file
git blame filename.txt

# Restore file from specific commit
git checkout abc1234 -- filename.txt
```

## Next Steps

- **[Git Branching and Merging](Git%20Branching%20and%20Merging.md)** - Work with branches for features
- **[Git Remote Repositories](Git%20Remote%20Repositories.md)** - Connect to GitHub/GitLab
- **[Git History and Logs](Git%20History%20and%20Logs.md)** - Explore your project history

---

*Last Updated: 2025-07-27*
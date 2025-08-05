# Git Troubleshooting

Common Git problems and their solutions, from simple fixes to complex recovery scenarios.

## Undo Operations

### Undo Last Commit

#### Keep Changes (Soft Undo)
```bash
# Undo commit but keep files staged
git reset --soft HEAD~1

# Undo commit and unstage files (but keep changes)
git reset HEAD~1
git reset --mixed HEAD~1  # Same as above
```

#### Discard Changes (Hard Undo)
```bash
# ⚠️ WARNING: This loses all changes
git reset --hard HEAD~1

# Safer: stash changes first
git stash
git reset --hard HEAD~1
git stash pop  # If you want changes back
```

#### Undo with New Commit (Safe for Shared Repos)
```bash
# Create new commit that undoes the last commit
git revert HEAD

# Revert without auto-commit (to edit message)
git revert --no-commit HEAD
```

### Undo Multiple Commits
```bash
# Undo last 3 commits, keep changes
git reset HEAD~3

# Undo last 3 commits, lose changes
git reset --hard HEAD~3

# Revert multiple commits (safe for shared repos)
git revert HEAD~2..HEAD
```

### Fix Commit Message
```bash
# Change last commit message
git commit --amend -m "New commit message"

# Change last commit message interactively
git commit --amend

# Change older commit messages
git rebase -i HEAD~3  # Choose how many commits back
# Change 'pick' to 'reword' for commits to change
```

## File and Staging Issues

### Unstage Files
```bash
# Unstage specific file
git reset filename.txt
git restore --staged filename.txt  # Git 2.23+

# Unstage all files
git reset
git restore --staged .  # Git 2.23+
```

### Discard Local Changes
```bash
# Discard changes to specific file
git checkout filename.txt
git restore filename.txt  # Git 2.23+

# Discard all local changes
git checkout .
git restore .  # Git 2.23+

# Nuclear option: reset everything
git reset --hard HEAD
```

### Recover Deleted Files
```bash
# Recover deleted file (if not committed)
git checkout HEAD -- filename.txt

# Find when file was deleted
git log --follow --stat -- filename.txt

# Recover from specific commit
git checkout abc1234 -- filename.txt
```

## Branch Problems

### Switch Branches with Uncommitted Changes
```bash
# Option 1: Stash changes
git stash
git checkout other-branch
git stash pop

# Option 2: Commit temporary work
git add .
git commit -m "WIP: temporary commit"
git checkout other-branch
# Later: git reset HEAD~1 to undo WIP commit
```

### Fix Detached HEAD
```bash
# Create branch from current position
git checkout -b fix-detached-head

# Or go back to a branch
git checkout main
```

### Recover Deleted Branch
```bash
# Find the commit where branch was
git reflog
git reflog show --all  # Show all branches

# Create new branch from found commit
git checkout -b recovered-branch abc1234

# Or reset existing branch to that commit
git branch -f branch-name abc1234
```

### Delete Wrong Branch
```bash
# Find the branch in reflog
git reflog

# Recreate branch from reflog
git checkout -b accidentally-deleted-branch HEAD@{1}
```

## Merge and Rebase Issues

### Abort Ongoing Operations
```bash
# Abort merge
git merge --abort

# Abort rebase
git rebase --abort

# Abort cherry-pick
git cherry-pick --abort

# Abort revert
git revert --abort
```

### Resolve Merge Conflicts
```bash
# See conflicted files
git status

# Edit conflicted files (look for conflict markers)
# <<<<<<< HEAD
# Your changes
# =======
# Their changes
# >>>>>>> branch-name

# After resolving, stage files
git add filename.txt

# Complete merge
git commit

# Use merge tool for complex conflicts
git mergetool
```

### Fix Rebase Conflicts
```bash
# During rebase, resolve conflicts then:
git add .
git rebase --continue

# Skip problematic commit
git rebase --skip

# Abort and start over
git rebase --abort
```

### Undo Merge
```bash
# If merge not yet pushed
git reset --hard HEAD~1

# If merge already pushed (creates new commit)
git revert -m 1 abc1234  # abc1234 is merge commit hash
```

## Remote Repository Issues

### Push Rejected (Non-Fast-Forward)
```bash
# Option 1: Rebase your changes (cleaner history)
git pull --rebase origin main
git push origin main

# Option 2: Merge (preserves branch structure)
git pull origin main
git push origin main

# Option 3: Force push (⚠️ DANGEROUS - only if sure)
git push --force-with-lease origin main
```

### Wrong Remote URL
```bash
# Check current remote
git remote -v

# Change remote URL
git remote set-url origin https://github.com/username/new-repo.git

# Add missing remote
git remote add origin https://github.com/username/repo.git
```

### Accidentally Pushed to Wrong Branch
```bash
# Reset the wrong branch
git checkout wrong-branch
git reset --hard HEAD~1  # Remove the commit

# Push the reset
git push --force-with-lease origin wrong-branch

# Push to correct branch
git checkout correct-branch
git cherry-pick abc1234  # The commit you removed
git push origin correct-branch
```

### Can't Push Due to Large Files
```bash
# Remove large file from history
git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch path/to/large/file' \
  --prune-empty --tag-name-filter cat -- --all

# Or use BFG Repo Cleaner (easier)
java -jar bfg.jar --delete-files large-file.zip
git reflog expire --expire=now --all && git gc --prune=now --aggressive
```

## Authentication Issues

### HTTPS Authentication Problems
```bash
# Clear stored credentials (Windows)
git config --global --unset credential.helper

# Clear stored credentials (macOS)
git credential-osxkeychain erase

# Switch to SSH (if you have SSH keys)
git remote set-url origin git@github.com:username/repo.git

# Or update HTTPS URL with token
git remote set-url origin https://token@github.com/username/repo.git
```

### SSH Key Issues
```bash
# Test SSH connection
ssh -T git@github.com

# Add SSH key to agent
ssh-add ~/.ssh/id_rsa

# Check SSH agent
ssh-add -l

# Generate new SSH key if needed
ssh-keygen -t ed25519 -C "your-email@example.com"
```

## Performance Issues

### Repository Too Slow
```bash
# Clean up repository
git gc --aggressive

# Remove unnecessary files
git clean -fd

# Prune remote tracking branches
git remote prune origin

# Check repository size
git count-objects -vH
```

### Large Repository Problems
```bash
# Shallow clone (limited history)
git clone --depth 1 https://github.com/user/repo.git

# Partial clone (no blobs initially)
git clone --filter=blob:none https://github.com/user/repo.git

# Clean up large files from history
git filter-branch --tree-filter 'rm -rf large-directory' HEAD
```

## Data Recovery

### Recover Lost Commits
```bash
# Find lost commits
git reflog
git fsck --lost-found

# Recover specific commit
git checkout abc1234
git checkout -b recovered-work

# Merge recovered work
git checkout main
git merge recovered-work
```

### Recover from Hard Reset
```bash
# Find the commit before reset
git reflog

# Reset back to that commit
git reset --hard HEAD@{1}

# Or create branch from that point
git checkout -b recovery HEAD@{1}
```

### Corrupt Repository
```bash
# Clone fresh copy if you have remote
git clone https://github.com/user/repo.git repo-backup

# Try to repair
git fsck
git gc --aggressive

# If severely corrupted, restore from backup
```

## Working Directory Issues

### Clean Working Directory
```bash
# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd

# Preview what will be removed
git clean -n

# Remove ignored files too
git clean -fX

# Remove everything not tracked
git clean -fdx
```

### File Permission Issues
```bash
# Ignore file permission changes
git config core.filemode false

# Fix permission changes that are staged
git diff --summary | grep --color 'mode change 100755 => 100644' | cut -d' ' -f7- | xargs -d'\n' chmod +x
```

### Line Ending Issues
```bash
# Configure line endings (Windows)
git config --global core.autocrlf true

# Configure line endings (macOS/Linux)
git config --global core.autocrlf input

# Fix existing line ending issues
git add --renormalize .
git commit -m "Fix line endings"
```

## Advanced Recovery

### Repository History Corruption
```bash
# Create backup first
cp -r .git .git-backup

# Try to recover
git reflog expire --expire=now --all
git gc --prune=now --aggressive
git fsck --full
```

### Partial Data Loss
```bash
# Find all reachable objects
git fsck --unreachable

# Examine unreachable objects
git show abc1234

# Recover useful objects
git merge abc1234
```

## Prevention Strategies

### Regular Backups
```bash
# Push regularly to remote
git push origin --all
git push origin --tags

# Create backup branches before risky operations
git branch backup-$(date +%Y%m%d-%H%M%S)

# Use multiple remotes
git remote add backup https://gitlab.com/user/repo.git
git push backup main
```

### Safe Practices
```bash
# Always check what you're doing
git status
git diff --staged
git log --oneline -5

# Use --dry-run when available
git clean -n  # Preview clean
git merge --no-commit  # Test merge

# Test commands on copies
cp -r project project-test
cd project-test
# Try risky commands here first
```

## Getting Help

### Git Help Commands
```bash
# Get help for specific command
git help commit
git commit --help

# Quick help
git commit -h

# List all commands
git help -a
```

### Debug Information
```bash
# Show Git configuration
git config --list

# Show repository information
git remote -v
git branch -a
git status
git log --oneline -10

# Show detailed status
git status --ignored --untracked-files=all
```

## Emergency Procedures

### Complete Reset (Nuclear Option)
```bash
# ⚠️ EXTREME: Loses ALL local changes and commits
git fetch origin
git reset --hard origin/main
git clean -fdx
```

### Start Over
```bash
# If everything is broken, start fresh
cd ..
git clone https://github.com/user/repo.git repo-fresh
cd repo-fresh
# Copy your important uncommitted work manually
```

---

*Last Updated: 2025-07-27*
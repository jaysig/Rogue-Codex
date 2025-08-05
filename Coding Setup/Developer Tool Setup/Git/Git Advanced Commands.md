# Git Advanced Commands

Advanced Git features for handling complex scenarios including stashing, cherry-picking, reset operations, and tagging.

## Stashing

Stashing saves your current work temporarily so you can switch branches or pull changes without committing incomplete work.

### Basic Stashing
```bash
# Stash current changes
git stash

# Stash with descriptive message
git stash push -m "Work in progress on login feature"

# Stash including untracked files
git stash -u

# Stash including ignored files
git stash -a
```

### Managing Stashes
```bash
# List all stashes
git stash list

# Show stash contents
git stash show
git stash show -p  # Show full diff

# Show specific stash
git stash show stash@{1}
git stash show -p stash@{1}
```

### Applying Stashes
```bash
# Apply most recent stash (keeps stash)
git stash apply

# Apply and remove most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{1}
git stash pop stash@{1}

# Apply stash to different branch
git stash branch new-branch-name stash@{1}
```

### Cleaning Up Stashes
```bash
# Delete specific stash
git stash drop stash@{1}

# Delete most recent stash
git stash drop

# Clear all stashes
git stash clear
```

### Advanced Stash Operations
```bash
# Stash only staged changes
git stash --staged

# Stash specific files
git stash push -m "Partial work" -- file1.txt file2.txt

# Create stash without affecting working directory
git stash create "message"
```

## Cherry-Picking

Cherry-picking applies specific commits from one branch to another without merging the entire branch.

### Basic Cherry-Pick
```bash
# Cherry-pick specific commit
git cherry-pick abc1234

# Cherry-pick multiple commits
git cherry-pick abc1234 def5678

# Cherry-pick range of commits
git cherry-pick abc1234..def5678

# Cherry-pick from another branch
git cherry-pick feature-branch~2
```

### Cherry-Pick Options
```bash
# Cherry-pick without auto-commit (for editing)
git cherry-pick --no-commit abc1234

# Cherry-pick and edit commit message
git cherry-pick --edit abc1234

# Cherry-pick keeping original author info
git cherry-pick abc1234  # Default behavior

# Cherry-pick and sign off
git cherry-pick --signoff abc1234
```

### Handling Cherry-Pick Conflicts
```bash
# When conflicts occur during cherry-pick
# 1. Resolve conflicts in files
# 2. Stage resolved files
git add .

# 3. Continue cherry-pick
git cherry-pick --continue

# Or abort cherry-pick
git cherry-pick --abort

# Or skip this commit
git cherry-pick --skip
```

## Reset Operations

Reset changes the current branch to point to a different commit. **Use carefully** as it can lose work.

### Types of Reset

#### Soft Reset
Moves HEAD but keeps staging area and working directory:
```bash
# Undo last commit, keep changes staged
git reset --soft HEAD~1

# Reset to specific commit, keep changes staged
git reset --soft abc1234
```

#### Mixed Reset (Default)
Moves HEAD and resets staging area, keeps working directory:
```bash
# Undo last commit, unstage changes but keep in working directory
git reset HEAD~1
git reset --mixed HEAD~1  # Same as above

# Unstage specific file
git reset filename.txt
```

#### Hard Reset
Moves HEAD, resets staging area AND working directory:
```bash
# ⚠️ DANGER: Loses all uncommitted changes
git reset --hard HEAD~1

# Reset to specific commit, lose all changes
git reset --hard abc1234

# Reset to match remote exactly
git reset --hard origin/main
```

### Safe Reset Practices
```bash
# Check what will be lost
git diff HEAD~1

# Stash changes before hard reset
git stash
git reset --hard HEAD~1

# Create backup branch before dangerous operations
git branch backup-$(date +%Y%m%d-%H%M%S)
git reset --hard abc1234
```

## Revert Operations

Revert creates new commits that undo previous commits. Safer than reset for shared repositories.

### Basic Revert
```bash
# Revert specific commit (creates new commit)
git revert abc1234

# Revert multiple commits
git revert abc1234 def5678

# Revert range of commits
git revert abc1234..def5678
```

### Revert Options
```bash
# Revert without auto-commit (for editing)
git revert --no-commit abc1234

# Revert and edit commit message
git revert --edit abc1234

# Revert merge commit (specify parent)
git revert -m 1 merge-commit-hash
```

### Handling Revert Conflicts
```bash
# When conflicts occur during revert
# 1. Resolve conflicts
# 2. Stage resolved files
git add .

# 3. Continue revert
git revert --continue

# Or abort revert
git revert --abort
```

## Tags

Tags mark specific points in Git history, commonly used for releases.

### Creating Tags

#### Lightweight Tags
```bash
# Create lightweight tag
git tag v1.0.0

# Tag specific commit
git tag v1.0.0 abc1234

# Tag with current date
git tag "release-$(date +%Y%m%d)"
```

#### Annotated Tags (Recommended)
```bash
# Create annotated tag with message
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag specific commit with annotation
git tag -a v1.0.0 abc1234 -m "Release version 1.0.0"

# Create tag and sign with GPG
git tag -s v1.0.0 -m "Signed release v1.0.0"
```

### Managing Tags
```bash
# List all tags
git tag

# List tags matching pattern
git tag -l "v1.*"

# Show tag information
git show v1.0.0

# List tags with commit info
git tag -n
git tag -n5  # Show 5 lines of annotation
```

### Sharing Tags
```bash
# Push specific tag
git push origin v1.0.0

# Push all tags
git push origin --tags

# Push all tags (alternative)
git push --tags
```

### Deleting Tags
```bash
# Delete local tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0

# Delete remote tag (alternative syntax)
git push origin :refs/tags/v1.0.0
```

## Advanced Workflows

### Interactive Rebase for History Cleanup
```bash
# Clean up last 3 commits
git rebase -i HEAD~3

# Interactive rebase from specific commit
git rebase -i abc1234

# Rebase onto different branch
git rebase -i --onto main feature-base feature-branch
```

### Bisect for Bug Hunting
```bash
# Start bisect session
git bisect start

# Mark current commit as bad
git bisect bad

# Mark known good commit
git bisect good v1.0.0

# Git checks out middle commit
# Test and mark as good or bad
git bisect good  # or git bisect bad

# Continue until bug is found
# Git will tell you the problematic commit

# End bisect session
git bisect reset
```

### Reflog for Recovery
```bash
# Show all recent Git operations
git reflog

# Show reflog for specific branch
git reflog show main

# Recover "lost" commit
git checkout abc1234
git checkout -b recovered-work

# Reset to previous state using reflog
git reset --hard HEAD@{1}
```

## Worktrees

Work on multiple branches simultaneously using worktrees:

```bash
# Create new worktree
git worktree add ../feature-branch feature-branch

# Create worktree with new branch
git worktree add -b new-feature ../new-feature

# List worktrees
git worktree list

# Remove worktree
git worktree remove ../feature-branch

# Prune deleted worktrees
git worktree prune
```

## Hooks

Automate tasks with Git hooks:

```bash
# Hook locations
ls .git/hooks/

# Common hooks:
# pre-commit: Run before commit
# post-commit: Run after commit
# pre-push: Run before push
# post-receive: Run on server after push

# Example pre-commit hook
#!/bin/sh
npm test || exit 1
```

## Configuration and Aliases

### Useful Aliases
Add to `.gitconfig`:
```bash
[alias]
    # Stash shortcuts
    st = stash
    sp = stash pop
    sa = stash apply
    sl = stash list
    
    # Reset shortcuts
    unstage = reset HEAD --
    undo = reset --soft HEAD~1
    
    # Log shortcuts
    last = log -1 HEAD
    visual = !gitk
    
    # Cherry-pick shortcut
    cp = cherry-pick
    
    # Tag shortcuts
    tags = tag -n
    
    # Cleanup
    cleanup = "!git branch --merged | grep -v '\\*\\|main\\|master' | xargs -n 1 git branch -d"
```

### Advanced Configuration
```bash
# Auto-correct misspelled commands
git config --global help.autocorrect 1

# Always rebase when pulling
git config --global pull.rebase true

# Use more colors
git config --global color.ui auto

# Show branch in prompt (add to ~/.bashrc or ~/.zshrc)
export PS1='[\u@\h \W$(__git_ps1 " (%s)")]\$ '
```

## Troubleshooting Advanced Scenarios

### Recover from Hard Reset
```bash
# Find lost commit in reflog
git reflog

# Create new branch from lost commit
git checkout -b recovery abc1234

# Or reset current branch to lost commit
git reset --hard abc1234
```

### Fix Detached HEAD
```bash
# Create branch from current position
git checkout -b fix-detached-head

# Or go back to previous branch
git checkout -
```

### Resolve Complex Merge Conflicts
```bash
# Use merge tool
git mergetool

# Show both sides of conflict
git checkout --conflict=diff3 .

# Abort complex merge
git merge --abort
git reset --hard HEAD
```

## Next Steps

- **[Git Best Practices](Git%20Best%20Practices.md)** - Learn professional Git workflows
- **[Git Troubleshooting](Git%20Troubleshooting.md)** - Solve common Git problems
- **[Git Security](Git%20Security.md)** - Secure your Git workflow

---

*Last Updated: 2025-07-27*
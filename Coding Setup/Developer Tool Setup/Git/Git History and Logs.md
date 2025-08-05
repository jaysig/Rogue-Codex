# Git History and Logs

Understanding your project's history is crucial for debugging, code reviews, and tracking changes. This guide covers viewing commit history, comparing changes, and analyzing your codebase over time.

## Viewing Commit History

### Basic Log Commands
```bash
# View commit history
git log

# One line per commit (most useful)
git log --oneline

# Show graph of branches and merges
git log --graph --oneline --all

# Show detailed changes in each commit
git log -p

# Show commit statistics (files changed, lines added/removed)
git log --stat

# Show last N commits
git log -3
git log --oneline -10
```

### Formatted Log Output
```bash
# Custom format
git log --pretty=format:"%h - %an, %ar : %s"

# Show dates
git log --pretty=format:"%h %ad | %s%d [%an]" --date=short

# Graph with colors
git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

### Filtering History
```bash
# Commits by author
git log --author="John Doe"

# Commits after specific date
git log --since="2023-01-01"
git log --after="2 weeks ago"

# Commits before specific date
git log --until="2023-12-31"
git log --before="1 month ago"

# Commits with specific message
git log --grep="fix"

# Commits that changed specific file
git log -- filename.txt

# Commits in specific directory
git log -- src/components/
```

## Comparing Changes

### Basic Diff Commands
```bash
# Changes not yet staged
git diff

# Changes staged for commit
git diff --staged
git diff --cached

# Changes between commits
git diff HEAD~1
git diff abc1234..def5678

# Changes between branches
git diff main..feature-branch

# Changes in specific file
git diff filename.txt
git diff HEAD~1 filename.txt
```

### Advanced Diff Options
```bash
# Show word-level changes (not line-level)
git diff --word-diff

# Show only file names that changed
git diff --name-only

# Show file names and status (added, modified, deleted)
git diff --name-status

# Ignore whitespace changes
git diff --ignore-all-space

# Show changes with more context lines
git diff -U10  # 10 lines of context instead of default 3
```

### Comparing Specific Commits
```bash
# Compare two specific commits
git diff commit1 commit2

# Compare commit with its parent
git diff commit^!

# Compare commit with working directory
git diff commit

# Compare with specific number of commits back
git diff HEAD~3
```

## File History and Blame

### File-Specific History
```bash
# History of specific file
git log filename.txt

# History with changes shown
git log -p filename.txt

# Follow file through renames
git log --follow filename.txt

# See who changed what line
git blame filename.txt

# Blame with commit info
git blame -c filename.txt

# Blame specific lines
git blame -L 10,20 filename.txt
```

### Finding When Changes Were Made
```bash
# Find when specific text was added/removed
git log -S "function name" filename.txt

# Find when regex pattern was added/removed
git log -G "regex pattern" filename.txt

# Find commits that added/removed lines
git log --pickaxe-regex -S "pattern"
```

## Searching Through History

### Finding Commits
```bash
# Search commit messages
git log --grep="bug fix"

# Search commit messages (case insensitive)
git log --grep="BUG" -i

# Search by multiple criteria
git log --grep="feature" --author="john" --since="1 week ago"

# Search code content
git log -S "function_name"

# Search with regex
git log --grep="^fix:" --perl-regexp
```

### Finding Lost Commits
```bash
# Show all commits including "lost" ones
git reflog

# Find commits not reachable from any branch
git fsck --lost-found

# Search in reflog
git reflog --grep="message"
```

## Analyzing Changes

### Statistics and Summaries
```bash
# Show number of commits by author
git shortlog -sn

# Show commit activity by date
git log --pretty=format:"%ad" --date=short | sort | uniq -c

# Show files changed most often
git log --name-only --pretty=format: | sort | uniq -c | sort -rg

# Show lines added/removed by author
git log --author="John" --pretty=tformat: --numstat | awk '{add+=$1; del+=$2} END {print "Added: " add " Deleted: " del}'
```

### Branch Comparisons
```bash
# Commits in feature branch not in main
git log main..feature-branch

# Commits in main not in feature branch
git log feature-branch..main

# Commits in either branch but not both
git log main...feature-branch

# Show merge base
git merge-base main feature-branch
```

## Useful Log Aliases

Add these to your `.gitconfig` file:

```bash
[alias]
    # Short log
    lg = log --graph --oneline --all
    
    # Detailed log with graph
    ll = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    
    # Show files changed
    lf = log --name-status --oneline
    
    # Show log with patches
    lp = log -p
    
    # Show recent commits
    recent = log --oneline -10
    
    # Show commits by author
    mine = log --author="$(git config user.name)" --oneline
```

## Advanced History Analysis

### Finding Regressions
```bash
# Find when bug was introduced (binary search)
git bisect start
git bisect bad HEAD
git bisect good v1.0.0
# Git will check out commits for you to test
git bisect good  # or git bisect bad
# Continue until Git finds the problematic commit
git bisect reset
```

### Tracking File Moves
```bash
# See history across file renames
git log --follow --stat -- filename.txt

# Find when file was renamed
git log --summary | grep rename

# See file move history
git log --name-status --follow filename.txt
```

### Performance Analysis
```bash
# Show commits that changed the most lines
git log --stat --oneline | head -20

# Find largest commits
git log --pretty=format:"%h %s" --stat | grep -E "files? changed" | sort -k4 -gr | head -10

# Show commit frequency over time
git log --pretty=format:"%ad" --date=format:"%Y-%m" | sort | uniq -c
```

## Common Use Cases

### Code Review Preparation
```bash
# See what changed since last tag
git log --oneline v1.0.0..HEAD

# See changes in feature branch
git log --oneline main..feature-branch

# Detailed changes for review
git log -p --reverse main..feature-branch
```

### Debugging
```bash
# When did this file last change?
git log -1 --stat filename.txt

# Who wrote this function?
git blame -L 50,60 filename.txt

# What changed in the last week?
git log --since="1 week ago" --oneline
```

### Release Notes
```bash
# Changes since last release
git log --oneline v1.0.0..HEAD

# Group by type (if using conventional commits)
git log --oneline v1.0.0..HEAD | grep "^feat:"
git log --oneline v1.0.0..HEAD | grep "^fix:"
```

## Troubleshooting

### Common Issues
```bash
# Log showing too much information
git log --oneline  # Simpler format

# Can't find specific commit
git reflog  # Shows all commits including "lost" ones

# Need to see changes in merge commit
git log --first-parent  # Follow main branch only
git show --first-parent abc1234  # Show merge commit changes

# History looks weird after rebase
git log --graph --all  # See full branch structure
```

### Performance with Large Repos
```bash
# Limit log output for better performance
git log --oneline -50

# Show only merge commits
git log --merges --oneline

# Skip merge commits
git log --no-merges --oneline

# Limit to specific path for performance
git log --oneline -- specific/directory/
```

## Next Steps

- **[Git Remote Repositories](Git%20Remote%20Repositories.md)** - Work with remote repositories
- **[Git Advanced Commands](Git%20Advanced%20Commands.md)** - Learn powerful Git features
- **[Git Troubleshooting](Git%20Troubleshooting.md)** - Solve common problems

---

*Last Updated: 2025-07-27*
# Claude Code with Git Worktrees

Running multiple Claude Code sessions simultaneously using Git worktrees for complete isolation and parallel development workflows.

## Overview

Git worktrees enable running multiple Claude Code instances in completely isolated environments while sharing the same Git history. This approach is ideal for working on multiple features, bug fixes, or experiments simultaneously without conflicts.

## Setup Process

### Creating Worktrees for Claude Code
```bash
# Create a new worktree with a new feature branch
git worktree add ../project-feature-auth -b feature/user-authentication

# Create a worktree for bug fix work
git worktree add ../project-bugfix-api -b bugfix/api-timeout

# Create a worktree for experimental work
git worktree add ../project-experiment -b experiment/new-architecture
```

### Launching Claude Code in Each Worktree
```bash
# Terminal 1: Feature development
cd ../project-feature-auth
claude

# Terminal 2: Bug fix work
cd ../project-bugfix-api  
claude

# Terminal 3: Experimental development
cd ../project-experiment
claude
```

## Key Benefits for Claude Code

### Complete Isolation
- Each Claude Code instance works with independent file states
- No interference between simultaneous development tasks
- Changes in one worktree don't affect other Claude Code sessions

### Parallel Development
- Work on multiple features simultaneously with different Claude Code instances  
- Compare different implementations side by side
- Test approaches across different branches easily

### Context Preservation
- Each Claude Code session maintains context for its specific task
- No need to switch contexts or lose conversation history
- Dedicated development environment for each project area

### Shared Git Benefits
- All worktrees share the same Git history and remotes
- Efficient disk usage (Git objects shared between worktrees)
- Easy branch management and merging between worktrees

## Claude Code Workflow Patterns

### Feature Development Pattern
```bash
# 1. Create feature worktree
git worktree add ../myapp-user-dashboard -b feature/user-dashboard

# 2. Launch Claude Code for feature work
cd ../myapp-user-dashboard
claude

# 3. In Claude Code session:
# - Design component architecture
# - Implement user dashboard components
# - Write tests for new functionality
# - Create documentation

# 4. When complete, merge and cleanup
git checkout main
git merge feature/user-dashboard
git worktree remove ../myapp-user-dashboard
```

### Bug Fix Pattern
```bash
# 1. Create hotfix worktree from main
git worktree add ../myapp-critical-fix main

# 2. Launch dedicated Claude Code for urgent fix
cd ../myapp-critical-fix
claude

# 3. In Claude Code session:
# - Investigate and diagnose issue
# - Implement minimal fix
# - Test fix thoroughly
# - Prepare for immediate deployment

# 4. Deploy fix while continuing other work elsewhere
```

### Code Review Pattern
```bash
# 1. Create review worktree for PR
git worktree add ../myapp-review-pr-123 origin/feature/new-api

# 2. Launch Claude Code for review
cd ../myapp-review-pr-123
claude

# 3. In Claude Code session:
# - Analyze code changes and architecture
# - Run tests and check functionality
# - Provide detailed feedback and suggestions
# - Test integration with existing codebase
```

## Best Practices

### Worktree Organization
- Use descriptive names: `../myapp-feature-auth`, `../myapp-bugfix-login`
- Keep related worktrees in the same parent directory
- Include project prefix for easy identification in terminal lists

### Environment Setup
```bash
# Automate development environment setup for each worktree
create_claude_worktree() {
    local branch_name=$1
    local worktree_dir="../myapp-$branch_name"
    
    git worktree add "$worktree_dir" -b "$branch_name"
    cd "$worktree_dir"
    
    # Setup development environment
    npm install
    cp ../main/.env.example .env
    
    echo "Claude Code worktree ready: $worktree_dir"
    echo "Run 'claude' to start development session"
}
```

### Resource Management
- Monitor system resources when running multiple Claude Code instances
- Consider memory usage with multiple development servers
- Use different ports for development servers in each worktree

### Task Coordination
- Use clear branch naming to identify worktree purpose
- Maintain separate TODO lists or task tracking for each Claude Code session
- Regular syncing with main branch to avoid conflicts

## Advanced Patterns

### Role-Based Worktrees
```bash
# Implementation worktree
git worktree add ../myapp-implementation -b feature/payment-system
cd ../myapp-implementation && claude

# Testing worktree  
git worktree add ../myapp-testing main
cd ../myapp-testing && claude

# Documentation worktree
git worktree add ../myapp-docs -b docs/api-update
cd ../myapp-docs && claude
```

### Comparative Development
```bash
# Approach A
git worktree add ../myapp-approach-a -b experiment/redux-implementation
cd ../myapp-approach-a && claude

# Approach B
git worktree add ../myapp-approach-b -b experiment/context-implementation  
cd ../myapp-approach-b && claude

# Compare implementations in real-time with different Claude Code sessions
```

## Managing Multiple Sessions

### Terminal Organization
- Use terminal multiplexer (tmux/screen) with named sessions
- Dedicated terminal window/tab for each Claude Code worktree
- Clear naming conventions for easy session identification

### IDE Integration
- Open each worktree as separate workspace in VS Code
- Use JetBrains IDEs with multiple project windows
- Configure different IDE themes/settings per worktree if helpful

### Development Servers
```bash
# Run different ports for each worktree
# Worktree 1: Main feature development
cd ../myapp-feature && npm run dev    # Port 3000

# Worktree 2: Bug fix testing  
cd ../myapp-bugfix && npm run dev -- --port 3001

# Worktree 3: Experimental features
cd ../myapp-experiment && npm run dev -- --port 3002
```

## Cleanup and Maintenance

### Regular Cleanup
```bash
# List all worktrees
git worktree list

# Remove completed worktrees
git worktree remove ../myapp-completed-feature

# Clean up references to manually deleted worktrees
git worktree prune
```

### Automated Cleanup Script
```bash
#!/bin/bash
# cleanup-worktrees.sh
echo "Active worktrees:"
git worktree list

echo "Pruning deleted worktrees..."
git worktree prune

echo "Cleanup complete"
```

## Performance Considerations

### System Resources
- Each Claude Code instance consumes memory and CPU
- Monitor system performance with multiple concurrent sessions
- Consider closing unused Claude Code sessions to free resources

### Token Usage
- Multiple Claude Code sessions increase overall token consumption
- Each session maintains separate conversation context
- Budget accordingly for parallel development workflows

### Git Operations
- Git operations are shared across all worktrees (same .git directory)
- Push/pull operations affect all worktrees
- Coordinate Git operations to avoid conflicts

---

*Last Updated: 2025-08-05*
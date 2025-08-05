# Agent Sync Notes

This directory contains copies of fitness coaching agents from the main Rogue Codex repository to enable standalone Fitness Guide functionality.

## Source Location
**Main Repository**: `/Users/proyogi/Documents/HODL/Rogue Codex/.claude/agents/fitness-training/`

## Sync Requirements

### ⚠️ IMPORTANT: Keep Agents Synchronized
These agents are copies, not symlinks. Changes made to agents in either location should be synchronized manually.

**When to sync:**
- After updating any agent in main Rogue Codex repository
- Before deploying Fitness Guide as standalone repository  
- When adding new fitness coaching agents
- After bug fixes or feature improvements to existing agents

### Sync Commands
```bash
# Sync FROM Rogue Codex TO Fitness Guide
cp -r "/path/to/Rogue Codex/.claude/agents/fitness-training" "/path/to/Fitness Guide/.claude/agents/"

# Sync FROM Fitness Guide TO Rogue Codex (if agents modified here)
cp -r "/path/to/Fitness Guide/.claude/agents/fitness-training" "/path/to/Rogue Codex/.claude/agents/"
```

## Agent Inventory

### Core Gym Coordination
- **gym-owner.md** - Master coordinator for multiple fitness agents

### Strength & Power Training
- **powerlifting-coach.md** - Squat, bench, deadlift specialization
- **personal-trainer.md** - General fitness and beginner guidance

### Endurance Training  
- **endurance-coach.md** - Long-distance training and cardiovascular fitness
- **running-coach.md** - Running technique and race preparation
- **cycling-coach.md** - Cycling performance and bike handling
- **swimming-coach.md** - Swimming technique and triathlon preparation

### Specialized Training
- **crossfit-coach.md** - Functional fitness and CrossFit methodology
- **outdoor-hiit-coach.md** - High-intensity interval training and outdoor workouts
- **special-forces-coach.md** - Military selection prep and tactical fitness

### Recovery & Mobility
- **mobility/** directory - Flexibility and injury prevention agents

### Nutrition
- **nutrition/** directory - Specialized nutrition coaching agents

## Version Tracking

### Last Sync: 2025-08-05
**Source**: Rogue Codex fitness-training agents
**Destination**: Fitness Guide .claude/agents/
**Action**: Initial copy of all fitness coaching agents

### Change Log
- **2025-08-05**: Initial setup - copied all fitness-training agents to enable standalone Fitness Guide functionality

## Fitness Guide Specific Modifications

### Agent Adaptation Notes
When the Fitness Guide becomes standalone, these agents may need modifications:
- **File path references**: Update any hardcoded paths to Fitness Guide structure
- **Data source references**: Ensure agents reference Fitness Guide User Data files
- **Cross-references**: Update links to other fitness guide components

### Integration Points
These agents integrate with the Fitness Guide system through:
- **Routing from CLAUDE.md**: Main system routes complex requests to appropriate agents
- **User Data access**: Agents read/write to Fitness Guide User Data files
- **Program Library**: Agents reference programs in References/Program_Library/
- **Template compliance**: All agents use Fitness Guide table and response standards

## Testing Checklist

When syncing agents, verify:
- [ ] All agent files copied successfully
- [ ] Agent routing works from main Fitness Guide system
- [ ] Agents can access User Data files correctly  
- [ ] Generated programs save to correct locations
- [ ] Response formats match Fitness Guide standards
- [ ] Cross-agent coordination (gym-owner → specialists) functions

## Future Considerations

### Standalone Repository Preparation
When Fitness Guide becomes its own repository:
1. **Agent independence**: Ensure agents don't reference main Rogue Codex files
2. **Documentation updates**: Update agent documentation for standalone context
3. **Testing suite**: Verify all agents function in isolated environment
4. **Path updates**: Fix any absolute path references

### Sync Automation
Consider future automation options:
- **Git submodules**: Link to main agent repository
- **Sync scripts**: Automated copying with conflict detection
- **Version control**: Track changes between repository versions

## Contact & Maintenance

**Primary maintainer**: Keep these agents synchronized with main Rogue Codex repository
**Update frequency**: Check for changes monthly or after major agent updates
**Conflict resolution**: When agents diverge, prioritize fitness-specific enhancements while maintaining core functionality

This sync system ensures the Fitness Guide can operate standalone while maintaining compatibility with the broader Rogue Codex agent ecosystem.
# Fitness Guide .claude Folder Overview

This document outlines the complete structure and contents of the Fitness Guide's `.claude/` directory for Claude Code integration.

## Current Structure

```
Fitness Guide/.claude/
├── CLAUDE_FOLDER_OVERVIEW.md (this file)
├── agents/
│   ├── AGENT_SYNC_NOTES.md
│   └── fitness-training/
│       ├── gym-owner.md
│       ├── workouts/
│       │   ├── crossfit-coach.md
│       │   ├── cycling-coach.md
│       │   ├── endurance-coach.md
│       │   ├── outdoor-hiit-coach.md
│       │   ├── personal-trainer.md
│       │   ├── powerlifting-coach.md
│       │   ├── running-coach.md
│       │   ├── special-forces-coach.md
│       │   └── swimming-coach.md
│       ├── mobility/
│       │   └── [flexibility coaching agents]
│       └── nutrition/
│           └── [nutrition coaching agents]
│
└── commands/
    ├── fa.md (Fitness Adventure command)
    ├── verify-prs.md (PR verification system)
    └── [other fitness commands]
```

## File Descriptions

### Core Configuration
- **CLAUDE_FOLDER_OVERVIEW.md**: This overview document
- **settings.local.json**: Local Claude Code settings (if needed for standalone operation)

### Agent System
- **agents/AGENT_SYNC_NOTES.md**: Synchronization tracking with main Rogue Codex agents
- **agents/fitness-training/**: Complete copy of fitness coaching agents for standalone operation

### Command System
- **commands/fa.md**: Fitness Adventure command mode activation
- **commands/verify-prs.md**: PR verification and data integrity checking
- **commands/[others]**: Additional fitness-specific commands

## Required Additional Files

### 1. Local Settings Configuration
**File**: `.claude/settings.local.json`
**Purpose**: Fitness Guide specific Claude Code settings

```json
{
  "fitness_guide": {
    "data_mode": "smart_two_mode",
    "auto_pr_detection": true,
    "cross_file_updates": true,
    "response_format": "data_first_when_appropriate",
    "command_mode_available": true
  },
  "file_paths": {
    "user_data": "User Data/",
    "pr_files": "User Data/PRs/",
    "logs": "User Data/Logs/",
    "references": "References/",
    "programs": "Current_Programs/"
  },
  "agent_routing": {
    "nutrition_requests": "fitness-training/nutrition/nutritionist",
    "program_design": "fitness-training/gym-owner",
    "strength_focus": "fitness-training/workouts/powerlifting-coach",
    "endurance_focus": "fitness-training/workouts/endurance-coach"
  }
}
```

### 2. Fitness Adventure Command
**File**: `.claude/commands/fa.md`
**Purpose**: Quick activation of Fitness Adventure command mode

```markdown
# Fitness Adventure Command (fa)

Quick activation command for Fitness Adventure mode.

## Usage
```bash
claude fa
```

Equivalent to: "Run Fitness Adventure"

## What it does
- Activates command mode interface
- Switches to data-first response format
- Enables direct fitness commands (LOG, SHOW, PLAN, etc.)
- Provides ASCII-style interaction

## See Also
- Fitness Adventure.md - Full command mode documentation
- CLAUDE.md - Two-mode system explanation
```

### 3. Quick Setup Command
**File**: `.claude/commands/setup-fitness.md`
**Purpose**: Initialize new user's fitness tracking system

```markdown
# Setup Fitness Command

Initializes the Fitness Guide system for new users.

## Usage
```bash
claude setup-fitness
```

## What it does
1. Creates User Data directory structure
2. Initializes Profile.md with basic questions
3. Sets up initial PR files for major lifts
4. Creates first workout log template
5. Explains how to use the system

## Interactive Setup
Guides users through:
- Basic stats (age, weight, experience level)
- Goals (strength, endurance, body composition)
- Equipment availability (home, gym, travel)
- Training preferences (frequency, duration)
- Initial baseline measurements

## Output
Creates complete file structure ready for immediate use.
```

### 4. System Health Check
**File**: `.claude/commands/health-check.md`
**Purpose**: Verify Fitness Guide system integrity

```markdown
# Health Check Command

Verifies Fitness Guide system integrity and data consistency.

## Usage
```bash
claude health-check [--fix]
```

## Checks Performed
1. **File Structure**: Ensures all required directories exist
2. **PR Consistency**: Verifies PR data matches workout logs
3. **Date Formats**: Confirms consistent YYYY-MM-DD usage
4. **Cross-References**: Validates file linkages
5. **Table Formatting**: Checks markdown table syntax
6. **Missing Files**: Identifies gaps in data structure

## Auto-Fix Option
`--fix` flag automatically resolves common issues:
- Creates missing directories
- Standardizes exercise names
- Fixes date format inconsistencies
- Repairs broken table formatting
```

### 5. Export/Backup Command
**File**: `.claude/commands/backup-fitness.md`
**Purpose**: Create portable backups of fitness data

```markdown
# Backup Fitness Command

Creates comprehensive backups of Fitness Guide data.

## Usage
```bash
claude backup-fitness [--format json|markdown|csv]
```

## Export Formats
- **markdown**: Preserves original file structure
- **json**: Machine-readable format for analysis
- **csv**: Spreadsheet-compatible data export

## Backup Contents
- All workout logs with PRs and metrics
- Complete PR history for all exercises  
- Body composition tracking data
- Program history and current plans
- Goal progress and achievement dates
```

## Integration Requirements

### MCP Server Compatibility
If using MCP servers, ensure compatibility with:
- **Project Memory**: For storing user preferences and patterns
- **Time Server**: For date/time calculations and scheduling
- **File System**: For accessing and modifying User Data files

### Claude Code Settings
Recommended settings for optimal Fitness Guide operation:
- **Memory persistence**: Maintain context across sessions
- **File watch**: Monitor User Data changes for auto-updates
- **Agent routing**: Efficient delegation to specialized coaches

## Standalone Repository Preparation

### Files to Update for Standalone Operation
1. **Remove dependencies**: Ensure no references to parent Rogue Codex files
2. **Update paths**: Make all file paths relative to Fitness Guide root
3. **Agent independence**: Verify agents work without external dependencies
4. **Documentation**: Update all references for standalone context

### Additional Files for Standalone
- **LICENSE**: Appropriate license for standalone distribution
- **.gitignore**: Exclude user data and local settings
- **CONTRIBUTING.md**: Guidelines for community contributions
- **CHANGELOG.md**: Version history and updates

## Testing Checklist

Before deploying as standalone repository:
- [ ] All commands execute correctly
- [ ] Agent routing functions properly
- [ ] File operations (create, read, update) work
- [ ] PR detection and verification runs
- [ ] Data integrity checks pass
- [ ] Export/backup functions work
- [ ] Two-mode system responds appropriately
- [ ] Cross-file updates maintain consistency

## Maintenance Notes

### Regular Tasks
- **Monthly**: Sync agents with main Rogue Codex repository
- **After updates**: Test all commands and agent routing
- **Before releases**: Run comprehensive health checks
- **Data validation**: Periodic PR verification runs

### Performance Optimization
- **File indexing**: Consider indexing for large workout log collections
- **Caching**: Cache frequently accessed PR data
- **Batch operations**: Group file updates for efficiency

This overview ensures the Fitness Guide `.claude/` folder contains everything needed for standalone operation while maintaining compatibility with the broader Rogue Codex ecosystem.
# Verify PRs Command

This command systematically checks recent workout logs to ensure all PRs have been properly detected and recorded.

## Command Usage

```bash
claude verify-prs [options]
```

**Options:**
- `--days N` - Check last N days of workouts (default: 30)
- `--all` - Check all workout logs (ignores PR-checked flags)
- `--force` - Re-check files even if marked as PR-verified
- `--exercise NAME` - Check specific exercise only

## How It Works

### 1. File Tracking System
Each workout log file includes a PR verification status:

```markdown
<!-- PR-STATUS: VERIFIED-2025-08-05 -->
# Workout Log: 2025-08-05
[workout content]
---
*PR Status: Verified on 2025-08-05*
```

### 2. Verification Process
1. **Scan workout logs** for files without `PR-STATUS: VERIFIED` or with old verification dates
2. **Parse each exercise** entry for weight/rep combinations
3. **Compare against current PR files** for each exercise
4. **Identify missed PRs** that should have been detected
5. **Update both workout log and PR files** if PRs found
6. **Mark file as verified** with current date

### 3. PR Detection Algorithm
For each exercise performance (Weight × Reps):

```python
def check_for_pr(exercise_name, weight, reps, date):
    # Load current PR file for exercise
    pr_file = load_pr_file(exercise_name)
    
    # Find best performance for similar rep range (±2 reps)
    rep_range = range(reps - 2, reps + 3)
    best_in_range = get_best_for_rep_range(pr_file, rep_range)
    
    # Check if this performance is a PR
    if is_new_pr(weight, reps, best_in_range):
        # Update PR file
        update_pr_file(exercise_name, weight, reps, date)
        
        # Update workout log with PR notation
        update_workout_log(date, exercise_name, "**PR!**")
        
        return True
    return False

def is_new_pr(weight, reps, current_best):
    if not current_best:
        return True  # First recorded performance
    
    current_weight, current_reps = current_best
    
    # New PR if:
    # 1. Higher weight with same or more reps
    # 2. Same weight with more reps
    return (weight > current_weight and reps >= current_reps) or \
           (weight == current_weight and reps > current_reps)
```

## Command Implementation

### Basic Verification
```bash
claude verify-prs
```

**Output Example:**
```markdown
🔍 **PR Verification Report** - 2025-08-05

**Files Checked**: 12 workout logs (last 30 days)
**PRs Found**: 3 missed PRs detected

| Date | Exercise | Performance | Status | Action |
|------|----------|-------------|--------|--------|
| 2025-07-28 | Bench Press | 225×8 | Missed PR | Updated files |
| 2025-08-01 | Squat | 315×5 | Missed PR | Updated files |
| 2025-08-03 | Deadlift | 405×3 | Missed PR | Updated files |

**Files Updated**:
- ✅ 2025-07-28.md - Added PR notation
- ✅ Bench_Press.md - New 8RM record
- ✅ 2025-08-01.md - Added PR notation  
- ✅ Squat.md - New 5RM record
- ✅ 2025-08-03.md - Added PR notation
- ✅ Deadlift.md - New 3RM record

**All files now marked as PR-verified**
```

### Specific Exercise Check
```bash
claude verify-prs --exercise "Bench Press" --days 60
```

**Output Example:**
```markdown
🔍 **Bench Press PR Verification** - Last 60 Days

**Files Checked**: 18 files containing Bench Press
**Current PRs**: All properly detected ✅

| Date | Performance | PR Status | Notes |
|------|-------------|-----------|-------|
| 2025-08-05 | 225×8 | Detected ✅ | Current 8RM |
| 2025-07-28 | 220×8 | Detected ✅ | Previous 8RM |
| 2025-07-15 | 225×5 | Detected ✅ | Current 5RM |

**No missed PRs found for Bench Press**
```

## File Status Tracking

### Workout Log PR Status
Each workout file includes tracking metadata:

```markdown
<!-- PR-STATUS: VERIFIED-2025-08-05 -->
<!-- EXERCISES-CHECKED: Squat, Bench Press, Deadlift -->

# Workout Log: 2025-08-05

[workout content]

---
*PR Status: Verified on 2025-08-05*
*Exercises checked: Squat, Bench Press, Deadlift*
```

### PR File Verification Log
Each PR file tracks when it was last verified:

```markdown
# Bench Press Personal Records

[PR content]

## Verification Log
| Date | Action | Notes |
|------|--------|-------|
| 2025-08-05 | verify-prs command | No missed PRs found |
| 2025-07-28 | Manual PR update | New 8RM: 225×8 |
| 2025-07-15 | verify-prs command | Updated 5RM record |
```

## Error Handling

### Missing PR Files
```markdown
⚠️ **Warning**: PR file not found for "Romanian Deadlift"

**Action**: Creating new PR file with current performance as baseline
**File**: User Data/PRs/Strength/Romanian_Deadlift.md
**Initial PR**: 185×8 (2025-07-28)
```

### Ambiguous Exercise Names
```markdown
⚠️ **Warning**: Exercise name variation detected

**Found in logs**: "DB Bench", "Dumbbell Bench Press", "DB Bench Press"
**Standard name**: "Dumbbell Bench Press"

**Action**: Standardizing all entries to "Dumbbell Bench Press"
**Files updated**: 3 workout logs, 1 PR file
```

### Date Inconsistencies
```markdown
❌ **Error**: Date inconsistency detected

**Workout file**: 2025-07-28.md
**PR entry date**: 2025-07-30
**Issue**: PR date is after workout date

**Action**: Correcting PR date to match workout date (2025-07-28)
```

## Advanced Features

### Batch Verification
```bash
claude verify-prs --all --force
```
- Checks ALL workout logs regardless of verification status
- Re-verifies files even if marked as checked
- Useful for system-wide PR audit

### Exercise Standardization
```bash
claude verify-prs --standardize-names
```
- Identifies exercise name variations
- Proposes standardized names
- Updates all files with consistent naming

### PR Gap Analysis
```bash
claude verify-prs --gap-analysis
```
- Identifies potential PRs based on progression patterns
- Highlights unusual drops in performance
- Suggests workouts that might have unrecorded PRs

## Integration with Fitness Guide

### Automatic Scheduling
The verify-prs command can be automatically triggered:

1. **Weekly**: Every Sunday, check last 7 days
2. **Monthly**: First of month, comprehensive 30-day check  
3. **Post-workout**: After logging significant performances
4. **Before progress reports**: Ensure accurate data for summaries

### User Notifications
```markdown
💡 **Suggestion**: Run PR verification

Last verification: 15 days ago
Recent heavy sessions detected: 3
Recommended: `claude verify-prs --days 15`
```

## Performance Considerations

### Efficient File Processing
- **Skip verified files**: Don't re-read files with recent verification dates
- **Exercise filtering**: Only check relevant PR files for detected exercises
- **Batch updates**: Group file modifications to minimize I/O

### Memory Management
- **Stream processing**: Handle large workout logs without loading entirely
- **Lazy loading**: Only load PR files when needed for comparison
- **Cache results**: Remember PR values during single verification session

This command ensures the Fitness Guide maintains accurate PR records automatically, catching any missed achievements and keeping the data consistent across all files.
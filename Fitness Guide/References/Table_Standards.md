# Mandatory Table Formatting Standards

This file defines the exact table formats required for all Fitness Guide data outputs to ensure consistency and immediate actionability.

## Core Table Requirements

### Universal Formatting Rules
- **Headers**: Always include descriptive headers with proper markdown alignment
- **Alignment**: Use consistent pipe (|) spacing for visual clarity
- **Units**: Include measurement units in headers or data where applicable
- **Width**: Maintain consistent column widths within table types
- **No broken syntax**: All tables must render properly in markdown

### Standard Column Order Guidelines
- **Date columns**: Always leftmost when present (YYYY-MM-DD format)
- **Primary metric**: Weight, reps, or main measurement next
- **Secondary metrics**: Supporting data in logical progression
- **Status/notes**: Rightmost column for qualitative information

## Workout Log Table Format

### Basic Exercise Log
```markdown
| Exercise | Set 1 | Set 2 | Set 3 | Set 4 | Notes |
|----------|-------|-------|-------|-------|-------|
| Exercise Name | WeightxReps | WeightxReps | WeightxReps | WeightxReps | Brief note |
```

### Enhanced Exercise Log (with RPE/Volume)
```markdown
| Exercise | Weight | Reps | Sets | RPE | Volume | Notes |
|----------|--------|------|------|-----|--------|-------|
| Exercise Name | XXX lbs | XX | X | X.X | XXXX lbs | Status |
```

### Session Summary Table
```markdown
| Session Info | Value |
|--------------|-------|
| Date | YYYY-MM-DD |
| Duration | XX minutes |
| Total Volume | XXXX lbs |
| Exercises | X |
| Working Sets | XX |
| Average RPE | X.X |
```

## PR History Table Format

### Individual Exercise PR Table
```markdown
| Date | Weight | Reps | Previous | Improvement | % Gain | Notes |
|------|--------|------|----------|-------------|--------|-------|
| YYYY-MM-DD | XXX lbs | XX | Previous PR | +X lbs | +X.X% | Context |
```

### Multi-Rep Range PR Table
```markdown
| Rep Range | Current PR | Date | Previous | Improvement | Est 1RM |
|-----------|------------|------|----------|-------------|---------|
| 1RM | XXX lbs | YYYY-MM-DD | Previous | +X lbs | XXX lbs |
| 3RM | XXX lbs | YYYY-MM-DD | Previous | +X lbs | XXX lbs |
| 5RM | XXX lbs | YYYY-MM-DD | Previous | +X lbs | XXX lbs |
| 8RM | XXX lbs | YYYY-MM-DD | Previous | +X lbs | XXX lbs |
| 10RM | XXX lbs | YYYY-MM-DD | Previous | +X lbs | XXX lbs |
```

## Progress Summary Table Format

### Time-Based Progress
```markdown
| Timeframe | Starting | Current | Change | % Change | Trend |
|-----------|----------|---------|--------|----------|-------|
| 30 Days | XXX lbs | XXX lbs | +X lbs | +X.X% | ↗️ |
| 90 Days | XXX lbs | XXX lbs | +X lbs | +X.X% | ↗️ |
| 1 Year | XXX lbs | XXX lbs | +X lbs | +X.X% | ↗️ |
```

### Multi-Exercise Progress Summary
```markdown
| Exercise | 30d Change | 90d Change | Current PR | Trend |
|----------|------------|------------|------------|-------|
| Squat | +X lbs | +X lbs | XXX lbs | ↗️ |
| Bench Press | +X lbs | +X lbs | XXX lbs | ↗️ |
| Deadlift | +X lbs | +X lbs | XXX lbs | ➡️ |
```

## Body Metrics Table Format

### Body Composition Tracking
```markdown
| Date | Weight | Body Fat % | Muscle Mass | Waist | Change | Goal Progress |
|------|--------|------------|-------------|-------|--------|---------------|
| YYYY-MM-DD | XXX lbs | XX.X% | XXX lbs | XX.X" | ±X lbs | XX% to goal |
```

### Body Metrics Change Analysis
```markdown
| Metric | Current | Previous | Change | % Change | 30d Trend |
|--------|---------|----------|--------|----------|-----------|
| Weight | XXX lbs | XXX lbs | ±X lbs | ±X.X% | Direction |
| Body Fat | XX.X% | XX.X% | ±X.X | ±X.X% | Direction |
| Waist | XX.X" | XX.X" | ±X.X" | ±X.X% | Direction |
```

## Workout Planning Table Format

### Exercise Selection Table
```markdown
| Exercise | Sets x Reps | Weight | Rest | RPE Target | Notes |
|----------|-------------|--------|------|------------|-------|
| Primary Lift | SxR | XXX lbs | X min | X-X | Focus |
| Secondary | SxR | XXX lbs | X min | X-X | Support |
| Accessory | SxR | XXX lbs | Xs | X-X | Volume |
```

### Weekly Split Planning
```markdown
| Day | Focus | Primary Exercises | Duration | Volume Target |
|-----|-------|-------------------|----------|---------------|
| Monday | Upper | Bench, Rows, Press | 60 min | 15,000 lbs |
| Tuesday | Lower | Squat, RDL, Lunge | 60 min | 20,000 lbs |
| Wednesday | Rest | - | - | - |
| Thursday | Upper | Press, Pull-ups | 45 min | 12,000 lbs |
| Friday | Lower | Deadlift, Squat | 60 min | 18,000 lbs |
```

## Nutrition Planning Table Format

### Meal Plan Table
```markdown
| Meal | Food | Quantity | Calories | Protein | Carbs | Fat |
|------|------|----------|----------|---------|-------|-----|
| Breakfast | Food item | Amount | XXX | XXg | XXg | XXg |
| Lunch | Food item | Amount | XXX | XXg | XXg | XXg |
| Dinner | Food item | Amount | XXX | XXg | XXg | XXg |
| **Daily Total** | - | - | **XXXX** | **XXXg** | **XXXg** | **XXXg** |
```

### Grocery List Table
```markdown
| Category | Item | Quantity | Unit Cost | Total | Priority |
|----------|------|----------|-----------|-------|----------|
| Protein | Chicken breast | 2 lbs | $4/lb | $8 | High |
| Carbs | Rice | 2 lbs | $2/lb | $4 | High |
| Fats | Olive oil | 1 bottle | $6 | $6 | Medium |
| **Total** | - | - | - | **$XX** | - |
```

## Analytics and Reporting Tables

### Weekly Performance Summary
```markdown
| Metric | Target | Actual | Achievement | Notes |
|--------|--------|--------|-------------|-------|
| Workouts | 4 | 3 | 75% | Missed Friday |
| Volume | 60,000 lbs | 55,500 lbs | 93% | On track |
| PRs | 0-1 | 2 | 200% | Great week |
| Recovery | 8hr sleep avg | 7.5hr | 94% | Nearly there |
```

### Goal Progress Tracking
```markdown
| Goal | Starting | Current | Target | Progress | Deadline | Status |
|------|----------|---------|--------|----------|----------|--------|
| Squat 400 | 350 lbs | 365 lbs | 400 lbs | 30% | 2025-12-01 | On Track |
| BW to 180 | 195 lbs | 187 lbs | 180 lbs | 53% | 2025-10-01 | Ahead |
| 5K sub-25 | 28:30 | 26:15 | 25:00 | 64% | 2025-09-15 | On Track |
```

## Command Mode Response Tables

### Status Check Format
```markdown
| Metric | Value | Status | Next Action |
|--------|-------|--------|-------------|
| Last Workout | Yesterday | Recovery | Train tomorrow |
| Weekly Progress | 3/4 sessions | On track | Complete Friday |
| Current Program | Week 2/4 | Mid-cycle | Continue |
| Recovery | 8hrs sleep | Good | Maintain |
```

### Volume Analysis Format
```markdown
| Exercise | Today | This Week | Last Week | Change |
|----------|-------|-----------|-----------|--------|
| Chest | 8,500 lbs | 25,000 lbs | 23,500 lbs | +6% |
| Back | 12,000 lbs | 30,000 lbs | 28,000 lbs | +7% |
| Legs | 15,000 lbs | 45,000 lbs | 42,000 lbs | +7% |
| **Total** | **35,500** | **100,000** | **93,500** | **+7%** |
```

## Error and Status Message Formats

### Success Confirmations
```markdown
✅ **Action Completed**: Brief description - Date

[MAIN DATA TABLE]

**Key Metrics**:
- Metric 1: Value
- Metric 2: Value
- Metric 3: Value

*Brief relevant comment if needed*
```

### Error Messages
```markdown
❌ **Error**: Specific issue description

**Expected Format**: Example of correct input
**Received**: What was actually provided

*Try again with corrected format*
```

## Table Validation Rules

### Pre-Output Checklist
- [ ] Headers properly aligned with content
- [ ] All rows have same number of columns
- [ ] Units specified in headers or data
- [ ] Date format is YYYY-MM-DD throughout
- [ ] Numbers formatted consistently (no decimals for weights unless <1 lb)
- [ ] Pipe characters (|) properly spaced
- [ ] No empty cells without placeholders (use "-" for N/A)

### Quality Standards
- **Scannability**: User can extract key info in <5 seconds
- **Actionability**: Data directly supports next decisions
- **Consistency**: Same type of data always uses same table format
- **Completeness**: All relevant metrics included, no critical gaps
- **Accuracy**: All calculations validated before display

These table standards ensure that every Fitness Guide response provides immediately actionable data in a consistent, professional format that prioritizes user efficiency over conversational elements.
# Automated Calculation Templates

This file provides standardized formulas and calculation methods for the Fitness Guide system.

## Volume Calculations

### Basic Volume Formulas
```
Set Volume = Weight × Reps
Exercise Volume = Set Volume × Number of Sets  
Total Session Volume = Σ(Exercise Volume) for all exercises
Weekly Volume = Σ(Daily Volume) for training week
```

### Volume Examples
```
Bench Press: 185 lbs × 8 reps × 3 sets = 4,440 lbs
Squats: 275 lbs × 5 reps × 4 sets = 5,500 lbs
Session Total: 4,440 + 5,500 = 9,940 lbs
```

## PR Detection Logic

### PR Comparison Algorithm
```
For exercise X with performance Weight × Reps:

1. Look up best current performance for rep range (Reps ± 2)
2. Compare weights:
   - If Weight > Previous_Weight AND Reps >= Previous_Reps: NEW PR
   - If Weight = Previous_Weight AND Reps > Previous_Reps: NEW PR
   
3. Calculate improvements:
   - Weight Improvement = New_Weight - Previous_Weight
   - Percentage Gain = (Weight_Improvement / Previous_Weight) × 100
   - Rep Improvement = New_Reps - Previous_Reps (if applicable)
```

### PR Classification Examples
```
Previous: 225×5    New: 235×5     → NEW PR (+10 lbs, +4.4%)
Previous: 225×5    New: 225×8     → NEW PR (same weight, +3 reps)
Previous: 225×5    New: 220×6     → NOT A PR (lower weight)
Previous: 225×5    New: 235×3     → MAYBE PR (need 1RM calculation)
```

## Progress Trend Calculations

### Time-Based Progress
```
30-Day Change = (Current_Best - Best_30_Days_Ago) / Best_30_Days_Ago × 100
90-Day Change = (Current_Best - Best_90_Days_Ago) / Best_90_Days_Ago × 100
Annual Progress = (Current_Best - Best_1_Year_Ago) / Best_1_Year_Ago × 100
```

### Goal Progress Tracking
```
Goal Progress % = (Current_Value - Starting_Value) / (Target_Value - Starting_Value) × 100

Example:
Starting Weight: 200 lbs
Current Weight: 185 lbs  
Target Weight: 175 lbs
Progress = (185 - 200) / (175 - 200) × 100 = 60%
```

## Rep Max Estimates

### Primary Formulas
```
1RM Estimate (Epley): Weight × (1 + Reps/30)
1RM Estimate (Brzycki): Weight × (36/(37-Reps))
5RM Estimate: 1RM × 0.85
10RM Estimate: 1RM × 0.75
```

### Rep Max Table Generation
```
For a performance of 225×8:
1RM = 225 × (1 + 8/30) = 225 × 1.267 = 285 lbs
3RM = 285 × 0.90 = 257 lbs  
5RM = 285 × 0.85 = 242 lbs
10RM = 285 × 0.75 = 214 lbs
```

## Body Composition Calculations

### Change Calculations
```
Weight Change = Current_Weight - Previous_Weight
Weight Change % = (Weight_Change / Previous_Weight) × 100
Body Fat Change = Current_BF% - Previous_BF%
Muscle Mass Change = Current_Muscle - Previous_Muscle
```

### BMI Calculation
```
BMI = Weight_lbs / (Height_inches)² × 703
BMI = Weight_kg / (Height_meters)²
```

## Workout Intensity Metrics

### Volume Calculations by Body Part
```
Chest Volume = Σ(Bench + Incline + Dips + Flyes + etc.)
Back Volume = Σ(Rows + Pull-ups + Lat Pulldowns + etc.)
Leg Volume = Σ(Squats + Leg Press + RDL + etc.)
```

### Training Density
```
Training Density = Total_Volume / Session_Duration_Minutes
Sets Per Minute = Total_Sets / Session_Duration_Minutes
Average Rest Time = (Session_Duration - Working_Time) / (Total_Sets - 1)
```

## Trend Analysis

### Progress Direction Indicators
```
Trend Direction:
- Improving: ↗️ (positive change >2%)
- Stable: ➡️ (change between -2% to +2%)
- Declining: ↘️ (negative change >2%)
```

### Rate of Progress
```
Monthly Rate = (Current - Previous) / Months_Between
Weekly Rate = Monthly_Rate / 4.33
Annual Projection = Current + (Monthly_Rate × 12)
```

## Workout Planning Calculations

### Volume Progression
```
Progressive Overload Options:
1. Weight: Previous_Weight + (2.5 to 10 lbs)
2. Reps: Previous_Reps + (1 to 3 reps)
3. Sets: Previous_Sets + 1 set
4. Density: Same volume, less rest time
```

### Training Max Calculations (5/3/1 style)
```
Training Max = True_1RM × 0.90
Week 1 (3×5): Training_Max × 0.65, 0.75, 0.85
Week 2 (3×3): Training_Max × 0.70, 0.80, 0.90  
Week 3 (5/3/1): Training_Max × 0.75, 0.85, 0.95
```

## Data Validation Rules

### Input Validation
```
Weight Range: 5 lbs to 1000 lbs (flag outliers)
Reps Range: 1 to 50 reps (flag unusual ranges)
Sets Range: 1 to 10 sets (flag excessive volume)
```

### Consistency Checks
```
Exercise Name Matching:
- "Bench Press" = "Bench" = "BP" = "Bench Press"
- Standardize to: "Bench Press"

Unit Consistency:
- Always use established user preference (lbs vs kg)
- Flag mixed units within same session
```

## Calculation Priority Order

When multiple calculations are needed:
1. **Volume calculations** (immediate feedback)
2. **PR detection** (impacts multiple files)
3. **Rep max estimates** (based on current performance)
4. **Progress trends** (requires historical data)
5. **Goal progress** (long-term tracking)

## Error Handling

### Missing Data
```
If Previous_PR not found: Use current performance as baseline
If Bodyweight missing: Skip relative strength calculations
If Date inconsistent: Use current date and flag for review
```

### Calculation Limits
```
Max reasonable 1RM: 3× bodyweight (flag for review)
Max session volume: 50,000 lbs (flag as potential error)
Max reps: 50 (flag unusual endurance work)
```

## Usage in Responses

### Example Implementation
```markdown
✅ **Workout Logged**: Upper Body - 2025-08-05

| Exercise | Set 1 | Set 2 | Set 3 | Volume |
|----------|-------|-------|-------|--------|
| Bench Press | 185×8 | 185×8 | 185×8 | 4,440 lbs |

**Key Metrics**:
- Total Volume: 4,440 lbs
- Est. 1RM: 234 lbs (Epley formula)
- Session Density: 59 lbs/minute

*Consistent performance across all sets. Ready for 190 lbs next session.*
```

These calculations should be applied automatically to provide users with immediate, actionable feedback while maintaining data consistency across all files.
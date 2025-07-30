# Daily Workout Template

Template for logging individual workout sessions with structured data capture and AI-assisted analysis.

## 🤖 AI Generation Prompt

Copy and paste this prompt to generate a daily workout:

```yaml
workout_generation:
  goal: "[strength/hypertrophy/endurance/fat_loss/general_fitness]"
  experience_level: "[beginner/intermediate/advanced]"
  available_time: "[30/45/60/75/90] minutes"
  equipment: "[home/gym/bodyweight/specific_equipment]"
  focus_areas: "[full_body/upper/lower/push/pull/legs/cardio]"
  current_program: "[program_name or 'none']"
  energy_level: "[1-10 scale]"
  recent_workouts: "[list last 3 workouts or 'none']"
  injuries_limitations: "[any current issues or 'none']"
  
output_format: |
  Please generate a workout session with:
  1. Warm-up routine (5-10 minutes)
  2. Main workout with specific sets/reps/weights
  3. Cool-down routine (5-10 minutes)
  4. RPE targets for each exercise
  5. Rest periods between sets
  6. Exercise alternatives if equipment unavailable
  7. Form cues for key exercises
```

## 📝 Daily Log Template

```markdown
---
date: [YYYY-MM-DD]
workout_type: [Strength/Cardio/Flexibility/Mixed]
program: [Current program name]
week: [Week X of program]
duration_planned: [Minutes]
location: [Home/Gym/Outdoor]
equipment: [Available equipment]
---

# Workout Log: [Date] - [Workout Name]

## Pre-Workout Assessment
- **Time**: [Start time]
- **Energy Level**: [1-10]
- **Motivation**: [1-10]
- **Sleep Quality**: [Last night, 1-10]
- **Soreness/Stiffness**: [Areas and severity]
- **Nutrition**: [Pre-workout meal timing and content]
- **Hydration**: [Adequate/Low/High]
- **Stress Level**: [1-10]
- **Notes**: [Any factors affecting today's workout]

## Today's Workout

### Warm-Up (5-10 minutes)
- [ ] [Exercise 1] - [Duration/reps]
- [ ] [Exercise 2] - [Duration/reps]
- [ ] [Exercise 3] - [Duration/reps]
- **Quality**: [Good/Fair/Poor]
- **Notes**: [Stiffness areas, mobility issues]

### Main Workout

#### Exercise 1: [Exercise Name]
**Target**: [Sets] x [Reps] @ [Weight/Intensity]
- Set 1: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- Set 2: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- Set 3: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- **Form Quality**: [Excellent/Good/Fair/Poor]
- **Notes**: [Technique observations, difficulty, adjustments]

#### Exercise 2: [Exercise Name]
**Target**: [Sets] x [Reps] @ [Weight/Intensity]
- Set 1: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- Set 2: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- Set 3: [Weight] x [Reps] (RPE: [1-10]) Rest: [Minutes]
- **Form Quality**: [Excellent/Good/Fair/Poor]
- **Notes**: [Technique observations, difficulty, adjustments]

[Continue for all exercises...]

### Cool-Down (5-10 minutes)
- [ ] [Activity 1] - [Duration]
- [ ] [Activity 2] - [Duration]
- [ ] [Stretching focus] - [Duration]
- **Relaxation Level**: [1-10]

## Post-Workout Assessment
- **Duration**: [Actual workout time]
- **Energy Level**: [1-10] (Post-workout)
- **Difficulty**: [Too Easy/Just Right/Too Hard]
- **Overall Form**: [Excellent/Good/Fair/Poor]
- **Enjoyment**: [1-10]
- **Pump/Feel**: [1-10]
- **Predicted Soreness**: [None/Mild/Moderate/Significant]
- **Recovery Needed**: [Light/Moderate/Heavy]

## Achievements & Progress
- **New PRs**: [Any personal records]
- **Form Improvements**: [Technical breakthroughs]
- **Milestones**: [Significant accomplishments]
- **Challenges**: [Difficulties faced]
- **Confidence Boost**: [What went well]

## Next Session Planning
- **Weight Adjustments**: [Increases/decreases needed]
- **Exercise Modifications**: [Changes to consider]
- **Focus Areas**: [What to emphasize next time]
- **Recovery Priorities**: [Areas needing attention]
- **Motivation Notes**: [Reminders for next session]

## Data Summary
```json
{
  "date": "[YYYY-MM-DD]",
  "duration_minutes": "[number]",
  "workout_type": "[type]",
  "energy_pre": "[1-10]",
  "energy_post": "[1-10]",
  "rpe_average": "[1-10]",
  "exercises_completed": "[number]",
  "total_sets": "[number]",
  "form_quality": "[1-10]",
  "enjoyment": "[1-10]",
  "new_prs": "[number]",
  "program_adherence": "[percentage]"
}
```

## Links
- Previous session: [[YYYY-MM-DD Workout]]
- Next planned: [[YYYY-MM-DD Workout]]
- Program: [[Program Name]]
- Exercise references: [[Exercise 1]] | [[Exercise 2]]

Tags: #workout #[workout_type] #[program_name] #week-[X] #[year] #[month]
```

## 🔄 Weekly Summary Generator

```yaml
weekly_analysis_prompt:
  input_data: "[paste workout data JSON from each daily log]"
  analysis_focus:
    - consistency: "workout completion rate and schedule adherence"
    - progression: "weight increases, rep improvements, form quality"
    - recovery: "energy levels, soreness patterns, sleep quality"
    - program_adherence: "planned vs actual exercises and modifications"
    - trends: "patterns in energy, motivation, and performance"
  
  output_format: |
    Generate a weekly summary including:
    1. Training consistency metrics
    2. Performance progression analysis
    3. Recovery and energy patterns
    4. Program adherence assessment
    5. Recommendations for next week
    6. Potential issues or concerns
    7. Celebration of achievements
```

---
*Last Updated: 2025-07-30*
# Power User Prompts

Advanced AI prompts for sophisticated fitness tracking and analysis workflows.

## 🤖 Weekly Analysis Prompt

For comprehensive weekly review and strategic planning:

```json
{
  "weekly_fitness_analysis": {
    "data_summary": {
      "training_completion": {
        "planned_workouts": "[number]",
        "completed_workouts": "[number]",
        "completion_percentage": "[%]",
        "missed_sessions": "[reasons: time/energy/motivation/illness/other]"
      },
      "performance_metrics": {
        "total_training_time": "[hours:minutes]",
        "average_workout_quality": "[1-10 scale]",
        "average_session_rpe": "[1-10 scale]",
        "new_prs_achieved": "[number and types]",
        "form_improvements": "[list key technical advances]"
      },
      "wellness_indicators": {
        "average_morning_energy": "[1-10]",
        "average_sleep_quality": "[1-10]",
        "average_post_workout_energy": "[1-10]",
        "recovery_adequacy": "[excellent/good/adequate/poor]",
        "motivation_trend": "[increasing/stable/decreasing]"
      }
    },
    "weekly_context": {
      "life_factors": "[work stress/travel/family obligations/health issues]",
      "program_phase": "[current program name and week number]",
      "goal_focus": "[primary objective this week]",
      "environmental_factors": "[weather/gym access/equipment changes]"
    },
    "analysis_request": "Provide comprehensive weekly analysis including: 1) Performance trend assessment, 2) Recovery and energy pattern analysis, 3) Goal progress evaluation, 4) Optimal performance condition identification, 5) Challenge pattern recognition, 6) Next week strategic recommendations, 7) Program adherence and effectiveness assessment."
  }
}
```

## 🤖 Monthly Strategic Analysis Prompt

For deep monthly review and long-term planning:

```json
{
  "monthly_fitness_strategic_analysis": {
    "quantitative_summary": {
      "training_volume": {
        "total_workouts": "[completed vs planned for the month]",
        "total_training_time": "[hours:minutes]",
        "consistency_rate": "[percentage of planned sessions completed]",
        "average_session_duration": "[minutes]",
        "weekly_consistency": "[week 1: X%, week 2: Y%, etc.]"
      },
      "performance_progression": {
        "strength_improvements": "[list key lifts with before/after numbers]",
        "total_prs_achieved": "[number across all categories]",
        "technical_skill_advances": "[movement quality improvements]",
        "endurance_gains": "[cardio capacity improvements if applicable]",
        "program_completion": "[phases or programs finished]"
      },
      "wellness_metrics": {
        "average_energy_trends": "[morning, post-workout energy patterns]",
        "sleep_quality_patterns": "[consistency and correlation with performance]",
        "recovery_adequacy": "[how well rest supported training demands]",
        "motivation_consistency": "[engagement and drive patterns]"
      }
    },
    "strategic_context": {
      "life_phase": "[current life demands and circumstances]",
      "program_effectiveness": "[what worked well vs what struggled]",
      "goal_evolution": "[how priorities or targets have shifted]",
      "resource_availability": "[time, energy, equipment changes]"
    },
    "analysis_request": "Provide comprehensive monthly strategic analysis including: 1) Quantitative progress assessment with trend identification, 2) Qualitative pattern recognition across performance and wellness, 3) Program effectiveness evaluation with specific recommendations, 4) Strategic goal reassessment and priority optimization, 5) Resource allocation analysis for maximum efficiency, 6) Long-term trajectory evaluation and course corrections, 7) Next month's strategic focus and tactical implementation plan."
  }
}
```

## 🤖 Custom Template Generation Prompt

For creating situation-specific templates:

```yaml
template_generation_request:
  scenario: "[busy_day/travel/emergency_motivation/minimal_time/equipment_limited]"
  time_available: "[30_seconds/2_minutes/5_minutes/10_minutes]"
  primary_goal: "[maintain_habit/capture_key_data/stay_motivated/track_progress]"
  tracking_elements: "[workout_completion/energy_levels/achievements/basic_metrics]"
  format_preference: "[ultra_minimal/structured_brief/voice_friendly/mobile_optimized]"
  
  generation_request: |
    Create a fitness tracking template optimized for this scenario that:
    1. Captures essential information in minimal time
    2. Maintains connection to fitness goals and progress
    3. Supports habit consistency even in challenging circumstances
    4. Provides meaningful data for future analysis
    5. Feels sustainable and non-burdensome
    Include both the template format and usage instructions.
```

## 🎯 Daily Routine Optimization Prompt

For personalizing daily tracking workflows:

```yaml
daily_routine_optimization:
  current_situation:
    morning_energy: "[typically low/moderate/high]"
    workout_timing: "[morning/lunch/evening preference]"
    available_time: "[5/10/15/20] minutes for tracking"
    consistency_challenges: "[time/motivation/complexity/other]"
    tracking_goals: "[performance/motivation/habits/insights]"
  
  lifestyle_factors:
    work_schedule: "[fixed/flexible/irregular]"
    family_obligations: "[minimal/moderate/significant]"
    travel_frequency: "[rarely/occasionally/frequently]"
    stress_levels: "[low/moderate/high typical stress]"
  
  optimization_request: |
    Design a personalized daily fitness tracking routine that:
    1. Fits my schedule and energy patterns
    2. Provides maximum value with minimal time investment
    3. Adapts to varying daily circumstances
    4. Maintains long-term sustainability
    5. Includes specific efficiency techniques
```

## ⚡ Quick Reference Templates

### Voice-to-Text Ultra-Brief
```yaml
# Voice Log Template (Speak this):
voice_log_format: "Date [today's date]. Energy [number]. Workout [type or none]. Quality [number]. One win: [achievement]. Tomorrow focus: [one word]."

# Example:
# "January 15th. Energy 7. Workout upper body strength. Quality 8. One win: new deadlift PR. Tomorrow focus: recovery."
```

### Emergency Quick Check
```markdown
# Quick Check: [Date]

**Energy**: [1-10]
**Movement**: [None/Light/Moderate/Full workout]
**Win**: [One positive thing]
**Tomorrow**: [One word intention]

Done. ✓
```

### Travel/Disruption Minimal
```json
{
  "disrupted_day": {
    "date": "[YYYY-MM-DD]",
    "situation": "[travel/sick/crisis/no_time]",
    "movement": "[none/walk/stretch/adapted_workout/full]",
    "energy": "[1-10]",
    "positive": "[one good thing about today]",
    "adaptability_win": "[how you stayed flexible]"
  }
}
```

## Usage Notes

- **Copy and paste** these prompts into your AI assistant
- **Fill in the bracketed information** with your specific data
- **Customize the analysis_request** sections based on your specific goals
- **Use these as starting points** - modify based on what insights you find most valuable

## 🏋️ Workout Generation Prompts

### Quick Workout Generator
```yaml
workout_request:
  session_type: "[strength/cardio/flexibility/mixed]"
  duration: "[30/45/60/75/90] minutes"
  equipment: "[bodyweight/dumbbells/barbell/gym/home/specific_equipment]"
  fitness_level: "[beginner/intermediate/advanced]"
  energy_level: "[low/moderate/high] (1-10 scale)"
  focus_area: "[full_body/upper/lower/push/pull/legs/core/cardio]"
  recent_training: "[list last 2-3 workouts or 'none']"
  limitations: "[injuries/time_constraints/equipment_issues or 'none']"
  goals: "[strength/muscle/endurance/fat_loss/maintenance]"

output_requirements:
  format: "structured workout with warm-up, main exercises, cool-down"
  include: "sets, reps, weights/intensity, rest periods, RPE targets"
  alternatives: "exercise substitutions if equipment unavailable"
  progression: "how to make next session harder/easier"
  safety: "form cues and warning signs"
  timing: "realistic time breakdown for each section"

Please generate a complete workout session based on these parameters.
```

### Program Design Generator
```xml
<program_generation>
  <user_profile>
    <experience_level>[beginner/intermediate/advanced]</experience_level>
    <training_history>[years of consistent training]</training_history>
    <current_fitness_level>[1-10 self-assessment]</current_fitness_level>
    <injury_history>[any relevant injuries or limitations]</injury_history>
  </user_profile>
  
  <goals>
    <primary_goal>[strength/hypertrophy/fat_loss/endurance/general_fitness/athletic_performance]</primary_goal>
    <secondary_goals>[list 1-2 additional goals]</secondary_goals>
    <timeline>[program duration in weeks]</timeline>
    <success_metrics>[how you'll measure success]</success_metrics>
  </goals>
  
  <constraints>
    <schedule>
      <days_per_week>[3/4/5/6]</days_per_week>
      <session_duration>[30/45/60/75/90 minutes]</session_duration>
      <preferred_days>[Monday, Wednesday, Friday, etc.]</preferred_days>
    </schedule>
    <equipment>
      <available_equipment>[list all available equipment]</available_equipment>
      <limitations>[space, noise, budget constraints]</limitations>
    </equipment>
    <lifestyle_factors>
      <work_schedule>[regular/irregular/shift_work]</work_schedule>
      <stress_levels>[low/moderate/high]</stress_levels>
      <recovery_capacity>[excellent/good/poor]</recovery_capacity>
    </lifestyle_factors>
  </constraints>
  
  <preferences>
    <training_style>[powerlifting/bodybuilding/crossfit/general/mixed]</training_style>
    <exercise_preferences>[compound_focus/variety/bodyweight/machines]</exercise_preferences>
    <complexity_preference>[simple/moderate/complex]</complexity_preference>
  </preferences>
  
  <output_request>
    Please create a comprehensive training program including:
    1. Program overview with phases and periodization
    2. Weekly schedule with specific workout days
    3. Exercise selection with sets, reps, and progression schemes
    4. Warm-up and cool-down protocols
    5. Deload weeks and recovery protocols
    6. Progress tracking methods
    7. Exercise substitutions for common scenarios
    8. Expected timeline for results
  </output_request>
</program_generation>
```

### Workout Analysis and Optimization
```json
{
  "workout_analysis": {
    "session_data": {
      "date": "[workout date]",
      "exercises_performed": "[list with sets, reps, weights]",
      "total_duration": "[minutes]",
      "overall_rpe": "[1-10]",
      "energy_level": {
        "pre_workout": "[1-10]",
        "post_workout": "[1-10]"
      }
    },
    "context": {
      "sleep_quality": "[hours and quality 1-10]",
      "nutrition_timing": "[last meal timing and content]",
      "stress_level": "[1-10]",
      "recent_workouts": "[last 2-3 sessions summary]",
      "current_program": "[program name and week]"
    },
    "analysis_request": "Provide comprehensive workout analysis including: 1) Performance assessment vs recent sessions, 2) Energy and RPE correlation analysis, 3) Volume and intensity evaluation, 4) Recovery recommendations, 5) Next session adjustments, 6) Potential form or programming issues, 7) Progress indicators and patterns"
  }
}
```

---
*Last Updated: 2025-07-31*
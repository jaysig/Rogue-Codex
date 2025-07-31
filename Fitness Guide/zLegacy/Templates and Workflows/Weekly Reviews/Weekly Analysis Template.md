# Weekly Analysis Template

Comprehensive weekly review system with AI-powered analysis for strategic fitness planning and pattern recognition.

## 🤖 Weekly Analysis Generation Prompt

Copy and paste this prompt for AI-assisted weekly analysis:

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

## 📊 Weekly Review Template

### Week Overview: [Week of Date]

```markdown
# Weekly Fitness Review: [Week of Date]

## Quick Summary Dashboard
- **Program**: [Current program name - Week X]
- **Completion**: [X/Y] workouts completed ([%])
- **Total Time**: [Hours:Minutes] training
- **Key Win**: [Biggest achievement this week]
- **Main Challenge**: [Primary obstacle encountered]
- **Next Week Focus**: [One sentence priority]

## Detailed Performance Analysis

### Training Completion Assessment
| Day | Planned Workout | Completed | Duration | Quality (1-10) | Notes |
|-----|----------------|-----------|----------|----------------|-------|
| Mon | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Tue | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Wed | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Thu | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Fri | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Sat | [Workout type] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |
| Sun | [Rest/Active recovery] | ✓/✗ | [Minutes] | [1-10] | [Key observations] |

### Performance Metrics Summary
```yaml
weekly_performance:
  volume_metrics:
    total_sets: "[number]"
    total_reps: "[estimated total]"
    total_weight_moved: "[tonnage if tracked]"
    training_density: "[sets per minute of training]"
  
  intensity_metrics:
    average_rpe: "[1-10 across all exercises]"
    peak_intensity_sessions: "[which days pushed hardest]"
    recovery_sessions: "[lighter days executed as planned]"
    progressive_overload: "[exercises where load/reps increased]"
  
  quality_metrics:
    average_session_rating: "[1-10 overall workout quality]"
    form_consistency: "[excellent/good/needs attention]"
    technical_breakthroughs: "[list improvements in exercise execution]"
    equipment_utilization: "[efficiency of gym/home setup usage]"
```

### Achievement Tracking
```json
{
  "weekly_achievements": {
    "personal_records": {
      "strength_prs": [
        {
          "exercise": "[name]",
          "previous_best": "[weight/reps]",
          "new_record": "[weight/reps]",
          "improvement": "[percentage or absolute gain]"
        }
      ],
      "volume_prs": [
        {
          "metric": "[total sets/reps/tonnage]",
          "new_record": "[value]",
          "context": "[single session or weekly total]"
        }
      ],
      "technical_prs": [
        {
          "skill": "[movement pattern or form element]",
          "achievement": "[what was accomplished]",
          "significance": "[why this matters for progress]"
        }
      ]
    },
    "consistency_achievements": {
      "attendance": "[perfect week/improvement over last week]",
      "habit_formation": "[new positive behaviors established]",
      "barrier_overcome": "[obstacles successfully navigated]"
    },
    "wellness_achievements": {
      "energy_improvements": "[better recovery/morning energy]",
      "sleep_optimization": "[better rest quality or duration]",
      "motivation_maintenance": "[sustained enthusiasm despite challenges]"
    }
  }
}
```

## 🔍 Pattern Recognition Analysis

### Energy and Performance Correlations

```yaml
pattern_analysis:
  optimal_performance_conditions:
    best_workout_day: "[day of week] - [why it worked well]"
    peak_energy_time: "[time of day] workouts performed best"
    ideal_sleep_correlation: "[hours of sleep] led to [energy level] and [performance quality]"
    nutrition_timing_success: "[meal timing] relative to workout optimized performance"
    stress_level_impact: "[low/moderate/high stress days] correlated with [performance outcome]"
  
  challenge_patterns:
    consistent_struggle_day: "[day of week] - [reasons for difficulty]"
    energy_drain_factors: "[what consistently reduced performance]"
    motivation_killers: "[circumstances that made showing up hard]"
    recovery_inadequacy_signs: "[when rest wasn't sufficient]"
    environmental_obstacles: "[external factors that disrupted training]"
  
  weekly_trend_direction:
    performance_trajectory: "[improving/maintaining/declining throughout week]"
    motivation_curve: "[how enthusiasm changed day by day]"
    energy_sustainability: "[whether energy was maintained or depleted]"
    goal_alignment: "[how well training supported objectives]"
```

### AI Pattern Deep-Dive Prompt

```xml
<weekly_pattern_analysis>
  <performance_data>
    <daily_energy_levels>[Mon: X, Tue: Y, Wed: Z, etc.]</daily_energy_levels>
    <workout_quality_ratings>[daily 1-10 ratings]</workout_quality_ratings>
    <completion_success>[which days met plans vs which didn't]</completion_success>
    <sleep_correlation>[hours slept vs next day performance]</sleep_correlation>
  </performance_data>
  
  <contextual_factors>
    <work_stress_levels>[daily stress ratings if tracked]</work_stress_levels>
    <nutrition_consistency>[meal timing and quality notes]</nutrition_consistency>
    <environmental_changes>[gym access, weather, equipment availability]</environmental_changes>
    <social_factors>[workout partners, family support, social pressures]</social_factors>
  </contextual_factors>
  
  <goal_progress_context>
    <current_program_phase>[program name and week within program]</current_program_phase>
    <target_progressions>[which exercises were supposed to advance]</target_progressions>
    <actual_progressions>[which exercises did advance and by how much]</actual_progressions>
    <goal_timeline>[how this week fits into larger goal timeline]</goal_timeline>
  </contextual_factors>
  
  <analysis_request>
    Based on this week's complete data, identify:
    1. My personal optimal performance formula (conditions that consistently produce best results)
    2. Warning signs and early indicators of suboptimal performance
    3. Recovery adequacy assessment and optimization opportunities
    4. Goal progress trajectory and realistic timeline adjustments
    5. Most impactful single change I could make for next week
    6. Long-term pattern implications for program design
  </analysis_request>
</weekly_pattern_analysis>
```

## 📈 Goal Progress Evaluation

### Goal Tracking Matrix

```markdown
# Goal Progress Assessment: [Week of Date]

## Primary Goals Status
| Goal | Original Target | Timeline | This Week Progress | Cumulative Progress | On Track? | Adjustments Needed |
|------|----------------|----------|-------------------|-------------------|-----------|-------------------|
| [Goal 1] | [Specific target] | [By when] | [What advanced this week] | [% complete] | Y/N | [What to change] |
| [Goal 2] | [Specific target] | [By when] | [What advanced this week] | [% complete] | Y/N | [What to change] |
| [Goal 3] | [Specific target] | [By when] | [What advanced this week] | [% complete] | Y/N | [What to change] |

## Leading Indicators Analysis
### Process Goals (Controllable Actions)
- **Workout consistency**: Target [X/week] | Actual [Y/week] | [% success]
- **Sleep quality**: Target [X hrs avg] | Actual [Y hrs avg] | [meeting target Y/N]
- **Recovery practices**: Target [specific practices] | Actual [what was done] | [consistency rating]
- **Nutrition alignment**: Target [meal timing/quality] | Actual [adherence level] | [% compliance]

### Outcome Goals (Results-Based)
- **Strength improvements**: [Expected weekly gains] vs [Actual improvements]
- **Body composition**: [Expected changes] vs [Observed changes if measured]
- **Performance benchmarks**: [Test results or capacity improvements]
- **Subjective improvements**: [Energy, confidence, enjoyment levels]

## Goal Refinement Analysis
```json
{
  "goal_assessment": {
    "realistic_timeline_check": {
      "original_expectations": "[what you thought was possible]",
      "actual_progress_rate": "[what's actually happening]",
      "timeline_adjustment": "[faster/slower/on track]",
      "revised_completion_date": "[if adjustment needed]"
    },
    "goal_priority_alignment": {
      "most_motivating_goal": "[which goal drives consistency]",
      "least_motivating_goal": "[which feels like a burden]",
      "conflicting_goals": "[any goals that work against each other]",
      "goal_hierarchy_refinement": "[reordered priority list]"
    },
    "approach_effectiveness": {
      "working_strategies": "[methods producing results]",
      "ineffective_approaches": "[methods not producing results]",
      "missing_elements": "[what might be needed to accelerate progress]",
      "sustainable_practices": "[what can be maintained long-term]"
    }
  }
}
```
```

## 🎯 Strategic Planning for Next Week

### Upcoming Week Preparation

```yaml
next_week_strategy:
  program_progression:
    current_program: "[name and upcoming week number]"
    planned_progressions: "[which exercises to advance]"
    volume_adjustments: "[sets/reps modifications planned]"
    intensity_modifications: "[weight increases or technique focus]"
    deload_considerations: "[any recovery weeks or lighter sessions needed]"
  
  schedule_optimization:
    known_challenges: "[travel/work demands/family obligations]"
    high_priority_sessions: "[workouts that must happen regardless]"
    flexible_sessions: "[workouts that can be moved or modified]"
    contingency_plans: "[backup options for disrupted days]"
    minimum_effective_dose: "[absolute minimum training to maintain progress]"
  
  focus_priorities:
    primary_emphasis: "[strength/technique/consistency/recovery - pick one]"
    secondary_focus: "[complementary area to support primary]"
    habit_formation: "[one new behavior to establish]"
    obstacle_prevention: "[specific preparation for known challenges]"
```

### AI Strategic Planning Prompt

```json
{
  "weekly_strategic_planning": {
    "current_status": {
      "program_progress": "[how current program is working]",
      "goal_advancement": "[rate of progress toward targets]",
      "energy_sustainability": "[whether current approach is sustainable]",
      "motivation_level": "[enthusiasm for upcoming training]"
    },
    "upcoming_week_context": {
      "schedule_constraints": "[known time/energy limitations]",
      "environmental_factors": "[gym access, weather, equipment availability]",
      "life_demands": "[work/family/travel that might impact training]",
      "recovery_status": "[how recovered you feel going into the week]"
    },
    "optimization_priorities": {
      "biggest_opportunity": "[area with most potential for improvement]",
      "critical_success_factor": "[what must go right for a successful week]",
      "potential_obstacle": "[most likely challenge to successful execution]",
      "motivational_focus": "[what will keep you consistent]"
    },
    "planning_request": "Design next week's training approach considering: 1) Optimal workout scheduling based on my patterns, 2) Progressive overload recommendations, 3) Recovery integration strategies, 4) Contingency planning for obstacles, 5) Motivation maintenance techniques, 6) Success metrics for the upcoming week."
  }
}
```

### Weekly Implementation Plan

```markdown
# Implementation Plan: [Week of Date]

## Daily Workout Schedule
### Monday: [Planned workout type]
- **Focus**: [Primary emphasis for session]
- **Key exercises**: [2-3 most important movements]
- **Progression target**: [Specific advancement goal]
- **Success criteria**: [How to know session was successful]
- **Backup plan**: [If time/energy is limited]

### Tuesday: [Planned workout type]
- **Focus**: [Primary emphasis for session]
- **Key exercises**: [2-3 most important movements]
- **Progression target**: [Specific advancement goal]
- **Success criteria**: [How to know session was successful]
- **Backup plan**: [If time/energy is limited]

[Continue for all training days...]

## Weekly Success Metrics
### Quantitative Targets
- **Workout completion**: [X/Y sessions minimum]
- **Total training time**: [Hours:Minutes target]
- **Progressive overload**: [Specific exercises to advance]
- **Consistency score**: [Daily tracking completion %]

### Qualitative Objectives
- **Energy management**: [Sustainable throughout week]
- **Form focus**: [Technical improvement priority]
- **Enjoyment maintenance**: [Training remains positive experience]
- **Recovery adequacy**: [Feeling prepared for each session]

## Potential Challenge Mitigation
### Identified Risks
- **Schedule conflict**: [Specific day/time issue] → **Solution**: [Alternative plan]
- **Energy depletion**: [Anticipated low energy day] → **Solution**: [Modified approach]
- **Motivation drop**: [Expected enthusiasm challenge] → **Solution**: [Motivation strategy]
- **Equipment limitation**: [Known access issue] → **Solution**: [Alternative exercises]

### Success Support Systems
- **Environmental setup**: [How to optimize workout space/equipment]
- **Social support**: [How others can help with consistency]
- **Habit linkage**: [Connect training to existing routines]
- **Progress celebration**: [How to acknowledge weekly achievements]
```

## 🔄 System Optimization Review

### Weekly System Efficiency Assessment

```yaml
system_effectiveness_review:
  tracking_efficiency:
    daily_routine_time: "[average minutes per day for all tracking]"
    weekly_review_time: "[minutes for this comprehensive review]"
    time_value_ratio: "[high/medium/low perceived value for time invested]"
    friction_points: "[what takes too long or feels cumbersome]"
  
  data_utility:
    most_valuable_insights: "[which data points provide greatest value]"
    least_useful_metrics: "[what's tracked but not helpful]"
    missing_information: "[what would be valuable to add]"
    pattern_recognition_success: "[how well system reveals trends]"
  
  motivation_impact:
    consistency_support: "[how tracking helps with adherence]"
    achievement_recognition: "[how well system captures progress]"
    goal_alignment: "[whether tracking supports actual objectives]"
    long_term_sustainability: "[can this approach be maintained]"
  
  optimization_opportunities:
    simplification_potential: "[what could be streamlined]"
    automation_possibilities: "[what could be made more efficient]"
    value_enhancement: "[how to get more insight from same effort]"
    personalization_refinements: "[how to better match individual needs]"
```

## 📚 Integration and Linking

### Related Documents
- **Previous week**: [[Weekly Review - Previous Date]]
- **Monthly analysis**: [[Monthly Review - Current Month]]
- **Program details**: [[Current Program Name]]
- **Goal tracking**: [[Annual/Quarterly Goal Progress]]

### Daily Log References
- **Monday workout**: [[Date - Monday Workout]]
- **Tuesday workout**: [[Date - Tuesday Workout]]
- **Wednesday workout**: [[Date - Wednesday Workout]]
- **Thursday workout**: [[Date - Thursday Workout]]
- **Friday workout**: [[Date - Friday Workout]]
- **Saturday workout**: [[Date - Saturday Workout]]
- **Sunday activity**: [[Date - Sunday Activity]]

### AI Analysis Archive
- **Performance analysis**: [[Week X Performance AI Analysis]]
- **Pattern recognition**: [[Week X Pattern Analysis]]
- **Strategic planning**: [[Week X+1 Strategic Plan]]

### Tags
#weekly-review #[program-name] #week-[number] #[month] #[year] #[primary-goal]

---
*Last Updated: 2025-07-30*
```
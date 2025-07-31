# Program Generator

AI-assisted workout program creation with structured prompts for generating comprehensive training plans.

## 🤖 Program Creation Prompt

Copy and paste this prompt to generate a complete workout program:

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
      <location>[home/gym/outdoor]</location>
      <available_equipment>[list available equipment or 'full gym']</available_equipment>
      <equipment_limitations>[any restrictions]</equipment_limitations>
    </equipment>
    <preferences>
      <exercise_preferences>[favorite exercises or movement patterns]</exercise_preferences>
      <exercise_dislikes>[exercises to avoid if possible]</exercise_dislikes>
      <intensity_preference>[high/moderate/low intensity preference]</intensity_preference>
    </preferences>
  </constraints>
  
  <output_requirements>
    Please generate a complete program including:
    1. Program overview with phases and progression
    2. Weekly schedule with specific workouts
    3. Exercise selection with sets/reps/intensity
    4. Progression protocols for each phase
    5. Deload and recovery weeks
    6. Exercise substitutions for equipment limitations
    7. Program assessment benchmarks
    8. Transition recommendations for program completion
  </output_requirements>
</program_generation>
```

## 📋 Program Template Structure

```markdown
# [Program Name] - [Goal Focus]

## Program Overview
- **Duration**: [X weeks total]
- **Schedule**: [X days per week]
- **Primary Goal**: [Main objective]
- **Secondary Goals**: [Additional benefits]
- **Experience Level**: [Target audience]
- **Equipment**: [Required equipment]
- **Time per Session**: [Average duration]
- **Program Type**: [Linear/Undulating/Block/Conjugate]

## Program Phases

### Phase 1: Foundation (Weeks 1-[X])
**Focus**: [Movement quality, base building, adaptation]
- **Volume**: [Sets/week per muscle group]
- **Intensity**: [Percentage ranges or RPE targets]
- **Frequency**: [Sessions per muscle group per week]
- **Key Adaptations**: [What the body learns in this phase]

### Phase 2: Development (Weeks [X]-[X])
**Focus**: [Skill refinement, load progression]
- **Volume**: [Progressive increase details]
- **Intensity**: [How intensity increases]
- **Frequency**: [Any changes to frequency]
- **Key Adaptations**: [Targeted improvements]

### Phase 3: Intensification (Weeks [X]-[X])
**Focus**: [Peak performance, goal achievement]
- **Volume**: [How volume changes]
- **Intensity**: [Peak intensity targets]
- **Frequency**: [Final frequency adjustments]
- **Key Adaptations**: [Peak adaptations]

### Deload/Recovery (Week [X])
**Focus**: [Recovery, super-compensation]
- **Volume Reduction**: [Percentage decrease]
- **Intensity Maintenance**: [How to maintain intensity]
- **Active Recovery**: [Alternative activities]

## Weekly Schedule

### Week 1-[X] Template

**Day 1 - [Workout Focus]**
```yaml
workout_structure:
  warm_up:
    duration: "10 minutes"
    exercises:
      - exercise: "[movement]"
        duration: "[time/reps]"
        purpose: "[mobility/activation/preparation]"
  
  main_workout:
    exercise_1:
      name: "[Primary compound movement]"
      sets: "[number]"
      reps: "[range]"
      intensity: "[weight/RPE/percentage]"
      rest: "[minutes]"
      progression: "[how to advance]"
    
    exercise_2:
      name: "[Secondary movement]"
      sets: "[number]"
      reps: "[range]"
      intensity: "[weight/RPE/percentage]"
      rest: "[minutes]"
      progression: "[how to advance]"
    
    exercise_3:
      name: "[Accessory movement]"
      sets: "[number]"
      reps: "[range]"
      intensity: "[weight/RPE/percentage]"
      rest: "[minutes]"
      progression: "[how to advance]"
  
  cool_down:
    duration: "5-10 minutes"
    focus: "[flexibility/mobility areas]"
```

**Day 2 - [Workout Focus]**
[Similar YAML structure for each training day]

## Progression Protocols

### Strength Progression
```json
{
  "progression_model": "[linear/double_progression/percentage_based]",
  "advancement_criteria": {
    "reps": "[when to increase weight based on reps]",
    "rpe": "[RPE targets for progression]",
    "form_quality": "[form standards required]"
  },
  "weight_increases": {
    "upper_body": "[kg/lb increments]",
    "lower_body": "[kg/lb increments]",
    "small_muscles": "[kg/lb increments]"
  },
  "stall_protocol": "[what to do when progress stops]"
}
```

### Volume Progression
```json
{
  "weekly_progression": {
    "week_1": "[baseline sets]",
    "week_2": "[sets increase]",
    "week_3": "[peak sets]",
    "week_4": "[deload sets]"
  },
  "set_addition_criteria": "[when to add sets]",
  "maximum_volumes": "[upper limits per muscle group]"
}
```

## Exercise Substitutions

| Original Exercise | Equipment Alternative | Difficulty Alternative |
|------------------|----------------------|----------------------|
| [Primary exercise] | [Home/minimal equipment version] | [Easier/harder version] |
| [Secondary exercise] | [Alternative equipment option] | [Progression/regression] |
| [Accessory exercise] | [Bodyweight alternative] | [Scaled version] |

## Assessment Benchmarks

### Baseline Testing (Week 1)
```yaml
strength_tests:
  - exercise: "[Primary lift]"
    test_type: "[1RM/3RM/5RM]"
    measurement: "[weight achieved]"
  
  - exercise: "[Secondary lift]"
    test_type: "[rep test at bodyweight]"
    measurement: "[reps completed]"

body_composition:
  - measurement: "[weight/body_fat/circumferences]"
    baseline_value: "[starting measurement]"

performance_tests:
  - test: "[cardio/endurance measure]"
    baseline: "[starting performance]"
```

### Mid-Program Assessment (Week [X])
[Similar structure with progress comparisons]

### Final Assessment (Week [X])
[Complete re-testing with improvement calculations]

## Program Completion Transition

### Success Indicators
- [ ] [Specific strength improvements achieved]
- [ ] [Body composition changes met]
- [ ] [Performance benchmarks reached]
- [ ] [Consistency maintained throughout program]

### Next Program Recommendations
```yaml
program_progression:
  strength_focus:
    next_program: "[Advanced strength program]"
    rationale: "[Why this progression makes sense]"
  
  hypertrophy_focus:
    next_program: "[Muscle building specialization]"
    rationale: "[Logical next step]"
  
  maintenance:
    next_program: "[Maintenance routine]"
    rationale: "[When to maintain vs progress]"
```

## Troubleshooting Guide

### Common Issues
- **Lack of Progress**: [Assessment questions and solutions]
- **Excessive Fatigue**: [Recovery optimization strategies]
- **Schedule Conflicts**: [Program modification options]
- **Equipment Limitations**: [Alternative exercise protocols]
- **Motivation Loss**: [Re-engagement strategies]

## Program Data Template
```json
{
  "program_id": "[unique identifier]",
  "start_date": "[YYYY-MM-DD]",
  "user_profile": {
    "experience": "[level]",
    "goals": "[primary and secondary]",
    "constraints": "[schedule and equipment]"
  },
  "baseline_metrics": {
    "strength": "[key lift numbers]",
    "body_composition": "[measurements]",
    "performance": "[benchmark scores]"
  },
  "weekly_data": [
    {
      "week": 1,
      "compliance": "[percentage]",
      "average_rpe": "[1-10]",
      "total_volume": "[sets or tonnage]",
      "notes": "[key observations]"
    }
  ]
}
```

Tags: #program-template #[goal] #[experience-level] #[duration]
```

## 🔄 Program Modification Prompt

```xml
<program_modification>
  <current_program>[name and details of current program]</current_program>
  <modification_reason>[why changes are needed]</modification_reason>
  <new_constraints>[any new limitations or preferences]</new_constraints>
  <progress_data>[current performance and adherence data]</progress_data>
  
  <modification_request>
    Please modify the program to address:
    1. [Specific issue #1]
    2. [Specific issue #2]
    3. [Any new goals or priorities]
    
    Maintain the same overall structure but adjust for the new requirements.
  </modification_request>
</program_modification>
```

---
*Last Updated: 2025-07-30*
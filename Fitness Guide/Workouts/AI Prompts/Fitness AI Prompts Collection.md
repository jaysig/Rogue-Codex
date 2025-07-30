# Fitness AI Prompts Collection

Comprehensive collection of copy-paste AI prompts for workout generation, analysis, and optimization using structured data formats.

## 🏋️ Workout Generation Prompts

### Quick Workout Generator
```yaml
# Copy and paste this entire block
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
```json
{
  "program_design_request": {
    "user_profile": {
      "experience": "[months/years of training]",
      "current_fitness": "[1-10 self-assessment]",
      "training_history": "[previous programs or 'none']",
      "injury_history": "[relevant injuries or 'none']",
      "age_range": "[20s/30s/40s/50s/60s+]"
    },
    "program_parameters": {
      "duration": "[4/6/8/12/16] weeks",
      "frequency": "[3/4/5/6] days per week",
      "session_length": "[30/45/60/75/90] minutes",
      "primary_goal": "[strength/hypertrophy/fat_loss/endurance/athletic_performance]",
      "secondary_goals": "[additional objectives]"
    },
    "constraints": {
      "schedule": "[available days and times]",
      "equipment": "[home/gym/minimal/specific equipment list]",
      "preferences": "[liked/disliked exercises or movement patterns]",
      "limitations": "[physical/time/equipment constraints]"
    },
    "output_specifications": {
      "structure": "weekly breakdown with daily workouts",
      "progression": "phase-based periodization with deload weeks",
      "exercises": "specific movements with sets/reps/intensity",
      "alternatives": "exercise substitutions for different scenarios",
      "assessment": "baseline and progress testing protocols",
      "flexibility": "modification options for common issues"
    }
  },
  "request": "Generate a complete training program meeting all specified criteria with detailed implementation guidance."
}
```

## 📊 Analysis and Progress Prompts

### Workout Analysis
```xml
<workout_analysis>
  <session_data>
    <workout_date>[YYYY-MM-DD]</workout_date>
    <planned_workout>[original workout plan]</planned_workout>
    <actual_workout>[what was actually completed]</actual_workout>
    <performance_data>
      <exercises>
        <exercise name="[exercise_name]">
          <sets>[number_completed]</sets>
          <reps>[actual_reps_per_set]</reps>
          <weight>[loads_used]</weight>
          <rpe>[perceived_exertion_1-10]</rpe>
          <form_quality>[1-10_scale]</form_quality>
          <notes>[observations_and_feelings]</notes>
        </exercise>
        <!-- Repeat for each exercise -->
      </exercises>
    </performance_data>
    <session_metrics>
      <duration>[actual_minutes]</duration>
      <energy_pre>[1-10]</energy_pre>
      <energy_post>[1-10]</energy_post>
      <overall_rpe>[session_difficulty_1-10]</overall_rpe>
      <enjoyment>[1-10]</enjoyment>
      <adherence>[percentage_of_plan_completed]</adherence>
    </session_metrics>
  </session_data>
  
  <analysis_request>
    Please analyze this workout session and provide:
    1. Performance assessment compared to planned workout
    2. Strength/endurance progression indicators
    3. Recovery and fatigue analysis
    4. Form and technique observations
    5. Recommendations for next session
    6. Program adherence evaluation
    7. Potential issues or concerns
    8. Positive achievements to celebrate
  </analysis_request>
</workout_analysis>
```

### Weekly Progress Analysis
```yaml
# Weekly Training Analysis Prompt
weekly_analysis:
  training_week: "[week of YYYY-MM-DD]"
  program_context: "[current program name and week number]"
  
  workout_data:
    monday:
      completed: "[yes/no]"
      duration: "[minutes]"
      quality: "[1-10]"
      key_exercises: "[list with performance]"
      notes: "[observations]"
    tuesday:
      completed: "[yes/no]"
      duration: "[minutes]"
      quality: "[1-10]"
      key_exercises: "[list with performance]"
      notes: "[observations]"
    # Continue for all training days
  
  weekly_metrics:
    total_training_time: "[hours:minutes]"
    workouts_completed: "[X of Y planned]"
    average_energy: "[1-10 scale]"
    average_motivation: "[1-10 scale]"
    average_sleep: "[1-10 scale]"
    average_recovery: "[1-10 scale]"
    new_prs: "[list any personal records]"
    missed_sessions: "[reasons if any]"
  
  analysis_request: |
    Please provide a comprehensive weekly analysis including:
    1. Training consistency and adherence patterns
    2. Performance trends and improvements
    3. Recovery and energy patterns
    4. Program progression assessment
    5. Identification of strengths and challenges
    6. Recommendations for upcoming week
    7. Adjustments needed to program or approach
    8. Motivation and confidence observations
```

## 🎯 Goal-Specific Prompts

### Strength-Focused Prompt
```json
{
  "strength_training_request": {
    "strength_goals": {
      "primary_lifts": "[squat/bench/deadlift/overhead_press/other]",
      "current_maxes": {
        "exercise_1": "[current 1RM or estimated]",
        "exercise_2": "[current 1RM or estimated]",
        "exercise_3": "[current 1RM or estimated]"
      },
      "target_improvements": {
        "timeframe": "[weeks/months]",
        "goal_increases": "[specific weight or percentage targets]"
      }
    },
    "programming_preferences": {
      "style": "[powerlifting/olympic/general_strength]",
      "frequency": "[how often per exercise per week]",
      "intensity_preference": "[high/moderate/varied]",
      "volume_tolerance": "[high/moderate/low]"
    },
    "request": "Design a strength-focused program with specific progression protocols, accessory work selection, and peaking strategies for the target lifts."
  }
}
```

### Fat Loss Focused Prompt
```xml
<fat_loss_program>
  <current_status>
    <body_composition>[current weight, estimated body fat %]</body_composition>
    <activity_level>[sedentary/lightly_active/moderately_active/very_active]</activity_level>
    <cardio_preference>[HIIT/steady_state/mixed/minimal]</cardio_preference>
    <strength_training_experience>[beginner/intermediate/advanced]</strength_training_experience>
  </current_status>
  
  <fat_loss_goals>
    <target_timeline>[weeks/months for goal achievement]</target_timeline>
    <weight_loss_target>[pounds/kg to lose]</weight_loss_target>
    <body_composition_goals>[muscle maintenance/gain while losing fat]</body_composition_goals>
    <sustainability_priority>[high/moderate - how sustainable vs aggressive]</sustainability_priority>
  </fat_loss_goals>
  
  <program_request>
    Design a comprehensive fat loss program including:
    1. Optimal training split for fat loss and muscle retention
    2. Cardio integration strategy (type, frequency, intensity)
    3. Resistance training priorities and exercise selection
    4. Progressive overload strategies during caloric deficit
    5. Recovery and stress management considerations
    6. Monitoring and adjustment protocols
    7. Plateau-breaking strategies
  </program_request>
</fat_loss_program>
```

## 🔧 Problem-Solving Prompts

### Program Modification
```yaml
program_modification_request:
  current_situation:
    program: "[name and details of current program]"
    progress_to_date: "[what has been achieved so far]"
    time_in_program: "[weeks/months following current plan]"
    adherence_rate: "[percentage of workouts completed as planned]"
  
  issues_encountered:
    performance: "[stalled lifts, decreased performance, etc.]"
    recovery: "[poor recovery, excessive fatigue, etc.]"
    motivation: "[boredom, lack of enjoyment, etc.]"
    logistics: "[schedule changes, equipment access, etc.]"
    physical: "[minor injuries, limitations, etc.]"
  
  modification_goals:
    primary_need: "[what needs to be fixed most urgently]"
    constraints: "[new limitations or requirements]"
    preferences: "[what should be maintained or emphasized]"
    timeline: "[how long for the modified approach]"
  
  request: |
    Please suggest specific modifications to address the identified issues while:
    1. Maintaining progress toward original goals
    2. Working within new constraints
    3. Addressing the root causes of current problems
    4. Providing clear implementation steps
    5. Including monitoring metrics to track improvement
```

### Exercise Substitution
```json
{
  "exercise_substitution_request": {
    "original_exercise": "[exercise that needs to be replaced]",
    "reason_for_substitution": "[injury/equipment/preference/progression]",
    "constraints": {
      "available_equipment": "[list of accessible equipment]",
      "physical_limitations": "[any restrictions or considerations]",
      "experience_level": "[with alternative movements]",
      "program_context": "[where this fits in current program]"
    },
    "substitution_criteria": {
      "muscle_groups": "[must target same primary muscles]",
      "movement_pattern": "[should maintain similar pattern or can vary]",
      "difficulty_level": "[easier/same/harder than original]",
      "training_goal": "[strength/hypertrophy/endurance/power]"
    },
    "request": "Provide 2-3 exercise alternatives with rationale for each, including any necessary programming adjustments (sets/reps/intensity modifications)."
  }
}
```

## 📈 Assessment and Testing Prompts

### Fitness Assessment Design
```yaml
fitness_assessment_request:
  assessment_purpose: "[baseline/progress_check/program_completion/goal_specific]"
  time_available: "[single_session/multiple_days/ongoing]"
  testing_categories:
    strength: "[yes/no - include strength testing]"
    endurance: "[yes/no - include cardio/muscular endurance]"
    flexibility: "[yes/no - include mobility/flexibility tests]"
    body_composition: "[yes/no - include measurements]"
    functional: "[yes/no - include movement quality tests]"
  
  specific_focus:
    primary_goals: "[what the assessment should primarily evaluate]"
    key_metrics: "[most important measurements to track]"
    comparison_baseline: "[previous assessment data if available]"
  
  practical_constraints:
    equipment: "[available testing equipment]"
    supervision: "[solo/partner/professional supervision]"
    experience: "[familiarity with testing protocols]"
    safety_considerations: "[any limitations or concerns]"
  
  output_request: |
    Design a comprehensive fitness assessment including:
    1. Specific tests for each requested category
    2. Proper warm-up and preparation protocols
    3. Clear instructions for test execution
    4. Scoring/measurement methods
    5. Safety considerations and contraindications
    6. Results interpretation guidelines
    7. How to use results for program planning
```

## 🥗 Nutrition Integration Prompts

### Training Nutrition Optimization
```json
{
  "nutrition_timing_request": {
    "training_schedule": {
      "typical_workout_time": "[morning/afternoon/evening]",
      "workout_duration": "[average minutes per session]",
      "training_frequency": "[days per week]",
      "workout_intensity": "[light/moderate/high average intensity]"
    },
    "current_nutrition": {
      "eating_schedule": "[meal timing and frequency]",
      "pre_workout_habits": "[current pre-workout nutrition]",
      "post_workout_habits": "[current post-workout nutrition]",
      "hydration_patterns": "[typical water intake and timing]"
    },
    "goals": {
      "performance": "[maximize_energy/endurance/strength/recovery]",
      "body_composition": "[maintain/lose_fat/gain_muscle]",
      "convenience": "[high/moderate/low - complexity tolerance]"
    },
    "constraints": {
      "dietary_restrictions": "[allergies/preferences/limitations]",
      "preparation_time": "[available time for meal prep]",
      "budget_considerations": "[cost sensitivity]"
    },
    "request": "Provide specific nutrition timing recommendations including pre-workout, during workout (if applicable), post-workout, and daily meal timing strategies optimized for my training goals and constraints."
  }
}
```

## 🔄 Recovery and Adaptation Prompts

### Recovery Assessment
```xml
<recovery_analysis>
  <recovery_data>
    <sleep_metrics>
      <average_hours>[nightly sleep duration]</average_hours>
      <sleep_quality>[1-10 subjective rating]</sleep_quality>
      <consistency>[regular bedtime/wake time yes/no]</consistency>
    </sleep_metrics>
    
    <stress_indicators>
      <life_stress>[1-10 work/personal stress level]</life_stress>
      <training_stress>[perceived training load 1-10]</training_stress>
      <recovery_time>[how long to feel recovered between sessions]</recovery_time>
    </stress_indicators>
    
    <physical_signs>
      <energy_levels>[daily energy 1-10 average]</energy_levels>
      <soreness_patterns>[typical soreness duration and intensity]</soreness_patterns>
      <motivation>[training motivation 1-10]</motivation>
      <performance_trends>[improving/maintaining/declining]</performance_trends>
    </physical_signs>
  </recovery_data>
  
  <analysis_request>
    Please analyze my recovery status and provide:
    1. Assessment of current recovery adequacy
    2. Identification of potential recovery limiters
    3. Specific recommendations for improvement
    4. Training load adjustments if needed
    5. Recovery strategy priorities
    6. Monitoring metrics to track improvement
    7. Warning signs that indicate overreaching
  </analysis_request>
</recovery_analysis>
```

## 🎪 Specialty Program Prompts

### Athletic Performance
```yaml
athletic_performance_request:
  sport_context:
    primary_sport: "[specific sport or activity]"
    competition_level: "[recreational/club/college/professional]"
    season_timing: "[off_season/pre_season/in_season/post_season]"
    competition_schedule: "[upcoming events and timing]"
  
  performance_goals:
    primary_attributes: "[speed/power/strength/endurance/agility/etc.]"
    sport_specific_skills: "[movements or abilities to enhance]"
    weakness_areas: "[identified limiters to address]"
    injury_prevention: "[common injury patterns in sport]"
  
  training_integration:
    sport_training_load: "[hours per week in sport-specific training]"
    strength_training_experience: "[background in gym training]"
    available_training_time: "[additional hours available for strength/conditioning]"
    facility_access: "[gym/field/track/pool/etc. availability]"
  
  request: |
    Design a sport-specific strength and conditioning program that:
    1. Complements rather than interferes with sport training
    2. Addresses the key physical qualities for performance
    3. Includes injury prevention strategies
    4. Periodizes appropriately for competition schedule
    5. Provides testing benchmarks relevant to sport performance
```

## 📱 Quick Reference Prompts

### Emergency Workout Generator
```json
{
  "quick_workout": {
    "time_available": "[15/20/30/45] minutes",
    "equipment": "[none/minimal/what_you_have]",
    "space": "[small_room/outdoor/gym]",
    "energy": "[low/medium/high]",
    "goal": "[wake_up/stress_relief/strength/cardio/stretch]",
    "request": "Generate an efficient workout for these exact constraints"
  }
}
```

### Form Check Request
```yaml
form_check_request:
  exercise: "[specific exercise name]"
  current_approach: "[how you currently perform it]"
  concerns: "[what feels wrong or difficult]"
  experience: "[how long you've been doing this exercise]"
  request: "Provide detailed form breakdown and common mistake corrections"
```

---
*Last Updated: 2025-07-30*
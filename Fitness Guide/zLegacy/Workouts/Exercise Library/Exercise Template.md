# Exercise Template

Structured template for creating comprehensive exercise documentation with AI-assisted analysis and programming guidance.

## 🤖 Exercise Analysis Prompt

Copy and paste this prompt to generate detailed exercise information:

```json
{
  "exercise_analysis": {
    "exercise_name": "[specific exercise name]",
    "analysis_request": {
      "biomechanics": "detailed movement analysis including joint actions and muscle activation patterns",
      "technique": "step-by-step execution instructions with setup, movement phases, and key coaching cues",
      "programming": "optimal set/rep ranges, intensity guidelines, and frequency recommendations",
      "progressions": "easier and harder variations with clear progression criteria",
      "safety": "contraindications, injury risks, and safety modifications",
      "integration": "how this exercise fits into different program types and training goals"
    },
    "output_format": "comprehensive exercise profile suitable for exercise library documentation",
    "target_audience": "[beginner/intermediate/advanced or 'all levels']"
  }
}
```

## 📋 Exercise Documentation Template

```markdown
# Exercise: [Exercise Name]

## Exercise Classification
- **Category**: [Strength/Cardio/Flexibility/Mobility/Power/Endurance]
- **Movement Pattern**: [Squat/Hinge/Push/Pull/Carry/Lunge/Rotation]
- **Primary Muscles**: [Main muscle groups worked]
- **Secondary Muscles**: [Supporting muscle groups]
- **Equipment**: [Required equipment]
- **Difficulty Level**: [Beginner/Intermediate/Advanced]
- **Exercise Type**: [Compound/Isolation/Unilateral/Bilateral]

## Biomechanical Analysis
```yaml
joint_actions:
  primary_joints:
    - joint: "[hip/knee/ankle/shoulder/elbow/spine]"
      action: "[flexion/extension/abduction/adduction/rotation]"
      range_of_motion: "[degrees or description]"
  
  secondary_joints:
    - joint: "[supporting joint]"
      action: "[stabilization or movement]"
      role: "[stabilizer/synergist/antagonist]"

muscle_activation:
  prime_movers:
    - muscle: "[primary muscle]"
      activation_level: "[high/moderate/low]"
      function: "[concentric/eccentric/isometric]"
  
  stabilizers:
    - muscle: "[stabilizing muscle]"
      role: "[core stability/joint stability/postural]"
```

## Execution Instructions

### Setup Phase
1. **Body Position**: [Starting position and alignment]
2. **Equipment Setup**: [How to arrange/adjust equipment]
3. **Grip/Stance**: [Hand placement, foot position, width]
4. **Core Engagement**: [Breathing and core activation]
5. **Mental Preparation**: [Focus points and intention]

### Movement Execution

#### Concentric Phase (Working/Lifting)
- **Duration**: [Tempo recommendation, e.g., "2 seconds"]
- **Muscle Action**: [Which muscles initiate and drive the movement]
- **Breathing**: [Inhale/exhale timing]
- **Key Focus**: [Primary coaching cue for this phase]
- **Range of Motion**: [Start and end positions]

#### Peak Contraction
- **Hold Duration**: [Any pause at peak, e.g., "brief pause"]
- **Muscle Emphasis**: [Maximum activation point]
- **Position Check**: [Key alignment cues]

#### Eccentric Phase (Lowering/Return)
- **Duration**: [Tempo recommendation, e.g., "3 seconds controlled"]
- **Muscle Action**: [Controlled lengthening]
- **Breathing**: [Inhale/exhale timing]
- **Key Focus**: [Primary coaching cue for this phase]
- **End Position**: [Return to start position details]

### Primary Coaching Cues
1. **Setup Cue**: "[Most important setup reminder]"
2. **Movement Cue**: "[Key movement focus]"
3. **Safety Cue**: "[Critical safety reminder]"
4. **Performance Cue**: "[Optimization tip]"

## Programming Guidelines

### Set and Rep Recommendations
```yaml
training_goals:
  strength:
    sets: "[3-5]"
    reps: "[1-5]"
    intensity: "[85-95% 1RM or RPE 8-9]"
    rest: "[3-5 minutes]"
  
  hypertrophy:
    sets: "[3-4]"
    reps: "[6-12]"
    intensity: "[65-85% 1RM or RPE 6-8]"
    rest: "[2-3 minutes]"
  
  endurance:
    sets: "[2-3]"
    reps: "[12-20+]"
    intensity: "[50-65% 1RM or RPE 5-7]"
    rest: "[1-2 minutes]"
  
  power:
    sets: "[3-5]"
    reps: "[1-5]"
    intensity: "[30-60% 1RM, explosive]"
    rest: "[3-5 minutes]"
```

### Frequency Recommendations
- **Beginner**: [X times per week with reasoning]
- **Intermediate**: [X times per week with reasoning]
- **Advanced**: [X times per week with reasoning]
- **Recovery Considerations**: [Minimum rest between sessions]

## Progression and Regression Options

### Regressions (Easier Versions)
```json
{
  "level_1_easiest": {
    "exercise": "[simplest version]",
    "modifications": "[assistance/range/load reductions]",
    "target_audience": "[complete beginners or limitations]"
  },
  "level_2_building": {
    "exercise": "[intermediate step]",
    "modifications": "[partial assistance or range]",
    "target_audience": "[building toward full exercise]"
  },
  "level_3_preparation": {
    "exercise": "[near full version]",
    "modifications": "[minimal assistance]",
    "target_audience": "[almost ready for full exercise]"
  }
}
```

### Progressions (Harder Versions)
```json
{
  "level_1_advanced": {
    "exercise": "[slightly harder version]",
    "modifications": "[increased range/instability/load]",
    "target_audience": "[mastered basic version]"
  },
  "level_2_expert": {
    "exercise": "[significantly harder]",
    "modifications": "[major complexity/load increase]",
    "target_audience": "[advanced practitioners]"
  },
  "level_3_elite": {
    "exercise": "[elite level variation]",
    "modifications": "[maximum complexity/load]",
    "target_audience": "[elite athletes/advanced enthusiasts]"
  }
}
```

## Safety Considerations

### Contraindications
- **Absolute**: [Conditions where exercise should never be performed]
- **Relative**: [Conditions requiring modification or caution]
- **Temporary**: [Situations requiring temporary avoidance]

### Injury Risk Factors
```yaml
risk_assessment:
  high_risk_areas:
    - body_region: "[vulnerable area, e.g., lower back]"
      risk_factors: "[what increases risk]"
      prevention: "[how to minimize risk]"
  
  common_mistakes:
    - mistake: "[technical error]"
      consequence: "[potential injury or reduced effectiveness]"
      correction: "[how to fix]"
```

### Warning Signs to Stop
- **Pain**: [Types of pain that require stopping]
- **Form Breakdown**: [Technical failures that indicate stop]
- **Excessive Fatigue**: [Fatigue levels that compromise safety]
- **Equipment Issues**: [Equipment problems requiring cessation]

### Modifications for Limitations
```yaml
common_limitations:
  mobility_restrictions:
    limitation: "[specific mobility issue]"
    modification: "[exercise adjustment]"
    progression: "[how to improve over time]"
  
  strength_deficits:
    limitation: "[strength weakness]"
    modification: "[assistance or load reduction]"
    progression: "[building strength approach]"
  
  injury_history:
    limitation: "[previous injury concern]"
    modification: "[protective adjustment]"
    monitoring: "[what to watch for]"
```

## Integration and Programming

### Exercise Pairing
```yaml
pairs_well_with:
  supersets:
    - exercise: "[complementary exercise]"
      rationale: "[why they work well together]"
      rest_protocol: "[how to structure rest]"
  
  circuits:
    - exercises: "[list of circuit partners]"
      rationale: "[circuit logic]"
      timing: "[work/rest intervals]"
```

### Avoid Pairing With
- **Exercise**: [Conflicting exercise]
  - **Reason**: [Why they don't work well together]
  - **Alternative**: [Better pairing option]

### Warm-Up Requirements
```yaml
preparation_needs:
  mobility:
    - area: "[body region needing mobility]"
      duration: "[time needed]"
      exercises: "[specific prep movements]"
  
  activation:
    - muscles: "[muscles needing activation]"
      exercises: "[activation movements]"
      intensity: "[light/moderate activation level]"
  
  movement_prep:
    - pattern: "[movement pattern to rehearse]"
      progressions: "[how to build up to working sets]"
```

## Progress Tracking

### Primary Metrics
- **Strength**: [Weight/load progression tracking]
- **Volume**: [Sets × reps progression]
- **Endurance**: [Time or rep endurance improvements]
- **Technical**: [Form quality improvements]

### Secondary Metrics
- **Range of Motion**: [Flexibility improvements]
- **Speed**: [Movement velocity changes]
- **Stability**: [Balance and control improvements]
- **Confidence**: [Comfort and mastery level]

### Personal Record Categories
```json
{
  "pr_types": {
    "absolute_strength": "[1RM or maximum load]",
    "rep_maxes": "[3RM, 5RM, 10RM benchmarks]",
    "volume_prs": "[highest volume in single session]",
    "endurance_prs": "[maximum reps at specific weight]",
    "technical_prs": "[form milestones achieved]"
  }
}
```

## Exercise Data Template
```json
{
  "exercise_session": {
    "date": "[YYYY-MM-DD]",
    "exercise": "[exercise name]",
    "sets_completed": [
      {
        "set_number": 1,
        "weight": "[load used]",
        "reps": "[reps completed]",
        "rpe": "[1-10 scale]",
        "rest": "[minutes rested]",
        "form_quality": "[1-10 scale]",
        "notes": "[observations]"
      }
    ],
    "total_volume": "[weight × reps × sets]",
    "session_rpe": "[overall difficulty 1-10]",
    "progression_made": "[yes/no/maintained]",
    "next_session_plan": "[adjustments for next time]"
  }
}
```

## Related Exercises and Links
- **Similar Movement Pattern**: [[Exercise 1]] | [[Exercise 2]]
- **Muscle Group Alternatives**: [[Alternative 1]] | [[Alternative 2]]
- **Progression Chain**: [[Easier Version]] → **This Exercise** → [[Harder Version]]
- **Program Integration**: [[Program 1]] | [[Program 2]] | [[Program 3]]

## Tags
#exercise #[category] #[movement-pattern] #[primary-muscle] #[equipment] #[difficulty-level]

---
*Last Updated: 2025-07-30*
```

## 🔄 Exercise Comparison Prompt

```xml
<exercise_comparison>
  <exercises_to_compare>
    <exercise_1>[first exercise name]</exercise_1>
    <exercise_2>[second exercise name]</exercise_2>
    <exercise_3>[third exercise name - optional]</exercise_3>
  </exercises_to_compare>
  
  <comparison_criteria>
    <muscle_activation>Compare which muscles are worked and activation levels</muscle_activation>
    <difficulty>Rank by technical difficulty and learning curve</difficulty>
    <equipment>Compare equipment requirements and accessibility</equipment>
    <injury_risk>Assess relative safety and injury risk factors</injury_risk>
    <effectiveness>Compare effectiveness for different training goals</effectiveness>
    <versatility>How well each exercise fits different programs</versatility>
  </comparison_criteria>
  
  <output_request>
    Please provide a detailed comparison including:
    1. Pros and cons of each exercise
    2. Best use cases for each
    3. Who should choose which exercise
    4. How they can be used together in a program
    5. Progression pathway between them if applicable
  </output_request>
</exercise_comparison>
```

---
*Last Updated: 2025-07-30*
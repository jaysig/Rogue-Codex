# Next Workout Planning

AI-driven system for designing optimal workouts based on recent performance, recovery status, and program progression goals.

## Current Workout Planning Status

### Next Session Overview
| Element | Details | Status | Last Updated |
|---------|---------|---------|-------------|
| Next Workout Date | [Date] | [Planned/Confirmed] | [When planned] |
| Workout Type | [Strength/Cardio/Mixed] | [Ready/Needs Planning] | [When designed] |
| Primary Focus | [Main objective] | [Confirmed/Under Review] | [When set] |
| Equipment Needed | [Equipment list] | [Available/Need to Secure] | [When checked] |
| Estimated Duration | [Minutes] | [Planned] | [When estimated] |

### Planning Context
- **Days since last similar workout**: [Number]
- **Current recovery status**: [Fresh/Moderate fatigue/High fatigue]
- **Recent performance trend**: [Improving/Stable/Declining]
- **Program phase**: [Current phase and week]
- **Upcoming schedule considerations**: [Any constraints]

## Workout Planning Framework

### Multi-Step Planning Process

#### Step 1: Context Assessment
| Assessment Area | Current Status | Impact on Next Workout | Planning Weight |
|----------------|----------------|----------------------|-----------------|
| Recovery Level | [Fresh/Fatigued/Overreached] | [How it affects intensity/volume] | [High/Medium/Low] |
| Recent Performance | [Strong/Average/Weak] | [Confidence/progression implications] | [High/Medium/Low] |
| Schedule Constraints | [Time/equipment/energy available] | [Workout modifications needed] | [High/Medium/Low] |
| Program Progression | [On track/ahead/behind] | [Advancement vs consolidation] | [High/Medium/Low] |
| Motivation Level | [High/Medium/Low] | [Workout complexity/challenge level] | [Medium/Low] |

#### Step 2: Workout Architecture Design
| Component | Options | Selection Criteria | Chosen Option |
|-----------|---------|-------------------|---------------|
| Primary Movement Pattern | [Squat/Hinge/Push/Pull/Carry] | [Program needs, recovery status] | [Selected] |
| Training Emphasis | [Strength/Power/Endurance/Skill] | [Goals, energy level, progression] | [Selected] |
| Volume Load | [High/Moderate/Low] | [Recovery, recent training, goals] | [Selected] |
| Intensity Range | [Max effort/Moderate/Light] | [Readiness, program phase] | [Selected] |
| Session Duration | [Long/Standard/Short] | [Time available, energy level] | [Selected] |

## AI Workout Planning Prompts

### XML Prompt for Complete Workout Design
```xml
<next_workout_planning>
<instructions>
Design my next workout based on comprehensive analysis of recent performance, current recovery status, and program objectives. Create a complete, detailed workout plan with specific exercises, sets, reps, and coaching cues.

Planning date: [Today's date]
Planned workout date: [When workout will happen]
Available time: [Duration available]
Equipment access: [Available equipment]
</instructions>

<current_context>
<program_status>
Current program: [Program name and phase]
Program week: [Week X of Y]
Recent program adherence: [Completion rate and quality]
Program goals: [Primary objectives]
Next program milestone: [Upcoming target or transition]
</program_status>

<recent_performance_data>
Last workout: [Date and brief summary]
- Type: [Strength/cardio/mixed]
- Quality: [1-10 rating]
- Completion: [Full/partial completion]
- Key achievements: [PRs, breakthroughs, good performances]
- Challenges: [Struggles, form issues, energy problems]

Last 3 workouts trend:
- Consistency: [Pattern of completion/quality]
- Performance: [Improving/stable/declining trend]
- Recovery: [How well recovered between sessions]
- Motivation: [Energy and enthusiasm levels]
</recent_performance_data>

<current_readiness_assessment>
Recovery indicators:
- Sleep quality last night: [1-10]
- Current energy level: [1-10]
- Muscle soreness: [Location and severity]
- Stress level: [1-10]
- Motivation for training: [1-10]

Physical readiness:
- Any injuries or limitations: [Current issues]
- Movement quality: [Any restrictions or concerns]
- Time since last similar workout: [Days]
- Overall body feeling: [Fresh/moderate fatigue/high fatigue]
</current_readiness_assessment>

<contextual_factors>
Schedule and logistics:
- Available training time: [Realistic duration]
- Equipment access: [What's available today]
- Training environment: [Home/gym/outdoor/etc.]
- Post-workout obligations: [Schedule considerations]

Life context:
- Work/life stress level: [Impact on training capacity]
- Recent sleep patterns: [How sleep has been]
- Nutrition status: [When last ate, hydration]
- Weather/seasonal factors: [If relevant]
</contextual_factors>
</current_context>

<workout_design_requirements>
<primary_objectives>
1. Program adherence: [Maintain progression according to program]
2. Recovery balance: [Match intensity to current readiness]
3. Skill development: [Continue technique improvement]
4. Motivation maintenance: [Keep engagement high]
5. Injury prevention: [Avoid overreach, maintain movement quality]
</primary_objectives>

<specific_focus_areas>
Based on recent analysis, prioritize:
1. [Primary focus area from recent coaching analysis]
2. [Secondary focus area]
3. [Technical element needing attention]
4. [Weakness or imbalance to address]
</specific_focus_areas>

<progression_considerations>
Advancement decisions:
- Which exercises are ready for load progression?
- Where should volume be increased?
- What technical skills need more practice?
- Which areas need consolidation vs progression?
- Are there any plateau-breaking strategies needed?
</progression_considerations>
</workout_design_requirements>

<output_specifications>
<workout_structure>
Design complete workout including:

1. Dynamic warm-up (5-10 minutes)
   - Specific movements to prepare for today's work
   - Any corrective exercises based on current needs
   - Movement quality prep for main exercises

2. Main workout block
   - 3-5 primary exercises with full prescription
   - Sets, reps, weight/intensity recommendations
   - Rest periods between sets
   - RPE targets for each exercise
   - Form cues and technique focus points

3. Accessory/supplemental work
   - 2-3 supporting exercises
   - Volume and intensity appropriate for current state
   - Address weaknesses or imbalances

4. Cool-down and recovery
   - Stretching or mobility work
   - Recovery techniques if appropriate
   - Mental/emotional decompression
</workout_structure>

<specific_details>
For each exercise provide:
- Exercise name and variation
- Sets × reps scheme
- Load recommendation (weight, intensity, or progression)
- Target RPE (rate of perceived exertion)
- Rest periods between sets
- Key coaching cues for form
- Progression/regression options if needed
- Integration with overall session flow
</specific_details>

<coaching_guidance>
Include specific guidance on:
1. Pre-workout preparation and mindset
2. In-workout pacing and energy management
3. When to push vs when to pull back
4. Signs to watch for during session
5. Post-workout assessment priorities
6. Recovery recommendations for after session
</coaching_guidance>
</output_specifications>
</next_workout_planning>
```

### YAML Prompt for Quick Workout Adjustment
```yaml
workout_adjustment_planning:
  task: "Modify planned workout based on current readiness and constraints"
  
  original_plan:
    planned_workout: "[Originally designed workout]"
    planned_duration: "[Original time allocation]"
    planned_intensity: "[Original intensity level]"
    planned_focus: "[Primary objectives]"
    
  current_situation:
    available_time: "[Actual time available now]"
    energy_level: "[Current 1-10 rating]"
    physical_readiness: "[Any soreness, stiffness, fatigue]"
    equipment_changes: "[Different from planned]"
    motivation_level: "[Current drive to train]"
    
  constraint_factors:
    time_limitation: "[How much time actually available]"
    energy_limitation: "[Lower/same/higher energy than expected]"
    equipment_limitation: "[Missing equipment or different setup]"
    physical_limitation: "[Any new soreness, stiffness, or issues]"
    environmental_factors: "[Space, noise, privacy, weather concerns]"
    
  adjustment_priorities:
    maintain_program_integrity: "[Keep core program elements if possible]"
    match_current_capacity: "[Adjust to realistic current state]"
    preserve_technique_focus: "[Don't sacrifice form for completion]"
    ensure_positive_experience: "[End feeling accomplished, not defeated]"
    
  modification_options:
    time_adjustments:
      - "Reduce warm-up to essentials only"
      - "Focus on primary movements, reduce accessories"
      - "Shorter rest periods if appropriate for goals"
      - "Superset compatible exercises to save time"
      
    intensity_adjustments:
      - "Reduce load if energy/readiness is low"
      - "Focus on form and movement quality"
      - "Use higher reps at lower intensity"
      - "Emphasize time under tension vs max load"
      
    exercise_substitutions:
      - "Replace complex movements with simpler versions"
      - "Substitute based on available equipment"
      - "Use unilateral work if space is limited"
      - "Bodyweight alternatives for missing equipment"
      
    volume_modifications:
      - "Reduce total sets while maintaining movement patterns"
      - "Focus on quality reps vs total volume"
      - "Prioritize program-critical exercises"
      - "Save non-essential work for better days"
      
  output_requirements:
    modified_workout: "Complete revised workout plan"
    rationale: "Explain why changes were made"
    program_impact: "How this affects overall program progression"
    make_up_plan: "What to prioritize in next session if work was reduced"
    success_criteria: "How to judge if modified workout was effective"
    
  coaching_notes:
    mindset_guidance: "How to approach the modified session mentally"
    effort_calibration: "What effort level to target given modifications"
    progress_recognition: "How to view this workout in context of goals"
    future_planning: "What this session tells us about future planning"
```

## Workout Planning Templates

### Strength-Focused Session Template
| Component | Duration | Content | Progression Logic |
|-----------|----------|---------|------------------|
| Dynamic Warm-up | 8-10 min | [Movement prep specific to main lifts] | [Based on mobility needs] |
| Primary Compound | 15-20 min | [Main lift: sets×reps@intensity] | [Progressive overload application] |
| Secondary Compound | 10-15 min | [Supporting movement] | [Volume/intensity balance] |
| Accessory Work | 10-15 min | [2-3 isolation/corrective exercises] | [Address weaknesses/imbalances] |
| Cool-down | 5-8 min | [Stretching/mobility for worked areas] | [Recovery preparation] |

### Cardio-Focused Session Template
| Component | Duration | Content | Intensity Management |
|-----------|----------|---------|---------------------|
| Warm-up | 5-8 min | [Gradual intensity increase] | [Prepare cardiovascular system] |
| Main Cardio Block | 20-40 min | [Primary cardio work] | [Target heart rate zones] |
| Strength Circuit | 8-12 min | [Bodyweight/light resistance] | [Complement, don't compete with cardio] |
| Cool-down | 5-10 min | [Gradual intensity decrease] | [Promote recovery] |

## Progressive Planning Logic

### Loading Progression Decision Tree
```yaml
progression_decision_framework:
  
  primary_lift_progression:
    conditions_check:
      form_quality: "[Excellent/Good/Needs work]"
      rpe_last_session: "[Target RPE achieved/exceeded/under]"
      recovery_status: "[Full recovery/partial/overreached]"
      
    progression_rules:
      if_all_green_lights:
        action: "Increase load according to program progression"
        amount: "[Program-specified increment]"
        
      if_form_quality_excellent_and_rpe_under_target:
        action: "Consider larger load increase or volume increase"
        options: ["Increase weight beyond normal", "Add extra set", "Increase reps"]
        
      if_form_breakdown_or_rpe_too_high:
        action: "Maintain or reduce load, focus on form"
        approach: ["Same weight with better execution", "Slight deload", "Technique focus"]
        
      if_recovery_compromised:
        action: "Reduce intensity, maintain movement patterns"
        modification: ["Lower percentage work", "Volume reduction", "Technique practice"]
        
  volume_progression:
    weekly_volume_check:
      completion_rate: "[Percentage of planned volume completed]"
      quality_scores: "[Average session quality this week]"
      recovery_between_sessions: "[Full/Partial/Poor recovery]"
      
    volume_adjustments:
      if_completing_all_with_high_quality:
        consideration: "Ready for volume increase next week"
        options: ["Add extra set to main lifts", "Add accessory exercise", "Increase training frequency"]
        
      if_struggling_to_complete:
        action: "Reduce volume to sustainable level"
        approach: ["Remove least important exercises", "Reduce sets on accessories", "Focus on program essentials"]
        
  skill_development_focus:
    technique_assessment:
      movement_quality: "[Improving/Stable/Declining]"
      consistency: "[Reliable technique/Variable/Inconsistent]"
      complexity_readiness: "[Ready for advancement/Need consolidation]"
      
    skill_progression:
      if_technique_solid:
        advance_to: "[Next exercise progression or increased complexity]"
        
      if_technique_variable:
        focus_on: "[Consistency at current level]"
        tools: ["More practice volume", "Tempo work", "Partial range focus"]
        
      if_technique_declining:
        regress_to: "[Simpler variation or reduced load]"
        priority: "Rebuild movement quality foundation"
```

## Session Planning Workflows

### Daily Planning Checklist
- [ ] Review yesterday's workout analysis and coaching notes
- [ ] Assess current physical and mental readiness
- [ ] Check program progression requirements
- [ ] Confirm time and equipment availability
- [ ] Select appropriate workout template
- [ ] Customize exercises and loading based on context
- [ ] Set session objectives and success criteria
- [ ] Plan post-workout analysis approach

### Weekly Planning Integration
| Day | Program Requirement | Readiness Assessment | Planned Focus | Backup Plan |
|-----|-------------------|---------------------|---------------|-------------|
| Monday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Tuesday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Wednesday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Thursday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Friday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Saturday | [Program calls for] | [Expected readiness] | [Primary objective] | [If energy/time limited] |
| Sunday | [Rest/Active recovery] | [Recovery focus] | [Restoration] | [Modified activity] |

## Workout Success Criteria

### Session Evaluation Framework
| Success Level | Criteria | Indicators | Next Session Impact |
|---------------|----------|------------|-------------------|
| Excellent | [Exceeded expectations] | [Specific achievements] | [Ready for progression] |
| Good | [Met objectives] | [Solid performance markers] | [Continue planned progression] |
| Adequate | [Completed core work] | [Minimum standards met] | [Maintain current level] |
| Poor | [Significant struggles] | [Warning signs present] | [Need modification/recovery] |

### Progress Tracking Integration
- **Immediate**: Log workout completion and quality assessment
- **Daily**: Update analysis in [[Workout Analysis and Feedback]]
- **Weekly**: Aggregate data for [[Weekly Coaching Review]]  
- **Monthly**: Feed into [[Coaching Plan Overview]] for long-term tracking

## Integration Links
- [[Workout Analysis and Feedback]] - Performance data input
- [[Coaching Plan Overview]] - Long-term program alignment
- [[Weekly Coaching Review]] - Comprehensive progress assessment
- [[Baseline Stats]] - Physical readiness indicators
- [[Personal Records]] - Achievement opportunities identification

Tags: #workout-planning #ai-coaching #program-progression #session-design

---
*Last Updated: 2025-07-30*
# Baseline Assessment

Initial fitness evaluation and periodic reassessments to track overall fitness development and identify areas for focused improvement.

## Current Fitness Level Summary

### Overall Assessment Status
| Assessment Date | Overall Level | Strength Level | Cardio Level | Flexibility Level | Next Assessment |
|----------------|---------------|----------------|--------------|------------------|-----------------|
| [Latest date] | [Beginner/Intermediate/Advanced] | [Level] | [Level] | [Level] | [Date] |

### Goal Progress Overview
| Primary Goal | Target | Current Status | Timeline | Progress % | On Track? |
|-------------|--------|----------------|----------|------------|-----------|
| [Goal 1] | [Target] | [Current] | [Date] | [%] | Y/N |
| [Goal 2] | [Target] | [Current] | [Date] | [%] | Y/N |
| [Goal 3] | [Target] | [Current] | [Date] | [%] | Y/N |

## Initial Baseline Assessment

### Cardiovascular Fitness Baseline
| Test | Initial Score | Date | Classification | Target Score | Current Score |
|------|---------------|------|----------------|--------------|---------------|
| Resting Heart Rate | [BPM] | [Date] | [Excellent/Good/Fair/Poor] | [Target] | [Current] |
| 3-Min Step Test | [Recovery HR] | [Date] | [Classification] | [Target] | [Current] |
| 1-Mile Walk/Run | [Time] | [Date] | [Classification] | [Target] | [Current] |
| VO2 Max Estimate | [ml/kg/min] | [Date] | [Classification] | [Target] | [Current] |

### Strength Fitness Baseline
| Exercise | Initial Score | Date | Classification | Target Score | Current Score |
|----------|---------------|------|----------------|--------------|---------------|
| Push-ups (max) | [Reps] | [Date] | [Level] | [Target] | [Current] |
| Pull-ups/Chin-ups | [Reps] | [Date] | [Level] | [Target] | [Current] |
| Plank Hold | [Seconds] | [Date] | [Level] | [Target] | [Current] |
| Wall Sit | [Seconds] | [Date] | [Level] | [Target] | [Current] |
| Bodyweight Squats | [Reps] | [Date] | [Level] | [Target] | [Current] |

### Flexibility & Mobility Baseline
| Assessment | Initial Score | Date | Classification | Target Score | Current Score |
|------------|---------------|------|----------------|--------------|---------------|
| Sit-and-Reach | [Distance] | [Date] | [Level] | [Target] | [Current] |
| Overhead Reach | [Pass/Fail] | [Date] | [Assessment] | [Target] | [Current] |
| Hip Flexor Length | [Assessment] | [Date] | [Level] | [Target] | [Current] |
| Ankle Mobility | [Degrees/Distance] | [Date] | [Level] | [Target] | [Current] |
| Shoulder Mobility | [Assessment] | [Date] | [Level] | [Target] | [Current] |

## LLM-Assisted Assessment Prompts

### XML Prompt for Complete Baseline Assessment
```xml
<baseline_fitness_assessment>
<instructions>
I need to complete a comprehensive baseline fitness assessment. Please guide me through each test systematically, providing proper instructions for accurate and safe execution. Help me classify my results and set appropriate goals.

Assessment date: [Today's date]
Current fitness background: [Brief description of activity level]
Equipment available: [List available equipment]
Any physical limitations: [Note any injuries or restrictions]
Primary fitness goals: [What I want to achieve]
</instructions>

<cardiovascular_assessment>
<resting_heart_rate>
Guide me to properly measure my resting heart rate:
- Best time to measure (upon waking, before getting up)
- Proper technique (pulse location, counting method)
- Multiple measurements for accuracy
- Classification of the result
</resting_heart_rate>

<step_test>
Walk me through the 3-minute step test:
- Equipment needed (12-inch step or sturdy platform)
- Proper stepping technique and rhythm
- Safety considerations
- How to measure recovery heart rate
- Interpretation of results
</step_test>

<cardio_endurance>
Help me choose and execute an appropriate cardio test:
- 1-mile walk test (if beginner/moderate fitness)
- 1-mile run test (if higher fitness level)
- Alternative tests if space/weather limited
- Proper warm-up and safety protocols
- How to pace myself for accurate results
</cardio_endurance>
</cardiovascular_assessment>

<strength_assessment>
<bodyweight_strength>
Guide me through each strength test with proper form:

1. Push-up test:
   - Proper form demonstration
   - Modified vs standard options
   - Counting protocol (continuous reps until failure)
   - Rest periods between attempts

2. Pull-up/Chin-up test:
   - Equipment options (bar, door frame, assisted)
   - Proper grip and form
   - Modified options if unable to perform standard
   - Accurate counting method

3. Plank hold test:
   - Proper plank position setup
   - Form checkpoints during hold
   - When to stop timing (form breakdown)
   - Safety considerations

4. Wall sit test:
   - Proper positioning against wall
   - Correct leg angle and stance
   - Form maintenance cues
   - Timing protocol

5. Bodyweight squat test:
   - Proper squat form demonstration
   - Depth and range of motion requirements
   - Counting protocol for maximum reps
   - When to stop (form breakdown)
</bodyweight_strength>
</strength_assessment>

<flexibility_assessment>
<mobility_tests>
Guide me through flexibility assessments:

1. Sit-and-reach test:
   - Proper setup and positioning
   - Movement execution
   - Measurement technique
   - Safety considerations (no bouncing)

2. Overhead reach test:
   - Positioning and technique
   - Assessment criteria
   - Modifications if shoulder issues exist

3. Hip flexor assessment:
   - Positioning for accurate assessment
   - What to look for and measure
   - Comparison between sides

4. Ankle mobility test:
   - Wall test setup and execution
   - Measurement technique
   - Functional implications

5. Shoulder mobility screen:
   - Behind-back reach test
   - Assessment criteria and measurement
   - Safety considerations
</mobility_tests>
</flexibility_assessment>

<results_analysis>
After completing all tests, help me:
1. Classify each result (excellent/good/fair/poor or beginner/intermediate/advanced)
2. Identify my strongest areas
3. Identify areas needing the most improvement
4. Set realistic short-term and long-term goals for each category
5. Recommend appropriate starting program types
6. Schedule next assessment date (typically 8-12 weeks)
</results_analysis>

<data_formatting>
Format all results as markdown table entries I can copy into my tracking tables, including:
- Date of assessment
- All test results with units
- Classifications for each test
- Comparison to age/gender norms if available
- Recommended focus areas
- Suggested goal targets for next assessment
</data_formatting>
</baseline_fitness_assessment>
```

### JSON Prompt for Quarterly Reassessment
```json
{
  "task": "quarterly_fitness_reassessment",
  "instructions": "Guide me through a comprehensive fitness reassessment and analyze progress since baseline",
  "assessment_info": {
    "current_date": "[Today's date]",
    "baseline_date": "[Original assessment date]", 
    "months_since_baseline": "[Number of months]",
    "current_program": "[Program I've been following]",
    "baseline_data": "[Provide baseline results for comparison]"
  },
  "reassessment_protocol": {
    "cardiovascular_retests": [
      {
        "test": "resting_heart_rate",
        "baseline": "[Previous result]",
        "measurement_protocol": "Same conditions as baseline - upon waking, multiple measurements",
        "expected_improvement": "Lower RHR indicates improved fitness"
      },
      {
        "test": "step_test_recovery",
        "baseline": "[Previous result]", 
        "measurement_protocol": "Same 3-minute step test, measure 1-minute recovery HR",
        "expected_improvement": "Faster heart rate recovery"
      },
      {
        "test": "cardio_endurance",
        "baseline": "[Previous time/distance]",
        "measurement_protocol": "Same test format as baseline",
        "expected_improvement": "Faster time or greater distance"
      }
    ],
    "strength_retests": [
      {
        "test": "push_ups",
        "baseline": "[Previous max reps]",
        "measurement_protocol": "Maximum consecutive reps with proper form",
        "expected_improvement": "Increased repetitions"
      },
      {
        "test": "plank_hold", 
        "baseline": "[Previous time]",
        "measurement_protocol": "Maximum hold time with proper form",
        "expected_improvement": "Longer hold duration"
      },
      {
        "test": "pull_ups",
        "baseline": "[Previous reps]",
        "measurement_protocol": "Maximum consecutive reps",
        "expected_improvement": "Increased repetitions or progression from assisted"
      },
      {
        "test": "wall_sit",
        "baseline": "[Previous time]", 
        "measurement_protocol": "Maximum hold time in proper position",
        "expected_improvement": "Longer duration"
      },
      {
        "test": "bodyweight_squats",
        "baseline": "[Previous max reps]",
        "measurement_protocol": "Maximum consecutive reps with full range of motion",
        "expected_improvement": "Increased repetitions"
      }
    ],
    "flexibility_retests": [
      {
        "test": "sit_and_reach",
        "baseline": "[Previous measurement]",
        "measurement_protocol": "Same setup and measurement technique",
        "expected_improvement": "Greater reach distance"
      },
      {
        "test": "overhead_reach",
        "baseline": "[Previous assessment]",
        "measurement_protocol": "Behind back clasp test",
        "expected_improvement": "Improved range or ability to clasp"
      },
      {
        "test": "hip_mobility",
        "baseline": "[Previous assessment]",
        "measurement_protocol": "Same assessment technique",
        "expected_improvement": "Greater range of motion"
      },
      {
        "test": "ankle_mobility",
        "baseline": "[Previous measurement]",
        "measurement_protocol": "Wall test with same measurement",
        "expected_improvement": "Greater dorsiflexion range"
      }
    ]
  },
  "progress_analysis": {
    "improvement_calculations": "Calculate % improvement for each test",
    "category_assessment": "Overall improvement in cardio, strength, flexibility",
    "goal_progress_check": "Compare current results to goals set at baseline",
    "program_effectiveness": "Analyze which areas improved most/least with current program"
  },
  "output_format": {
    "progress_summary_table": {
      "columns": ["Test", "Baseline", "Current", "Improvement", "% Change", "Goal Progress"],
      "include_all_tests": true
    },
    "category_analysis": {
      "strongest_improvements": "Top 3 areas of progress",
      "areas_needing_focus": "Areas with minimal or no improvement", 
      "unexpected_results": "Surprising improvements or disappointments"
    },
    "recommendations": {
      "program_adjustments": "Modifications needed based on results",
      "new_focus_areas": "Where to concentrate efforts next quarter",
      "goal_updates": "Revised targets based on current progress"
    }
  },
  "next_steps": {
    "new_goal_setting": "Updated targets for next assessment",
    "program_selection": "Recommended program changes",
    "assessment_schedule": "Next reassessment date (3 months)"
  }
}
```

## Assessment History & Progress Tracking

### Quarterly Assessment Results
| Quarter | Overall Level | Cardio Score | Strength Score | Flexibility Score | Primary Achievement | Focus Area |
|---------|---------------|--------------|----------------|-------------------|-------------------|------------|
| Baseline | [Level] | [Score] | [Score] | [Score] | [Initial assessment] | [Starting focus] |
| Q1 | [Level] | [Score] | [Score] | [Score] | [Key improvement] | [Next focus] |
| Q2 | [Level] | [Score] | [Score] | [Score] | [Key improvement] | [Next focus] |
| Q3 | [Level] | [Score] | [Score] | [Score] | [Key improvement] | [Next focus] |
| Q4 | [Level] | [Score] | [Score] | [Score] | [Key improvement] | [Next focus] |

### Year-Over-Year Comparison
| Assessment | Year 1 | Year 2 | Year 3 | Improvement Trajectory |
|------------|---------|---------|---------|----------------------|
| Overall Fitness Level | [Level] | [Level] | [Level] | [Trend analysis] |
| Cardiovascular Capacity | [Score] | [Score] | [Score] | [% improvement] |
| Strength Metrics | [Score] | [Score] | [Score] | [% improvement] |
| Flexibility/Mobility | [Score] | [Score] | [Score] | [% improvement] |
| Body Composition | [Score] | [Score] | [Score] | [Changes noted] |

## Functional Movement Screen

### Movement Quality Assessment
| Movement Pattern | Baseline Score | Current Score | Limitations Noted | Corrective Focus |
|------------------|----------------|---------------|-------------------|------------------|
| Deep Squat | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| Hurdle Step | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| In-line Lunge | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| Shoulder Mobility | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| Active Straight Leg | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| Trunk Stability | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |
| Rotary Stability | [1-3 scale] | [1-3 scale] | [Issues identified] | [Corrective exercises] |

### Movement Quality Goals
| Target Date | Movement Focus | Current Score | Target Score | Action Plan | Progress Check |
|------------|----------------|---------------|--------------|-------------|----------------|
| [Date] | [Movement pattern] | [Current] | [Target] | [Specific exercises] | [Check date] |
| [Date] | [Movement pattern] | [Current] | [Target] | [Specific exercises] | [Check date] |
| [Date] | [Movement pattern] | [Current] | [Target] | [Specific exercises] | [Check date] |

## Assessment Scheduling & Reminders

### Assessment Calendar
| Assessment Type | Frequency | Last Completed | Next Due | Preparation Needed |
|----------------|-----------|----------------|----------|--------------------|
| Full Baseline | Annual | [Date] | [Date] | [Prep checklist] |
| Quarterly Progress | Every 3 months | [Date] | [Date] | [Prep checklist] |
| Monthly Check-in | Monthly | [Date] | [Date] | [Key metrics only] |
| Body Measurements | Bi-weekly | [Date] | [Date] | [Equipment check] |

### Pre-Assessment Checklist
- [ ] Schedule assessment during optimal conditions (rested, fed appropriately)
- [ ] Gather necessary equipment (measuring tape, stopwatch, step platform)
- [ ] Review previous assessment results for comparison
- [ ] Prepare assessment area (safe space, proper lighting)
- [ ] Plan adequate time (60-90 minutes for full assessment)
- [ ] Have recording materials ready (this document, pen, phone for timing)

## Integration Links
- [[Body Measurements Tracker]] - Physical metrics tracking
- [[Health Vitals Tracker]] - Daily health monitoring  
- [[Coach Analysis]] - AI assessment evaluation
- [[Personal Records]] - Achievement tracking

Tags: #baseline #assessment #fitness-testing #progress-tracking #goals

---
*Last Updated: 2025-07-30*
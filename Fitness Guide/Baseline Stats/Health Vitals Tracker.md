# Health Vitals Tracker

Daily and weekly tracking system for health indicators with trend analysis and LLM-assisted data collection for optimal wellness monitoring.

## Current Health Status (Latest Readings)

### Quick Reference Dashboard
| Vital | Current | Date | 7-Day Avg | Trend | Target Range |
|-------|---------|------|-----------|-------|--------------|
| Resting HR | [Latest BPM] | [Date] | [Avg] | ↑/↓/→ | 60-100 BPM |
| Sleep Hours | [Latest] | [Date] | [Avg] | ↑/↓/→ | 7-9 hours |
| Sleep Quality | [Latest /10] | [Date] | [Avg] | ↑/↓/→ | 7+ /10 |
| Energy Level | [Latest /10] | [Date] | [Avg] | ↑/↓/→ | 7+ /10 |
| Stress Level | [Latest /10] | [Date] | [Avg] | ↑/↓/→ | <5 /10 |

## Daily Health Tracking Tables

### Current Week - Daily Vitals
| Date | RHR | Sleep Hrs | Sleep Qual | Energy | Mood | Stress | Soreness | Notes |
|------|-----|-----------|------------|--------|------|--------|----------|-------|
| Mon [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Tue [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Wed [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Thu [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Fri [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Sat [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| Sun [Date] | [BPM] | [Hours] | [1-10] | [1-10] | [1-10] | [1-10] | [Areas] | [Notes] |
| **Weekly Avg** | **[Avg]** | **[Avg]** | **[Avg]** | **[Avg]** | **[Avg]** | **[Avg]** | **[Pattern]** | **[Summary]** |

### Lifestyle Factors Tracking
| Date | Hydration | Caffeine | Alcohol | Supplements | Meal Timing | Exercise Impact |
|------|-----------|----------|---------|-------------|-------------|-----------------|
| Mon [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Tue [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Wed [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Thu [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Fri [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Sat [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |
| Sun [Date] | [Cups/L] | [Amount] | [Servings] | [List] | [Regular/Irregular] | [Positive/Negative/None] |

## LLM Data Collection Prompts

### XML Prompt for Daily Health Check
```xml
<daily_health_check>
<instructions>
I need to complete my daily health vitals check. Please guide me through each measurement and subjective assessment systematically. Help me maintain consistency in how I evaluate and record these metrics.

Current date: [Today's date]
Time of assessment: [Morning/Evening]
Recent factors: [Any significant events, stress, travel, etc.]
</instructions>

<assessment_sequence>
<vital_signs>
Ask me to measure and record:
1. Resting heart rate - guide me to take this properly (upon waking, before getting up)
2. Blood pressure - if I have a cuff available
3. Weight - if this is a measurement day
</vital_signs>

<sleep_assessment>  
Help me evaluate last night's sleep:
1. Total hours slept - actual sleep time, not just time in bed
2. Sleep quality (1-10 scale) - how restful and restorative it felt
3. Time to fall asleep - minutes from lying down to sleeping
4. Night wakings - number of times I woke up
5. Morning alertness - how alert I felt upon waking (1-10)
</sleep_assessment>

<subjective_ratings>
Guide me through rating (1-10 scale):
1. Current energy level - how energetic I feel right now
2. Mood - overall emotional state today
3. Stress level - current stress/anxiety (10 = maximum stress)
4. Motivation - drive to accomplish goals today
</subjective_ratings>

<physical_assessment>
Help me note:
1. Muscle soreness - location and intensity (0-10)
2. Joint stiffness - any areas of concern
3. Overall aches - general body discomfort level
4. Digestive comfort - how my stomach/digestion feels
</physical_assessment>

<lifestyle_factors>
Ask about:
1. Hydration - cups/liters of water consumed yesterday
2. Caffeine intake - amount and timing yesterday
3. Alcohol consumption - servings if any
4. Supplements taken - list what I consumed
5. Meal timing - regular meals or irregular eating pattern
</lifestyle_factors>
</assessment_sequence>

<data_formatting>
Format the complete assessment as a markdown table row I can copy into my tracking table, including:
- Date
- All measurements and ratings
- Brief notes about any significant factors
- Comparison to recent averages if I provide previous data
- Suggestions for today's focus based on the assessment
</data_formatting>
</daily_health_check>
```

### JSON Prompt for Weekly Health Review
```json
{
  "task": "weekly_health_review",
  "instructions": "Help me analyze a week of health data and identify patterns, trends, and areas for improvement",
  "data_input": {
    "week_period": "[Week of dates]",
    "daily_data": "I'll provide my week's tracking table data",
    "context_factors": "Any major life events, travel, stress, changes this week"
  },
  "analysis_framework": {
    "trend_analysis": [
      {
        "metric": "resting_heart_rate",
        "evaluate": "average, trend direction, day-to-day variability",
        "flag_concerns": "sustained elevation, unusual patterns"
      },
      {
        "metric": "sleep_metrics", 
        "evaluate": "average hours, quality scores, consistency",
        "identify": "best and worst sleep nights, factors contributing"
      },
      {
        "metric": "energy_levels",
        "evaluate": "daily patterns, correlation with sleep and lifestyle",
        "identify": "energy peaks and dips, contributing factors"
      },
      {
        "metric": "stress_and_mood",
        "evaluate": "emotional patterns, stress triggers, mood stability",
        "identify": "challenging days and recovery patterns"
      }
    ],
    "correlation_analysis": [
      "sleep_quality vs energy_levels",
      "exercise_days vs mood_scores", 
      "caffeine_intake vs sleep_quality",
      "stress_levels vs physical_symptoms",
      "hydration vs energy_levels"
    ],
    "lifestyle_impact": [
      "hydration_consistency",
      "caffeine_timing_effects",
      "alcohol_impact_on_sleep",
      "supplement_correlation_with_wellness",
      "meal_timing_effects"
    ]
  },
  "output_format": {
    "weekly_summary": {
      "averages": "All key metrics with trend indicators",
      "best_day": "Highest overall wellness day with contributing factors",
      "challenging_day": "Most difficult day with identified causes",
      "improvement_areas": "Top 2-3 areas needing attention"
    },
    "pattern_recognition": {
      "positive_patterns": "What's working well this week",
      "concerning_patterns": "Areas of concern or decline", 
      "day_of_week_patterns": "Any consistent daily variations"
    },
    "recommendations": {
      "immediate_actions": "Changes to implement this week",
      "monitoring_focus": "Metrics to pay special attention to",
      "lifestyle_adjustments": "Specific behavior modifications to try"
    },
    "next_week_priorities": "Top 3 health focus areas for upcoming week"
  },
  "follow_up": {
    "goal_check": "Progress toward health goals",
    "intervention_tracking": "Effectiveness of recent changes",
    "celebration": "Acknowledge positive achievements this week"
  }
}
```

## Weekly Health Summary Tables

### 4-Week Health Trends
| Week | Avg RHR | Avg Sleep | Avg Energy | Avg Mood | Avg Stress | Key Events | Overall Rating |
|------|---------|-----------|------------|----------|------------|------------|----------------|
| Week 1 | [BPM] | [Hours] | [Score] | [Score] | [Score] | [Events] | [1-10] |
| Week 2 | [BPM] | [Hours] | [Score] | [Score] | [Score] | [Events] | [1-10] |
| Week 3 | [BPM] | [Hours] | [Score] | [Score] | [Score] | [Events] | [1-10] |
| Week 4 | [BPM] | [Hours] | [Score] | [Score] | [Score] | [Events] | [1-10] |

### Monthly Health Patterns
| Month | Best Metric | Challenging Area | Major Changes | Health Score | Goals Progress |
|-------|-------------|------------------|---------------|--------------|----------------|
| [Month] | [Strength] | [Weakness] | [Changes made] | [1-10] | [On track/Behind] |
| [Month] | [Strength] | [Weakness] | [Changes made] | [1-10] | [On track/Behind] |
| [Month] | [Strength] | [Weakness] | [Changes made] | [1-10] | [On track/Behind] |

## Health Goals Tracking

### Current Health Goals
| Goal Category | Target | Current Status | Timeline | Progress % | Next Milestone |
|---------------|--------|----------------|----------|------------|----------------|
| Sleep Quality | 8+ hours, 8+ quality | [Current avg] | [Date] | [%] | [Next target] |
| Stress Management | <4 stress score | [Current avg] | [Date] | [%] | [Next target] |
| Energy Optimization | 8+ energy score | [Current avg] | [Date] | [%] | [Next target] |
| Recovery Enhancement | <60 RHR | [Current avg] | [Date] | [%] | [Next target] |

## Red Flag Alert System

### Health Concerns Checklist
Monitor for these patterns that may require attention:

#### Sleep Issues
- [ ] <6 hours sleep for 3+ consecutive nights
- [ ] Sleep quality <5 for a week
- [ ] Difficulty falling asleep >30 minutes regularly
- [ ] Frequent night wakings (>3 per night)

#### Cardiovascular Concerns  
- [ ] RHR elevated >10 BPM above baseline for 3+ days
- [ ] Blood pressure readings outside normal range
- [ ] Unusual heart rhythm sensations
- [ ] Chest discomfort during normal activities

#### Energy & Mood Red Flags
- [ ] Energy levels <4 for a week
- [ ] Mood scores <4 for multiple days
- [ ] Stress levels >8 consistently
- [ ] Motivation <3 for extended periods

#### Physical Warning Signs
- [ ] Persistent muscle soreness >5 days
- [ ] Joint stiffness interfering with movement
- [ ] Digestive issues lasting >3 days
- [ ] Unusual fatigue despite adequate sleep

## Integration & Analysis

### Performance Correlation Tracking
| Week | Health Score | Workout Quality | Productivity | Relationships | Overall Life Satisfaction |
|------|-------------|-----------------|--------------|---------------|---------------------------|
| [Week] | [Avg] | [Avg] | [Rating] | [Rating] | [Rating] |
| [Week] | [Avg] | [Avg] | [Rating] | [Rating] | [Rating] |
| [Week] | [Avg] | [Avg] | [Rating] | [Rating] | [Rating] |

### Intervention Effectiveness Log
| Date Started | Intervention | Target Metric | Baseline | Current | Effectiveness | Continue? |
|-------------|--------------|---------------|----------|---------|---------------|-----------|
| [Date] | [Change made] | [Metric] | [Starting value] | [Current value] | [Improved/Same/Worse] | Y/N |
| [Date] | [Change made] | [Metric] | [Starting value] | [Current value] | [Improved/Same/Worse] | Y/N |

## Integration Links
- [[Body Measurements Tracker]] - Physical composition metrics
- [[Baseline Assessment]] - Initial health evaluation
- [[Coach Analysis]] - AI-powered health trend analysis
- [[Workouts Organization]] - Exercise impact on health

Tags: #health #vitals #daily-tracking #wellness #baseline

---
*Last Updated: 2025-07-30*
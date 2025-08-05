# Fitness Guide Response Templates

This file provides exact response templates for common user interactions to ensure consistent, data-first responses across all Fitness Guide sessions.

## Two-Mode Response Philosophy

### 🗣️ Conversational Mode (Planning & Advisory)
**Use for**: Nutrition planning, program design, form coaching, goal setting, problem solving

**Conversational Flow**:
1. **Acknowledge request** and explain what you'll help with
2. **Gather information** through natural questions
3. **Provide guidance** and education as needed
4. **Create structured output** once planning is complete
5. **Save to appropriate files** for future tracking

### 📊 Data-First Mode (Logging & Tracking)
**Use for**: Workout logging, progress tracking, body metrics, status reports, quick lookups

**Data-First Priority Order**:
1. **Action confirmation** (✅ status with brief description)
2. **Primary data table** (the main information requested)
3. **Key metrics summary** (bullet points of important numbers)
4. **Brief commentary** (1-2 sentences maximum, data-focused)

**Response Length Guidelines (Data-First Mode Only)**:
- **Structured data**: 70%+ of response content
- **Commentary**: <30% of response content
- **Maximum commentary**: 2 sentences per response

## Conversational Mode Templates

### Nutrition Planning Conversation Template
```markdown
I'll help you create a nutrition plan. Let me gather some information to make this personalized for you.

**Based on your profile**: [current stats from user data]
- Current weight: [weight] lbs
- Training frequency: [X] days per week
- Goal: [goal from profile]

**Let's customize your plan**:
1. What's your typical meal schedule? (3 meals + snacks, intermittent fasting, etc.)
2. Any foods you want to avoid? Common dislikes: liver, brussels sprouts, cottage cheese...
3. Dietary restrictions? (vegetarian, keto, gluten-free, allergies, etc.)
4. How much meal prep are you willing to do? (daily cooking vs batch prep)
5. Budget considerations? (premium vs standard ingredients)

*Once I have these details, I'll create a structured meal plan with specific portions and macros.*
```

### Program Design Conversation Template
```markdown
I'd love to help design a [goal] program for you. Let me understand your situation better.

**Based on what I know**: [relevant user data]
- Current experience: [level from profile]
- Recent training: [pattern from workout logs]
- Equipment: [from settings]

**Let's dial this in**:
1. How many days per week can you realistically train?
2. How long per session? (30min, 45min, 60min+)
3. Any movements you want to emphasize or avoid?
4. Do you have a training partner or prefer solo?
5. Any time constraints? (gym closes early, travel, etc.)

**About [specific goal/event]**: [explain what this goal entails, physical demands, common challenges]

*Once I understand your constraints, I'll create a structured program with specific exercises, sets, and progression.*
```

### Goal Setting Conversation Template
```markdown
Great goal! Let's break down how to achieve [goal] effectively.

**Current status**: [relevant current metrics]
- Starting point: [current measurement]
- Previous attempts: [any history found]
- Timeline mentioned: [if provided]

**Let's plan this properly**:
1. What's driving this goal? (event, health, confidence, etc.)
2. What timeline feels realistic to you?
3. What's worked/not worked for you before?
4. What support do you have? (family, gym buddy, etc.)
5. How will you measure progress along the way?

**This goal typically involves**: [explain what achieving this goal requires]
- [Key component 1]
- [Key component 2] 
- [Key component 3]

*Once we have your preferences, I'll create a structured plan with milestones and tracking.*
```

### Problem-Solving Conversation Template  
```markdown
Let's troubleshoot this [issue]. I want to understand what's happening so we can fix it.

**What I'm seeing**: [relevant data from logs if available]
- Recent [exercise/metric]: [pattern]
- Training context: [recent volume/intensity]

**Help me understand**:
1. When does this [problem] happen? (always, certain exercises, after fatigue?)
2. How long has this been going on?
3. What does it feel like? (sharp, dull, tight, weak?)
4. What have you tried already?
5. Any recent changes? (program, sleep, stress, equipment?)

**Common causes for [problem]**: [list typical issues and solutions]
- [Cause 1]: [explanation]
- [Cause 2]: [explanation]
- [Cause 3]: [explanation]

*Based on your answers, I'll provide specific recommendations and modifications.*
```

## Data-First Mode Templates

### Workout Logging Response Templates

### Single Exercise Log Template
```markdown
✅ **Exercise Logged**: [Exercise Name] - [Date]

| Set | Weight | Reps | RPE | Rest | Notes |
|-----|--------|------|-----|------|-------|
| 1   | [weight] | [reps] | [rpe] | [time] | [note] |
| 2   | [weight] | [reps] | [rpe] | [time] | [note] |
| 3   | [weight] | [reps] | [rpe] | [time] | [note] |

**Session Metrics**:
- Volume: [total] lbs
- Avg RPE: [average]
- Est 1RM: [calculated] lbs

*[Brief performance comment if relevant]*
```

### Full Workout Log Template
```markdown
✅ **Workout Logged**: [Workout Type] - [Date]

| Exercise | Set 1 | Set 2 | Set 3 | Set 4 | Volume |
|----------|-------|-------|-------|-------|--------|
| [Exercise 1] | [W×R] | [W×R] | [W×R] | [W×R] | [vol] lbs |
| [Exercise 2] | [W×R] | [W×R] | [W×R] | - | [vol] lbs |
| [Exercise 3] | [W×R] | [W×R] | [W×R] | [W×R] | [vol] lbs |

**Session Summary**:
- Total Volume: [total] lbs
- Duration: [time] minutes
- Working Sets: [count]
- PRs: [count]

*[Brief session assessment if relevant]*
```

### PR Detection Response Template
```markdown
🔥 **New PR Detected**: [Exercise] - [Date]

| Metric | Previous | New | Improvement |
|--------|----------|-----|-------------|
| Weight | [prev] lbs | [new] lbs | +[diff] lbs |
| Reps | [prev] | [new] | +[diff] |
| Est 1RM | [prev] lbs | [new] lbs | +[diff] lbs |

**PR Context**:
- Time since last PR: [days/weeks]
- Percentage gain: +[percent]%
- Rep range: [range] RM

*[Brief performance note]*
```

## Progress Tracking Response Templates

### Exercise Progress Template
```markdown
📊 **[Exercise] Progress Summary**

| Date | Weight | Reps | Est 1RM | Improvement |
|------|--------|------|---------|-------------|
| [recent] | [w] lbs | [r] | [1rm] lbs | Current |
| [prev1] | [w] lbs | [r] | [1rm] lbs | +[diff] lbs |
| [prev2] | [w] lbs | [r] | [1rm] lbs | +[diff] lbs |

**Progress Metrics**:
- 30-day change: +[amount] lbs (+[percent]%)
- 90-day change: +[amount] lbs (+[percent]%)
- Rate of gain: [amount] lbs/month

*[Trend assessment]*
```

### Weekly Summary Template
```markdown
📈 **Weekly Training Summary**: Week of [date range]

| Day | Focus | Exercises | Volume | Duration | PRs |
|-----|-------|-----------|--------|----------|-----|
| Mon | [type] | [count] | [vol] lbs | [time] min | [prs] |
| Tue | [type] | [count] | [vol] lbs | [time] min | [prs] |
| Wed | Rest | - | - | - | - |
| Thu | [type] | [count] | [vol] lbs | [time] min | [prs] |
| Fri | [type] | [count] | [vol] lbs | [time] min | [prs] |

**Weekly Totals**:
- Sessions completed: [count]/[target]
- Total volume: [amount] lbs
- PRs achieved: [count]
- Average session: [time] minutes

*[Performance assessment]*
```

## Body Metrics Response Templates

### Body Measurement Update Template
```markdown
⚖️ **Body Metrics Updated**: [Date]

| Metric | Current | Previous | Change | % Change |
|--------|---------|----------|--------|----------|
| Weight | [current] lbs | [prev] lbs | [±diff] lbs | [±percent]% |
| Body Fat | [current]% | [prev]% | [±diff]% | [±percent]% |
| Waist | [current]" | [prev]" | [±diff]" | [±percent]% |

**Trend Analysis**:
- 30-day trend: [direction] [amount]
- Goal progress: [percent]% complete
- Target date: [date]

*[Progress assessment]*
```

### Goal Progress Template
```markdown
🎯 **Goal Progress Update**: [Goal Name]

| Timeframe | Starting | Current | Target | Progress | Remaining |
|-----------|----------|---------|--------|----------|-----------|
| Total | [start] | [current] | [target] | [percent]% | [amount] |
| This Month | [month start] | [current] | [month target] | [percent]% | [amount] |

**Progress Metrics**:
- Rate of change: [amount] per [timeframe]
- Estimated completion: [date]
- Days remaining: [count]

*[Goal assessment]*
```

## Workout Planning Response Templates

### Workout Generation Template
```markdown
💪 **Workout Generated**: [Workout Type] - [Date]

| Exercise | Sets × Reps | Weight | Rest | RPE Target |
|----------|-------------|--------|------|------------|
| [Primary] | [S×R] | [weight] lbs | [time] | [rpe range] |
| [Secondary] | [S×R] | [weight] lbs | [time] | [rpe range] |
| [Accessory 1] | [S×R] | [weight] lbs | [time] | [rpe range] |
| [Accessory 2] | [S×R] | [weight] lbs | [time] | [rpe range] |

**Session Planning**:
- Estimated duration: [time] minutes
- Target volume: [amount] lbs
- Focus: [training emphasis]

*[Programming rationale]*
```

### Program Selection Template
```markdown
📋 **Program Selected**: [Program Name]

| Week | Focus | Main Lifts | Intensity | Volume |
|------|-------|------------|-----------|--------|
| 1 | [focus] | [lifts] | [percent] | [sets] |
| 2 | [focus] | [lifts] | [percent] | [sets] |
| 3 | [focus] | [lifts] | [percent] | [sets] |
| 4 | Deload | [lifts] | [percent] | [sets] |

**Program Details**:
- Duration: [weeks] weeks
- Frequency: [days]/week
- Training maxes needed: [Yes/No]

*[Program overview]*
```

## Nutrition Response Templates

### Nutrition Plan Template
```markdown
🍽️ **Nutrition Plan Created**: [Plan Type]

| Meal | Food | Portion | Calories | Protein | Carbs | Fat |
|------|------|---------|----------|---------|-------|-----|
| Breakfast | [foods] | [amounts] | [cals] | [prot]g | [carbs]g | [fat]g |
| Lunch | [foods] | [amounts] | [cals] | [prot]g | [carbs]g | [fat]g |
| Dinner | [foods] | [amounts] | [cals] | [prot]g | [carbs]g | [fat]g |
| **Daily Total** | - | - | **[total]** | **[prot]g** | **[carbs]g** | **[fat]g** |

**Plan Targets**:
- Target calories: [amount]
- Protein target: [amount]g ([grams]/lb bodyweight)
- Training day adjustments: [details]

*[Plan overview]*
```

### Grocery List Template
```markdown
🛒 **Grocery List Generated**: [Duration] 

| Category | Item | Quantity | Est. Cost | Priority |
|----------|------|----------|-----------|----------|
| Protein | [item] | [qty] | $[cost] | High |
| Carbs | [item] | [qty] | $[cost] | High |
| Fats | [item] | [qty] | $[cost] | Medium |
| Produce | [item] | [qty] | $[cost] | High |
| Pantry | [item] | [qty] | $[cost] | Low |

**Shopping Summary**:
- Total items: [count]
- Estimated cost: $[amount]
- Weekly budget: $[range]

*[Shopping notes]*
```

## Analysis Response Templates

### Performance Analysis Template
```markdown
📊 **Performance Analysis**: [Exercise/Timeframe]

| Metric | Value | Previous | Change | Trend |
|--------|-------|----------|--------|-------|
| Volume | [current] | [prev] | [±change] | [direction] |
| Intensity | [current] | [prev] | [±change] | [direction] |
| PRs | [current] | [prev] | [±change] | [direction] |
| Consistency | [current]% | [prev]% | [±change]% | [direction] |

**Analysis Summary**:
- Strongest area: [metric]
- Improvement needed: [metric]
- Recommended focus: [recommendation]

*[Analysis insight]*
```

### Recovery Assessment Template
```markdown
💤 **Recovery Assessment**: [Date Range]

| Metric | Average | Target | Status | Impact |
|--------|---------|--------|--------|--------|
| Sleep | [hrs] | [target] hrs | [status] | [impact] |
| Energy | [rating]/10 | 7+ | [status] | [impact] |
| Soreness | [rating]/10 | <4 | [status] | [impact] |
| Motivation | [rating]/10 | 7+ | [status] | [impact] |

**Recovery Status**:
- Overall score: [score]/10
- Training readiness: [status]
- Recommendations: [actions]

*[Recovery assessment]*
```

## Error and Status Templates

### Input Error Template
```markdown
❌ **Input Error**: [Specific Issue]

**Expected Format**: [Correct format example]
**Received**: [What was provided]

**Examples**:
- [Example 1]
- [Example 2]
- [Example 3]

*Try again with the correct format*
```

### Data Missing Template
```markdown
⚠️ **Data Required**: [Missing Information]

**Currently Missing**:
- [Item 1]
- [Item 2]
- [Item 3]

**To Continue**:
1. [Action needed]
2. [Alternative option]

*Provide the missing information to proceed*
```

### Success Confirmation Template
```markdown
✅ **Action Completed**: [Action Description]

**Files Updated**:
- [File 1]: [What changed]
- [File 2]: [What changed]

**Next Steps**:
- [Suggested action 1]
- [Suggested action 2]

*[Brief confirmation note]*
```

## Command Mode Response Templates

### Command Success Template
```markdown
✓ [Action]: [Brief result description]

[DATA TABLE]

[Key metric]: [Value] | [Key metric 2]: [Value]
```

### Command Status Template
```markdown
| Metric | Value | Status |
|--------|-------|--------|
| [Item 1] | [Value] | [Status] |
| [Item 2] | [Value] | [Status] |
| [Item 3] | [Value] | [Status] |

[Brief status summary]
```

### Command Error Template
```markdown
ERROR: [Specific issue]
Expected: [Format]
Example: [Usage example]
```

## Response Quality Validation

### Template Compliance Checklist
- [ ] Action confirmation at start (✅ format)
- [ ] Primary data in table format
- [ ] Key metrics as bullet points
- [ ] Commentary limited to 1-2 sentences
- [ ] Consistent table formatting
- [ ] All units specified
- [ ] Dates in YYYY-MM-DD format
- [ ] No broken markdown syntax

### Response Effectiveness Criteria
- **Scannability**: Key information visible in <5 seconds
- **Actionability**: User knows what to do next
- **Completeness**: All relevant data included
- **Consistency**: Same format for same data types
- **Brevity**: No unnecessary conversational elements

These templates ensure every Fitness Guide response follows the data-first philosophy while maintaining consistency and professional presentation across all user interactions.
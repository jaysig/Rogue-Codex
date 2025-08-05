# Fitness Guide

A conversational fitness management system that uses markdown files as its database. Talk naturally about fitness - the system intelligently handles data logging, progress tracking, and program planning through smart two-mode interactions.

## 🚀 Quick Start

**Just start talking about fitness:**
- "Just did squats 315x5" → Automatic workout logging with PR detection
- "Show me my bench progress" → Data tables with trends and projections  
- "I need a nutrition plan" → Guided conversation → Structured meal plan
- "What should I train today?" → Personalized workout recommendations

## 🧠 How It Works: Two-Mode System

The Fitness Guide automatically chooses between two interaction modes based on what you need:

### 🗣️ Conversational Mode (Planning & Advisory)
**When you need guidance, planning, or education:**

- **Nutrition planning**: "I want to lose 20 pounds"
- **Program design**: "I need a marathon training plan" 
- **Form coaching**: "My bench press feels off"
- **Goal setting**: "I want to deadlift 500 lbs"
- **Problem solving**: "My shoulder hurts during overhead press"

**The flow**: Natural conversation → Information gathering → Structured output

**Example**:
```
You: "I need a nutrition plan for muscle gain"

System: "I'll help create a plan. Based on your profile (182 lbs, training 4x/week), 
         I estimate ~2,400 calories daily. Let's customize this:
         - What's your meal schedule preference?
         - Any foods to avoid?
         - Dietary restrictions?"

You: [Provide preferences through conversation]

System: [Creates structured meal plan table with specific portions and macros]
```

### 📊 Data-First Mode (Logging & Tracking)
**When you're logging data or checking status:**

- **Workout logging**: "Did chest: bench 185x8x3, incline DB 60x10x3"
- **Progress tracking**: "Show my squat progress"
- **Body metrics**: "Weighed 182 today, body fat 11.5%"
- **Status updates**: "How was my training this week?"
- **Quick lookups**: "What's my current bench PR?"

**The response**: Immediate structured tables with key metrics

**Example**:
```
You: "Just did squats 315x5"

System: ✅ Workout Logged: Lower Body - 2025-08-05

        | Exercise | Set 1 | Volume | Notes |
        |----------|-------|---------|--------|
        | Back Squat | 315x5 | 1,575 lbs | Solid |

        Session Metrics:
        - Volume: 1,575 lbs
        - Est 1RM: 355 lbs
        - Form: Consistent
```

## 📁 File Structure

### 🔧 Setup for Personal Use

**IMPORTANT**: The `User Data/` folder contains mock/template data for demonstration. When you start using this system:

1. **Rename the folder**: `User Data/` → `Mock User Data/` (to preserve templates)
2. **Create your own**: `User Data/` folder for your personal fitness data
3. **Add to .gitignore**: Include `User Data/` in your `.gitignore` to keep personal data private

```gitignore
# Personal fitness data (keep private)
User Data/

# Local Claude settings
.claude/settings.local.json
```

The system automatically manages these files:

```
Fitness Guide/
├── README.md (this file)
├── CLAUDE.md (system instructions)
├── Fitness Adventure.md (command mode)
├── .gitignore (keeps personal data private)
│
├── Mock User Data/ (templates - safe to commit)
│   ├── Profile.md (example profile)
│   ├── [template files...]
│
├── User Data/ (your personal data - add to .gitignore!)
│   ├── Profile.md (goals, settings, preferences)
│   ├── Workout_Settings.md (equipment, gym setups)
│   │
│   ├── Logs/
│   │   ├── Workouts/2025_Week_31.md (daily workouts)
│   │   ├── Nutrition/2025_Week_31.md (meal tracking)
│   │   └── Recovery/2025_Week_31.md (sleep, energy)
│   │
│   ├── PRs/ (Personal Records)
│   │   ├── Strength/Squat.md, Bench_Press.md, etc.
│   │   ├── Endurance/Running_5K.md, etc.
│   │   └── Skills/Pull_Ups.md, etc.
│   │
│   └── Tracking/
│       ├── Body_Metrics.md (weight, measurements)
│       ├── Health_Vitals.md (sleep, energy, recovery)
│       └── Progress_Photos.md (photo log)
│
├── References/
│   ├── Calculation_Templates.md (automated formulas)
│   ├── Table_Standards.md (formatting requirements)
│   ├── Response_Templates.md (interaction patterns)
│   └── Program_Library/ (structured programs)
│
└── Current_Programs/ (active training plans)
```

**You don't manage these files manually** - just talk naturally and the system handles all file creation, updates, and cross-references automatically.

## 🎯 Common Workflows

### Workout Logging
```
You: "Crushed legs today - squats 275x5x4, leg press 4 platesx15x3"

→ System parses exercises automatically
→ Creates/updates daily workout log
→ Checks for PRs against historical data  
→ Updates PR files if records broken
→ Calculates volume and metrics
→ Returns formatted summary table
```

### Progress Tracking
```
You: "How's my bench press going?"

→ System reads PR file and recent logs
→ Calculates trends (30-day, 90-day)  
→ Generates rep max estimates
→ Shows progress table with projections
→ Optional: ASCII progress chart
```

### Program Planning
```
You: "I want to train for a powerlifting meet"

→ Conversational phase: experience, timeline, equipment
→ Educational phase: explains meet requirements
→ Planning phase: customizes program structure
→ Output phase: structured training plan tables
→ Management phase: saves to Current_Programs/
```

### Nutrition Planning
```
You: "I need to lose 20 pounds"

→ Gathers current stats and preferences
→ Routes to nutrition specialist
→ Conversational planning: meals, restrictions, lifestyle
→ Creates structured meal plan with macros
→ Offers grocery list generation
→ Saves plan with review dates
```

## 🎮 Command Mode (Optional)

For power users, activate command mode for direct data manipulation:

```
You: "Run Fitness Adventure"

> LOG bench 225x8x3
✓ Logged: Bench Press - 2025-08-05
Volume: 5,400 lbs | Est 1RM: 284 lbs

> SHOW bench
| Date | Weight | Reps | 1RM Est | Notes |
|------|--------|------|---------|-------|
| 2025-08-05 | 225 | 8 | 284 | Current |
| 2025-07-15 | 220 | 8 | 278 | +5 lbs |

> PLAN chest
| Exercise | Sets x Reps | Weight | Rest |
|----------|-------------|--------|------|
| Bench Press | 5x5 | 225 | 3min |
| Incline DB | 3x8 | 60 | 2min |
```

## 🚦 Getting Started

### Repository Setup (Important!)
1. **Rename template data**: `User Data/` → `Mock User Data/`
2. **Create your folder**: Make a new `User Data/` folder for your personal data
3. **Update .gitignore**: Add `User Data/` to keep your personal fitness data private
4. **Verify privacy**: Ensure `Mock User Data/` (templates) can be committed, but `User Data/` (personal) stays local

### First Time Setup
1. **Tell the system about yourself**: "I'm 182 lbs, been lifting for 2 years, want to gain muscle"
2. **Set your equipment**: "I train at a commercial gym with full equipment"
3. **Establish baselines**: Log a few workouts to establish your current performance
4. **Set initial goals**: "I want to bench 225 lbs by the end of the year"

### Daily Usage
- **Log workouts naturally**: Describe what you did in plain language
- **Check progress regularly**: "Show me my weekly summary" 
- **Plan ahead**: "What should I train tomorrow?"
- **Track body metrics**: "Weighed 181 this morning"

### Advanced Features
- **Program selection**: "I want to start the 5/3/1 program"
- **Nutrition planning**: Route to specialized nutrition coaching
- **Form coaching**: Get technique guidance for specific lifts
- **Goal tracking**: Automatic progress calculations toward targets

## 📊 Data & Privacy

- **Local storage**: All data stored in markdown files on your system
- **No external sync**: Files stay on your machine unless you choose to sync
- **Version control friendly**: All files are plain text markdown
- **Export friendly**: Easy to backup, move, or process data
- **Human readable**: You can read and edit any file manually if needed

## 🔧 Customization

### Equipment Settings
Tell the system about your setup:
- "I train at home with dumbbells up to 100 lbs"
- "I have a commercial gym membership"
- "I'm traveling - hotel gym only"

### Program Preferences
- "I prefer full-body workouts 3x per week"
- "I want to focus on powerlifting"
- "I need 45-minute sessions maximum"

### Nutrition Preferences  
- "I'm vegetarian"
- "I do intermittent fasting"
- "I need meal prep friendly options"

## 🆘 Troubleshooting

### System Not Understanding
- **Be specific**: "bench press 185x8" vs "did some bench"
- **Include units**: "185 lbs" vs just "185"
- **One workout per message**: Don't combine multiple days

### Data Issues
- **PR not detected**: Check exercise name consistency ("Bench Press" vs "Bench")
- **Files not updating**: System will fix cross-references automatically
- **Missing data**: System will ask for what it needs

### Getting Help
- **Ask directly**: "How do I log a workout?"
- **Request examples**: "Show me how to enter body measurements"
- **Get guidance**: "I'm not sure what program to choose"

## 🎯 Tips for Best Results

### Logging Workouts
- **Be consistent with exercise names**: "Bench Press" not "bench" or "BP"
- **Include all sets**: "225x8x3" or "225x8, 225x8, 225x8"
- **Note important details**: "225x8 RPE 9" or "felt heavy today"

### Tracking Progress
- **Check weekly**: "How was my training this week?"
- **Monitor trends**: "Show me my squat progress"
- **Celebrate PRs**: System will automatically detect and celebrate

### Planning Programs
- **Be honest about constraints**: Time, equipment, experience level
- **Communicate goals clearly**: "I want to run a 5K" vs "get in shape"
- **Update when things change**: New equipment, schedule changes, injuries

## 🔮 Advanced Features

### Specialized Coaching
The system can route you to specialized agents for:
- **Powerlifting coaching**: Meet prep, max strength focus
- **Running coaching**: Distance training, technique improvement  
- **Nutrition coaching**: Meal planning, macro tracking
- **Recovery coaching**: Flexibility, injury prevention
- **Special populations**: Beginners, seniors, specific needs

### Program Library
Access to structured programs:
- **Strength**: Starting Strength, 5/3/1, StrongLifts
- **Endurance**: Couch to 5K, Marathon training
- **Hybrid**: CrossFit, tactical fitness, functional training

### Analytics
- **Progress trends**: 30/90-day changes across all metrics
- **Volume tracking**: Weekly/monthly training loads
- **Goal projections**: Estimated timeline to reach targets
- **Performance patterns**: Identify strengths and weaknesses

---

## 💪 Ready to Start?

Just begin talking about fitness. The system will figure out what you need and guide you through the process. Whether you're logging today's workout or planning next month's program, natural conversation is all you need.

**Example first interaction**: 
*"I'm new to this. I'm 175 lbs, want to build muscle, and have access to a full gym. I did chest today - bench press 135x8x3 sets, and some incline dumbbell work with 40s."*

The system will create your profile, log your workout, establish baselines, and ask what you'd like to work on next.

Welcome to effortless fitness tracking! 🚀
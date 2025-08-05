# Fitness Adventure - Command Mode

## To Start
Tell Claude: "Run Fitness Adventure" to activate command mode.

## Available Commands

### Logging Commands (Table Output)
- `LOG <exercise> <weight>x<reps>` - Generate workout table with volume calculations
- `LOG WORKOUT` - Interactive workout table builder
- `LOG WEIGHT <pounds>` - Update body metrics table with trend analysis
- `LOG MEAL <description>` - Add to nutrition tracking table
- `LOG SLEEP <hours>` - Update recovery metrics table

### Display Commands (Data Tables)
- `SHOW STATS` - Current PR table across all exercises
- `SHOW <exercise>` - Exercise history table with progression metrics
- `SHOW <exercise> GRAPH` - ASCII progress chart + summary table
- `SHOW WEEK` - Weekly workout summary table
- `SHOW PROGRESS` - Goal progress table with percentages
- `GRAPH <metric>` - ASCII visualization + trend data table

### Planning Commands (Structured Workouts)
- `PLAN <muscle group>` - Workout table with sets/reps/weights
- `PLAN WEEK` - Weekly split table with session details
- `NEXT WORKOUT` - Next session table with progression targets

### Analysis Commands (Metrics Tables)
- `ANALYZE WEEK` - Weekly performance metrics table
- `ANALYZE <exercise>` - Exercise progression analysis table
- `CHECK FORM <exercise>` - Form cues table with key points

### Quick Actions (Data Points)
- `PR?` - PR status table with improvement data
- `VOLUME` - Volume calculation table by exercise/bodypart
- `REST DAY?` - Recovery metrics table with recommendations
- `STATUS` - Current status metrics table
- `GROCERY LIST` - Shopping list table with costs

### System Commands
- `HELP` - Show available commands table
- `HELP <command>` - Command usage table with examples
- `EXIT` - Exit command mode

## Command Examples - Data-First Format

```
> LOG squat 315x5
✓ Logged: Squat - 2025-08-05
🔥 NEW PR! Previous: 305x5

| Set | Weight | Reps | RPE | Volume |
|-----|--------|------|-----|--------|
| 1   | 315    | 5    | 9   | 1,575  |

Session: 1,575 lbs | Est 1RM: 355 lbs

> SHOW squat
| Date | Weight | Reps | 1RM Est | Notes |
|------|--------|------|---------|-------|
| 2025-08-05 | 315 | 5 | 355 | PR |
| 2025-07-15 | 305 | 5 | 344 | +10 |
| 2025-07-01 | 295 | 5 | 332 | +10 |

30d: +20 lbs | 90d: +40 lbs | Trend: ↗️

> SHOW squat GRAPH
SQUAT 5RM PROGRESSION (lbs)
320 |               ⭐ 315
310 |          ⭐ 305
300 |     ⭐ 295
290 |⭐ 285
280 |
    +----+----+----+----+
    Jun  Jul  Jul  Aug

Gain: +30 lbs | Rate: +10/month

> PLAN legs
| Exercise | Sets x Reps | Weight | Rest |
|----------|-------------|--------|------|
| Back Squat | 5x5 | 315 | 3min |
| RDL | 3x8 | 225 | 2min |
| Leg Press | 3x12 | 405 | 90s |
| Leg Curls | 3x15 | 90 | 60s |

Duration: 55min | Focus: Strength/Volume

> STATUS
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| Week Progress | 3/4 | 4 | On Track |
| Recovery | 24hrs | <48hrs | Ready |
| Next Session | Tomorrow | Upper | Scheduled |

> GROCERY LIST full week
| Category | Item | Qty | Est Cost |
|----------|------|-----|----------|
| Protein | Ground beef 93/7 | 2 lbs | $12 |
| Dairy | Greek yogurt | 32 oz | $6 |
| Produce | Bananas | 8 | $3 |
| Carbs | Sweet potatoes | 4 | $4 |
| Pantry | Rice | 2 lb bag | $3 |

Total: $28 | Weekly budget: $45-55
```

## ⚡ Command Mode Data-First Requirements

**CRITICAL: Command mode prioritizes data tables over conversation**

### Response Format Standards (MANDATORY)
1. **Primary output**: Always structured data (tables, lists, metrics)
2. **Secondary output**: Brief status confirmation (1 line max)
3. **NO explanations**: Pure data execution only
4. **Table formatting**: Consistent markdown tables for all data
5. **Error handling**: `ERROR: [specific issue]` format only

### Command Response Templates

#### LOG Commands Output Format
```
> LOG bench 225x8x3
✓ Logged: Bench Press - 2025-08-05

| Set | Weight | Reps | RPE | Notes |
|-----|--------|------|-----|-------|
| 1   | 225    | 8    | 7   | Good  |
| 2   | 225    | 8    | 7.5 | Good  |
| 3   | 225    | 8    | 8   | Good  |

Volume: 5,400 lbs | Est 1RM: 284 lbs
```

#### SHOW Commands Output Format
```
> SHOW bench
| Date | Weight | Reps | 1RM Est | Improvement |
|------|--------|------|---------|-------------|
| 2025-08-05 | 225 | 8 | 284 | Current |
| 2025-07-15 | 220 | 8 | 278 | +5 lbs |
| 2025-07-01 | 215 | 8 | 272 | +5 lbs |

30d trend: ↗️ +10 lbs | 90d trend: ↗️ +25 lbs
```

#### PLAN Commands Output Format
```
> PLAN chest
| Exercise | Sets x Reps | Weight | Rest |
|----------|-------------|--------|------|
| Bench Press | 5x5 | 225 | 3 min |
| Incline DB | 3x8 | 60 | 2 min |
| Dips | 3x12 | BW | 90s |

Est. Duration: 45 min | Focus: Strength
```

#### STATUS Commands Output Format
```
> STATUS
| Metric | Value | Status |
|--------|-------|--------|
| Week Progress | 3/4 workouts | On track |
| Last Workout | Yesterday | Recovery |
| Next Session | Tomorrow | Upper |
| Weekly Volume | 28,500 lbs | Target |
```

### Command Mode Behavior Rules
1. **Execute immediately**: No analysis or planning discussion
2. **Data-first response**: Tables and metrics before any text
3. **Limit responses**: Maximum 3 lines of non-tabular text
4. **No motivation**: Skip encouragement and generic comments
5. **Clear formatting**: All tables properly aligned with headers
6. **Consistent units**: Maintain user's preferred measurement system

### Error Response Format
```
> LOG bench 500x20
ERROR: Weight/rep combination seems unusual - confirm?
> SHOW nonexistent
ERROR: Exercise 'nonexistent' not found in records
```

### Cross-File Update Protocol (AUTOMATIC)
Every command that modifies data MUST:
1. **Update primary file** (workout log, PR file, etc.)
2. **Check related files** for consistency requirements
3. **Update cross-references** automatically
4. **Validate data integrity** before confirming success

Command mode transforms fitness tracking into direct data manipulation - users input commands, system outputs structured data, no conversation required.
# Fitness Adventure - Command Mode

## To Start
Tell Claude: "Run Fitness Adventure" to activate command mode.

## Available Commands

### Logging Commands
- `LOG <exercise> <weight>x<reps>` - Log a single exercise
- `LOG WORKOUT` - Start logging a full workout session
- `LOG WEIGHT <pounds>` - Log body weight
- `LOG MEAL <description>` - Log a meal
- `LOG SLEEP <hours>` - Log sleep duration

### Display Commands
- `SHOW STATS` - Display current stats and PRs
- `SHOW <exercise>` - Show specific exercise history
- `SHOW <exercise> GRAPH` - Show ASCII progress chart
- `SHOW WEEK` - Show this week's workouts
- `SHOW PROGRESS` - Show progress toward goals
- `GRAPH <metric>` - Generate ASCII graph for any tracked metric

### Planning Commands  
- `PLAN <muscle group>` - Generate workout for muscle group
- `PLAN WEEK` - Generate weekly workout split
- `NEXT WORKOUT` - Get your next scheduled workout

### Analysis Commands
- `ANALYZE WEEK` - Analyze weekly performance
- `ANALYZE <exercise>` - Analyze specific lift progression
- `CHECK FORM <exercise>` - Get form tips

### Quick Actions
- `PR?` - Check if last logged exercise was a PR
- `VOLUME` - Calculate today's volume
- `REST DAY?` - Check if you should rest
- `STATUS` - Quick status check
- `GROCERY LIST` - Generate shopping list from nutrition plan

### System Commands
- `HELP` - Show this command list
- `HELP <command>` - Get help for specific command
- `EXIT` - Exit command mode

## Command Examples

```
> LOG squat 315x5
✓ Logged: Squat 315 lbs x 5 reps
🎉 NEW PR! Previous best was 305x5

> SHOW squat
Squat History:
- 2025-07-31: 315x5 (PR)
- 2025-07-15: 305x5
- 2025-07-01: 295x5
Would you like to see this as a graph? (Y/N)

> SHOW squat GRAPH
SQUAT PROGRESSION (lbs)
320 |               ⭐ 315
310 |          ⭐ 305
300 |     ⭐ 295
290 |⭐ 285
280 |
    +----+----+----+----+
    Jun  Jul  Jul  Aug

Progress: +30 lbs (10.5%)
Rate: +10 lbs/month 🔥

> PLAN legs
Leg Day Workout:
1. Squat: 3x5 @ 315 lbs
2. Romanian Deadlift: 3x8 @ 225 lbs
3. Leg Press: 3x12 @ 405 lbs
4. Leg Curls: 3x15 @ 90 lbs

> STATUS
Current Week: 3 workouts completed
Today: Rest day recommended
Next: Upper body tomorrow

> GROCERY LIST
How many days? (3-4 days or full week)
> full week
What proteins do you have at home?
> chicken and eggs
Any produce still fresh?
> none

GROCERY LIST - 1 Week
□ Ground beef 93/7 (2 lbs)
□ Greek yogurt (32 oz)
□ Bananas (8)
□ Sweet potatoes (4)
□ Rice (2 lb bag)
Estimated: $45-55
```

## Command Mode Behavior

When in command mode:
1. Claude waits for command input
2. Executes command immediately 
3. Returns concise result
4. Shows prompt for next command
5. No explanations unless requested

This provides the classic text adventure feel with direct command execution.
# Nutrition Information Gathering Template

## Pre-Agent Data Collection

When a user requests nutrition planning, gather this information from their files before routing to the nutritionist agent:

### 1. Body Metrics (from User Data/Tracking/Body_Metrics.md)
- Current weight
- Height (if available)
- Body fat percentage (if tracked)
- Recent weight trends (gaining/losing/maintaining)

### 2. Goals (from User Data/Profile.md)
- Primary fitness goals (weight loss, muscle gain, performance, etc.)
- Target weight (if specified)
- Timeline for goals
- Sport-specific needs

### 3. Activity Level (from User Data/Logs/Workouts/)
- Training frequency (days per week)
- Workout intensity (heavy lifting, cardio, mixed)
- Average session duration
- Recovery days per week

### 4. Existing Preferences (if noted anywhere)
- Meal timing preferences
- Known food preferences/aversions
- Previous diet attempts
- Cultural/religious considerations

## Nutritionist Agent Question Flow

### Initial Response
```
"Okay, let me check on that...

Based on your current stats:
- Weight: [X] lbs
- Activity: [Y] days/week of [type] training
- Goals: [primary goal]

I estimate you'll need roughly [Z] calories per day.
```

### Essential Questions

1. **Meal Schedule**
   - "What's your typical meal schedule?"
   - Options: 3 meals, 2 meals + snacks, intermittent fasting (16:8, 18:6), OMAD
   - Pre/post workout nutrition timing

2. **Food Preferences**
   - "Any foods you absolutely want to avoid?"
   - Common dislikes to mention:
     - Proteins: liver, organ meats, certain fish
     - Vegetables: brussels sprouts, mushrooms, eggplant
     - Other: cottage cheese, greek yogurt, tofu
   - "Any favorite foods you'd like to include regularly?"

3. **Dietary Restrictions**
   - "Any dietary restrictions I should know about?"
   - Allergies (nuts, dairy, gluten, shellfish)
   - Lifestyle choices (vegetarian, vegan, pescatarian)
   - Medical (diabetes, high blood pressure, IBS)
   - Religious/cultural (halal, kosher, etc.)

4. **Macronutrient Priorities**
   - Protein target: [0.8-1g per lb bodyweight for most goals]
   - Carb timing preferences (around workouts?)
   - Fat preferences (higher fat/lower carb or balanced?)

5. **Practical Constraints**
   - "How much time do you have for meal prep?"
   - "Do you eat out frequently?"
   - "Budget considerations?"
   - "Access to kitchen/cooking facilities?"

## Sample Context Pass to Nutritionist

```
Route to nutritionist agent with context:

Current Stats:
- Weight: 178 lbs
- Height: 5'10" (if known)
- Body fat: 18% (if tracked)

Goals:
- Primary: Build muscle while staying lean
- Target: 185 lbs
- Timeline: 6 months

Activity Level:
- Training: 4 days/week (Upper/Lower split)
- Intensity: Heavy compound lifts + accessories
- Cardio: 2x per week, 20 min sessions

Known Preferences:
- Likes: Chicken, rice, eggs
- Dislikes: Fish, mushrooms
- Previous: Tried keto, prefers balanced approach
```

## Common Food Lists for Reference

### Most Loved Fitness Foods
- Proteins: Chicken breast, eggs, Greek yogurt
- Carbs: Rice, oats, sweet potatoes
- Fats: Peanut butter, avocado, olive oil
- Convenience: Protein powder, protein bars

### Most Hated/Avoided Foods
- Liver and organ meats
- Brussels sprouts
- Cottage cheese (texture issues)
- Plain tuna
- Mushrooms
- Tofu (for non-vegetarians)
- Kale (when forced)

### Common Restrictions to Check
- Lactose intolerance
- Gluten sensitivity
- Nut allergies
- Vegetarian/vegan
- Keto/low-carb
- Intermittent fasting

## Output Format for Nutrition Plan

After gathering all information, the nutritionist should provide:

1. Daily calorie target with macros
2. Sample meal plan (1-3 days)
3. Food substitution list
4. Pre/post workout nutrition
5. Supplement recommendations (if appropriate)
6. Weekly meal prep strategy
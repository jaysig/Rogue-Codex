# Gemini Fitness Guide Agent Evaluation Prompts

This document contains a series of prompts designed to test an AI agent's ability to understand and respond to user queries based on the content within the "Fitness Guide" directory.

---

## 1. Baseline Stats & Assessment

### User Prompts:

1.  "I want to do a full baseline fitness assessment. Can you walk me through it? I have a yoga mat, a 12-inch box, and a stopwatch. I'm a beginner and my main goal is to lose 10 pounds."
2.  "What was my resting heart rate during my last assessment, and what was its classification?"
3.  "Guide me through taking my bi-weekly body measurements. I have a scale and a measuring tape."
4.  "Based on my `Body Measurements Tracker.md`, what is the trend for my waist circumference over the last 3 months?"
5.  "I just took my progress photos. Can you help me analyze them compared to my photos from 8 weeks ago? I feel like my shoulders look broader and my waist is a bit smaller. My weight is down 5 lbs."
6.  "What's on my pre-assessment checklist for my next quarterly review?"
7.  "Pull up my latest health vitals. How is my 7-day average sleep quality trending?"
8.  "I'm feeling stressed and my energy is low today. Can you look at my `Health Vitals Tracker.md` from the last time I felt this way and see what might have contributed to it?"

---

## 2. Coach AI & Planning

### User Prompts:

1.  "What is the primary goal of my current coaching plan and what is the timeline?"
2.  "According to my `Coaching Plan Overview.md`, what coaching phase am I in and what is the main focus?"
3.  "Analyze my last workout from `[YYYY-MM-DD Workout].md`. My RPE for squats was higher than planned. What do you recommend for my next squat session?"
4.  "Design my next workout. Today is a strength day. I have access to a full gym, 60 minutes to train, and my energy level is an 8/10. My last workout was a lower body day, and I'm feeling a bit of fatigue in my hamstrings."
5.  "I only have 30 minutes for my workout today instead of the planned 60. Can you give me a modified version of the planned workout?"
6.  "Let's do my weekly coaching review for the week of [Date]. Pull the data from my daily logs and give me a summary of my consistency, top achievement, and main challenge."
7.  "Based on my last 4 weekly reviews, what is my biggest challenge pattern? Suggest a strategy to address it."
8.  "What was the last major coaching decision recorded in my `Coaching Plan Overview.md` and what was the outcome?"

---

## 3. Personal Records (PRs)

### User Prompts:

1.  "What is my current 1 rep max for the deadlift?"
2.  "Log a new PR for me. I just ran a 5K in 24:30."
3.  "What's my longest workout streak according to my `Wellness PRs.md`?"
4.  "I just did 10 consecutive pull-ups for the first time! Can you document this in my `Skill Movement PRs.md` and guide me through the celebration template?"
5.  "How far am I from my goal of a sub-2-hour half marathon?"
6.  "What was my best week for sleep quality in the last month?"
7.  "Compare my squat progression over the last 6 months based on my `Strength PRs.md`."
8.  "I want to set a new goal for my 1-mile run. What would be a realistic but challenging target for the next 3 months?"

---

## 4. Templates & Workflows

### User Prompts:

1.  "I'm feeling unmotivated today. Can you give me the 'Motivation Rescue Template'?"
2.  "I'm traveling and only have resistance bands and my bodyweight. Can you generate a 30-minute full-body workout for me?"
3.  "Explain the 3 phases of the system implementation."
4.  "What's the 'Ultra-Minimal Daily' tracking template for days when I have less than a minute?"
5.  "I think my weekly review process is taking too long. Can you give me the `weekly_workflow_review` prompt so I can optimize it?"
6.  "How do I handle a day with disruptions like travel or sickness according to the templates?"
7.  "Generate a personalized daily fitness tracking routine for me. I have about 10 minutes a day, my schedule is flexible, and my main goal is consistency."
8.  "What's the process for a monthly deep review?"

---

## 5. Workouts & Exercise Library

### User Prompts:

1.  "What's the difference between a squat and a hinge movement pattern?"
2.  "Give me the execution instructions for a kettlebell swing from the exercise library."
3.  "What are some easier versions (regressions) for a push-up?"
4.  "I'm feeling pain in my shoulder when I bench press. What are some common mistakes and safety considerations for this exercise?"
5.  "Generate a 4-week strength program for an intermediate lifter who can train 4 days a week for 60 minutes a session."
6.  "What exercises pair well with the overhead press for a superset?"
7.  "I'm about to do my workout. Can you pull up the `Daily Workout Template` for me to fill out?"
8.  "Analyze the JSON data from my last 5 workouts and tell me if my total volume for bench press is trending up."

---

## 6. Advanced & Conversational Scenarios

This section tests the agent's ability to synthesize information from multiple documents, ask clarifying questions, and handle more complex, multi-step user requests.

### User Prompts:

1.  **Goal-Oriented Planning & Information Gap Analysis**
    *   **Prompt:** "I'm training for GORUCK Selection. I have two months. What information do you still need from me before you can suggest a fitness program?"
    *   **Ideal Agent Behavior:**
        *   Recognizes "GORUCK Selection" as a high-intensity endurance event (may require a web search if not in its knowledge base).
        *   Scans all existing `Fitness Guide` documents (`Baseline Assessment`, `Personal Records`, `Coaching Plan Overview`, etc.).
        *   Identifies missing critical information, such as: current endurance benchmarks (e.g., timed runs, rucks), specific strength numbers for load-bearing exercises, current weekly training volume, and any specific weaknesses.
        *   Responds with a clear, concise list of questions for the user (e.g., "To create the best plan, I need to know: 1. Your current best 5-mile run time. 2. Your current best 12-mile ruck time and the weight you carried. 3. Your max pull-ups and push-ups. 4. How many hours per week are you currently training?").

2.  **High-Level Program Generation**
    *   **Prompt:** "Okay, I've updated my files with that info. Now, can you create the best possible 2-month fitness program to get me in shape for GORUCK Selection?"
    *   **Ideal Agent Behavior:**
        *   Acknowledges the new information.
        *   Synthesizes the user's data to create a high-level, periodized 8-week plan.
        *   Uses the `Program Generator.md` template as a basis.
        *   The plan should logically progress, incorporating key elements for the event: rucking, running, high-rep calisthenics, and work capacity/HIIT sessions.
        *   It should include a taper week before the event.
        *   Presents the plan in a clear, week-by-week format.

3.  **Dynamic Workout Progression**
    *   **Prompt:** "Here's my workout from today: [user pastes a completed workout log]. Please give me my next workout."
    *   **Ideal Agent Behavior:**
        *   Parses the user-provided workout log.
        *   References the user's current program in `Program Templates` or `Coaching Plan Overview`.
        *   Determines the *next* scheduled workout in the sequence.
        *   Applies logic from `Next Workout Planning.md`, potentially modifying the upcoming workout based on the performance of the one just completed (e.g., "I see you hit your target reps easily on the bench press, so for the next session, I'll increase the weight as planned. However, you noted your RPE on lunges was very high, so we'll keep the weight the same but focus on form.").

4.  **Cross-Domain Integration (Fitness to Nutrition)**
    *   **Prompt:** "That was a tough workout. Based on that, can you update my meal plan for the rest of the day?"
    *   **Ideal Agent Behavior:**
        *   Recognizes that there are no explicit "Meal Plan" documents in the provided file structure.
        *   Responds helpfully without hallucinating a meal plan.
        *   It should state its limitation clearly (e.g., "I don't have access to a pre-existing meal plan for you.").
        *   It should then provide general, context-aware advice (e.g., "However, after a high-volume strength workout like that, it's crucial to replenish glycogen and support muscle repair. I'd recommend a meal with 30-40g of protein and 60-80g of carbohydrates within the next 2 hours. Would you like some examples of meals that fit this profile?").

5.  **Item/Exercise Substitution**
    *   **Prompt:** "My workout calls for barbell back squats, but my gym's squat racks are all taken. What's a good replacement?"
    *   **Ideal Agent Behavior:**
        *   References the `Exercise Library/Exercise Template.md` for squats.
        *   Identifies the primary movement pattern (squat) and muscles worked.
        *   Suggests several valid alternatives based on common equipment availability, explaining the pros and cons of each.
        *   Example response: "Since the squat racks are busy, here are a few good alternatives: 1. **Dumbbell Goblet Squats:** These are great for maintaining an upright torso. You might need to use higher reps as the weight will be lighter. 2. **Bulgarian Split Squats:** Excellent for unilateral strength and stability. 3. **Leg Press:** If a machine is free, this can effectively target your quads and glutes, though it's less of a full-body stability challenge. For today, I'd recommend Bulgarian Split Squats to keep the stability element."

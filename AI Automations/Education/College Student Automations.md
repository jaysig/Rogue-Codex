# College Student Automations

Simple automation tools to help college students manage school work, stay organized, and save time using free and cheap AI tools.

## What This Is

These automations help students handle boring school tasks automatically so you can focus on learning and having fun. Think of it like having a personal assistant for school.

**Who This Helps:** College students, community college students, anyone in school  
**Tools Used:** n8n (free), Google tools, AI helpers  
**Time Saved:** 5-10 hours per week  
**Cost:** Free to $15/month  

---

## 📅 Smart Schedule Manager

**What It Does:** Keeps track of all your classes, assignments, and deadlines automatically.

**How It Works:**
1. Syncs all your class schedules from different apps
2. Adds assignment deadlines from syllabi
3. Sends reminders before due dates
4. Blocks study time in your calendar
5. Warns you about schedule conflicts

**What You Need:**
- Google Calendar (free)
- Your class syllabi (PDF files)
- n8n account (free)
- Phone for notifications

**Step-by-Step n8n Setup:**

1. **Create Schedule Management Workflow**
   - Start new workflow called "Smart Schedule Manager"
   - Add "Google Calendar" node connected to your school calendar

2. **Extract Due Dates from Syllabi**
   - Add "Google Drive" node to watch for new syllabus uploads
   - Connect "OpenAI" node with prompt: "Find all assignment due dates in this syllabus and list them with course name and assignment type"
   - Use "Extract from File" node for PDF syllabi

3. **Add Assignments to Calendar**
   - Use "Google Calendar" node to create events for each due date
   - Set multiple reminders automatically:
     - 1 week before (for big projects)
     - 3 days before (start working reminder)
     - 1 day before (final check reminder)

4. **Block Study Time**
   - Add "Code" node to calculate needed study hours
   - Create "Focus Time" blocks before each due date
   - Block out 2-hour chunks in your calendar automatically

5. **Set Up Conflict Warnings**
   - Use "IF" node to check for schedule overlaps
   - Send "Slack" or text message if too many assignments due same week
   - Suggest redistributing work or asking for extensions

6. **Create Daily Agenda**
   - Add "Schedule Trigger" to run every morning at 7 AM
   - Pull today's classes, assignments, and study blocks
   - Send summary text message to start your day organized

7. **Track Class Attendance**
   - Optional: Add location-based check-ins
   - Send reminder 15 minutes before each class
   - Track which classes you attend most/least

**Alternative: Make.com Setup**

If you prefer Make.com instead of n8n:

1. **Create Schedule Scenario**
   - Go to Make.com and create "Smart Schedule Manager"
   - Add "Google Calendar > Watch events" as trigger

2. **Extract Syllabus Due Dates**
   - Add "Google Drive > Watch files" for new syllabi
   - Connect "OpenAI > Create a chat completion"
   - Use prompt: "Find all assignment due dates in this syllabus"

3. **Add Calendar Events**
   - Use "Google Calendar > Create an event" for each due date
   - Set multiple reminders automatically
   - Create study time blocks before deadlines

4. **Daily Schedule Summary**
   - Add "Schedule" module for 7 AM daily trigger
   - Pull today's events from Google Calendar
   - Send summary via "SMS" or push notification

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build these scenarios faster.

**What You Get:**
- Never forget another assignment
- Better time management
- Less stress about deadlines
- Automatic study time blocking

---

## 📚 Research Paper Helper

**What It Does:** Helps you find sources, organize research, and track citations automatically.

**How It Works:**
1. Searches multiple databases for sources
2. Saves articles and creates bibliographies
3. Organizes notes by topic
4. Checks for citation formatting
5. Tracks word count and progress

**What You Need:**
- Google Drive or Dropbox
- Library database access
- n8n automation tool
- Citation manager (Zotero is free)

**Step-by-Step n8n Setup:**

1. **Create Research Automation Workflow**
   - Start workflow called "Research Paper Helper"
   - Add "Manual Trigger" to start research for each new paper

2. **Set Up Source Finding**
   - Add "HTTP Request" nodes for:
     - Google Scholar searches
     - Your library's database
     - Free research sites like JSTOR, PubMed
   - Use search terms you provide to find relevant articles

3. **Organize Sources Automatically**
   - Add "Google Drive" node to create folders for each paper topic
   - Use "Zotero" node to save articles with automatic citations
   - Tag sources by subtopic (introduction, methods, conclusion)

4. **Extract Key Information**
   - Add "OpenAI" node to read abstracts and pull out:
     - Main research question
     - Key findings
     - Relevant quotes for your paper
   - Save summaries in organized notes

5. **Track Citation Format**
   - Set up "Zotero" or citation tool integration
   - Automatically format citations in APA, MLA, or Chicago style
   - Create bibliography as you add sources

6. **Monitor Progress**
   - Use "Google Docs" node to track word count
   - Set milestones: outline (day 3), first draft (day 7), final (day 10)
   - Send progress reminders and encouragement

7. **Find Related Sources**
   - When you add a good source, automatically search for:
     - Papers that cite this source
     - Papers by the same author
     - Similar topics in same journal

**Alternative: Make.com Setup**

1. **Create Research Scenario**
   - Name scenario "Research Paper Helper"
   - Add "Webhooks > Custom webhook" to start research

2. **Search Academic Sources**
   - Add "HTTP > Make a request" modules for:
     - Google Scholar API
     - Your library database
     - PubMed or JSTOR

3. **Organize Research Automatically**
   - Add "Google Drive > Create a folder" for each paper topic
   - Use "Dropbox > Upload a file" to save articles
   - Connect "Zotero" if available for citation management

4. **Extract Key Information**
   - Add "OpenAI > Create a chat completion"
   - Extract: research question, findings, quotes
   - Save summaries in organized notes

5. **Track Writing Progress**
   - Add "Google Docs > Get document" to monitor word count
   - Set milestone reminders and encouragement messages

**What You Get:**
- Faster research process
- Properly formatted citations
- Organized notes and sources
- Progress tracking for big papers

### 🤖 LLM-Only Alternative

**If you just need this done once or occasionally...**

You can get research help for any paper in a single conversation with an AI assistant. Great for shorter papers, quick research needs, or when you're just starting to learn about a topic.

**What an LLM can do:**
Help you find research directions, organize your thoughts, create outlines, and suggest search terms and sources to look for.

**Simple Multi-Step Prompt:**

```
I'm writing a research paper about [YOUR TOPIC] for [CLASS NAME]. The paper needs to be [LENGTH] and is due [DATE].

My assignment requirements:
- [LIST ANY SPECIFIC REQUIREMENTS: number of sources, citation style, etc.]

Please help me with:

1. RESEARCH STRATEGY
   - Break down my topic into 3-4 key research questions
   - Suggest the best types of sources to look for
   - Recommend specific databases and search terms

2. PAPER OUTLINE
   - Create a logical structure for my paper
   - Suggest what to cover in each section
   - Estimate how many sources I need for each part

3. SOURCE HUNTING HELP
   - List specific journals that would have relevant articles
   - Suggest government databases or reports to check
   - Recommend key authors or experts in this field

4. CITATION GUIDANCE
   - Remind me about [APA/MLA/Chicago] formatting rules
   - Show example citations for the types of sources I'll use
   - Explain how to organize my bibliography

5. RESEARCH SCHEDULE
   - Break down the work by day until my due date
   - Suggest milestones and deadlines
   - Include time for writing and revision

Please make this practical and actionable for a college student.
```

**JSON Template Option:**
For organized research planning, add this:

```
Format the research plan as JSON:
{
  "research_questions": [
    "Main question 1...",
    "Supporting question 2..."
  ],
  "search_strategy": {
    "databases": ["PubMed", "JSTOR", "..."],
    "keywords": ["term1", "term2", "..."],
    "source_types": ["peer-reviewed articles", "books", "..."]
  },
  "paper_outline": {
    "introduction": "What to cover and estimated word count",
    "body_sections": ["Section 1 topic", "Section 2 topic"],
    "conclusion": "Key points to summarize"
  },
  "schedule": [
    {"day": 1, "task": "Research phase 1", "goal": "Find 5 sources"},
    {"day": 2, "task": "Research phase 2", "goal": "Read and take notes"}
  ]
}
```

**What this approach can't do:**
- Won't automatically search databases for you
- Can't save or organize your actual sources
- No automatic citation formatting
- Won't track your writing progress over time

**When to upgrade to full automation:**
- You're writing multiple research papers per semester
- You want automatic source saving and organization
- You need help tracking citations across many projects
- You collaborate on research with other students regularly

---

## 💰 Money Tracker for Students

**What It Does:** Watches your spending and helps you stick to your budget.

**How It Works:**
1. Connects to your bank account or apps
2. Categorizes spending automatically
3. Warns when you're overspending
4. Tracks textbook and supply costs
5. Finds student discounts automatically

**What You Need:**
- Banking app or spending tracker
- Google Sheets (free)
- n8n automation
- Student ID for discounts

**Setup Steps:**
1. Connect your spending apps to Google Sheets
2. Set up budget categories (food, books, fun)
3. Create spending limit alerts
4. Add student discount finder

**What You Get:**
- Know where your money goes
- Stay within budget
- Find student discounts
- Save money for important things

---

## 📖 Study Group Coordinator

**What It Does:** Organizes study groups and shares materials automatically.

**How It Works:**
1. Polls classmates for best meeting times
2. Books study rooms automatically
3. Shares notes and materials with the group
4. Reminds everyone about study sessions
5. Tracks who's coming to each session

**What You Need:**
- Group chat (WhatsApp, Discord, etc.)
- Calendar scheduling tool (Calendly)
- File sharing (Google Drive, Dropbox)
- n8n for coordination

**Setup Steps:**
1. Set up group chat and file sharing
2. Connect scheduling tools
3. Create reminder systems
4. Link to campus room booking if available

**What You Get:**
- Easy study group organization
- Better group communication
- Shared study materials
- Higher attendance at sessions

---

## 🎯 Grade Tracker & Predictor

**What It Does:** Tracks all your grades and predicts your final GPA.

**How It Works:**
1. Records grades from all classes
2. Calculates current GPA automatically
3. Predicts final grades based on remaining work
4. Shows what scores you need for target grades
5. Alerts you when grades are falling

**What You Need:**
- Google Sheets or Excel
- Access to your student portal
- n8n automation
- Grade information from syllabi

**Setup Steps:**
1. Set up grade tracking spreadsheet
2. Connect to student portal if possible
3. Add grade calculation formulas
4. Set up low-grade alerts

**What You Get:**
- Clear picture of academic performance
- Know exactly what grades you need
- Early warning for struggling classes
- Motivation from tracking improvement

---

## 📱 Campus Life Assistant

**What It Does:** Keeps you informed about campus events, dining, and opportunities.

**How It Works:**
1. Monitors campus event calendars
2. Checks dining hall menus and hours
3. Finds scholarship and internship opportunities
4. Tracks library hours and availability
5. Sends weather alerts for outdoor events

**What You Need:**
- Campus app or website access
- Email for notifications
- n8n automation tool
- Location services for weather

**Setup Steps:**
1. Connect to your campus information systems
2. Set up notification preferences
3. Add scholarship/internship search terms
4. Link weather service for alerts

**What You Get:**
- Never miss campus opportunities
- Better meal planning
- Scholarship alerts
- Library study space updates

---

## 🎯 Getting Started (Super Easy)

### Start Free
- Use n8n free tier (plenty for students)
- Google tools are free with student email
- Many AI tools have student discounts
- University often provides free software

### Pick One to Start
- Choose the automation that would help you most
- Set it up completely before adding others
- Test with small amounts of data first
- Ask friends or IT help desk for assistance

### Learning Resources
- YouTube has tons of n8n tutorials
- Student tech groups on campus
- Online forums with friendly helpers
- University tech support

### Budget for Students
- n8n: Free (or $5/month for more features)
- Google Workspace: Free with .edu email
- AI tools: Often free student tiers
- Total cost: Usually under $15/month

---

## 🛡️ Student Tips

### Protect Your Privacy
- Use your student email for accounts
- Don't share login information
- Follow your school's tech policies
- Keep personal and school data separate

### Start Simple
- Begin with one class or subject
- Use tools you already know
- Don't try to automate everything at once
- Focus on your biggest time wasters first

### Get Help When Stuck
- University IT departments are helpful
- Study groups can learn together
- Online communities answer questions
- YouTube tutorials show everything step-by-step

---

## 📞 Common Student Questions

**Q: Is this cheating?**
A: These tools organize and remind you - they don't do your work for you. Always check your school's policies.

**Q: What if I'm not good with technology?**
A: Start with simple automations. Most students get basic ones working in an hour or two.

**Q: Will this work with my school's systems?**
A: Most schools use common platforms that work with these tools. Check with IT if unsure.

**Q: What happens when I graduate?**
A: You'll have valuable automation skills that employers love, plus you can adapt these for work life.

---

## 📈 What Students Say

### Time Savings
- "I save 8 hours a week on organizing and reminders"
- "Never missed a deadline since setting this up"
- "Study groups actually happen now"

### Grade Improvements
- "My GPA went up because I stay organized"
- "I know exactly what I need to study for"
- "No more scrambling before exams"

### Life Quality
- "Less stress about keeping track of everything"
- "More time for friends and activities"
- "Feel more in control of my college experience"

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
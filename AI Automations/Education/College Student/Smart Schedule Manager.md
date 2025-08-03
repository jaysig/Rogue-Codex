# Smart Schedule Manager

Keeps track of all your classes, assignments, and deadlines automatically.

## What This Does

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

---

## Step-by-Step n8n Setup

### 1. Create Schedule Management Workflow
- Start new workflow called "Smart Schedule Manager"
- Add "Google Calendar" node connected to your school calendar

### 2. Extract Due Dates from Syllabi
- Add "Google Drive" node to watch for new syllabus uploads
- Connect "OpenAI" node with prompt: "Find all assignment due dates in this syllabus and list them with course name and assignment type"
- Use "Extract from File" node for PDF syllabi

### 3. Add Assignments to Calendar
- Use "Google Calendar" node to create events for each due date
- Set multiple reminders automatically:
  - 1 week before (for big projects)
  - 3 days before (start working reminder)
  - 1 day before (final check reminder)

### 4. Block Study Time
- Add "Code" node to calculate needed study hours
- Create "Focus Time" blocks before each due date
- Block out 2-hour chunks in your calendar automatically

### 5. Set Up Conflict Warnings
- Use "IF" node to check for schedule overlaps
- Send "Slack" or text message if too many assignments due same week
- Suggest redistributing work or asking for extensions

### 6. Create Daily Agenda
- Add "Schedule Trigger" to run every morning at 7 AM
- Pull today's classes, assignments, and study blocks
- Send summary text message to start your day organized

### 7. Track Class Attendance
- Optional: Add location-based check-ins
- Send reminder 15 minutes before each class
- Track which classes you attend most/least

---

## Alternative: Make.com Setup

If you prefer Make.com instead of n8n:

### 1. Create Schedule Scenario
- Go to Make.com and create "Smart Schedule Manager"
- Add "Google Calendar > Watch events" as trigger

### 2. Extract Syllabus Due Dates
- Add "Google Drive > Watch files" for new syllabi
- Connect "OpenAI > Create a chat completion"
- Use prompt: "Find all assignment due dates in this syllabus"

### 3. Add Calendar Events
- Use "Google Calendar > Create an event" for each due date
- Set multiple reminders automatically
- Create study time blocks before deadlines

### 4. Daily Schedule Summary
- Add "Schedule" module for 7 AM daily trigger
- Pull today's events from Google Calendar
- Send summary via "SMS" or push notification

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build these scenarios faster.

---

## What You Get

- Never forget another assignment
- Better time management
- Less stress about deadlines
- Automatic study time blocking

---

## Cost Estimates

### Small Business (Individual Student)
**Monthly Operating Cost: $0-15**

**Breakdown:**
- n8n: Free tier (perfect for personal use)
- Google Calendar/Drive: Free (usually through school)
- OpenAI API: $5-15/month (syllabus processing and text analysis)
- SMS notifications: Free (through Google or carrier)

**Assumptions:**
- Processing 4-6 syllabi per semester
- Managing 15-25 assignments per semester
- Daily schedule notifications
- Basic conflict detection and reminders

### Medium Business (Student Organization/Study Group)
**Monthly Operating Cost: $30-80**

**Breakdown:**
- n8n Pro: $20/month (team features and higher usage)
- AI processing: $20-40/month (group schedule coordination)
- Calendar management: $10-20/month (shared calendar features)
- Communication tools: $10-20/month (group notifications and coordination)

**Assumptions:**
- Coordinating schedules for 20-50 students
- Managing group project deadlines
- Shared study session scheduling
- Group event coordination

### Enterprise (University/Department Level)
**Monthly Operating Cost: $500-1,500**

**Breakdown:**
- Enterprise automation: $200-400/month (institutional deployment)
- Advanced AI processing: $200-500/month (bulk syllabus processing)
- Integration platform: $100-300/month (LMS and university system integration)
- Student communication: $100-300/month (campus-wide notification system)

**Assumptions:**
- University-wide deployment for hundreds of students
- Integration with learning management systems (Canvas, Blackboard)
- Automated course registration and planning
- Campus-wide event and deadline coordination

---

## Getting Started Guide

### Budget Planning for Students
Start completely free and upgrade only if needed:
- Week 1: Set up basic n8n workflow with Google Calendar
- Week 2: Add syllabus processing with free AI tier
- Month 1: Add SMS notifications if helpful
- Semester 2: Consider premium features if you're using heavily

---

## Best Practices

### Academic Organization
- Upload all syllabi at the beginning of each semester
- Review and adjust study time blocks based on actual workload
- Use consistent naming for courses and assignments
- Backup your calendar data regularly

### Time Management
- Block study time immediately when assignments are added
- Build in buffer time for large projects
- Set realistic study session lengths (2-3 hours max)
- Include breaks and meals in your daily schedule

---

## Common Questions

**Q: What if my professor changes assignment dates?**
A: The system can detect changes if you re-upload updated syllabi, but always check with professors directly for changes.

**Q: Can this work with my school's learning management system?**
A: Basic integration works through email notifications and calendar exports. Full LMS integration requires more setup.

**Q: Will this help me study better?**
A: It helps you stay organized and never miss deadlines, but you still need to do the actual studying during blocked time.

**Q: What if I don't want to share my calendar data?**
A: Use a separate school-only Google account, or set up local calendar systems that don't sync to cloud services.

---

## Success Metrics

### Track These Numbers
- Percentage of assignments submitted on time
- Amount of last-minute cramming reduced
- Study session consistency and completion
- Overall stress level about deadlines

### Expect These Results
- 95%+ assignment submission rate improvement
- 50% reduction in deadline-related stress
- 30% more consistent study habits
- Better work-life balance through time blocking

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
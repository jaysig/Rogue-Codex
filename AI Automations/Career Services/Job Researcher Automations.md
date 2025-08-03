# Job Researcher Automations

Easy automation workflows to help job seekers find opportunities, track applications, and land interviews using smart AI tools.

## What This Is

These automations help people looking for jobs work smarter, not harder. Like having a personal career coach and research assistant working 24/7.

**Who This Helps:** Job seekers, career changers, recent graduates, anyone looking for work  
**Tools Used:** n8n (free), LinkedIn, job boards, AI research tools  
**Time Saved:** 15-20 hours per week on job searching  
**Results:** More interviews, better applications, faster job search  

---

## 🔍 Smart Job Discovery Engine

**What It Does:** Automatically finds job openings that match your skills and preferences from multiple job sites.

**How It Works:**
1. Searches LinkedIn, Indeed, Glassdoor, and other job boards
2. Filters jobs by your salary, location, and skill requirements
3. Removes duplicate postings automatically
4. Scores each job based on how well it matches you
5. Sends daily digest emails with best matches

**What You Need:**
- Resume uploaded to identify your skills
- n8n automation account (free)
- Access to major job boards
- Email for daily job alerts

**Step-by-Step n8n Setup:**

1. **Create Job Search Workflow**
   - Start workflow called "Smart Job Discovery Engine"
   - Add "Schedule Trigger" to search for jobs every morning at 8 AM

2. **Set Up Job Board Connections**
   - Add "HTTP Request" nodes for different job sites:
     - LinkedIn Jobs API
     - Indeed scraping
     - Glassdoor searches
     - Company career pages
   - Use your search criteria for each site

3. **Analyze Your Skills**
   - Add "OpenAI" node to read your resume
   - Extract skills, experience level, job titles
   - Create matching criteria: "Must have: Python, JavaScript" / "Nice to have: AWS, React"

4. **Filter and Score Jobs**
   - Use "Code" node to score each job:
     - Required skills match = 50 points
     - Salary range good = 30 points
     - Location preference = 20 points
   - Only show jobs scoring 70+ points

5. **Remove Duplicates**
   - Add "Remove Duplicates" node
   - Match by company name + job title
   - Keep the job posting with most complete information

6. **Create Daily Reports**
   - Use "Set" node to compile top 10 jobs
   - Add "Email" node to send digest each morning
   - Include: job title, company, salary, match score, apply link

7. **Track What You've Seen**
   - Save all job IDs in "Google Sheets"
   - Don't show jobs you've already seen
   - Track which types of jobs you actually apply to

**Alternative: Make.com Setup**

If you prefer Make.com instead of n8n:

1. **Create Job Search Scenario**
   - Name scenario "Smart Job Discovery Engine"
   - Add "Schedule" module to run every morning

2. **Connect Job Boards**
   - Add "HTTP > Make a request" for job sites:
     - LinkedIn Jobs API
     - Indeed job search
     - Company career pages
   - Use your criteria for each search

3. **Analyze and Score Jobs**
   - Add "OpenAI > Create a chat completion" to analyze job descriptions
   - Score based on skill matches and preferences
   - Filter out jobs below your threshold

4. **Remove Duplicates and Create Report**
   - Use "Tools > Remove duplicates" by company + title
   - Compile top matches with "Array aggregator"
   - Send daily digest via email with job links

💡 **Make MCP Tip**: The [Make MCP server](https://github.com/integromat/make-mcp-server) can help build job search scenarios in Claude Code.

**What You Get:**
- 50+ relevant jobs found daily
- No more manual searching across sites
- Only see jobs that actually match you
- Never miss newly posted opportunities

---

## 📋 Application Tracking System

**What It Does:** Keeps track of every job you apply to and manages all your follow-ups.

**How It Works:**
1. Records every application with company details
2. Tracks application status (applied, interview, rejected, offer)
3. Sets automatic follow-up reminders
4. Monitors response rates and success patterns
5. Organizes all related documents and communications

**What You Need:**
- Google Sheets or similar spreadsheet
- Calendar app for reminders
- n8n automation tool
- Email access for tracking responses

**Step-by-Step n8n Setup:**

1. **Create Application Tracking Workflow**
   - Start workflow called "Application Tracking System"
   - Add "Webhook" node to receive new application data

2. **Set Up Tracking Spreadsheet**
   - Create "Google Sheets" with columns:
     - Company, Job Title, Date Applied, Status, Follow-up Date, Interview Date, Notes
   - Add "Google Sheets" node to log each application automatically

3. **Capture Application Data**
   - Use "Set" node to collect info when you apply:
     - Company name and job details
     - Application date and method (LinkedIn, company site, etc.)
     - Contact person if available
   - Send this data through webhook

4. **Set Up Follow-up Reminders**
   - Add "Wait" node for different timeframes:
     - 1 week: send thank you email
     - 2 weeks: follow up on application status
     - 1 month: check if position is still open

5. **Track Email Responses**
   - Add "IMAP Email" node to monitor for company responses
   - Use filters to catch emails from companies you applied to
   - Automatically update spreadsheet when you get responses

6. **Create Weekly Reports**
   - Add "Schedule Trigger" for Monday mornings
   - Compile stats: applications sent, responses received, interviews scheduled
   - Send summary email with this week's action items

7. **Monitor Success Patterns**
   - Use "Code" node to analyze which applications work best:
     - Which job boards give most responses
     - What time of week gets fastest replies
     - Which types of companies respond most

**Alternative: Make.com Setup**

1. **Create Application Tracking Scenario**
   - Name scenario "Application Tracking System"
   - Add "Webhooks > Custom webhook" for new applications

2. **Set Up Tracking System**
   - Add "Google Sheets > Add a row" to log applications
   - Include: company, job title, date, status, follow-up date
   - Auto-populate current date and initial status

3. **Monitor Email Responses**
   - Add "Gmail > Watch emails" to catch company replies
   - Use filters to identify emails from applied companies
   - Automatically update application status

4. **Schedule Follow-ups**
   - Add "Sleep" modules for different timeframes:
     - 1 week: thank you email
     - 2 weeks: status check
     - 1 month: position inquiry

5. **Generate Reports**
   - Add "Schedule" module for Monday morning reports
   - Compile stats from Google Sheets
   - Email weekly progress summary

**What You Get:**
- Never lose track of applications
- Professional follow-up every time
- Data on what's working best
- Organized approach to job searching

---

## 🏢 Company Intelligence Gatherer

**What It Does:** Automatically researches companies before you apply or interview.

**How It Works:**
1. Pulls company information from multiple sources
2. Finds recent news and developments
3. Identifies key people you should know about
4. Researches company culture and values
5. Creates summary reports for interview prep

**What You Need:**
- Company name or job posting URL
- Business news monitoring (Google Alerts)
- n8n automation platform
- Research report template

**Setup Steps:**
1. Set up automatic company data collection
2. Connect business news monitoring
3. Create company research report templates
4. Link LinkedIn for employee research

**What You Get:**
- Impressive knowledge in interviews
- Better understanding of company fit
- Conversation starters for networking
- More targeted applications

### 🤖 LLM-Only Alternative

**If you just need this done once or occasionally...**

You can research any company thoroughly in a single conversation with an AI assistant. Perfect for preparing for specific interviews or applications without setting up automation.

**What an LLM can do:**
Create a complete company research report with recent news, culture insights, key people, and interview talking points.

**Simple Multi-Step Prompt:**

```
I'm interviewing with [COMPANY NAME] for a [JOB TITLE] position. Please help me research this company.

Create a research report with these sections:

1. COMPANY OVERVIEW
   - What they do in simple terms
   - How they make money
   - Size and growth stage

2. RECENT NEWS (last 6 months)
   - Major announcements
   - Product launches
   - Leadership changes
   - Industry recognition

3. COMPANY CULTURE
   - Work environment and values
   - Employee reviews highlights
   - Remote work policies
   - Growth opportunities

4. KEY PEOPLE TO KNOW
   - CEO and leadership team
   - People in my target department
   - Anyone I might interview with

5. CONVERSATION STARTERS
   - Recent achievements to mention
   - Industry trends they're part of
   - Questions about their strategy
   - Smart questions about the role

6. POTENTIAL RED FLAGS
   - Recent negative news
   - Employee concerns
   - Financial challenges
   - Cultural issues to be aware of

Please format this as an easy-to-review document I can study before my interview.
```

**JSON Template Option:**
For organized notes, add this to your prompt:

```
Please format the key information as JSON:
{
  "company_snapshot": {
    "business_model": "...",
    "revenue": "...",
    "employee_count": "...",
    "recent_valuation": "..."
  },
  "recent_news": [
    {
      "headline": "...",
      "date": "...",
      "impact": "..."
    }
  ],
  "interview_talking_points": [
    "Point about recent growth...",
    "Question about their AI strategy..."
  ],
  "red_flags": ["Any concerns to be aware of..."]
}
```

**What this approach can't do:**
- Won't automatically update with new information
- No ongoing monitoring of company changes
- Can't set up alerts for new developments
- Limited to publicly available information

**When to upgrade to full automation:**
- You're job searching actively and researching 10+ companies
- You want ongoing updates about target companies
- You need alerts when dream companies have new openings
- You're in a long job search spanning several months

---

## 🤝 LinkedIn Networking Assistant

**What It Does:** Helps you build professional connections and engage with your network systematically.

**How It Works:**
1. Finds relevant people to connect with
2. Sends personalized connection requests
3. Schedules regular engagement with your network
4. Tracks who responds and engages back
5. Manages ongoing relationship building

**What You Need:**
- LinkedIn account (Premium recommended)
- Connection tracking system
- n8n automation setup
- Message templates for outreach

**Setup Steps:**
1. Define your target connections (companies, roles, locations)
2. Create personalized message templates
3. Set up connection request automation
4. Build engagement tracking system

**What You Get:**
- Growing professional network
- More people who can refer you
- Better visibility in your industry
- Warm introductions to opportunities

---

## 📧 Interview Preparation Automation

**What It Does:** Automatically prepares you for interviews with company-specific information and practice questions.

**How It Works:**
1. Researches the company and interviewers
2. Generates likely interview questions
3. Finds company-specific talking points
4. Creates personalized preparation materials
5. Schedules practice sessions and reminders

**What You Need:**
- Interview confirmation details
- AI question generator (ChatGPT works)
- n8n automation tool
- Practice scheduling system

**Setup Steps:**
1. Set up automatic company research triggers
2. Create interview question generators
3. Build preparation material templates
4. Link practice scheduling and reminders

**What You Get:**
- Thorough preparation for every interview
- Confidence from knowing company background
- Better answers to common questions
- Higher interview success rates

---

## 💌 Professional Communication Manager

**What It Does:** Handles all your job search emails professionally and consistently.

**How It Works:**
1. Sends thank you emails after interviews
2. Manages follow-up communication timelines
3. Tracks email responses and engagement
4. Personalizes messages based on company research
5. Maintains professional tone and timing

**What You Need:**
- Email templates for different situations
- Calendar integration for timing
- n8n automation platform
- Contact management system

**Setup Steps:**
1. Create email templates (thank you, follow-up, etc.)
2. Set up automatic sending schedules
3. Link calendar for interview follow-ups
4. Build response tracking system

**What You Get:**
- Professional communication every time
- Never forget to send thank you notes
- Consistent follow-up without being pushy
- Better impression with hiring managers

---

## 🎯 Getting Started (Anyone Can Do This)

### Start With The Basics
- Begin with job discovery automation
- Add application tracking next
- Build up to networking and research
- Master each tool before adding more

### Use Free Tools First
- n8n has a generous free tier
- Google Sheets for tracking
- LinkedIn basic account works
- Many job boards are free to search

### Learn As You Go
- Watch YouTube tutorials for each tool
- Join job seeker communities online
- Practice with a few applications first
- Ask for help when you get stuck

### Budget Expectations
- n8n: Free (or $20/month for advanced features)
- LinkedIn Premium: $30/month (worth it for job searching)
- AI tools: Often have free tiers
- Total: Can start free, upgrade to $50/month for full features

---

## 🛡️ Job Search Best Practices

### Stay Professional
- All automation should feel personal and genuine
- Follow company application instructions
- Respect people's time and preferences
- Build real relationships, not just collect contacts

### Keep It Legal and Ethical
- Follow job board terms of service
- Don't spam or over-automate outreach
- Respect privacy and professional boundaries
- Be honest about your background and experience

### Maintain Quality Over Quantity
- Better to apply to fewer jobs with quality applications
- Focus on building genuine professional relationships
- Customize automation to feel personal
- Monitor and improve your success rates

---

## 📞 Common Job Seeker Questions

**Q: Will employers know I'm using automation?**
A: Good automation feels personal and professional. The goal is efficiency, not to replace genuine effort.

**Q: How long before I see results?**
A: Most people see more interviews within 2-3 weeks of setting up these systems.

**Q: What if I'm not tech-savvy?**
A: Start with simple tracking in Google Sheets. Add automation gradually as you learn.

**Q: Can this help with career changes?**
A: Yes! The research tools are especially helpful for learning about new industries.

---

## 📈 Success Metrics to Track

### Job Search Efficiency
- Applications sent per week
- Response rate from applications
- Time from application to interview
- Interview to offer conversion rate

### Network Growth
- New LinkedIn connections per month
- Informational interviews scheduled
- Referrals received
- Industry event attendance

### Quality Improvements
- Interview feedback scores
- Application completion rates
- Follow-up response rates
- Offer negotiation success

---

## 🏆 Real Job Seeker Results

### Faster Job Search
- "Found my job in 6 weeks instead of 6 months"
- "10x more relevant opportunities discovered"
- "Never missed a follow-up or thank you note"

### Better Interviews
- "Always impressed interviewers with company knowledge"
- "Felt confident and prepared for every interview"
- "Got second interviews 70% of the time"

### Stronger Network
- "Built 300+ professional connections in 3 months"
- "Received 12 referrals from automated networking"
- "Found hidden job opportunities through connections"

### Work-Life Balance
- "Job searching didn't take over my life"
- "More time for interview prep instead of job hunting"
- "Less stress from staying organized"

---

## 🚀 Advanced Job Search Strategies

### Market Intelligence
- Track hiring trends in your industry
- Monitor salary ranges for target roles
- Watch for company expansion announcements
- Identify growing companies early

### Personal Branding
- Automate professional content sharing
- Build thought leadership in your field
- Track engagement on your professional posts
- Maintain consistent online presence

### Strategic Timing
- Apply to jobs at optimal times
- Follow up at appropriate intervals
- Schedule outreach for maximum impact
- Time interview requests strategically

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
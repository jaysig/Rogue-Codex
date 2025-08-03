# Underwriter Automations

Simple automation workflows to help insurance underwriters work faster and smarter using n8n and AI tools.

## What This Is

These automations help underwriters handle paperwork, check risks, and make decisions faster. Think of it like having a smart assistant that never gets tired.

**Who This Helps:** Insurance underwriters, risk analysts, policy reviewers  
**Tools Used:** n8n (free automation tool), AI helpers, email, spreadsheets  
**Time Saved:** 2-3 hours per day  

---

## 🚨 Smart Document Checker

**What It Does:** Automatically reads and sorts new insurance applications so you don't have to.

**How It Works:**
1. New application arrives in email
2. AI reads the documents and pulls out important info
3. Checks for missing papers automatically
4. Sorts applications by risk level (low, medium, high)
5. Sends you a simple summary in email

**What You Need:**
- Email account (Gmail, Outlook)
- n8n account (free to start)
- AI service (ChatGPT or similar)

**Step-by-Step n8n Setup:**

1. **Create Document Processing Workflow**
   - Start new workflow called "Smart Document Checker"
   - Add "IMAP Email" node to watch your inbox for new applications

2. **Set Up Email Monitoring**
   - Connect your work email (Gmail, Outlook, etc.)
   - Filter for emails with subject containing "application" or from specific clients
   - Set to check every 5 minutes for new messages

3. **Extract Document Information**
   - Add "Extract from File" node to pull text from PDFs
   - Connect "OpenAI" node with prompt: "Read this insurance application and extract: applicant name, property address, coverage amount, any red flags"

4. **Create Risk Assessment**
   - Add "Code" node with simple risk scoring:
     - High coverage amount + poor credit = high risk
     - Flood zone + water damage history = high risk
     - Clean record + good credit = low risk

5. **Sort and Organize**
   - Use "Switch" node to route applications:
     - Low risk → auto-approve queue
     - Medium risk → standard review queue  
     - High risk → urgent review queue

6. **Track Everything**
   - Add "Google Sheets" node to log all applications
   - Include date received, risk score, missing documents
   - Create automatic status updates

7. **Send Smart Alerts**
   - Use "Email" node to send summaries:
     - "5 new applications: 2 low risk, 2 medium, 1 high risk"
     - Include missing document list for each application

**What You Get:**
- No more sorting through piles of papers
- Quick risk scores for each application
- Missing document alerts
- 90% faster initial review

---

## 📊 Risk Alert System

**What It Does:** Watches for high-risk situations and tells you right away.

**How It Works:**
1. Monitors all your active policies
2. Checks news for problems (floods, accidents, etc.)
3. Looks at market changes that affect risk
4. Sends instant alerts to your phone or email
5. Creates daily risk reports automatically

**What You Need:**
- Policy database access
- News monitoring service
- n8n automation tool
- Text/email alerts

**Step-by-Step n8n Setup:**

1. **Create Risk Monitoring Workflow**
   - Start workflow called "Risk Alert System"
   - Add "Schedule Trigger" to check for risks every hour

2. **Monitor News and Events**
   - Add "RSS" node for weather alerts and natural disasters
   - Add "Twitter" node to search for: "flood OR fire OR storm OR earthquake"
   - Add location filters for your coverage areas

3. **Connect Policy Database**
   - Add "MySQL" or database node to access your active policies
   - Filter policies by location and coverage type
   - Match policies with current risk events

4. **Set Up Risk Scoring**
   - Add "Code" node with risk calculations:
     - Severe weather warning + property policies = high alert
     - Market crash + investment policies = medium alert
     - Industry news + commercial policies = low alert

5. **Create Smart Alerts**
   - Use "IF" node for different risk levels:
     - High risk → send text message immediately
     - Medium risk → send email within 1 hour
     - Low risk → add to daily report

6. **Generate Daily Reports**
   - Add "Set" node to compile all risk events
   - Use "Email" node to send daily summary at 8 AM
   - Include recommended actions for each risk

7. **Track Alert History**
   - Store all alerts in "Google Sheets" for tracking
   - Note which alerts led to claims
   - Improve risk scoring over time

**What You Get:**
- Never miss important risk changes
- Daily summary reports
- Instant alerts for urgent issues
- Better decision-making info

---

## 📋 Client Update Machine

**What It Does:** Keeps clients informed without you writing emails all day.

**How It Works:**
1. Tracks where each application is in the process
2. Sends automatic updates to clients
3. Schedules follow-up calls
4. Creates personalized messages
5. Handles routine questions automatically

**What You Need:**
- Client contact database
- Email system
- n8n automation platform
- Pre-written message templates

**Step-by-Step n8n Setup:**

1. **Create Client Communication Workflow**
   - Start workflow called "Client Update Machine"
   - Add "Webhook" node to receive application status changes

2. **Set Up Status Tracking**
   - Connect to your policy management system
   - Track status changes: submitted → review → underwriting → approved/denied
   - Capture timestamps for each stage

3. **Create Email Templates**
   - Add "Email" nodes for each status:
     - "We received your application" (immediate)
     - "Your application is under review" (day 3)
     - "We need additional information" (if missing docs)
     - "Your policy is approved" (final decision)

4. **Add Personal Touches**
   - Use "Set" node to include personal details:
     - "Hi {{ $json.clientName }}"
     - "Your {{ $json.propertyAddress }} application"
     - Reference specific policy details

5. **Schedule Follow-ups**
   - Add "Wait" nodes for appropriate delays:
     - Send acknowledgment immediately
     - Follow up after 3 business days
     - Weekly updates for complex cases

6. **Handle Common Questions**
   - Add "Email Trigger" for incoming questions
   - Use "AI" node to generate responses to common questions
   - Route complex questions to human underwriters

7. **Track Communication History**
   - Log all communications in "Google Sheets"
   - Include client satisfaction ratings
   - Note which messages get the best responses

**What You Get:**
- Happy clients who stay informed
- 70% less time writing emails
- Fewer "what's my status?" phone calls
- Professional communication every time

---

## 💰 Pricing Helper

**What It Does:** Calculates fair prices based on current market data.

**How It Works:**
1. Gathers latest pricing from competitors
2. Checks current risk factors
3. Reviews your profit targets
4. Suggests optimal pricing
5. Updates pricing guides automatically

**What You Need:**
- Market data sources
- Competitor pricing info
- n8n automation tool
- Spreadsheet or pricing system

**Setup Steps:**
1. Find reliable data sources
2. Set up automatic data collection
3. Create pricing calculation rules
4. Test with known examples

**What You Get:**
- Always competitive pricing
- Data-driven decisions
- Faster quote turnaround
- Better profit margins

---

## 📈 Performance Dashboard

**What It Does:** Shows how well you're doing in simple charts and numbers.

**How It Works:**
1. Collects data from all your systems
2. Creates easy-to-read charts
3. Tracks your key goals
4. Compares to last month/year
5. Highlights areas needing attention

**What You Need:**
- Access to your work systems
- Dashboard tool (Google Sheets works)
- n8n for data collection
- 15 minutes to set up charts

**Setup Steps:**
1. List what numbers matter most to you
2. Connect to your data sources
3. Create simple charts and graphs
4. Set up automatic updates

**What You Get:**
- Clear picture of your performance
- Spot problems early
- Celebrate your wins
- Data to support pay raises

---

## 🎯 Getting Started

### Choose One First
Pick the automation that would save you the most time right now. Don't try to do all of them at once.

### Start Simple
- Begin with the free version of n8n
- Use tools you already know (email, spreadsheets)
- Test everything with fake data first
- Ask for help when you need it

### Build Skills Gradually
- Watch YouTube tutorials for n8n basics
- Join online communities for help
- Practice with simple workflows first
- Add more features as you learn

### Cost Expectations
- n8n: Free for basic use, $20/month for more features
- AI services: $10-20/month for light use
- Total: Usually under $50/month per person

---

## 🛡️ Important Notes

### Keep It Secure
- Never share login passwords
- Use secure connections only
- Follow your company's data rules
- Regular security checkups

### Start Small
- Test with one type of application first
- Get comfortable before expanding
- Train your team gradually
- Measure results as you go

### Get Support
- Your IT team can help with setup
- Online communities answer questions
- Video tutorials show step-by-step
- Start with simple examples

---

## 📞 Common Questions

**Q: Is this hard to learn?**
A: Start with simple automations. Most people get basic workflows running in a few hours.

**Q: Will this replace my job?**
A: No! It makes you better at your job by handling boring tasks so you can focus on important decisions.

**Q: What if something breaks?**
A: All automations can be turned off instantly. Always keep backup processes ready.

**Q: How much time does setup take?**
A: Simple automations: 2-4 hours. Complex ones: 1-2 days. But then they run forever.

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
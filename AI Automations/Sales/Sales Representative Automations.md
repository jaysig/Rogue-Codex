# Sales Representative Automations

Simple automation workflows to help sales reps find better leads, close more deals, and spend less time on paperwork using smart AI tools.

## What This Is

These automations handle the repetitive parts of sales so you can focus on building relationships and closing deals. Like having a personal sales assistant that works 24/7.

**Who This Helps:** Sales representatives, account managers, business development reps, sales managers  
**Tools Used:** n8n or Make.com, CRM software, email tools, AI helpers  
**Time Saved:** 10-15 hours per week  
**Results:** 30-50% more qualified leads, 25% faster deal closing  

---

## 🎯 Lead Qualification Engine

**What It Does:** Automatically scores new leads and sends hot prospects to you immediately while filtering out tire kickers.

**How It Works:**
1. Watches for new leads from website forms, social media, and referrals
2. Researches each lead's company size, budget, and buying signals
3. Gives each lead a "hotness" score based on your ideal customer profile (example: Stratton Financial scored 94/100)
4. Routes hot leads to you instantly and warm leads to nurturing sequences
5. Tracks which lead sources produce the best customers

**What You Need:**
- Website contact forms or lead magnets
- CRM system (HubSpot, Salesforce, Pipedrive)
- Company research tools (LinkedIn, Clearbit)
- Email and SMS for notifications

**Step-by-Step n8n Setup:**

1. **Create Lead Qualification Workflow**
   - Start new workflow called "Lead Qualification Engine"
   - Add "Webhook" node to receive leads from website forms

2. **Research Lead Company**
   - Add "HTTP Request" node to lookup company on LinkedIn or Clearbit
   - Extract: company size, industry, revenue, recent news
   - Use "OpenAI" node to analyze: "Is this company a good fit for [your product]?"

3. **Score Lead Quality**
   - Add "Code" node with scoring system:
     - Company size match = 30 points
     - Budget indicators = 25 points
     - Urgency signals = 20 points
     - Authority level = 25 points
   - Total score determines lead temperature

4. **Route by Score**
   - Use "Switch" node for different score ranges:
     - 80+ points = Hot lead (immediate alert)
     - 50-79 points = Warm lead (add to nurture sequence)
     - Below 50 = Cold lead (monthly newsletter only)

5. **Alert Sales Rep**
   - For hot leads: Send instant SMS and email with lead details
   - Include research summary and suggested talking points
   - Add to CRM with high priority flag

**Alternative: Make.com Setup**

1. **Create Lead Scoring Scenario**
   - Name scenario "Lead Qualification Engine"
   - Add "Webhooks > Custom webhook" for form submissions

2. **Lead Research**
   - Add "LinkedIn" or "Clearbit" module for company data
   - Use "OpenAI > Create a chat completion" to analyze fit
   - Extract key buying signals and decision maker info

3. **Scoring and Routing**
   - Add "Math > Perform a function" to calculate lead score
   - Use "Router" to send leads down different paths
   - Hot leads get immediate notifications, others go to nurturing

4. **CRM Integration**
   - Add "HubSpot > Create contact" or similar CRM module
   - Include lead score and research notes
   - Set follow-up tasks automatically

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build lead scoring scenarios faster.

**What You Get:**
- Only talk to leads who can actually buy
- Never miss a hot prospect again
- Know exactly what to say before you call
- Focus time on deals most likely to close

---

## 📧 Follow-up Sequence Manager

**What It Does:** Sends perfectly timed follow-up emails and reminds you when to call, so no lead falls through the cracks.

**How It Works:**
1. Starts different email sequences based on lead type and interest level
2. Sends value-added content, case studies, and soft pitches automatically
3. Tracks email opens, clicks, and replies to gauge interest
4. Schedules phone call reminders at optimal times
5. Moves engaged leads to "ready to buy" list

**What You Need:**
- Email marketing platform (Mailchimp, ConvertKit, ActiveCampaign)
- CRM with contact management
- Calendar app for scheduling
- Pre-written email templates

**Step-by-Step n8n Setup:**

1. **Create Follow-up Workflow**
   - Start workflow called "Follow-up Sequence Manager"
   - Add "CRM Trigger" when new lead is added

2. **Determine Sequence Type**
   - Use "Switch" node based on lead source and interest:
     - Downloaded pricing guide = pricing sequence
     - Attended webinar = demo sequence
     - General inquiry = education sequence

3. **Schedule Email Sequence**
   - Add "Wait" nodes between emails:
     - Day 1: Welcome and resource delivery
     - Day 3: Case study with similar company
     - Day 7: Educational content
     - Day 14: Soft pitch with calendar link

4. **Track Engagement**
   - Monitor email opens and clicks
   - Use "IF" node: "If email opened 3+ times, mark as hot"
   - Score engagement level and update CRM

5. **Schedule Call Reminders**
   - Add task to CRM: "Call [name] about [specific interest]"
   - Include context from email interactions
   - Set optimal call time based on their timezone

**Alternative: Make.com Setup**

1. **Create Follow-up Scenario**
   - Name scenario "Follow-up Sequence Manager"
   - Add "CRM > Watch contacts" for new leads

2. **Sequence Logic**
   - Use "Router" to determine appropriate sequence
   - Add "Email > Send email" modules with delays
   - Include personalized content based on lead source

3. **Engagement Tracking**
   - Add "Email > Watch opens/clicks" modules
   - Update lead score based on engagement
   - Move highly engaged leads to priority list

4. **Task Creation**
   - Add "CRM > Create task" for call reminders
   - Include conversation context and suggested approach

**What You Get:**
- 5x more touchpoints without extra work
- Know exactly when prospects are engaged
- Never forget to follow up again
- Professional, consistent communication

---

## 📋 Proposal Generator

**What It Does:** Creates custom proposals with accurate pricing in minutes instead of hours.

**How It Works:**
1. Pulls client information and requirements from your CRM
2. Selects appropriate proposal template based on deal type
3. Calculates pricing based on your rules and current rates
4. Generates professional PDF with your branding
5. Tracks when proposals are opened and sends follow-up reminders

**What You Need:**
- Proposal templates (Word, Google Docs, or specialized software)
- Pricing calculator or rate sheets
- Digital signature tool (DocuSign, HelloSign)
- CRM with opportunity tracking

**Step-by-Step n8n Setup:**

1. **Create Proposal Workflow**
   - Start workflow called "Proposal Generator"
   - Add "Manual Trigger" when you're ready to create proposal

2. **Gather Client Data**
   - Pull opportunity details from CRM
   - Extract: company name, contact info, project scope, timeline
   - Include any special requirements or pricing adjustments

3. **Select Template and Calculate Pricing**
   - Use "Switch" node to choose template by project type
   - Add "Code" node to calculate pricing:
     - Base rate × hours + additional services
     - Apply discounts or rush charges
     - Include tax calculations

4. **Generate Proposal Document**
   - Add "Google Docs" or document generation node
   - Replace template variables with client-specific data
   - Include calculated pricing and payment terms

5. **Send and Track**
   - Add "Email" node to send proposal with tracking
   - Use "DocuSign" node for electronic signature
   - Set reminder to follow up in 3 days if not signed

**Alternative: Make.com Setup**

1. **Create Proposal Scenario**
   - Name scenario "Proposal Generator"
   - Add "Manual trigger" or "CRM > Watch opportunities"

2. **Data Collection and Template Selection**
   - Add "CRM > Get opportunity" details
   - Use "Router" to select template by deal type
   - Pull current pricing from spreadsheet or database

3. **Document Generation**
   - Add "Google Docs > Create document from template"
   - Replace placeholders with client and pricing data
   - Generate PDF for professional presentation

4. **Delivery and Tracking**
   - Add "Email > Send email" with proposal attached
   - Include "DocuSign > Send envelope" for signatures
   - Track opens and follow up automatically

**What You Get:**
- Cut proposal creation time by 80%
- Eliminate pricing errors and missed details
- Professional, consistent proposals every time
- Know immediately when prospects open proposals

---

## 📊 Pipeline Progress Tracker

**What It Does:** Monitors your deals and alerts you when opportunities are stuck or need attention.

**How It Works:**
1. Watches all deals in your CRM pipeline
2. Tracks how long deals stay in each stage
3. Identifies stuck opportunities that need action
4. Calculates probability of closing based on historical data
5. Sends daily pipeline health reports with action items

**What You Need:**
- CRM with deal pipeline (Salesforce, HubSpot, Pipedrive)
- Historical deal data for analysis
- Task management system
- Reporting dashboard

**Step-by-Step n8n Setup:**

1. **Create Pipeline Monitoring Workflow**
   - Start workflow called "Pipeline Progress Tracker"
   - Add "Schedule Trigger" to run daily at 8 AM

2. **Analyze Deal Progression**
   - Add "CRM" node to pull all active opportunities
   - Calculate days in current stage for each deal
   - Compare to average stage duration for similar deals

3. **Identify Stuck Deals**
   - Use "IF" node: "If deal in stage > 1.5x average time"
   - Flag deals that haven't progressed in 14+ days
   - Note deals approaching expected close dates

4. **Calculate Close Probability**
   - Add "Code" node with historical analysis:
     - Deals at this stage + days = X% close rate
     - Factor in deal size and lead source
     - Adjust for seasonal patterns

5. **Generate Action Report**
   - Create daily email with:
     - Deals needing immediate attention
     - Forecasted revenue for the month
     - Suggested actions for stuck deals
   - Include direct links to deals in CRM

**Alternative: Make.com Setup**

1. **Create Pipeline Monitoring Scenario**
   - Name scenario "Pipeline Progress Tracker"
   - Add "Schedule" module for daily analysis

2. **Deal Analysis**
   - Add "CRM > List opportunities" for active deals
   - Calculate stage duration and progression rates
   - Identify deals needing attention

3. **Probability Calculation**
   - Use "Math > Perform a function" for close probability
   - Based on historical data and current stage
   - Factor in deal characteristics

4. **Report Generation**
   - Add "Email > Send email" with daily summary
   - Include action items and priority deals
   - Link directly to CRM records

**What You Get:**
- Never let a good deal go cold
- Accurate sales forecasting
- Know exactly which deals to focus on today
- Catch pipeline problems before they hurt revenue

---

## 🧹 CRM Data Cleanup

**What It Does:** Keeps your CRM organized by finding duplicate contacts, updating old information, and filling in missing details.

**How It Works:**
1. Scans your CRM for duplicate contacts and companies
2. Merges duplicates while preserving all interaction history
3. Updates outdated contact information using web research
4. Fills in missing details like job titles and company info
5. Standardizes data format for better reporting

**What You Need:**
- CRM access (read and write permissions)
- Data enrichment service (Clearbit, ZoomInfo)
- Duplicate detection rules
- Data validation tools

**Step-by-Step n8n Setup:**

1. **Create Data Cleanup Workflow**
   - Start workflow called "CRM Data Cleanup"
   - Add "Schedule Trigger" to run weekly on Sundays

2. **Find Duplicate Contacts**
   - Add "CRM" node to export all contacts
   - Use "Code" node to identify potential duplicates:
     - Same email address
     - Similar names + same company
     - Same phone number

3. **Research and Enrich Data**
   - Add "Clearbit" or "LinkedIn" node to lookup contacts
   - Update missing job titles, company names, phone numbers
   - Verify email addresses are still valid

4. **Merge and Clean**
   - Present duplicate matches for review
   - Merge approved duplicates keeping all activity history
   - Standardize data formats (phone numbers, addresses)

5. **Generate Cleanup Report**
   - Email summary of changes made
   - List contacts that need manual review
   - Show data quality improvement metrics

**Alternative: Make.com Setup**

1. **Create Data Cleanup Scenario**
   - Name scenario "CRM Data Cleanup"
   - Add "Schedule" module for weekly cleaning

2. **Duplicate Detection**
   - Add "CRM > List contacts" for all records
   - Use "Tools > Remove duplicates" or custom logic
   - Flag potential matches for review

3. **Data Enrichment**
   - Add "Clearbit > Enrich contact" or similar service
   - Update missing information automatically
   - Validate email addresses and phone numbers

4. **Clean and Report**
   - Update CRM records with enriched data
   - Generate cleanup summary report
   - Track data quality improvements over time

**What You Get:**
- Clean, accurate CRM data you can trust
- No more embarrassing emails to wrong people
- Better reporting and segmentation
- Faster prospecting with complete contact info

---

## 🎯 Getting Started Guide

### Start With Lead Scoring
Most sales reps see immediate value from lead qualification - you'll stop wasting time on unqualified prospects within the first week.

### Use Your Existing CRM
Don't switch CRMs just for automation. Start with whatever system you're already using and connect automations to it.

### Begin With Email Sequences
Email follow-up automation is easy to set up and shows quick results. Start here before moving to more complex workflows.

### Budget Planning
- CRM: Usually $20-100/month per user
- n8n or Make.com: Free to $20/month for sales automations
- Data enrichment: $50-200/month depending on volume
- Total: Usually $100-300/month for complete sales automation

---

## 🛡️ Best Practices

### Maintain Personal Touch
- Always review automated messages before they go out
- Add personal notes to templated emails
- Use automation to remind you to call, not replace calls
- Keep relationship building as your top priority

### Track What Works
- Monitor response rates for different email sequences
- Test different subject lines and content
- Track which lead sources convert best
- Adjust automation based on results

### Stay Compliant
- Include unsubscribe options in all emails
- Respect CRM data privacy settings
- Follow your industry's communication regulations
- Keep customer consent records

---

## 📞 Common Questions

**Q: Will prospects know I'm using automation?**
A: Good automation feels helpful, not robotic. Always personalize messages and provide real value in every touchpoint.

**Q: What if automation sends the wrong message?**
A: Include approval steps for important communications and always review templates before they go live.

**Q: How do I know which leads to prioritize?**
A: Start with your current ideal customer profile. The automation will learn and improve scoring accuracy over time.

**Q: Can I still customize proposals for special deals?**
A: Absolutely. Automation creates the baseline proposal - you can always edit before sending to add special terms or pricing.

---

## 📈 Success Metrics

### Track These Numbers
- Percentage of leads qualified automatically vs manually
- Average time from lead to first meeting
- Email sequence open and response rates
- Number of deals in pipeline vs time invested

### Expect These Results
- 60% more qualified conversations from same lead volume
- 40% reduction in time spent on administrative tasks
- 25% improvement in deal closure rates
- 50% faster proposal generation and delivery

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
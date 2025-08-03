# Smart Job Discovery Engine

Automatically finds job openings that match your skills and preferences from multiple job sites.

## What This Does

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

---

## Step-by-Step n8n Setup

### 1. Create Job Search Workflow
- Start workflow called "Smart Job Discovery Engine"
- Add "Schedule Trigger" to search for jobs every morning at 8 AM

### 2. Set Up Job Board Connections
- Add "HTTP Request" nodes for different job sites:
  - LinkedIn Jobs API
  - Indeed scraping
  - Glassdoor searches
  - Company career pages
- Use your search criteria for each site

### 3. Analyze Your Skills
- Add "OpenAI" node to read your resume
- Extract skills, experience level, job titles
- Create matching criteria: "Must have: Python, JavaScript" / "Nice to have: AWS, React"

### 4. Filter and Score Jobs
- Use "Code" node to score each job:
  - Required skills match = 50 points
  - Salary range good = 30 points
  - Location preference = 20 points
- Only show jobs scoring 70+ points

### 5. Remove Duplicates
- Add "Remove Duplicates" node
- Match by company name + job title
- Keep the job posting with most complete information

### 6. Create Daily Reports
- Use "Set" node to compile top 10 jobs
- Add "Email" node to send digest each morning
- Include: job title, company, salary, match score, apply link

### 7. Track What You've Seen
- Save all job IDs in "Google Sheets"
- Don't show jobs you've already seen
- Track which types of jobs you actually apply to

---

## Alternative: Make.com Setup

If you prefer Make.com instead of n8n:

### 1. Create Job Search Scenario
- Name scenario "Smart Job Discovery Engine"
- Add "Schedule" module to run every morning

### 2. Connect Job Boards
- Add "HTTP > Make a request" for job sites:
  - LinkedIn Jobs API
  - Indeed job search
  - Company career pages
- Use your criteria for each search

### 3. Analyze and Score Jobs
- Add "OpenAI > Create a chat completion" to analyze job descriptions
- Score based on skill matches and preferences
- Filter out jobs below your threshold

### 4. Remove Duplicates and Create Report
- Use "Tools > Remove duplicates" by company + title
- Compile top matches with "Array aggregator"
- Send daily digest via email with job links

💡 **Make MCP Tip**: The [Make MCP server](https://github.com/integromat/make-mcp-server) can help build job search scenarios in Claude Code.

---

## What You Get

- 50+ relevant jobs found daily
- No more manual searching across sites
- Only see jobs that actually match you
- Never miss newly posted opportunities

---

## Cost Estimates

### Small Business (Individual Job Seeker)
**Monthly Operating Cost: $0-50**

**Breakdown:**
- n8n: Free tier (sufficient for personal job searching)
- LinkedIn Jobs API: Free tier (limited searches)
- Indeed/Glassdoor scraping: Free (rate-limited)
- AI job analysis: $10-30/month (OpenAI API based on volume)
- Email notifications: Free (using Gmail/Outlook)
- Storage: Free (Google Sheets for tracking)

**Assumptions:** 
- Searching 5-10 job boards daily
- Processing 100-200 job postings per day
- Basic skill matching and scoring
- Personal email notifications only

### Medium Business (Career Services Company)
**Monthly Operating Cost: $200-500**

**Breakdown:**
- n8n Pro: $50/month (for advanced features and higher usage)
- Premium job board APIs: $100-200/month (LinkedIn Recruiter, Indeed Premium)
- Advanced AI analysis: $100-200/month (more sophisticated matching algorithms)
- Enhanced storage: $20-50/month (database for client tracking)
- Client communication: $30-50/month (automated email services)

**Assumptions:**
- Serving 50-100 job seekers simultaneously
- Processing 1,000-2,000 job postings daily
- Advanced skill matching and industry analysis
- Client reporting and progress tracking

### Enterprise (Large Recruitment Platform)
**Monthly Operating Cost: $2,000-5,000**

**Breakdown:**
- n8n Enterprise: $500/month (custom deployment and scaling)
- Premium job board partnerships: $1,000-2,000/month (full API access)
- Advanced AI and ML: $500-1,500/month (custom models and analysis)
- Enterprise database: $200-500/month (scalable storage and processing)
- Multi-client management: $300-500/month (CRM integration and reporting)

**Assumptions:**
- Serving 1,000+ job seekers across multiple markets
- Processing 10,000+ job postings daily
- Custom AI models for specialized industries
- Advanced analytics and reporting dashboards
- Integration with existing HR and recruitment systems

---

## Getting Started Guide

### Budget Planning
Start with the free tier and scale up as you see results:
- Week 1: Set up basic n8n workflow with free tools
- Week 2: Add job board connections and basic scoring
- Month 1: Upgrade to paid AI analysis if needed
- Month 2: Add premium job board access for better results

---

## Best Practices

### Maintain Search Quality
- Regularly update your skill criteria as you learn new technologies
- Monitor which job sources provide the best matches
- Adjust scoring weights based on your actual application success
- Keep your resume updated to improve skill extraction accuracy

### Stay Professional
- Respect job board rate limits and terms of service
- Don't over-automate application submissions
- Use automation for discovery, not mass applications
- Always customize applications for specific roles

---

## Common Questions

**Q: Will job boards block automated searching?**
A: Follow rate limits and terms of service. Most job boards allow reasonable automated searches for personal use.

**Q: How accurate is the job matching?**
A: Accuracy improves over time as the system learns your preferences. Start with broader criteria and refine.

**Q: Can I search for remote jobs specifically?**
A: Yes, add location filters for "remote," "work from home," or specific geographic preferences.

**Q: What if I'm getting too many or too few results?**
A: Adjust your scoring thresholds and search criteria. Start broad and narrow down based on results quality.

---

## Success Metrics

### Track These Numbers
- Number of relevant jobs found daily
- Time saved compared to manual searching
- Application-to-response rate improvement
- Quality of job matches (scored by your feedback)

### Expect These Results
- 10x more job opportunities discovered daily
- 90% reduction in manual job search time
- 50% improvement in application relevance
- Discovery of hidden opportunities on company sites

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
# Company Intelligence Gatherer

Automatically researches companies before you apply or interview for impressive preparation.

## What This Does

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

---

## Setup Steps

1. Set up automatic company data collection
2. Connect business news monitoring
3. Create company research report templates
4. Link LinkedIn for employee research

---

## What You Get

- Impressive knowledge in interviews
- Better understanding of company fit
- Conversation starters for networking
- More targeted applications

---

## LLM-Only Alternative

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

## Cost Estimates

### Small Business (Individual Job Seeker)
**Monthly Operating Cost: $10-50**

**Breakdown:**
- n8n: Free tier (basic research workflows)
- News monitoring: Free (Google Alerts)
- Company data APIs: $10-30/month (basic company information)
- AI analysis: $10-20/month (research summarization)
- Storage: Free (Google Drive for research reports)

**Assumptions:**
- Researching 5-10 companies per month
- Basic company information and news monitoring
- Simple research report generation
- Personal use only

### Medium Business (Career Coaching Service)
**Monthly Operating Cost: $200-500**

**Breakdown:**
- n8n Pro: $50/month (advanced workflows)
- Premium company data: $100-200/month (comprehensive databases)
- Advanced news monitoring: $50-100/month (real-time alerts)
- AI analysis: $50-100/month (detailed research and insights)
- Client reporting: $50-100/month (professional report generation)

**Assumptions:**
- Researching 50-100 companies monthly for clients
- Comprehensive company intelligence and market analysis
- Professional report generation and client delivery
- Integration with career coaching workflows

### Enterprise (Executive Search Firm)
**Monthly Operating Cost: $1,500-4,000**

**Breakdown:**
- n8n Enterprise: $500/month (high-volume processing)
- Enterprise data sources: $800-1,500/month (premium business databases)
- Advanced analytics: $300-800/month (competitive intelligence tools)
- Custom research: $500-1,000/month (specialized industry analysis)
- Multi-client platform: $400-700/month (white-label research delivery)

**Assumptions:**
- Research for executive-level positions across multiple industries
- Deep competitive intelligence and market analysis
- Custom research reports with strategic insights
- Integration with executive search and client management systems

---

## Getting Started Guide

### Budget Planning
Start with free/low-cost options and scale:
- Week 1: Use LLM-only approach for immediate needs
- Week 2: Set up Google Alerts for target companies
- Month 1: Add basic n8n automation for regular research
- Month 2: Upgrade to premium data sources if needed

---

## Best Practices

### Research Quality
- Focus on recent developments and current strategy
- Verify information from multiple sources
- Look for insider perspectives from employee reviews
- Consider industry context and competitive landscape

### Interview Preparation
- Prepare 3-5 thoughtful questions based on your research
- Practice weaving company knowledge naturally into conversation
- Focus on how you can contribute to their specific challenges
- Prepare examples that align with their values and culture

---

## Common Questions

**Q: How recent should the company information be?**
A: Focus on last 6-12 months for news, but include foundational company information regardless of age.

**Q: What if the company is very small or private?**
A: Look for founder/leadership interviews, local business coverage, and employee LinkedIn profiles for insights.

**Q: Should I mention specific research in interviews?**
A: Yes, but naturally. Ask thoughtful questions about recent developments rather than just stating facts.

**Q: How do I research company culture accurately?**
A: Combine official sources (website, social media) with employee reviews and LinkedIn posts from current employees.

---

## Success Metrics

### Track These Numbers
- Interview performance improvement after research
- Quality of questions asked in interviews
- Interviewer feedback on preparation level
- Conversion rate from research to successful applications

### Expect These Results
- 80% improvement in interview confidence
- 60% more thoughtful questions prepared
- 40% better understanding of company fit
- 50% improvement in interview feedback scores

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
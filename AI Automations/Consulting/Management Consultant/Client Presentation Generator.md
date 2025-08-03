# Client Presentation Generator

**What It Does:** Automatically creates professional consulting presentation decks using McKinsey/BCG/Bain templates and your analysis data.

**How It Works:**
1. Takes your analysis findings and key messages as input
2. Applies consulting presentation structures (Pyramid Principle, SCR framework)
3. Creates slides with proper formatting, charts, and executive summaries
4. Generates speaker notes and appendix materials
5. Exports presentation-ready decks in PowerPoint format

**What You Need:**
- Presentation templates (McKinsey, BCG, Bain styles)
- Analysis data and findings
- Chart/graph generation tools
- PowerPoint automation tools

## Step-by-Step n8n Setup

1. **Create Presentation Generation Workflow**
   - Start workflow called "Client Presentation Generator"
   - Add "Form" trigger for presentation requirements input

2. **Structure Analysis & Planning**
   - Use "OpenAI" node with prompt: "Structure these findings using the Pyramid Principle: Executive Summary, Supporting Analysis, Recommendations. Apply SCR framework for key messages."
   - Define slide sequence and key messages
   - Identify supporting data and charts needed

3. **Content Creation**
   - Generate executive summary slides with key insights
   - Create supporting analysis slides with data visualizations
   - Develop recommendations with implementation timelines
   - Add appendix slides with detailed methodology

4. **Visual Design & Formatting**
   - Apply consulting template styles automatically
   - Generate charts and graphs from analysis data
   - Ensure consistent formatting and branding
   - Create professional slide layouts

5. **Quality Assurance**
   - Check slide flow and logical progression
   - Validate data accuracy and source citations
   - Generate speaker notes for each slide
   - Export final presentation files

## Alternative: Make.com Setup

1. **Create Deck Generation Scenario**
   - Name scenario "Client Presentation Generator"
   - Add "Forms > Watch responses" for presentation requests

2. **Content Structure**
   - Add "OpenAI > Create a chat completion" for storyline development
   - Apply consulting frameworks and structure
   - Generate slide outlines and key messages

3. **Slide Creation**
   - Add "Google Slides > Create presentation" with templates
   - Populate slides with analysis data and findings
   - Generate charts and visualizations automatically

4. **Final Production**
   - Add formatting and design consistency
   - Export "Google Drive > Download file" as PowerPoint
   - Send completed presentation to team

## What You Get
- Professional consulting presentation decks in hours instead of days
- Consistent application of proven consulting frameworks
- Automated chart generation and data visualization
- Speaker notes and appendix materials included

## 💰 Monthly Operating Costs

**Small Business (up to 250 employees, basic presentations):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Presentation tools: $50-150/month (PowerPoint automation, templates)
- Chart generation: $25-100/month (visualization tools)
- AI content creation: $100-300/month (presentation writing)
- **Total: $175-570/month**

**Medium Business (250-1,000 employees, advanced presentations):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Presentation tools: $200-500/month (enterprise automation tools)
- Chart generation: $150-400/month (advanced visualization)
- AI content creation: $500-1,000/month (complex presentation generation)
- **Total: $900-1,999/month**

**Enterprise (1,000+ employees, custom presentation systems):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Presentation tools: $1,000+/month (enterprise automation, custom templates)
- Chart generation: $800+/month (enterprise visualization platforms)
- AI content creation: $2,000+/month (enterprise content generation)
- **Total: $4,000+/month**

*Cost assumptions: Presentation complexity, custom template development, enterprise visualization requirements*

## 🔗 More Management Consultant Automations

**Need different solutions?**
- **[🏠 Management Consultant Overview](Management%20Consultant%20Overview.md)** - All automations for management consultants
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---
*Last Updated: 2025-08-03*
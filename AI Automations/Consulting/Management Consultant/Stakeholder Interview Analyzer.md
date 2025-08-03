# Stakeholder Interview Analyzer

**What It Does:** Automatically processes interview transcripts, extracts key insights, identifies patterns, and generates stakeholder analysis reports.

**How It Works:**
1. Transcribes recorded interviews using AI speech-to-text
2. Analyzes transcripts to extract key themes and insights
3. Maps stakeholder positions, concerns, and influence levels
4. Identifies conflicts, alignments, and decision-making patterns
5. Generates stakeholder management recommendations

**What You Need:**
- Interview recording tools
- Speech-to-text services (Whisper, Rev, Otter.ai)
- Interview analysis templates
- Stakeholder mapping frameworks

## Step-by-Step n8n Setup

1. **Create Interview Analysis Workflow**
   - Start workflow called "Stakeholder Interview Analyzer"
   - Add "File Upload" trigger for interview recordings

2. **Transcription Processing**
   - Add "OpenAI Whisper" or transcription service node
   - Convert audio/video files to text transcripts
   - Clean and format transcripts for analysis
   - Tag speakers and timestamp key moments

3. **Content Analysis**
   - Use "OpenAI" node to analyze transcripts:
     - Extract key themes and concerns
     - Identify stakeholder positions and motivations
     - Flag conflicts and alignment opportunities
     - Rate influence levels and decision-making power

4. **Stakeholder Mapping**
   - Create influence vs. interest matrices
   - Map relationships and communication patterns
   - Identify champions, blockers, and neutral parties
   - Generate stakeholder engagement strategies

5. **Insight Compilation**
   - Create comprehensive stakeholder analysis reports
   - Include direct quotes and supporting evidence
   - Provide recommendations for stakeholder management
   - Generate action plans for key relationships

## Alternative: Make.com Setup

1. **Create Interview Processing Scenario**
   - Name scenario "Stakeholder Interview Analyzer"
   - Add "Google Drive > Watch files" for interview uploads

2. **Transcription and Analysis**
   - Add "OpenAI > Create transcription" for audio processing
   - Use "OpenAI > Create a chat completion" for content analysis
   - Extract stakeholder insights and positions

3. **Mapping and Visualization**
   - Add "Google Sheets > Add row" for stakeholder data
   - Create influence/interest matrices and relationship maps
   - Generate stakeholder engagement recommendations

4. **Report Generation**
   - Add "Google Docs > Create document" for analysis reports
   - Include key insights, quotes, and recommendations
   - Send "Email > Send email" with completed analysis

## What You Get
- Comprehensive analysis of all stakeholder interviews
- Systematic identification of key themes and patterns
- Professional stakeholder maps and engagement strategies
- Actionable recommendations for relationship management

## 💰 Monthly Operating Costs

**Small Business (up to 250 employees, basic interview analysis):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Transcription services: $100-300/month (moderate interview volume)
- AI analysis: $150-400/month (transcript processing)
- Mapping tools: $25-100/month (stakeholder visualization)
- **Total: $275-820/month**

**Medium Business (250-1,000 employees, comprehensive analysis):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Transcription services: $500-1,200/month (high interview volume)
- AI analysis: $600-1,500/month (complex stakeholder analysis)
- Mapping tools: $150-400/month (advanced visualization)
- **Total: $1,300-3,199/month**

**Enterprise (1,000+ employees, global stakeholder management):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Transcription services: $2,000+/month (enterprise volume, multiple languages)
- AI analysis: $2,500+/month (enterprise-grade analysis)
- Mapping tools: $1,000+/month (enterprise stakeholder platforms)
- **Total: $5,700+/month**

*Cost assumptions: Interview volume, multi-language requirements, enterprise stakeholder management platforms*

## 🔗 More Management Consultant Automations

**Need different solutions?**
- **[🏠 Management Consultant Overview](Management%20Consultant%20Overview.md)** - All automations for management consultants
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---
*Last Updated: 2025-08-03*
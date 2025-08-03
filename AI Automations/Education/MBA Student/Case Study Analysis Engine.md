# Case Study Analysis Engine

Automatically analyzes business cases, extracts key insights, and generates strategic frameworks for class discussions and assignments.

## What This Does

**What It Does:** Streamlines the analysis of business cases using proven strategic frameworks and generates discussion-ready insights.

**How It Works:**
1. Extracts key information from case studies automatically
2. Applies strategic analysis frameworks (Porter's 5 Forces, SWOT, Value Chain)
3. Identifies main business problems and stakeholder perspectives
4. Generates strategic recommendations with supporting analysis
5. Creates discussion questions and class participation points

**What You Need:**
- Case study PDFs or documents
- Strategic framework templates
- n8n automation platform
- AI analysis tool (OpenAI or Claude work well)

---

## Step-by-Step n8n Setup

### 1. Create Case Analysis Workflow
- Start new workflow called "Case Study Analysis Engine"
- Add "File Upload" trigger for new case studies

### 2. Extract Case Content
- Add "PDF Reader" node to extract text from case studies
- Use "Text Splitter" to break into manageable sections
- Add "Document Classifier" to identify case type (strategy, finance, operations, marketing)

### 3. Apply Strategic Frameworks
- Add "OpenAI" node with framework analysis prompt:
  ```
  Analyze this business case using the following frameworks:
  
  1. SITUATION ANALYSIS:
  - Company background and current position
  - Industry context and competitive landscape
  - Key stakeholders and their interests
  
  2. PROBLEM IDENTIFICATION:
  - Primary business challenge
  - Root causes and contributing factors
  - Urgency and impact assessment
  
  3. STRATEGIC OPTIONS:
  - Alternative strategic approaches
  - Pros and cons of each option
  - Resource requirements and feasibility
  
  4. RECOMMENDATION:
  - Preferred strategic approach
  - Implementation timeline
  - Success metrics and risk mitigation
  ```

### 4. Generate Financial Analysis
- Add "Code" node to extract financial data from case
- Calculate key ratios and performance metrics
- Compare to industry benchmarks when available
- Create trend analysis for multi-year data

### 5. Create Competitive Analysis
- Use "Web Search" node to find current information about competitors
- Compare market positions and strategic moves
- Identify industry trends affecting the case company
- Update analysis with recent developments

### 6. Prepare Discussion Materials
- Add "Template" node to create structured output:
  - Executive summary (1 page)
  - Detailed analysis (3-5 pages)
  - Class discussion questions
  - PowerPoint slides for presentations
- Include citations and data sources

### 7. Track Learning Progress
- Add "Google Sheets" node to log case analyses
- Track which frameworks you've practiced
- Note feedback from professors and classmates
- Build portfolio of strategic analysis examples

---

## Alternative: Make.com Setup

### 1. Create Case Analysis Scenario
- Name scenario "Case Study Analysis Engine"
- Add "Google Drive > Watch files" for new case uploads

### 2. Case Content Processing
- Add "PDF > Extract text" to read case studies
- Use "Text parser > Split text" for section analysis
- Connect "OpenAI > Create completion" for framework application

### 3. Strategic Framework Analysis
- Create multiple OpenAI modules for different frameworks:
  - SWOT Analysis module
  - Porter's 5 Forces module
  - Financial analysis module
  - Competitive positioning module

### 4. Output Generation
- Add "Google Docs > Create document" for analysis reports
- Use "Google Slides > Create presentation" for class materials
- Create "Summary email" with key insights for quick review

### 5. Progress Tracking
- Add "Airtable > Add record" to track completed analyses
- Include case type, frameworks used, and key learnings
- Link to original case and generated materials

---

## What You Get

- 70% faster case analysis with consistent quality
- Comprehensive strategic framework application
- Professional presentation materials ready for class
- Financial analysis and competitive insights
- Discussion questions and participation points prepared

---

## Cost Estimates

### Small Business (Individual MBA Student)
**Monthly Operating Cost: $30-80**

**Breakdown:**
- n8n: Free tier (sufficient for personal case analysis)
- AI analysis processing: $20-50/month (OpenAI API for case processing)
- Business research tools: $10-30/month (industry data and competitor information)
- Document generation: Free (Google Docs/Slides)

**Assumptions:**
- Analyzing 3-5 cases per week during academic year
- Using standard strategic frameworks and financial analysis
- Personal study and class preparation focus
- Individual student implementation

### Medium Business (Study Group/MBA Cohort)
**Monthly Operating Cost: $200-500**

**Breakdown:**
- n8n Pro: $50/month (collaboration features for group analysis)
- Advanced AI processing: $100-250/month (comprehensive case analysis for group)
- Premium research tools: $50-150/month (advanced industry and competitive data)
- Collaboration platform: $50-100/month (shared analysis library and coordination)

**Assumptions:**
- 10-15 students sharing case analysis workload
- Collaborative case library and shared insights
- Advanced competitive intelligence and market research
- Group presentation preparation and coordination

### Enterprise (Business School Program)
**Monthly Operating Cost: $1,500-4,000**

**Breakdown:**
- Enterprise automation: $500-1,000/month (program-wide deployment)
- Advanced business intelligence: $500-1,500/month (comprehensive industry databases)
- Academic integration: $300-800/month (LMS integration and grading)
- Analytics platform: $200-700/month (learning analytics and performance tracking)

**Assumptions:**
- Program-wide implementation across multiple MBA cohorts
- Integration with academic systems and course management
- Advanced analytics for curriculum development and student performance
- Comprehensive business intelligence and case study databases

---

## Best Practices

### Academic Integrity
- Use automation for analysis structure and framework application
- Always include original thinking and personal insights
- Cite all sources and data used in analysis
- Review and verify all AI-generated content before submission

### Strategic Thinking Development
- Practice applying different frameworks to the same case
- Compare your analysis with classmates to identify blind spots
- Seek feedback from professors on framework application
- Build a personal library of successful analysis approaches

### Professional Preparation
- Format analyses as if presenting to real executives
- Practice defending your recommendations with data
- Learn to adapt analysis depth based on audience and time constraints
- Develop templates for different types of business problems

---

## Common Questions

**Q: Will professors notice if I use AI for case analysis?**
A: Use AI for structure and framework application, but include original insights and thinking. Most programs appreciate efficient preparation that leads to better class discussion.

**Q: How do I handle cases with incomplete information?**
A: This is common in real business situations. Make reasonable assumptions, state them clearly, and explain how additional information would change your analysis.

**Q: Can this help with different types of cases (finance, marketing, operations)?**
A: Yes, customize framework templates for different business disciplines and case types.

**Q: How do I prepare for cold calls in class?**
A: Create summary cards with key points from your analysis for quick reference during class discussions.

---

## Success Metrics

### Track These Numbers
- Time spent on case preparation (before vs. after automation)
- Quality of class participation and discussion contributions
- Professor feedback on analysis depth and framework application
- Consistency of analysis quality across different case types
- Confidence level when presenting recommendations

### Expect These Results
- 70% reduction in case preparation time with maintained quality
- Consistent application of strategic frameworks across all cases
- Improved class participation through better preparation
- Professional-quality analysis materials for portfolio development
- Higher confidence in strategic thinking and business problem-solving

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
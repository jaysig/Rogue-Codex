# Management Consultant Automations

Advanced automation workflows for management consultants to eliminate research drudgery, accelerate analysis, and focus on high-value strategic thinking using AI-powered tools.

## What This Is

These automations handle the time-intensive analytical work that eats up 60-80% of a consultant's day, so you can focus on client insights, strategic recommendations, and relationship building. Like having a team of analysts working 24/7.

**Who This Helps:** Management consultants, strategy consultants, MBB consultants, boutique consultants, independent consultants  
**Tools Used:** n8n or Make.com, AI analysis tools, data platforms, document processing  
**Time Saved:** 20-30 hours per week  
**Results:** 70% faster due diligence, 50% reduction in research time  

---

## 🔍 Due Diligence & Data Room Analyzer

**What It Does:** Automatically processes hundreds of documents in M&A data rooms, extracts key insights, identifies red flags, and generates preliminary analysis reports.

**How It Works:**
1. Monitors data room uploads and downloads all new documents
2. Uses AI to categorize documents (financial, legal, operational, strategic)
3. Extracts key metrics, dates, and risk factors from each document type
4. Cross-references information to identify inconsistencies or red flags
5. Generates structured analysis reports with findings and recommendations

**What You Need:**
- Data room access (Intralinks, Merrill DatSite, SS&C)
- Document processing AI (Claude, GPT-4, or specialized tools)
- Financial analysis templates
- Red flag identification rules

**Step-by-Step n8n Setup:**

1. **Create Due Diligence Workflow**
   - Start workflow called "Due Diligence & Data Room Analyzer"
   - Add "HTTP Request" trigger to monitor data room API for new uploads

2. **Document Classification**
   - Add "Extract from File" node to read document content
   - Use "OpenAI" node with prompt: "Categorize this document as: Financial Statements, Legal Contracts, Operational Reports, Strategic Plans, HR Documents, or Other. Extract key metrics and dates."
   - Route documents by type using "Switch" node

3. **Financial Analysis Automation**
   - For financial docs: Extract revenue, EBITDA, cash flow, debt levels
   - Calculate key ratios and growth rates automatically
   - Compare against industry benchmarks
   - Flag unusual trends or outliers

4. **Red Flag Detection**
   - Use "IF" nodes to check for common red flags:
     - Revenue concentration (>30% from single customer)
     - Declining margins over 2+ years
     - High executive turnover
     - Pending litigation over $X threshold
   - Generate alerts for critical issues

5. **Report Generation**
   - Compile findings into structured reports by category
   - Include executive summary with key risks and opportunities
   - Create data visualization charts for trends
   - Email reports to engagement team

**Alternative: Make.com Setup**

1. **Create Data Room Analysis Scenario**
   - Name scenario "Due Diligence & Data Room Analyzer"
   - Add data room webhook trigger for new documents

2. **AI-Powered Document Processing**
   - Add "OpenAI > Create a chat completion" for document analysis
   - Extract structured data based on document type
   - Identify key business metrics and risk factors

3. **Financial Analysis Engine**
   - Use "Math > Perform a function" for ratio calculations
   - Add "Filter" modules for red flag identification
   - Generate trend analysis and peer comparisons

4. **Automated Reporting**
   - Add "Google Docs > Create document" for analysis reports
   - Include charts and visualizations
   - Send "Email > Send email" with findings to team

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build due diligence scenarios faster.

**What You Get:**
- Complete data room analysis in hours instead of weeks
- Consistent red flag identification across all deals
- Structured reports ready for client presentation
- 80% reduction in document review time

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic due diligence needs):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Document processing AI: $100-300/month (moderate document volume)
- Data room access: $500-1,500/month (usually client-provided)
- Analysis tools: $50-150/month (financial databases, benchmarking)
- **Total: $650-1,970/month**

**Medium Business (250-1,000 employees, regular M&A activity):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Document processing AI: $500-1,500/month (high document volume)
- Data room access: $2,000-5,000/month (enterprise features)
- Analysis tools: $200-500/month (comprehensive databases)
- **Total: $2,750-7,099/month**

**Enterprise (1,000+ employees, complex multi-deal operations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Document processing AI: $2,000+/month (enterprise-grade processing)
- Data room access: $10,000+/month (enterprise, multi-deal access)
- Analysis tools: $1,000+/month (enterprise databases, custom analytics)
- **Total: $13,200+/month**

*Cost assumptions: Document volume scales with deal complexity, enterprise data room features, comprehensive industry databases*

---

## 🏢 Post-Merger Integration & Organizational Mapper

**What It Does:** Analyzes organizational structures from multiple entities, identifies redundancies, maps reporting relationships, and recommends integration strategies.

**How It Works:**
1. Ingests org charts, job descriptions, and employee data from merging entities
2. Maps roles, responsibilities, and reporting structures using AI analysis
3. Identifies overlapping functions and potential redundancies
4. Analyzes compensation disparities and cultural differences
5. Generates integration recommendations with timeline and cost estimates

**What You Need:**
- HRIS system access (Workday, BambooHR, ADP)
- Organizational data (job descriptions, comp data, performance reviews)
- Org chart visualization tools
- Cultural assessment surveys

**Step-by-Step n8n Setup:**

1. **Create PMI Mapping Workflow**
   - Start workflow called "Post-Merger Integration & Organizational Mapper"
   - Add "HRIS" triggers to pull employee data from both entities

2. **Role Analysis & Mapping**
   - Use "OpenAI" node to analyze job descriptions and extract:
     - Core responsibilities and skills required
     - Reporting relationships and team structures
     - Compensation levels and performance ratings
   - Map similar roles across both organizations

3. **Redundancy Identification**
   - Add "Code" node to calculate overlap percentages:
     - Same role + same department = 95% overlap
     - Similar role + different department = 60% overlap
     - Different role + same manager = 30% overlap
   - Flag positions for further review

4. **Cultural Integration Analysis**
   - Analyze communication patterns, work styles, values alignment
   - Identify potential cultural conflicts or synergies
   - Recommend integration strategies by department

5. **Integration Planning**
   - Generate org charts for proposed future state
   - Calculate cost savings from redundancy elimination
   - Create implementation timeline with key milestones
   - Identify key talent retention risks

**Alternative: Make.com Setup**

1. **Create PMI Analysis Scenario**
   - Name scenario "Post-Merger Integration & Organizational Mapper"
   - Add "HRIS > Get employees" from both organizations

2. **AI-Powered Role Mapping**
   - Add "OpenAI > Create a chat completion" for job description analysis
   - Map roles and identify functional overlaps
   - Analyze compensation and performance data

3. **Redundancy and Risk Analysis**
   - Use "Math > Perform a function" for overlap calculations
   - Add "Filter" modules for high-risk scenarios
   - Identify key talent retention priorities

4. **Integration Recommendations**
   - Add "Google Sheets > Add row" for tracking analysis
   - Generate visual org charts and integration plans
   - Create implementation timeline and cost estimates

**What You Get:**
- Complete organizational overlap analysis in days instead of months
- Data-driven redundancy identification and cost estimates
- Cultural integration risk assessment and mitigation strategies
- Clear implementation roadmap with success metrics

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic PMI needs):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- HRIS integrations: $100-300/month (API access, data processing)
- AI analysis: $200-500/month (org analysis, cultural assessment)
- Visualization tools: $50-150/month (org chart tools, dashboards)
- **Total: $350-970/month**

**Medium Business (250-1,000 employees, complex integrations):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- HRIS integrations: $500-1,000/month (enterprise API access)
- AI analysis: $800-2,000/month (complex organizational analysis)
- Visualization tools: $200-500/month (enterprise visualization, analytics)
- **Total: $1,550-3,599/month**

**Enterprise (1,000+ employees, multi-entity integrations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- HRIS integrations: $2,000+/month (enterprise systems, global data)
- AI analysis: $3,000+/month (enterprise-grade analysis, custom models)
- Visualization tools: $1,000+/month (enterprise dashboards, custom analytics)
- **Total: $6,200+/month**

*Cost assumptions: Employee count scales complexity, enterprise HRIS systems, advanced cultural analysis capabilities*

---

## 📊 Competitive Intelligence Engine

**What It Does:** Continuously monitors competitors, analyzes market movements, and generates actionable intelligence reports for strategic planning.

**How It Works:**
1. Monitors competitor websites, press releases, and financial filings
2. Tracks pricing changes, product launches, and strategic announcements
3. Analyzes hiring patterns and leadership changes
4. Compiles industry trends and market share movements
5. Generates weekly intelligence briefings with strategic implications

**What You Need:**
- Web scraping tools and APIs
- Financial data feeds (CapitalIQ, FactSet)
- News monitoring services
- Social media monitoring tools

**Step-by-Step n8n Setup:**

1. **Create Competitive Intelligence Workflow**
   - Start workflow called "Competitive Intelligence Engine"
   - Add "Schedule Trigger" to run daily monitoring

2. **Multi-Source Data Collection**
   - Add "HTTP Request" nodes for competitor websites
   - Connect "RSS" feeds for press releases and news
   - Use "API" nodes for financial data and job postings
   - Monitor social media mentions and sentiment

3. **AI-Powered Analysis**
   - Use "OpenAI" node to analyze collected information:
     - Categorize news by strategic importance
     - Extract key metrics and changes
     - Identify patterns and emerging trends
   - Compare against historical data for trend analysis

4. **Strategic Implications Assessment**
   - Analyze competitive moves for potential impact
   - Identify market opportunities and threats
   - Generate recommendations for client response

5. **Automated Reporting**
   - Compile findings into executive briefing format
   - Include market share analysis and trend charts
   - Send weekly reports to engagement teams
   - Create alerts for critical developments

**Alternative: Make.com Setup**

1. **Create Intelligence Monitoring Scenario**
   - Name scenario "Competitive Intelligence Engine"
   - Add "Schedule" module for regular monitoring

2. **Data Aggregation**
   - Add "RSS > Get feed items" for news monitoring
   - Use "HTTP > Make a request" for website changes
   - Connect financial data APIs for market analysis

3. **AI Analysis and Insights**
   - Add "OpenAI > Create a chat completion" for trend analysis
   - Extract strategic implications and recommendations
   - Track competitive positioning changes

4. **Intelligence Distribution**
   - Add "Google Docs > Create document" for briefings
   - Send "Email > Send email" alerts for critical changes
   - Update dashboards with latest intelligence

**What You Get:**
- Real-time competitive intelligence instead of quarterly updates
- Automated trend analysis and strategic implications
- Early warning system for competitive threats
- Data-driven market positioning recommendations

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic competitive monitoring):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Data feeds: $200-500/month (basic news, financial data)
- Web monitoring: $100-300/month (scraping tools, APIs)
- Analysis tools: $50-150/month (sentiment analysis, reporting)
- **Total: $350-970/month**

**Medium Business (250-1,000 employees, comprehensive intelligence):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Data feeds: $1,000-3,000/month (premium databases, real-time feeds)
- Web monitoring: $500-1,000/month (enterprise monitoring, global coverage)
- Analysis tools: $300-800/month (advanced analytics, custom dashboards)
- **Total: $1,850-4,899/month**

**Enterprise (1,000+ employees, strategic intelligence operations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Data feeds: $5,000+/month (enterprise databases, custom feeds)
- Web monitoring: $2,000+/month (enterprise monitoring, global intelligence)
- Analysis tools: $1,500+/month (enterprise analytics, AI models)
- **Total: $8,700+/month**

*Cost assumptions: Data feed complexity scales with business scope, enterprise intelligence requirements, global monitoring needs*

---

## 📊 Market Sizing & Analysis Engine

**What It Does:** Automatically calculates market sizes, analyzes industry trends, and generates comprehensive market analysis reports using multiple data sources.

**How It Works:**
1. Pulls data from industry databases, government sources, and company filings
2. Applies standard market sizing methodologies (top-down, bottom-up, value theory)
3. Cross-validates estimates using multiple approaches
4. Generates market size calculations with confidence intervals
5. Creates trend analysis and forecasting models

**What You Need:**
- Industry databases (IBISWorld, Euromonitor, Statista)
- Government data APIs (Census, Bureau of Labor Statistics)
- Company financial data sources
- Market research platforms

**Step-by-Step n8n Setup:**

1. **Create Market Sizing Workflow**
   - Start workflow called "Market Sizing & Analysis Engine"
   - Add "Schedule Trigger" for regular market data updates

2. **Multi-Source Data Collection**
   - Add "HTTP Request" nodes for industry database APIs
   - Connect government data feeds for macro-economic indicators
   - Pull company financial data for market participant analysis
   - Gather demographic and consumer spending data

3. **Market Size Calculation**
   - Use "Code" node to apply sizing methodologies:
     - Top-down: Total addressable market × penetration rate
     - Bottom-up: Units sold × average price × market participants
     - Value theory: Customer value × number of customers
   - Cross-validate results and flag significant discrepancies

4. **Trend Analysis & Forecasting**
   - Apply "Math" functions for growth rate calculations
   - Identify seasonal patterns and cyclical trends
   - Generate 3-5 year market forecasts with scenarios

5. **Report Generation**
   - Create structured market analysis reports
   - Include charts, graphs, and executive summaries
   - Provide methodology explanations and data sources

**Alternative: Make.com Setup**

1. **Create Market Analysis Scenario**
   - Name scenario "Market Sizing & Analysis Engine"
   - Add "Schedule" module for regular data updates

2. **Data Aggregation**
   - Add multiple "HTTP > Make a request" for data sources
   - Use "Math > Perform a function" for calculations
   - Apply market sizing formulas automatically

3. **Analysis and Validation**
   - Add "OpenAI > Create a chat completion" for trend analysis
   - Cross-validate estimates using multiple methodologies
   - Generate confidence scores for market size estimates

4. **Automated Reporting**
   - Add "Google Docs > Create document" for market reports
   - Include visualizations and executive summaries
   - Send "Email > Send email" with completed analysis

**What You Get:**
- Consistent market sizing methodology across all projects
- Real-time market data updates and trend tracking
- Cross-validated estimates with confidence intervals
- Professional market analysis reports ready for clients

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic market analysis):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Industry databases: $500-1,500/month (basic subscriptions)
- Government data APIs: Free to $100/month (premium access)
- Analysis tools: $50-200/month (charting, reporting)
- **Total: $550-1,820/month**

**Medium Business (250-1,000 employees, comprehensive analysis):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Industry databases: $2,000-5,000/month (premium subscriptions)
- Government data APIs: $200-500/month (enterprise access)
- Analysis tools: $300-800/month (advanced analytics)
- **Total: $2,550-6,399/month**

**Enterprise (1,000+ employees, global market intelligence):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Industry databases: $10,000+/month (enterprise, global coverage)
- Government data APIs: $1,000+/month (global data access)
- Analysis tools: $2,000+/month (enterprise analytics, custom models)
- **Total: $13,200+/month**

*Cost assumptions: Industry database complexity, global data requirements, custom analysis models*

---

## 🎯 Client Presentation Generator

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

**Step-by-Step n8n Setup:**

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

**Alternative: Make.com Setup**

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

**What You Get:**
- Professional consulting presentation decks in hours instead of days
- Consistent application of proven consulting frameworks
- Automated chart generation and data visualization
- Speaker notes and appendix materials included

**💰 Monthly Operating Costs:**

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

---

## 📞 Stakeholder Interview Analyzer

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

**Step-by-Step n8n Setup:**

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

**Alternative: Make.com Setup**

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

**What You Get:**
- Comprehensive analysis of all stakeholder interviews
- Systematic identification of key themes and patterns
- Professional stakeholder maps and engagement strategies
- Actionable recommendations for relationship management

**💰 Monthly Operating Costs:**

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

---

## 📈 Financial Model Builder

**What It Does:** Automatically creates comprehensive financial models with scenario analysis, sensitivity testing, and professional formatting.

**How It Works:**
1. Takes business assumptions and historical data as inputs
2. Builds complete 3-statement financial models (P&L, Balance Sheet, Cash Flow)
3. Creates scenario analysis with optimistic, base, and pessimistic cases
4. Generates sensitivity analysis for key variables
5. Produces executive summaries with key metrics and insights

**What You Need:**
- Historical financial data
- Business assumption templates
- Financial modeling software integration
- Scenario analysis frameworks

**Step-by-Step n8n Setup:**

1. **Create Financial Model Workflow**
   - Start workflow called "Financial Model Builder"
   - Add "Form" trigger for model parameters and assumptions

2. **Data Collection & Validation**
   - Pull historical financial data from company sources
   - Validate data quality and identify missing information
   - Apply standard accounting principles and adjustments
   - Set up model timeframes and reporting periods

3. **Model Construction**
   - Build P&L model with revenue drivers and cost structure
   - Create balance sheet with working capital calculations
   - Develop cash flow statement with operating/investing/financing activities
   - Link all statements with appropriate formulas

4. **Scenario & Sensitivity Analysis**
   - Create optimistic/base/pessimistic scenarios
   - Run sensitivity analysis on key variables (growth rates, margins, etc.)
   - Generate tornado charts and data tables
   - Calculate valuation ranges and key metrics

5. **Professional Formatting & Output**
   - Apply consulting-grade formatting and layouts
   - Generate executive summary dashboards
   - Create presentation-ready charts and graphs
   - Export models in Excel with documentation

**Alternative: Make.com Setup**

1. **Create Model Generation Scenario**
   - Name scenario "Financial Model Builder"
   - Add "Forms > Watch responses" for model requirements

2. **Data Processing**
   - Add "Google Sheets > Get rows" for historical data
   - Use "Math > Perform a function" for calculations
   - Build financial statement connections

3. **Analysis Generation**
   - Add scenario planning with multiple case development
   - Use "Math > Perform a function" for sensitivity analysis
   - Generate valuation metrics and ratios

4. **Model Export**
   - Add "Google Sheets > Create spreadsheet" for final model
   - Include formatting and documentation
   - Send "Email > Send email" with completed model

**What You Get:**
- Professional 3-statement financial models
- Comprehensive scenario and sensitivity analysis
- Executive dashboards with key metrics
- Presentation-ready charts and summaries

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic financial modeling):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Financial data feeds: $200-500/month (basic data sources)
- Modeling software: $100-300/month (Excel automation, templates)
- Analysis tools: $50-150/month (charting, scenario tools)
- **Total: $350-970/month**

**Medium Business (250-1,000 employees, advanced modeling):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Financial data feeds: $800-2,000/month (premium data sources)
- Modeling software: $400-1,000/month (advanced modeling platforms)
- Analysis tools: $200-600/month (enterprise analysis tools)
- **Total: $1,450-3,699/month**

**Enterprise (1,000+ employees, complex financial systems):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Financial data feeds: $3,000+/month (enterprise data platforms)
- Modeling software: $2,000+/month (enterprise financial modeling)
- Analysis tools: $1,500+/month (enterprise analytics platforms)
- **Total: $6,700+/month**

*Cost assumptions: Model complexity, data source requirements, enterprise financial platform integration*

---

## 🎯 Getting Started Guide

### Start with Due Diligence Automation
Most consultants see immediate value from automated document analysis - it eliminates the most time-consuming parts of deal work while improving accuracy.

### Use Your Current Data Sources
Connect automations to whatever databases and tools you already use. Don't switch platforms just for automation.

### Begin with Simple Analysis
Start with straightforward document processing before moving to complex organizational mapping or competitive intelligence.

### Budget Planning
- Data and analysis tools: Usually $500-5,000/month depending on scope
- n8n or Make.com: Free to $400/month for consulting automations  
- AI processing: $100-3,000/month based on analysis volume
- Total: Usually $1,000-15,000/month for complete consulting automation

---

## 🛡️ Best Practices

### Maintain Client Confidentiality
- Use secure, compliant platforms for all client data processing
- Include human review for sensitive analysis and recommendations
- Follow all client confidentiality and data protection requirements
- Keep proprietary information properly protected

### Ensure Analysis Quality
- Validate automated findings with manual spot checks
- Include confidence scores and data source citations
- Review AI recommendations before client presentation
- Maintain audit trails for all automated analysis

### Focus on Strategic Value
- Use automation to eliminate routine work, not replace strategic thinking
- Combine automated insights with consultant expertise and judgment
- Communicate how automation enhances rather than replaces consultant value
- Continuously improve analysis quality based on client feedback

---

## 📞 Common Questions

**Q: Will clients trust automated analysis?**
A: Position automation as enhancing speed and consistency while maintaining consultant oversight. Always include human validation and strategic interpretation.

**Q: What if automated analysis misses important insights?**
A: Include human review checkpoints and confidence scoring. Use automation for comprehensive data processing, not final recommendations.

**Q: How do we maintain competitive advantage if everyone uses AI?**
A: Focus on unique data sources, proprietary analysis frameworks, and superior strategic interpretation of automated insights.

**Q: Can we customize automation for different industries?**
A: Absolutely. Set up different analysis rules, benchmarks, and red flags for each industry vertical you serve.

---

## 📈 Success Metrics

### Track These Numbers
- Time saved on document analysis and research
- Accuracy improvement in red flag identification
- Speed of competitive intelligence generation
- Client satisfaction with analysis depth and speed
- Presentation creation time reduction
- Market sizing analysis consistency
- Stakeholder interview processing efficiency
- Financial model development speed

### Expect These Results
- 70% reduction in due diligence timeline
- 60% faster competitive analysis delivery
- 80% improvement in organizational mapping accuracy
- 50% increase in analysis comprehensiveness
- 85% faster presentation deck creation
- 90% reduction in market sizing research time
- 75% faster stakeholder analysis completion
- 60% reduction in financial modeling timeframes

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
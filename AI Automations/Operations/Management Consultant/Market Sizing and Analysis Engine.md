# Market Sizing & Analysis Engine

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

## Step-by-Step n8n Setup

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

## Alternative: Make.com Setup

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

## What You Get
- Consistent market sizing methodology across all projects
- Real-time market data updates and trend tracking
- Cross-validated estimates with confidence intervals
- Professional market analysis reports ready for clients

## 💰 Monthly Operating Costs

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

## 🔗 More Management Consultant Automations

**Need different solutions?**
- **[🏠 Management Consultant Overview](Management%20Consultant%20Overview.md)** - All automations for management consultants
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---
*Last Updated: 2025-08-03*
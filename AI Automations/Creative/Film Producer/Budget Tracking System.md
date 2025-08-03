# Budget Tracking System

Monitors production spending against budget across all departments with real-time alerts and cost control automation.

## What This Does

**What It Does:** Provides real-time budget monitoring and cost control for film productions of any size.

**How It Works:**
1. Tracks actual spending from receipts and invoices automatically
2. Compares spending to approved budget by department
3. Sends alerts when departments approach budget limits
4. Creates detailed cost reports for financiers and stakeholders
5. Forecasts final production costs based on current trends

**What You Need:**
- Production budget spreadsheet or accounting software
- Receipt/invoice collection system (photos, email, or expense app)
- n8n automation platform
- Bank account/credit card integration for expense tracking

---

## Step-by-Step n8n Setup

### 1. Create Budget Monitoring Workflow
- Start new workflow called "Production Budget Tracker"
- Add "Schedule Trigger" to check expenses daily at 9 AM

### 2. Collect Expense Data Automatically
- Add "Email Trigger" to receive expense reports from crew
- Connect "Expensify" or "Ramp" for automatic expense categorization
- Use "Bank API" integration to pull transaction data
- Add "Photo OCR" node to read receipts from phone uploads

### 3. Categorize Production Expenses
- Add "Code" node to sort expenses by production department:
  - **Above-the-line**: Director, producers, main cast fees
  - **Below-the-line**: Crew wages, equipment rentals, catering
  - **Post-production**: Editing, sound mixing, color correction, VFX
  - **Marketing**: Publicity, advertising, festival submissions
- Use AI to categorize unclear expenses automatically

### 4. Compare Against Budget Allocation
- Add "Google Sheets" connection to approved production budget
- Calculate spending percentage by category in real-time
- Track burn rate and projected final costs
- Identify departments over/under budget

### 5. Create Smart Budget Alerts
- Add "IF" nodes for different alert thresholds:
  - **75% spent** = Yellow alert to department head
  - **90% spent** = Red alert to line producer
  - **Unbudgeted expense** = Immediate approval required
  - **Daily spending over target** = Cash flow warning

### 6. Generate Financial Reports
- Add "Report Generator" for weekly stakeholder updates:
  - Current spending vs. budget by department
  - Cash flow projections and funding needs
  - Cost overrun explanations and mitigation plans
  - Completion forecast based on spending trends

### 7. Stakeholder Communication
- Add "Email Automation" for different recipients:
  - **Line Producer**: Daily spending summaries and alerts
  - **Executive Producer**: Weekly financial overview
  - **Financiers**: Monthly investor reports with ROI projections
  - **Department Heads**: Real-time budget status for their areas

---

## Alternative: Make.com Setup

### 1. Create Budget Tracking Scenario
- Name scenario "Production Budget Tracker"
- Add "Schedule > Every day" module for daily monitoring

### 2. Expense Collection
- Add "Gmail > Watch emails" for expense submissions
- Connect "Expensify > Get expenses" for automated categorization
- Use "Bank integration > Get transactions" for real-time spending data

### 3. Budget Analysis
- Add "Google Sheets > Search rows" to find budget allocations
- Use "Math > Calculate percentage" for spend rate analysis
- Create "Filter > Continue if" for alert conditions

### 4. Alert System
- Add "Multiple paths" for different alert types
- Route to "Email > Send" or "SMS > Send" based on urgency
- Include "Slack > Send message" for production team coordination

### 5. Reporting Dashboard
- Create "Weekly report" with spending summaries
- Generate "Investor updates" monthly
- Build "Department dashboards" for real-time budget status

---

## What You Get

- Real-time budget monitoring and cost control
- Early warning system for budget overruns
- Professional financial reports for stakeholders
- Automated expense categorization and tracking
- Data-driven production financial management

---

## Cost Estimates

### Small Business (Independent Film - Under $1M Budget)
**Monthly Operating Cost: $30-80**

**Breakdown:**
- n8n: Free tier (basic automation sufficient)
- Expense tracking app: $10-30/month (Expensify or similar)
- Bank/credit card integration: Free to $20/month
- Cloud storage: $10-20/month (Google Drive, Dropbox)
- SMS alerts: $10/month for urgent notifications

**Assumptions:**
- Independent or low-budget film production
- 20-50 expense transactions per week
- Basic department categorization and alerts
- Simple financial reporting for small investor group

### Medium Business (Medium Budget Film - $1M-$10M)
**Monthly Operating Cost: $200-500**

**Breakdown:**
- n8n Pro: $50/month (advanced workflows and team features)
- Professional expense management: $100-200/month (enterprise expense platform)
- Advanced accounting integration: $50-150/month (QuickBooks, Sage integration)
- Multi-department coordination: $50-100/month (Slack, project management tools)
- Professional reporting: $50-100/month (dashboard and analytics tools)

**Assumptions:**
- Professional film production with multiple departments
- 200-500 expense transactions weekly
- Complex budget categories and approval workflows
- Detailed financial reporting for multiple stakeholders

### Enterprise (Studio Production - $10M+ Budget)
**Monthly Operating Cost: $1,000-3,000**

**Breakdown:**
- Enterprise automation platform: $300-600/month (n8n Enterprise or custom)
- Studio-level financial management: $400-1,000/month (enterprise accounting and ERP)
- Advanced analytics and forecasting: $200-600/month (business intelligence tools)
- Multi-project coordination: $200-500/month (portfolio management across productions)
- Compliance and audit tools: $100-300/month (SOX compliance, audit trails)

**Assumptions:**
- Major studio production with complex financial requirements
- Thousands of expense transactions weekly
- Multi-project portfolio management
- Advanced compliance, audit, and investor reporting requirements

---

## Best Practices

### Financial Control
- Set up approval workflows for expenses over certain thresholds
- Require photo receipts for all expenses above $50
- Review and approve all budget category changes
- Maintain separate tracking for contingency and overages

### Stakeholder Communication
- Send daily budget updates to line producer and department heads
- Provide weekly summaries to executive producers and financiers
- Include context and explanations for any budget variances
- Maintain transparency while protecting sensitive financial information

### Production Efficiency
- Use real-time data to make informed production decisions
- Adjust shooting schedules based on budget performance
- Negotiate equipment and location costs using actual budget data
- Plan post-production spending based on production phase results

---

## Common Questions

**Q: How do I handle unexpected production costs?**
A: Set up contingency budget categories and automatic alerts when accessing contingency funds. Include approval workflows for emergency expenses.

**Q: What if cast or crew submit expenses incorrectly?**
A: Use AI to auto-categorize and flag unusual expenses for manual review. Train team on proper expense submission procedures.

**Q: How detailed should budget tracking be?**
A: Track at the level needed for decision-making. Independent films might use broader categories, while studio productions need detailed line-item tracking.

**Q: Can this work for multiple projects simultaneously?**
A: Yes, set up separate workflows for each production or use project codes to track multiple films in one system.

---

## Success Metrics

### Track These Numbers
- Percentage of budget spent vs. percentage of production completed
- Number of budget overruns caught early vs. discovered late
- Time saved on financial reporting and expense processing
- Accuracy of final cost predictions vs. actual production costs
- Stakeholder satisfaction with financial transparency and communication

### Expect These Results
- 80% reduction in budget overruns through early detection
- 60% faster expense processing and categorization
- 90% improvement in financial reporting accuracy and timeliness
- 50% less time spent on manual budget tracking and reconciliation
- Better production decisions through real-time financial visibility

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
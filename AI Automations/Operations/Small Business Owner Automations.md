# Small Business Owner Automations

Simple automation workflows to help small business owners manage finances, reduce paperwork, and focus on growing their business using easy AI tools.

## What This Is

These automations handle the boring business tasks that eat up your time every day. Think of it like having a smart assistant that never sleeps and never makes mistakes with your money.

**Who This Helps:** Small business owners, entrepreneurs, freelancers, consultants  
**Tools Used:** n8n or Make.com (both have free options), accounting software, AI helpers  
**Time Saved:** 15-20 hours per week  
**Money Saved:** $500-2000/month in reduced admin costs  

---

## 💰 Invoice Processing Engine

**What It Does:** Automatically turns receipts and bills into organized expense records and sends payment reminders.

**How It Works:**
1. Takes photos of receipts and scans them automatically
2. Pulls out important info like amount, date, vendor name
3. Sorts expenses into the right categories for taxes
4. Sends friendly payment reminders to customers who owe you money
5. Tracks which invoices are paid and which are overdue

**What You Need:**
- Phone camera for receipts
- Accounting software (QuickBooks, Xero, or FreshBooks)
- n8n or Make.com account
- Email access

**Step-by-Step n8n Setup:**

1. **Create Invoice Processing Workflow**
   - Start new workflow called "Invoice Processing Engine"
   - Add "Email" trigger to watch for receipt photos sent to special email

2. **Extract Receipt Information**
   - Add "Extract from File" node to read text from receipt images
   - Connect "OpenAI" node with prompt: "Extract vendor name, amount, date, and category from this receipt"
   - Use categories like: meals, office supplies, travel, utilities

3. **Categorize and Store**
   - Add "Switch" node to route by expense category
   - Connect "QuickBooks" or accounting software node to save expense
   - Include receipt image attachment for records

4. **Send Payment Reminders**
   - Add "Schedule Trigger" to check for overdue invoices daily
   - Use "IF" node: "If invoice is 7+ days overdue"
   - Send friendly email reminder with invoice attached

5. **Track Payment Status**
   - Monitor when payments come in through bank feed
   - Auto-update invoice status to "paid"
   - Send thank you email to customer

**Alternative: Make.com Setup**

1. **Create Invoice Scenario**
   - Name scenario "Invoice Processing Engine"
   - Add "Email > Watch emails" for receipt processing

2. **OCR and Data Extraction**
   - Add "Google Vision API" or "OpenAI > Analyze image"
   - Extract vendor, amount, date, tax category

3. **Accounting Integration**
   - Add "QuickBooks > Create expense" module
   - Auto-categorize based on vendor or amount patterns

4. **Payment Reminder System**
   - Add "Schedule" module for daily overdue check
   - Send "Email" reminders with professional templates

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build invoice scenarios faster.

**What You Get:**
- No more shoebox full of receipts
- Automatic expense categorization for taxes
- Faster customer payments
- 90% less time on bookkeeping

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, < $50M revenue):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Accounting software: $15-60/month (QuickBooks/Xero multi-user)
- OCR/AI processing: $5-30/month (moderate invoice volume)
- **Total: $20-110/month**

**Medium Business (250-1,000 employees, $50M-$1B revenue):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Accounting software: $100-300/month (advanced multi-entity features)
- OCR/AI processing: $50-150/month (high invoice volume)
- **Total: $200-549/month**

**Enterprise (1,000+ employees, $1B+ revenue):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Accounting software: $500+/month (enterprise ERP integration)
- OCR/AI processing: $200+/month (very high volume processing)
- **Total: $900+/month**

*Cost assumptions: Invoice volume scales dramatically with business size, multi-entity accounting needs, advanced compliance requirements*

---

## 📊 Weekly Financial Dashboard

**What It Does:** Creates a simple weekly money report so you always know how your business is doing.

**How It Works:**
1. Pulls data from your bank accounts and payment processors
2. Calculates this week vs last week performance
3. Shows cash flow, expenses, and profit in plain English
4. Alerts you to any unusual spending or cash flow problems
5. Emails you a summary every Monday morning

**What You Need:**
- Bank account and credit card access
- Payment processor (Stripe, PayPal, Square)
- Accounting software
- Spreadsheet program (Google Sheets)

**Step-by-Step n8n Setup:**

1. **Create Financial Dashboard Workflow**
   - Start workflow called "Weekly Financial Dashboard"
   - Add "Schedule Trigger" for Monday mornings at 8 AM

2. **Collect Financial Data**
   - Add "Bank API" or "Plaid" node to get account balances
   - Connect "Stripe" or "PayPal" node for payment data
   - Add "QuickBooks" node for expense categories

3. **Calculate Key Numbers**
   - Use "Code" node to calculate:
     - This week's revenue vs last week
     - Total expenses by category
     - Cash flow (money in minus money out)
     - Biggest expense categories

4. **Create Visual Summary**
   - Add "Google Sheets" node to create dashboard
   - Include charts for revenue trends and expense breakdown
   - Use simple traffic light colors (green=good, yellow=caution, red=problem)

5. **Send Weekly Report**
   - Add "Email" node to send dashboard every Monday
   - Include key insights: "Revenue up 15% this week" or "Office supplies spending doubled"
   - Highlight action items if needed

**Alternative: Make.com Setup**

1. **Create Financial Dashboard Scenario**
   - Name scenario "Weekly Financial Dashboard"
   - Add "Schedule" module for Monday reports

2. **Connect Financial Sources**
   - Add "Stripe > List charges" for revenue data
   - Add "QuickBooks > Get expenses" for spending data
   - Add "Bank API" or "Plaid" for account balances

3. **Calculate Metrics**
   - Use "Math > Perform a function" to calculate:
     - Week-over-week growth
     - Expense percentages by category
     - Cash runway (how long money will last)

4. **Generate Report**
   - Add "Google Sheets > Add a row" for data logging
   - Create charts and summary tables
   - Email formatted report with insights

**What You Get:**
- Know your business health in 2 minutes every week
- Catch cash flow problems early
- See which expenses are growing too fast
- Make smarter money decisions

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, basic to advanced reporting):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Payment processor APIs: Free (included with existing accounts)
- Reporting tools: Free (Google Sheets) to $25/month (business dashboards)
- **Total: $0-45/month**

**Medium Business (250-1,000 employees, enterprise reporting):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Payment processor APIs: $15-50/month (higher API limits, multiple processors)
- Reporting tools: $50-150/month (advanced BI tools, multi-entity reporting)
- **Total: $115-299/month**

**Enterprise (1,000+ employees, real-time multi-entity dashboards):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Payment processor APIs: $100+/month (enterprise API access, multiple regions)
- Reporting tools: $300+/month (enterprise BI, custom dashboards)
- **Total: $600+/month**

*Cost assumptions: Multiple payment processors, complex multi-entity reporting, real-time dashboard requirements*

---

## 🔄 Expense Tracking & Approval

**What It Does:** Automatically tracks business expenses and gets them approved without paperwork.

**How It Works:**
1. Captures receipts from your phone or email
2. Automatically logs mileage when you drive for business
3. Routes expense reports to the right person for approval
4. Handles reimbursements and tax category assignment
5. Keeps everything organized for tax time

**What You Need:**
- Smartphone with GPS
- Expense management app (Expensify, Receipt Bank)
- Approval workflow (email or Slack)
- Accounting software connection

**Step-by-Step n8n Setup:**

1. **Create Expense Tracking Workflow**
   - Start workflow called "Expense Tracking & Approval"
   - Add "Webhook" to receive expense submissions

2. **Capture Expense Data**
   - Add "Extract from File" for receipt OCR
   - Connect "GPS" node for automatic mileage tracking
   - Use "Set" node to format expense data with date, amount, category

3. **Smart Categorization**
   - Add "OpenAI" node with prompt: "Categorize this business expense: meals, travel, office, equipment, or other"
   - Use "Switch" node to route by expense type and amount

4. **Approval Workflow**
   - Add "IF" node: "If expense > $100, send for approval"
   - Connect "Email" or "Slack" node to manager/owner
   - Include receipt image and expense details

5. **Process Approved Expenses**
   - Add "Email Trigger" to catch approval responses
   - Connect accounting software to record approved expenses
   - Send confirmation email to employee

**Alternative: Make.com Setup**

1. **Create Expense Management Scenario**
   - Name scenario "Expense Tracking & Approval"
   - Add "Webhooks > Custom webhook" for expense submissions

2. **Receipt Processing**
   - Add "Google Vision API" for OCR
   - Extract vendor, amount, category automatically
   - Add location data if available

3. **Approval Routing**
   - Use "Filter" module: expenses over threshold need approval
   - Send "Email" or "Slack" message to approver
   - Include all expense details and receipt image

4. **Accounting Integration**
   - Add "QuickBooks > Create expense" for approved items
   - Assign proper tax categories and projects
   - Update expense status to "approved" and "recorded"

**What You Get:**
- No more lost receipts or forgotten expenses
- Automatic mileage tracking saves hours
- Fast approval process keeps everyone happy

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, moderate expense volume):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Expense app: $5-8/month per user (25-250 users: $125-2,000/month)
- OCR/AI processing: $25-100/month (moderate to high receipt volume)
- **Total: $150-2,120/month**

**Medium Business (250-1,000 employees, high expense volume):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Expense app: $8-12/month per user (250-1,000 users: $2,000-12,000/month)
- OCR/AI processing: $150-500/month (very high receipt volume)
- **Total: $2,200-12,599/month**

**Enterprise (1,000+ employees, enterprise expense management):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Expense app: $12-20/month per user (1,000+ users: $12,000+/month)
- OCR/AI processing: $750+/month (enterprise-grade processing)
- **Total: $12,950+/month**

*Cost assumptions: Per-user expense app licensing scales significantly, enterprise compliance and approval workflows*
- Tax-ready expense records all year

---

## 📞 Customer Payment Reminders

**What It Does:** Sends friendly but firm payment reminders to customers who owe you money.

**How It Works:**
1. Checks your accounting system daily for overdue invoices
2. Sends different reminder messages based on how late payment is
3. Escalates tone appropriately (friendly → firm → final notice)
4. Tracks which customers pay fastest and which are always late
5. Stops reminders automatically when payment arrives

**What You Need:**
- Invoicing software (QuickBooks, FreshBooks, Wave)
- Email system
- Customer contact database
- Payment processor integration

**Step-by-Step n8n Setup:**

1. **Create Payment Reminder Workflow**
   - Start workflow called "Customer Payment Reminders"
   - Add "Schedule Trigger" to run daily at 9 AM

2. **Check for Overdue Invoices**
   - Add "QuickBooks" or invoicing software node
   - Filter for invoices where: due date + 1 day < today
   - Exclude invoices already marked as "reminder sent today"

3. **Determine Reminder Level**
   - Use "Switch" node based on days overdue:
     - 1-7 days: friendly reminder
     - 8-21 days: firm but polite
     - 22+ days: final notice

4. **Send Appropriate Message**
   - Add "Email" nodes for each reminder type
   - Include invoice copy and easy payment link
   - Use customer's name and specific invoice details

5. **Track Response and Stop Reminders**
   - Monitor payment processor for incoming payments
   - Auto-update invoice status when paid
   - Send thank you email and stop reminder sequence

**Alternative: Make.com Setup**

1. **Create Payment Reminder Scenario**
   - Name scenario "Customer Payment Reminders"
   - Add "Schedule" module for daily reminder checks

2. **Invoice Status Check**
   - Add "QuickBooks > Search invoices" with overdue filter
   - Exclude recently sent reminders to avoid spam

3. **Escalation Logic**
   - Use "Router" module for different reminder levels
   - Each path has different email template and tone

4. **Payment Tracking**
   - Add "Stripe > Watch payments" or similar
   - Match payments to invoices automatically
   - Update status and send thank you notes

**What You Get:**
- Get paid 40% faster on average
- Professional, consistent reminder process
- No more awkward phone calls about money
- Know which customers need credit limits

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, moderate customer base):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Invoicing software: $15-60/month (multi-user, advanced features)
- Email service: Free to $25/month (professional templates, tracking)
- **Total: $15-105/month**

**Medium Business (250-1,000 employees, large customer base):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Invoicing software: $100-300/month (enterprise features, multi-entity)
- Email service: $50-150/month (advanced automation, CRM integration)
- **Total: $200-549/month**

**Enterprise (1,000+ employees, enterprise customer management):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Invoicing software: $500+/month (enterprise ERP integration)
- Email service: $200+/month (enterprise marketing automation)
- **Total: $900+/month**

*Cost assumptions: Customer base scales with business size, enterprise-grade invoicing and payment processing*

---

## 🛡️ Basic Bookkeeping Assistant

**What It Does:** Handles routine bookkeeping tasks so your numbers are always accurate and tax-ready.

**How It Works:**
1. Automatically categorizes transactions from bank feeds
2. Matches deposits to outstanding invoices
3. Reconciles bank accounts monthly
4. Flags unusual transactions for review
5. Keeps books organized for tax preparation

**What You Need:**
- Bank account with online access
- Accounting software (QuickBooks, Xero)
- Business transaction history
- Basic chart of accounts setup

**Step-by-Step n8n Setup:**

1. **Create Bookkeeping Workflow**
   - Start workflow called "Basic Bookkeeping Assistant"
   - Add "Schedule Trigger" to run daily for transaction processing

2. **Import Bank Transactions**
   - Add "Bank API" or "Plaid" node to fetch new transactions
   - Filter for business accounts only
   - Exclude already processed transactions

3. **Smart Transaction Categorization**
   - Add "OpenAI" node with prompt: "Categorize this business transaction: [description] [amount] into: office supplies, meals, travel, utilities, income, or other"
   - Use historical patterns to improve accuracy

4. **Match Payments to Invoices**
   - Compare incoming deposits to outstanding invoices
   - Auto-match by amount and customer name
   - Flag partial payments or unmatched deposits

5. **Generate Reconciliation Report**
   - Compare bank balance to accounting software balance
   - Highlight discrepancies for manual review
   - Email monthly reconciliation summary

**Alternative: Make.com Setup**

1. **Create Bookkeeping Scenario**
   - Name scenario "Basic Bookkeeping Assistant"
   - Add "Schedule" module for daily transaction processing

2. **Transaction Import and Categorization**
   - Add "Bank/Plaid > Get transactions"
   - Use "OpenAI > Create a chat completion" for smart categorization
   - Store patterns to improve future categorization

3. **Invoice Matching**
   - Add "QuickBooks > Get invoices" for outstanding items
   - Match deposits to invoices by amount and date range

4. **Reconciliation and Reporting**
   - Compare bank balances to accounting records
   - Generate discrepancy reports for review
   - Email monthly summaries to business owner

**What You Get:**
- Books always up to date without manual entry
- Tax preparation takes hours instead of days
- Catch errors and fraud quickly
- Professional financial records for loans or investors

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, multiple accounts, high transaction volume):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Bank API/Plaid: $25-100/month (multiple accounts, high transaction volume)
- Accounting software: $50-100/month (multi-user, advanced features)
- AI categorization: $50-150/month (high transaction volume)
- **Total: $125-370/month**

**Medium Business (250-1,000 employees, multi-entity accounting):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Bank API/Plaid: $150-400/month (enterprise transaction limits, multiple entities)
- Accounting software: $200-500/month (multi-entity, advanced reporting)
- AI categorization: $200-500/month (very high transaction volume)
- **Total: $600-1,499/month**

**Enterprise (1,000+ employees, complex multi-entity bookkeeping):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Bank API/Plaid: $500+/month (enterprise-grade, global transactions)
- Accounting software: $1,000+/month (enterprise ERP integration)
- AI categorization: $750+/month (enterprise-grade processing)
- **Total: $2,450+/month**

*Cost assumptions: Multi-entity accounting, global transactions, complex categorization rules, enterprise compliance*

---

## 🎯 Getting Started Guide

### Start With One Automation
Pick the one that would save you the most time right now. Most business owners start with invoice reminders or expense tracking.

### Use What You Have
- Connect to your existing accounting software first
- Start with your current email and banking setup
- Don't buy new tools until you see the automation working

### Learn Step by Step
- Watch YouTube tutorials for your chosen platform (n8n or Make.com)
- Join business automation communities online
- Start simple and add complexity over time

### Budget Planning
- n8n: Free for basic use, $20/month for teams
- Make.com: Free for small automations, $10/month for more
- Accounting software: Usually $20-50/month
- Total: Usually $50-150/month for complete setup

### Expected Results
- 70% reduction in time spent on financial admin
- 40% faster customer payments
- 90% fewer manual data entry errors
- 25% improvement in cash flow management

---

## 🛡️ Best Practices

### Keep Your Data Safe
- Never store bank passwords in automation tools
- Use secure API connections only
- Review automation actions weekly
- Keep backup copies of important financial data

### Start Simple
- Begin with one workflow and master it
- Add new automations only after the first one works well
- Test everything with small amounts first
- Have a manual backup plan

### Monitor Performance
- Track time saved each week
- Measure faster payment collection
- Monitor error rates in automated categorization
- Adjust settings based on results

---

## 📞 Common Questions

**Q: Is it safe to connect my bank account to automation?**
A: Yes, when done properly. Use read-only API connections, never share passwords, and choose reputable platforms with bank-level security.

**Q: What if the automation makes a mistake?**
A: All good automation includes human review steps for important decisions. You'll approve transactions over certain amounts and review monthly reports.

**Q: How long before I see results?**
A: Most business owners see time savings within the first week and payment improvements within 30 days.

**Q: Can I turn off automations if needed?**
A: Absolutely. You maintain full control and can pause, modify, or stop any automation at any time.

---

## 📈 Success Metrics

### Track These Numbers
- Hours saved per week on admin tasks
- Average days to collect payment (aim for 15-30% improvement)
- Percentage of expenses automatically categorized
- Accuracy rate of automated bookkeeping

### Expect These Results
- 80% reduction in manual receipt processing
- 40% faster invoice payment collection
- 95% accuracy in automated expense categorization
- 15-20 hours saved per week on financial admin

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
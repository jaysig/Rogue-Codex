# Detention Management and Billing System

**What It Does:** Automatically tracks driver detention time, calculates detention fees, manages billing for delayed loading/unloading, and helps recover lost revenue from facility delays that cost the industry $3.6 billion annually.

**How It Works:**
1. Automatically tracks arrival, start, and completion times at loading/unloading facilities
2. Calculates detention time based on industry standards and contracted grace periods
3. Generates detention invoices and tracks payment status with automated follow-up
4. Monitors facility performance and identifies chronic delay locations for route planning
5. Creates comprehensive detention reports for rate negotiations and operational planning

**What You Need:**
- ELD system with location tracking and duty status monitoring
- Fleet management platform with load and delivery data
- Invoicing and billing system for detention fee processing
- Communication platform for customer notifications and billing follow-up

**Step-by-Step n8n Setup:**

1. **Create Detention Tracking Workflow**
   - Start workflow called "Detention Management and Billing System"
   - Add triggers from ELD system for arrival/departure events at facilities

2. **Detention Time Calculation**
   - Add "Code" node to calculate detention periods:
     - Track arrival time at facility (GPS geofence entry)
     - Monitor loading/unloading start time (duty status change)
     - Calculate free time allowance (typically 2 hours industry standard)
     - Compute billable detention time beyond grace period
   - Cross-reference with contracted detention rates and billing terms

3. **Automated Documentation**
   - Capture detention evidence automatically:
     - GPS location data with timestamps
     - ELD duty status changes and driver logs
     - Photos of facility conditions (if equipped with dash cam)
     - Communication logs with facility personnel
   - Generate detention incident reports with all supporting documentation

4. **Billing & Invoice Generation**
   - Create detention invoices with automated calculations:
     - Billable detention hours and applicable rates
     - Supporting documentation and evidence attachments
     - Customer-specific billing terms and contact information
     - Payment due dates and follow-up schedules
   - Send invoices through appropriate channels (email, EDI, customer portals)

5. **Performance Monitoring & Reporting**
   - Track facility performance metrics:
     - Average detention time by facility and customer
     - Detention fee collection rates and payment timelines
     - Cost impact analysis for route planning decisions
     - Historical trends for rate negotiation data
   - Generate monthly detention reports for business analysis

**Alternative: Make.com Setup**

1. **Create Detention Tracking Scenario**
   - Name scenario "Detention Management and Billing System"
   - Add ELD system webhooks for location and duty status updates

2. **Time Calculation Pipeline**
   - Add "Date & time > Add/subtract time" for detention calculations
   - Use "Math > Perform a function" for billing rate calculations
   - Include "Filter" to identify billable detention events

3. **Documentation & Billing**
   - Add "Google Drive > Upload a file" for detention documentation
   - Use "Invoice > Create an invoice" or similar billing connector
   - Include "Email > Send an email" for invoice delivery

4. **Analytics & Reporting**
   - Add "Google Sheets > Add a row" for detention tracking logs
   - Use "Aggregator" for facility performance calculations
   - Include "Slack > Create a message" for detention alerts

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build detention management scenarios with pre-built transportation and billing connectors.

**What You Get:**
- Recover 50-80% of detention fees through automated tracking and billing
- Eliminate 3-4 hours/week of manual detention documentation and billing
- Improve route planning with facility performance data and chronic delay identification
- Increase detention fee collection rates from 50% to 85% through systematic follow-up
- Create comprehensive detention documentation for dispute resolution and rate negotiations

**💰 Monthly Operating Costs:**

**Owner-Operator/Small Fleet (1-5 trucks):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- ELD integration: Usually included in existing ELD subscription
- GPS tracking enhancement: $50-150/month (enhanced location services)
- Billing and invoicing tools: $30-100/month
- **Total: $80-270/month**

**Medium Fleet (5-25 trucks):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- ELD integration: $200-500/month (enhanced fleet management features)
- GPS tracking enhancement: $200-600/month (fleet-wide enhanced tracking)
- Billing and invoicing tools: $100-400/month
- **Total: $550-1,599/month**

**Large Fleet (25+ trucks):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- ELD integration: $800+/month (enterprise fleet management platforms)
- GPS tracking enhancement: $800+/month (enterprise tracking and analytics)
- Billing and invoicing tools: $400+/month (enterprise billing systems)
- **Total: $2,200+/month**

*Cost assumptions: Fleet size, detention frequency, billing complexity, integration requirements with existing ELD and fleet management systems*
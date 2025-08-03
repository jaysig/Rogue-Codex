# F&B Sales Professional Automations

Specialized automation workflows for food and beverage sales professionals to streamline customer relationship management, optimize territory coverage, and drive revenue growth using AI-powered tools tailored for the food service industry.

## What This Is

These automations handle the relationship management and administrative tasks that consume 60-70% of a food sales professional's time, so you can focus on the 20% of sales activities that generate 80% of revenue - building relationships, solving customer problems, and driving strategic account growth. Like having a dedicated sales support team.

**Who This Helps:** Food distributors, meat sales reps, beverage sales managers, restaurant account managers, foodservice specialists  
**Tools Used:** n8n or Make.com, CRM systems, route planning, inventory management, order processing  
**Time Saved:** 20-25 hours per week  
**Results:** 60% more face-to-face selling time, 50% faster order processing  

---

## 🥩 Customer Relationship & Account Management

**What It Does:** Automates comprehensive customer relationship management for food service accounts, focusing on the 20% of customers who generate 80% of revenue and growth opportunities.

**How It Works:**
1. Tracks customer ordering patterns, preferences, and seasonal trends
2. Manages account-specific pricing, promotions, and contract terms
3. Monitors customer satisfaction and identifies growth opportunities
4. Coordinates delivery schedules and inventory management
5. Automates follow-up communications and relationship building activities

**What You Need:**
- Customer Relationship Management (CRM) system (Salesforce, HubSpot, food industry CRM)
- Order management and inventory tracking systems
- Route planning and delivery coordination tools
- Customer communication and marketing platforms

**Step-by-Step n8n Setup:**

1. **Create Customer Management Workflow**
   - Start workflow called "Customer Relationship & Account Management"
   - Add triggers for customer interactions and order events

2. **Customer Intelligence & Analytics**
   - Add "Code" node to analyze customer data:
     - Track ordering frequency, volume, and seasonal patterns
     - Identify customer preferences for specific products and cuts
     - Monitor payment terms, credit limits, and account health
     - Analyze customer profitability and growth potential
   - Generate customer insight reports for strategic account planning

3. **Personalized Account Management**
   - Use "OpenAI" node to create tailored customer interactions:
     - Generate personalized product recommendations based on ordering history
     - Create customer-specific promotions and seasonal offerings
     - Develop menu suggestions and cost-saving opportunities
     - Craft personalized communications that resonate with each account

4. **Delivery & Service Coordination**
   - Automate logistics and service delivery:
     - Coordinate delivery schedules with customer operations
     - Track order fulfillment and delivery confirmation
     - Manage special requests for custom cuts or processing
     - Handle substitutions and emergency order fulfillment

5. **Relationship Building Automation**
   - Maintain consistent customer engagement:
     - Send regular check-ins and account health assessments
     - Share industry insights, market trends, and pricing updates
     - Celebrate customer milestones and business achievements
     - Coordinate trade shows, events, and educational opportunities

**Alternative: Make.com Setup**

1. **Create Food Service CRM Scenario**
   - Name scenario "Customer Relationship & Account Management"
   - Add "CRM > Watch customer updates" for account triggers

2. **Intelligence Gathering**
   - Add "Order System > Get history" for purchasing patterns
   - Use "Analytics > Calculate trends" for customer insights
   - Include "Market Data > Get pricing" for competitive analysis

3. **Personalization Engine**
   - Add "OpenAI > Create a chat completion" for customer recommendations
   - Generate tailored product suggestions and promotions
   - Create personalized communication and outreach

4. **Service Coordination**
   - Add "Logistics > Schedule delivery" for order fulfillment
   - Use "Inventory > Check availability" for order processing
   - Include "Communication > Send update" for delivery coordination

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build food service scenarios faster.

**What You Get:**
- Deep customer insights with personalized account management
- Optimized delivery coordination and service excellence
- Proactive relationship building with consistent engagement
- 70% improvement in customer retention and account growth

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, independent distributors/small territories):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Food service CRM: $200-600/month (specialized food industry CRM)
- Route planning: $100-300/month (delivery optimization tools)
- Communication tools: $50-150/month (customer communication platforms)
- **Total: $350-1,070/month**

**Medium Business (250-1,000 employees, regional distributors):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Food service CRM: $800-2,500/month (enterprise food service CRM)
- Route planning: $400-1,000/month (advanced logistics platforms)
- Communication tools: $200-500/month (enterprise communication tools)
- **Total: $1,450-4,099/month**

**Enterprise (1,000+ employees, national food distributors):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Food service CRM: $3,000+/month (enterprise food service platforms)
- Route planning: $1,500+/month (enterprise logistics and route optimization)
- Communication tools: $800+/month (enterprise communication systems)
- **Total: $5,500+/month**

*Cost assumptions: Territory size, customer count, enterprise food service platform requirements*

---

## 📍 Territory Management & Route Optimization

**What It Does:** Optimizes territory coverage and customer visit planning, focusing on the 20% of route optimization that drives 80% of sales efficiency and customer satisfaction.

**How It Works:**
1. Automatically plans optimal routes for customer visits and deliveries
2. Schedules customer visits based on importance, timing, and geographic efficiency
3. Tracks territory performance metrics and coverage analysis
4. Manages competitive intelligence and market opportunity mapping
5. Coordinates with warehouse and logistics for efficient order fulfillment

**What You Need:**
- Route planning and GPS optimization software
- Territory mapping and customer location tools
- Mobile apps for field sales activities
- Delivery tracking and logistics coordination systems

**Step-by-Step n8n Setup:**

1. **Create Territory Management Workflow**
   - Start workflow called "Territory Management & Route Optimization"
   - Add "Schedule Trigger" for daily route planning and optimization

2. **Intelligent Route Planning**
   - Add "HTTP Request" nodes to optimize customer visits:
     - Calculate optimal routes based on customer priority and location
     - Factor in delivery schedules, order volumes, and time constraints
     - Consider traffic patterns, weather conditions, and road restrictions
     - Balance new prospect visits with existing customer maintenance

3. **Customer Visit Prioritization**
   - Use "Switch" node to prioritize customer interactions:
     - High-value accounts requiring frequent personal attention
     - Accounts with pending orders or special requirements
     - Prospects with high conversion potential
     - Service recovery visits for customer issues or complaints

4. **Performance Tracking & Analytics**
   - Monitor territory metrics and optimization opportunities:
     - Track miles driven, time spent, and customers visited per day
     - Analyze sales per customer visit and conversion rates
     - Monitor territory penetration and market share by area
     - Identify gaps in coverage and untapped market opportunities

5. **Competitive Intelligence Gathering**
   - Collect market intelligence during customer visits:
     - Track competitor pricing, products, and promotional activities
     - Monitor customer satisfaction with competing suppliers
     - Identify switching opportunities and competitive vulnerabilities
     - Gather market trends and customer feedback for product development

**Alternative: Make.com Setup**

1. **Create Route Optimization Scenario**
   - Name scenario "Territory Management & Route Optimization"
   - Add "Schedule" module for daily route planning

2. **Route Calculation**
   - Add "Google Maps > Calculate route" for optimal path planning
   - Use "Customer Priority > Rank visits" for scheduling
   - Include "Traffic > Get conditions" for timing optimization

3. **Performance Monitoring**
   - Add "GPS > Track location" for visit verification
   - Use "Analytics > Calculate metrics" for territory performance
   - Include "CRM > Update activity" for visit documentation

4. **Intelligence Collection**
   - Add "Mobile App > Capture data" for field information
   - Use "Competitive > Track activity" for market intelligence
   - Include "Report > Generate summary" for territory analysis

**What You Get:**
- Optimized route planning with maximum customer coverage
- Data-driven territory management and performance tracking
- Systematic competitive intelligence and market analysis
- 60% improvement in territory efficiency and sales productivity

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, independent distributors/small territories):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Route planning: $100-300/month (GPS and route optimization)
- Territory mapping: $50-150/month (mapping and customer location tools)
- Mobile apps: $30-80/month (field sales mobile applications)
- **Total: $180-550/month**

**Medium Business (250-1,000 employees, regional distributors):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Route planning: $400-1,000/month (advanced route optimization)
- Territory mapping: $200-500/month (enterprise mapping platforms)
- Mobile apps: $150-400/month (enterprise mobile sales tools)
- **Total: $800-1,999/month**

**Enterprise (1,000+ employees, national food distributors):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Route planning: $1,500+/month (enterprise route optimization)
- Territory mapping: $800+/month (enterprise mapping and analytics)
- Mobile apps: $600+/month (enterprise mobile sales platforms)
- **Total: $3,100+/month**

*Cost assumptions: Territory size, number of sales reps, enterprise logistics platform requirements*

---

## 📋 Order Processing & Inventory Management

**What It Does:** Streamlines order taking, processing, and inventory coordination, focusing on the 20% of order management that ensures 80% of customer satisfaction and delivery accuracy.

**How It Works:**
1. Automates order entry, validation, and processing workflows
2. Provides real-time inventory availability and allocation management
3. Coordinates with warehouse and logistics for fulfillment planning
4. Manages special orders, custom cuts, and processing requirements
5. Tracks order status and provides customer communication updates

**What You Need:**
- Order management and processing systems
- Inventory management and tracking platforms
- Warehouse management and fulfillment coordination
- Customer communication and notification tools

**Step-by-Step n8n Setup:**

1. **Create Order Processing Workflow**
   - Start workflow called "Order Processing & Inventory Management"
   - Add triggers for customer orders and inventory updates

2. **Automated Order Validation**
   - Add "Code" node to validate and process orders:
     - Verify customer credit limits and payment terms
     - Check product availability and inventory levels
     - Validate special requirements and custom specifications
     - Calculate pricing, discounts, and delivery charges

3. **Inventory Coordination & Allocation**
   - Integrate with warehouse systems for inventory management:
     - Reserve inventory for confirmed orders
     - Coordinate special processing and custom cut requirements
     - Manage allocation for high-demand products
     - Track expiration dates and product rotation

4. **Fulfillment Planning & Coordination**
   - Coordinate order fulfillment and delivery scheduling:
     - Schedule picking, processing, and packaging activities
     - Coordinate delivery routes and timing with logistics
     - Manage temperature-controlled transportation requirements
     - Handle special delivery instructions and customer preferences

5. **Customer Communication & Updates**
   - Provide proactive order status communication:
     - Send order confirmation and processing updates
     - Notify customers of any changes or delays
     - Provide delivery tracking and arrival notifications
     - Handle order issues and customer service inquiries

**Alternative: Make.com Setup**

1. **Create Order Management Scenario**
   - Name scenario "Order Processing & Inventory Management"
   - Add "Order System > Watch orders" for processing triggers

2. **Validation Processing**
   - Add "Credit Check > Verify customer" for order approval
   - Use "Inventory > Check availability" for product validation
   - Include "Pricing > Calculate total" for order pricing

3. **Fulfillment Coordination**
   - Add "Warehouse > Schedule pick" for fulfillment planning
   - Use "Logistics > Plan delivery" for shipping coordination
   - Include "Temperature > Monitor conditions" for cold chain

4. **Communication Management**
   - Add "Email > Send email" for order confirmations
   - Use "SMS > Send message" for urgent updates
   - Include "Customer Portal > Update status" for tracking

**What You Get:**
- Streamlined order processing with reduced errors and delays
- Real-time inventory visibility and allocation optimization
- Coordinated fulfillment with improved delivery accuracy
- 75% reduction in order processing time and customer inquiries

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, independent distributors/small operations):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Order management: $200-600/month (basic order processing systems)
- Inventory systems: $150-400/month (inventory tracking and management)
- Communication tools: $50-150/month (customer notification systems)
- **Total: $400-1,170/month**

**Medium Business (250-1,000 employees, regional distributors):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Order management: $800-2,500/month (enterprise order processing)
- Inventory systems: $600-1,500/month (advanced inventory management)
- Communication tools: $200-500/month (enterprise communication platforms)
- **Total: $1,650-4,599/month**

**Enterprise (1,000+ employees, national food distributors):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Order management: $3,000+/month (enterprise order management systems)
- Inventory systems: $2,000+/month (enterprise inventory and warehouse systems)
- Communication tools: $800+/month (enterprise communication systems)
- **Total: $6,000+/month**

*Cost assumptions: Order volume, inventory complexity, enterprise food service platform requirements*

---

## 💰 Pricing & Promotion Management

**What It Does:** Automates pricing strategies and promotional campaigns, focusing on the 20% of pricing decisions that drive 80% of profitability and competitive advantage.

**How It Works:**
1. Monitors market pricing and competitive intelligence for dynamic pricing
2. Manages customer-specific pricing contracts and volume discounts
3. Automates promotional campaigns and seasonal offerings
4. Tracks pricing effectiveness and margin optimization opportunities
5. Provides real-time pricing guidance for sales negotiations

**What You Need:**
- Pricing management and optimization software
- Competitive intelligence and market data sources
- Promotion planning and campaign management tools
- Margin analysis and profitability tracking systems

**Step-by-Step n8n Setup:**

1. **Create Pricing Management Workflow**
   - Start workflow called "Pricing & Promotion Management"
   - Add triggers for market changes and pricing events

2. **Market Intelligence & Competitive Pricing**
   - Add "HTTP Request" nodes to monitor market conditions:
     - Track commodity prices and market trends for key products
     - Monitor competitor pricing and promotional activities
     - Analyze supply chain costs and cost inflation factors
     - Gather industry pricing intelligence and benchmarks

3. **Dynamic Pricing Optimization**
   - Use "OpenAI" node to optimize pricing strategies:
     - Calculate optimal pricing based on costs, competition, and demand
     - Generate customer-specific pricing recommendations
     - Adjust pricing for seasonal trends and market conditions
     - Optimize margins while maintaining competitive positioning

4. **Promotion Planning & Execution**
   - Automate promotional campaigns and seasonal offerings:
     - Plan seasonal promotions based on historical data and trends
     - Create customer-specific promotional offers and incentives
     - Coordinate promotional campaigns across customer segments
     - Track promotion effectiveness and ROI measurement

5. **Margin Analysis & Profitability Tracking**
   - Monitor pricing performance and profitability:
     - Track gross margins by product, customer, and territory
     - Identify pricing opportunities and margin improvement areas
     - Analyze price sensitivity and demand elasticity
     - Generate pricing guidance for sales negotiations

**Alternative: Make.com Setup**

1. **Create Pricing Strategy Scenario**
   - Name scenario "Pricing & Promotion Management"
   - Add "Market Data > Watch prices" for market triggers

2. **Competitive Analysis**
   - Add "Competitor > Get pricing" for market intelligence
   - Use "Commodity > Track prices" for cost analysis
   - Include "Analytics > Calculate margins" for profitability

3. **Pricing Optimization**
   - Add "OpenAI > Create a chat completion" for pricing strategy
   - Generate optimal pricing recommendations
   - Create customer-specific pricing proposals

4. **Promotion Management**
   - Add "Campaign > Create promotion" for seasonal offers
   - Use "Customer > Send offer" for targeted promotions
   - Include "Analytics > Track ROI" for campaign effectiveness

**What You Get:**
- Data-driven pricing with competitive market intelligence
- Automated promotional campaigns with measurable ROI
- Real-time pricing guidance for sales negotiations
- 65% improvement in margin optimization and profitability

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, independent distributors/small operations):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Pricing intelligence: $150-400/month (market data and competitive pricing)
- Promotion management: $100-300/month (campaign planning and tracking)
- Analytics tools: $50-150/month (margin and profitability analysis)
- **Total: $300-870/month**

**Medium Business (250-1,000 employees, regional distributors):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Pricing intelligence: $600-1,500/month (comprehensive market intelligence)
- Promotion management: $400-1,000/month (advanced campaign management)
- Analytics tools: $300-800/month (advanced analytics and optimization)
- **Total: $1,350-3,399/month**

**Enterprise (1,000+ employees, national food distributors):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Pricing intelligence: $2,000+/month (enterprise market intelligence)
- Promotion management: $1,500+/month (enterprise campaign management)
- Analytics tools: $1,000+/month (enterprise analytics and optimization)
- **Total: $4,700+/month**

*Cost assumptions: Market complexity, product range, enterprise pricing platform requirements*

---

## 📊 Sales Performance & Pipeline Analytics

**What It Does:** Provides comprehensive sales performance tracking and pipeline management, focusing on the 20% of analytics that drive 80% of sales improvement and forecasting accuracy.

**How It Works:**
1. Tracks individual and team sales performance against targets and quotas
2. Analyzes sales pipeline health and conversion probability
3. Provides predictive analytics for revenue forecasting and planning
4. Identifies sales trends, opportunities, and performance gaps
5. Generates actionable insights for sales coaching and development

**What You Need:**
- Sales performance tracking and analytics platforms
- Pipeline management and forecasting tools
- Business intelligence and reporting systems
- Sales coaching and development platforms

**Step-by-Step n8n Setup:**

1. **Create Sales Analytics Workflow**
   - Start workflow called "Sales Performance & Pipeline Analytics"
   - Add "Schedule Trigger" for regular performance analysis and reporting

2. **Performance Tracking & Measurement**
   - Monitor sales metrics and KPI achievement:
     - Track sales volume, revenue, and margin performance by rep
     - Monitor quota achievement and goal progression
     - Analyze customer acquisition and retention rates
     - Measure average order size and sales cycle length

3. **Pipeline Health & Forecasting**
   - Use "OpenAI" node to analyze pipeline data:
     - Assess opportunity probability and closing likelihood
     - Identify pipeline bottlenecks and conversion issues
     - Predict quarterly and annual revenue achievement
     - Generate accurate sales forecasts for planning

4. **Trend Analysis & Opportunity Identification**
   - Analyze sales patterns and market opportunities:
     - Identify seasonal trends and cyclical patterns
     - Recognize emerging customer needs and preferences
     - Spot competitive threats and market share changes
     - Highlight growth opportunities and expansion areas

5. **Coaching & Development Insights**
   - Generate sales coaching recommendations and development plans:
     - Identify skill gaps and training needs by sales rep
     - Recognize top performers and best practice sharing opportunities
     - Provide targeted coaching recommendations for improvement
     - Track professional development and skill enhancement progress

**Alternative: Make.com Setup**

1. **Create Performance Analytics Scenario**
   - Name scenario "Sales Performance & Pipeline Analytics"
   - Add "CRM > Get sales data" for performance information

2. **Metrics Calculation**
   - Add "Math > Perform a function" for performance calculations
   - Use "Analytics > Generate insights" for trend analysis
   - Include "Forecasting > Predict revenue" for planning

3. **Reporting Generation**
   - Add "Chart > Create visualization" for performance dashboards
   - Use "OpenAI > Create a chat completion" for insight generation
   - Include "Email > Send email" for regular reporting

4. **Development Planning**
   - Add "Performance > Assess gaps" for coaching identification
   - Use "Training > Recommend development" for skill building
   - Include "Goal > Track progress" for improvement monitoring

**What You Get:**
- Comprehensive sales performance tracking with actionable insights
- Accurate pipeline forecasting and revenue prediction
- Data-driven coaching and development recommendations
- 80% improvement in sales forecasting accuracy and performance management

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, independent distributors/small sales teams):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Sales analytics: $200-500/month (basic sales performance tracking)
- Pipeline management: $150-400/month (pipeline and forecasting tools)
- Reporting tools: $100-250/month (business intelligence and reporting)
- **Total: $450-1,170/month**

**Medium Business (250-1,000 employees, regional distributors):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Sales analytics: $800-2,000/month (advanced sales analytics platforms)
- Pipeline management: $600-1,500/month (enterprise pipeline management)
- Reporting tools: $400-1,000/month (enterprise business intelligence)
- **Total: $1,850-4,599/month**

**Enterprise (1,000+ employees, national food distributors):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Sales analytics: $3,000+/month (enterprise sales analytics)
- Pipeline management: $2,000+/month (enterprise pipeline and forecasting)
- Reporting tools: $1,500+/month (enterprise BI and analytics)
- **Total: $6,700+/month**

*Cost assumptions: Sales team size, data complexity, enterprise analytics platform requirements*

---

## 🎯 Getting Started Guide

### Start with Customer Relationship Management
Most F&B sales professionals see immediate value from automated customer intelligence and relationship tracking - it optimizes time spent with high-value accounts.

### Use Your Current Food Service Systems
Connect automations to whatever CRM, order management, and inventory systems you already use. Don't switch platforms just for automation.

### Begin with Route Optimization
Start with simple route planning and territory management before moving to complex pricing or analytics automation.

### Budget Planning
- Food service technology: Usually $500-3,000/month depending on business size
- n8n or Make.com: Free to $400/month for F&B sales automations
- Specialized food industry tools: Usually $500-2,000/month based on territory size
- Total: Usually $1,500-8,000/month for complete F&B sales automation

---

## 🛡️ Best Practices

### Maintain Food Safety Standards
- Ensure all automated processes comply with food safety regulations and HACCP requirements
- Include human oversight for temperature-sensitive products and cold chain management
- Maintain comprehensive traceability and documentation for all food products
- Regular review of automated processes for food safety compliance

### Preserve Customer Relationships
- Use automation to enhance, not replace, personal relationship building in food service
- Include human touch in critical customer interactions and problem resolution
- Review automated communications for appropriateness in the food service industry
- Maintain the trust and reliability that food service customers require

### Focus on Service Excellence
- Use automation to create more time for face-to-face customer engagement
- Combine automated efficiency with food industry expertise and problem-solving
- Continuously improve automation based on customer feedback and service outcomes
- Maintain the quality and reliability that food service operations demand

---

## 📞 Common Questions

**Q: Will customers accept automated order processing in food service?**
A: Focus on faster order fulfillment and fewer errors. Most food service customers appreciate efficient, accurate automation that ensures product availability and on-time delivery.

**Q: How do we handle special requirements like custom cuts or processing?**
A: Include specialized workflows for custom orders while maintaining human oversight for complex requirements. Use automation for standard processes while preserving flexibility.

**Q: What about maintaining personal relationships in food sales?**
A: Use automation to handle routine tasks so you have more time for relationship building. The goal is more face-to-face time, not less personal connection.

**Q: Can we customize automation for different food categories?**
A: Absolutely. Set up different workflows for meat, produce, dairy, frozen foods, etc., based on their unique handling and customer requirements.

---

## 📈 Success Metrics

### Track These Numbers
- Customer retention rates and account growth
- Territory coverage efficiency and customer visit frequency
- Order accuracy and delivery performance
- Margin optimization and pricing effectiveness
- Sales performance and quota achievement

### Expect These Results
- 70% improvement in customer retention and account growth
- 60% improvement in territory efficiency and sales productivity
- 75% reduction in order processing time and errors
- 65% improvement in margin optimization and profitability
- 80% improvement in sales forecasting accuracy

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
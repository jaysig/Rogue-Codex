# HR Leader Automations

Strategic automation workflows for HR leaders to streamline talent management, optimize workforce analytics, and drive organizational effectiveness using AI-powered tools that focus on people strategy over administrative tasks.

## What This Is

These automations handle the operational and administrative burdens that consume 60-70% of an HR leader's time, so you can focus on the 20% of strategic activities that drive 80% of organizational impact - talent strategy, culture transformation, and business partnership. Like having a dedicated HR operations team.

**Who This Helps:** Chief Human Resources Officers, VP of People, HR Directors, Talent Leaders, People Operations Managers  
**Tools Used:** n8n or Make.com, HRIS platforms, talent management systems, analytics tools  
**Time Saved:** 25-30 hours per week  
**Results:** 70% more strategic focus time, 60% faster talent processes  

---

## 👥 Strategic Talent Acquisition & Pipeline Management

**What It Does:** Automates end-to-end recruitment processes and talent pipeline management, focusing on the 20% of recruitment activities that secure 80% of top talent.

**How It Works:**
1. Identifies and sources high-quality candidates across multiple channels
2. Automates candidate screening and initial assessment processes
3. Manages interview scheduling and coordination across teams
4. Provides data-driven hiring insights and recommendation engines
5. Tracks candidate experience and recruiter performance metrics

**What You Need:**
- Applicant Tracking System (Workday, BambooHR, Greenhouse)
- Sourcing platforms (LinkedIn Recruiter, Indeed, ZipRecruiter)
- Interview scheduling and coordination tools
- Candidate assessment and evaluation platforms

**Step-by-Step n8n Setup:**

1. **Create Talent Acquisition Workflow**
   - Start workflow called "Strategic Talent Acquisition & Pipeline Management"
   - Add triggers for job postings and candidate applications

2. **Multi-Channel Candidate Sourcing**
   - Add "HTTP Request" nodes to search talent pools:
     - LinkedIn talent pipeline and passive candidate identification
     - Internal referral program and employee network mining
     - University recruiting and campus partnership management
     - Industry-specific job boards and professional networks
   - Score candidates based on fit criteria and market availability

3. **AI-Powered Candidate Screening**
   - Use "OpenAI" node to analyze candidate profiles:
     - Resume parsing and skill extraction
     - Culture fit assessment based on company values
     - Experience relevance and career trajectory analysis
     - Compensation expectations and negotiation likelihood
   - Generate candidate scorecards and recommendation rankings

4. **Interview Process Orchestration**
   - Coordinate complex interview processes automatically:
     - Schedule interviews across multiple stakeholders and time zones
     - Send preparation materials and job-specific questions to interviewers
     - Collect and aggregate interview feedback from all participants
     - Generate comprehensive candidate evaluation reports

5. **Talent Analytics & Pipeline Insights**
   - Track recruitment metrics and optimization opportunities:
     - Time-to-hire and cost-per-hire by role and department
     - Source effectiveness and quality-of-hire metrics
     - Diversity and inclusion pipeline analysis
     - Candidate experience satisfaction and improvement areas

**Alternative: Make.com Setup**

1. **Create Recruitment Pipeline Scenario**
   - Name scenario "Strategic Talent Acquisition & Pipeline Management"
   - Add "ATS > Watch applications" for candidate triggers

2. **Sourcing Automation**
   - Add "LinkedIn > Search profiles" for passive candidate identification
   - Use "Referral System > Track submissions" for employee referrals
   - Include "University > Get candidates" for campus recruiting

3. **Assessment Processing**
   - Add "OpenAI > Create a chat completion" for candidate evaluation
   - Generate fit scores and cultural alignment assessments
   - Rank candidates by potential and availability

4. **Process Management**
   - Add "Calendar > Create event" for interview scheduling
   - Use "Email > Send email" for candidate communication
   - Include "Survey > Send feedback" for interviewer input

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build talent acquisition scenarios faster.

**What You Get:**
- Streamlined talent acquisition with improved quality-of-hire
- Automated candidate sourcing and pipeline management
- Data-driven hiring decisions with comprehensive analytics
- 75% reduction in recruitment administrative tasks

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, growing companies):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- ATS and recruiting: $300-800/month (basic talent acquisition platforms)
- Sourcing tools: $200-500/month (LinkedIn Recruiter, job boards)
- Assessment platforms: $100-300/month (candidate evaluation tools)
- **Total: $600-1,620/month**

**Medium Business (250-1,000 employees, established companies):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- ATS and recruiting: $1,500-4,000/month (enterprise recruiting platforms)
- Sourcing tools: $800-2,000/month (comprehensive sourcing suite)
- Assessment platforms: $500-1,200/month (advanced assessment tools)
- **Total: $2,850-7,299/month**

**Enterprise (1,000+ employees, large organizations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- ATS and recruiting: $5,000+/month (enterprise talent platforms)
- Sourcing tools: $3,000+/month (enterprise sourcing and CRM)
- Assessment platforms: $2,000+/month (enterprise assessment suite)
- **Total: $10,200+/month**

*Cost assumptions: Hiring volume, recruiter count, enterprise HR platform requirements*

---

## 🎯 Performance Management & Employee Development

**What It Does:** Automates performance review cycles and development planning, focusing on the 20% of performance management that drives 80% of employee engagement and retention.

**How It Works:**
1. Manages complete performance review cycles and 360-degree feedback
2. Identifies skill gaps and creates personalized development plans
3. Tracks goal progress and achievement across organization
4. Provides predictive analytics on performance trends and flight risk
5. Coordinates career pathing and succession planning processes

**What You Need:**
- Performance management systems (Workday, SuccessFactors, Lattice)
- Learning management platforms (Cornerstone, Degreed, LinkedIn Learning)
- Goal tracking and OKR management tools
- Employee engagement and pulse survey platforms

**Step-by-Step n8n Setup:**

1. **Create Performance Management Workflow**
   - Start workflow called "Performance Management & Employee Development"
   - Add "Schedule Trigger" for review cycles and check-ins

2. **Automated Review Process Coordination**
   - Orchestrate comprehensive performance review cycles:
     - Send review notifications and deadline reminders
     - Coordinate 360-degree feedback collection from peers and direct reports
     - Generate performance summary reports with trend analysis
     - Schedule performance conversations and calibration meetings

3. **Development Planning & Skill Gap Analysis**
   - Use "OpenAI" node to analyze development needs:
     - Identify skill gaps based on role requirements and career goals
     - Generate personalized learning paths and development recommendations
     - Suggest internal mentoring and stretch assignment opportunities
     - Create succession planning recommendations for high-potential employees

4. **Goal Tracking & Progress Monitoring**
   - Monitor goal achievement and organizational alignment:
     - Track individual and team OKR progress against targets
     - Identify goals at risk of missing deadlines or deliverables
     - Generate goal achievement insights and course correction recommendations
     - Align individual performance with business objectives

5. **Predictive People Analytics**
   - Generate insights on performance trends and retention risk:
     - Predict employee flight risk based on performance and engagement data
     - Identify high-potential employees for accelerated development
     - Analyze performance distribution and calibration across teams
     - Generate recommendations for talent mobility and career development

**Alternative: Make.com Setup**

1. **Create Performance Enhancement Scenario**
   - Name scenario "Performance Management & Employee Development"
   - Add "HRIS > Watch performance data" for employee triggers

2. **Review Automation**
   - Add "Calendar > Create event" for review scheduling
   - Use "Survey > Send form" for 360-degree feedback collection
   - Include "Report > Generate summary" for performance analysis

3. **Development Planning**
   - Add "OpenAI > Create a chat completion" for skill gap analysis
   - Generate learning recommendations and career path suggestions
   - Create personalized development plans

4. **Analytics and Insights**
   - Add "Analytics > Calculate metrics" for performance trends
   - Use "Prediction > Assess risk" for retention analysis
   - Include "Dashboard > Update display" for leadership visibility

**What You Get:**
- Streamlined performance review processes with consistent execution
- Data-driven development planning and career pathing
- Predictive insights on performance trends and retention risk
- 70% reduction in performance management administrative overhead

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, growing companies):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Performance management: $400-1,000/month (basic performance platforms)
- Learning management: $200-600/month (learning and development tools)
- Analytics tools: $150-400/month (people analytics platforms)
- **Total: $750-2,020/month**

**Medium Business (250-1,000 employees, established companies):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Performance management: $2,000-5,000/month (enterprise performance platforms)
- Learning management: $1,000-3,000/month (comprehensive learning suite)
- Analytics tools: $800-2,000/month (advanced people analytics)
- **Total: $3,850-10,099/month**

**Enterprise (1,000+ employees, large organizations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Performance management: $8,000+/month (enterprise performance platforms)
- Learning management: $5,000+/month (enterprise learning ecosystems)
- Analytics tools: $3,000+/month (enterprise people analytics)
- **Total: $16,200+/month**

*Cost assumptions: Employee count, review complexity, enterprise HR platform requirements*

---

## 📊 Workforce Analytics & Strategic Planning

**What It Does:** Transforms HR data into strategic business insights, focusing on the 20% of workforce analytics that drive 80% of business decision-making.

**How It Works:**
1. Consolidates HR data from multiple systems into unified dashboards
2. Provides predictive analytics on workforce trends and planning needs
3. Generates strategic recommendations for organizational design and structure
4. Tracks diversity, equity, and inclusion metrics with actionable insights
5. Creates workforce scenario planning and business impact modeling

**What You Need:**
- HR Information Systems (Workday, SuccessFactors, BambooHR)
- Business intelligence and analytics platforms (Tableau, PowerBI, Visier)
- Workforce planning and modeling tools
- Survey and engagement measurement platforms

**Step-by-Step n8n Setup:**

1. **Create Workforce Analytics Workflow**
   - Start workflow called "Workforce Analytics & Strategic Planning"
   - Add "Schedule Trigger" for regular data analysis and reporting

2. **Data Integration & Consolidation**
   - Pull data from multiple HR systems and sources:
     - Employee demographics, tenure, and performance data
     - Compensation, benefits, and total rewards information
     - Engagement survey results and culture metrics
     - Recruiting, retention, and turnover analytics
   - Standardize data formats and create unified data warehouse

3. **Predictive Workforce Modeling**
   - Use "OpenAI" node to generate workforce insights:
     - Predict future staffing needs based on business growth plans
     - Identify skills gaps and future capability requirements
     - Model the impact of organizational changes on productivity
     - Generate recommendations for workforce optimization

4. **Strategic Business Reporting**
   - Create executive-level workforce reports and dashboards:
     - Workforce cost analysis and budget planning recommendations
     - Talent ROI metrics and productivity measurement
     - Market benchmarking and competitive positioning analysis
     - Risk assessment for critical roles and succession planning

5. **DEI Analytics & Action Planning**
   - Monitor diversity, equity, and inclusion metrics:
     - Track representation across levels, functions, and demographics
     - Analyze pay equity and compensation gap identification
     - Monitor hiring, promotion, and retention patterns by demographic groups
     - Generate actionable recommendations for DEI improvement

**Alternative: Make.com Setup**

1. **Create Strategic Analytics Scenario**
   - Name scenario "Workforce Analytics & Strategic Planning"
   - Add "Database > Query data" for workforce information

2. **Data Processing**
   - Add "Math > Perform a function" for workforce calculations
   - Use "Analytics > Generate insights" for trend analysis
   - Include "Filter" modules for demographic segmentation

3. **Report Generation**
   - Add "Chart > Create visualization" for dashboard creation
   - Use "OpenAI > Create a chat completion" for insight generation
   - Include "Email > Send email" for executive reporting

4. **Planning Support**
   - Add "Scenario > Model outcomes" for workforce planning
   - Use "Recommendation > Generate action" for strategic guidance
   - Include "Dashboard > Update display" for real-time monitoring

**What You Get:**
- Unified workforce analytics with predictive insights
- Strategic business recommendations based on people data
- Comprehensive DEI tracking with actionable improvement plans
- 80% improvement in data-driven HR decision making

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, growing companies):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Analytics platforms: $300-800/month (basic workforce analytics)
- Business intelligence: $200-600/month (BI tools and dashboards)
- Survey and engagement: $100-300/month (engagement measurement)
- **Total: $600-1,720/month**

**Medium Business (250-1,000 employees, established companies):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Analytics platforms: $1,500-4,000/month (advanced people analytics)
- Business intelligence: $1,000-3,000/month (enterprise BI platforms)
- Survey and engagement: $500-1,500/month (comprehensive engagement suite)
- **Total: $3,050-8,599/month**

**Enterprise (1,000+ employees, large organizations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Analytics platforms: $5,000+/month (enterprise people analytics)
- Business intelligence: $4,000+/month (enterprise BI and modeling)
- Survey and engagement: $2,000+/month (enterprise engagement platforms)
- **Total: $11,200+/month**

*Cost assumptions: Data complexity, analytics sophistication, enterprise platform requirements*

---

## ⚖️ Compliance & Employee Relations Management

**What It Does:** Automates HR compliance monitoring and employee relations processes, focusing on the 20% of compliance activities that prevent 80% of legal and regulatory risk.

**How It Works:**
1. Monitors employment law compliance and regulatory requirement changes
2. Manages employee relations cases and investigation workflows
3. Tracks compliance training completion and certification requirements
4. Automates policy acknowledgment and document management
5. Provides early warning systems for potential HR risks and issues

**What You Need:**
- HR compliance tracking systems
- Employee relations case management platforms
- Learning management systems for compliance training
- Policy management and acknowledgment tools

**Step-by-Step n8n Setup:**

1. **Create Compliance Management Workflow**
   - Start workflow called "Compliance & Employee Relations Management"
   - Add triggers for compliance events and employee relations issues

2. **Regulatory Compliance Monitoring**
   - Track compliance requirements across jurisdictions:
     - Federal and state employment law changes
     - EEOC requirements and reporting deadlines
     - OSHA safety regulations and training requirements
     - Wage and hour law compliance monitoring
   - Generate compliance calendars and deadline tracking

3. **Employee Relations Case Management**
   - Automate case intake and investigation workflows:
     - Route employee complaints and grievances to appropriate investigators
     - Generate investigation timelines and documentation requirements
     - Track case progress and ensure timely resolution
     - Maintain confidential case files and audit trails

4. **Training & Certification Tracking**
   - Monitor mandatory training compliance across organization:
     - Track completion rates for required compliance training
     - Generate automatic reminders for upcoming certification deadlines
     - Identify employees who are overdue for required training
     - Generate compliance training reports for leadership and auditors

5. **Risk Assessment & Early Warning**
   - Use "OpenAI" node to identify potential HR risks:
     - Analyze patterns in employee relations cases for systemic issues
     - Identify managers with high rates of employee complaints
     - Predict potential compliance violations based on data trends
     - Generate recommendations for proactive risk mitigation

**Alternative: Make.com Setup**

1. **Create Compliance Automation Scenario**
   - Name scenario "Compliance & Employee Relations Management"
   - Add "Compliance System > Watch updates" for regulatory changes

2. **Case Management**
   - Add "Case > Create record" for employee relations issues
   - Use "Investigation > Track progress" for case workflow
   - Include "Documentation > Store file" for audit trails

3. **Training Management**
   - Add "LMS > Get completion data" for training tracking
   - Use "Schedule" module for deadline reminders
   - Include "Report > Generate summary" for compliance reporting

4. **Risk Analysis**
   - Add "Analytics > Identify patterns" for risk assessment
   - Use "OpenAI > Create a chat completion" for insight generation
   - Include "Alert > Send notification" for urgent issues

**What You Get:**
- Proactive compliance monitoring with automatic regulatory tracking
- Streamlined employee relations case management and investigation
- Comprehensive training compliance tracking and reporting
- 85% reduction in compliance administrative overhead

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, growing companies):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Compliance tracking: $200-600/month (basic compliance monitoring)
- Case management: $150-400/month (employee relations tools)
- Training platforms: $100-300/month (compliance training systems)
- **Total: $450-1,320/month**

**Medium Business (250-1,000 employees, established companies):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Compliance tracking: $800-2,500/month (comprehensive compliance systems)
- Case management: $600-1,500/month (enterprise case management)
- Training platforms: $500-1,500/month (enterprise learning platforms)
- **Total: $1,950-5,599/month**

**Enterprise (1,000+ employees, large organizations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Compliance tracking: $3,000+/month (enterprise compliance platforms)
- Case management: $2,000+/month (enterprise case management)
- Training platforms: $2,000+/month (enterprise learning ecosystems)
- **Total: $7,200+/month**

*Cost assumptions: Regulatory complexity, case volume, enterprise compliance platform requirements*

---

## 🔄 Employee Lifecycle & Experience Optimization

**What It Does:** Automates the complete employee journey from hire to retire, focusing on the 20% of touchpoints that create 80% of employee experience impact.

**How It Works:**
1. Orchestrates seamless onboarding experiences for new hires
2. Manages career transitions, promotions, and role changes
3. Automates offboarding processes and knowledge transfer
4. Provides personalized employee experience recommendations
5. Tracks employee sentiment and experience metrics throughout lifecycle

**What You Need:**
- HRIS platforms for employee data management
- Onboarding and workflow automation tools
- Experience survey and feedback platforms
- Knowledge management and transfer systems

**Step-by-Step n8n Setup:**

1. **Create Employee Lifecycle Workflow**
   - Start workflow called "Employee Lifecycle & Experience Optimization"
   - Add triggers for lifecycle events (hire, promotion, transfer, departure)

2. **Onboarding Experience Automation**
   - Create comprehensive new hire experiences:
     - Generate personalized onboarding schedules and checklists
     - Coordinate equipment provisioning and system access
     - Schedule meet-and-greets with key team members and stakeholders
     - Track onboarding completion and new hire feedback

3. **Career Transition Management**
   - Automate internal mobility and career changes:
     - Manage promotion workflows and announcement communications
     - Coordinate role transitions and knowledge handoffs
     - Update compensation, benefits, and reporting relationships
     - Track career progression and employee satisfaction with changes

4. **Offboarding & Knowledge Preservation**
   - Streamline departure processes and knowledge transfer:
     - Generate offboarding checklists and timeline management
     - Coordinate exit interviews and feedback collection
     - Manage system access removal and security compliance
     - Capture institutional knowledge and transfer to team members

5. **Experience Personalization & Optimization**
   - Use "OpenAI" node to enhance employee experience:
     - Generate personalized career development recommendations
     - Identify experience pain points and improvement opportunities
     - Create customized communication and recognition strategies
     - Predict employee satisfaction and engagement risks

**Alternative: Make.com Setup**

1. **Create Lifecycle Management Scenario**
   - Name scenario "Employee Lifecycle & Experience Optimization"
   - Add "HRIS > Watch employee events" for lifecycle triggers

2. **Onboarding Automation**
   - Add "Onboarding > Create checklist" for new hire workflow
   - Use "IT > Provision access" for system setup
   - Include "Calendar > Create event" for orientation scheduling

3. **Transition Management**
   - Add "Workflow > Manage transition" for role changes
   - Use "Communication > Send announcement" for promotions
   - Include "Knowledge > Transfer documentation" for handoffs

4. **Experience Enhancement**
   - Add "Survey > Send feedback" for experience measurement
   - Use "OpenAI > Create a chat completion" for personalization
   - Include "Analytics > Track satisfaction" for experience metrics

**What You Get:**
- Seamless employee lifecycle management with consistent experiences
- Automated onboarding that accelerates time-to-productivity
- Comprehensive offboarding with knowledge preservation
- 75% improvement in employee experience consistency

**💰 Monthly Operating Costs:**

**Small Business (up to 250 employees, growing companies):**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Employee experience: $200-500/month (basic experience platforms)
- Onboarding tools: $150-400/month (onboarding automation)
- Survey platforms: $100-250/month (experience measurement)
- **Total: $450-1,170/month**

**Medium Business (250-1,000 employees, established companies):**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Employee experience: $800-2,000/month (comprehensive experience platforms)
- Onboarding tools: $600-1,500/month (enterprise onboarding automation)
- Survey platforms: $400-1,000/month (advanced experience measurement)
- **Total: $1,850-4,599/month**

**Enterprise (1,000+ employees, large organizations):**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Employee experience: $3,000+/month (enterprise experience platforms)
- Onboarding tools: $2,000+/month (enterprise onboarding ecosystems)
- Survey platforms: $1,500+/month (enterprise experience management)
- **Total: $6,700+/month**

*Cost assumptions: Employee volume, experience complexity, enterprise platform requirements*

---

## 🎯 Getting Started Guide

### Start with Talent Acquisition Automation
Most HR leaders see immediate value from streamlined recruiting processes - it improves quality-of-hire while reducing time-to-fill.

### Use Your Current HR Technology Stack
Connect automations to whatever HRIS, ATS, and performance management systems you already use. Don't switch platforms just for automation.

### Begin with Performance Management
Start with simple review cycle automation before moving to complex workforce analytics or compliance management.

### Budget Planning
- HR technology platforms: Usually included in existing HR infrastructure
- n8n or Make.com: Free to $400/month for HR automations
- Specialized people analytics: Usually $1,000-10,000/month depending on organization size
- Total: Usually $2,000-20,000/month for complete HR automation

---

## 🛡️ Best Practices

### Maintain Employee Privacy
- Ensure all automated processes comply with privacy laws and regulations
- Include human oversight for sensitive employee relations and performance decisions
- Protect confidential employee information in all automation workflows
- Regular review of automated processes for privacy and security compliance

### Preserve Human Connection
- Use automation to enhance, not replace, meaningful human interactions
- Include personal touch in critical employee lifecycle moments
- Review automated communications for empathy and appropriateness
- Maintain the trust and confidence that employees expect from HR

### Focus on Strategic Impact
- Use automation to create more time for strategic people initiatives
- Combine automated efficiency with human insight and business acumen
- Continuously improve automation based on employee feedback and business outcomes
- Maintain the strategic value that HR brings to organizational success

---

## 📞 Common Questions

**Q: Will employees be comfortable with automated HR processes?**
A: Focus on the benefits - faster responses, consistent processes, and more time for strategic support. Most employees appreciate efficient, fair automation over slow manual processes.

**Q: What if automated decisions impact employee fairness?**
A: Include human review checkpoints for critical decisions like performance reviews and promotions. Use automation for efficiency while maintaining human judgment for important employee matters.

**Q: How do we ensure compliance with employment laws?**
A: Work with legal teams to build compliance requirements into automated workflows. Maintain audit trails and regular compliance reviews for all automated HR processes.

**Q: Can we customize automation for different employee populations?**
A: Absolutely. Set up different workflows for executives, managers, individual contributors, and remote employees based on their unique needs and experience requirements.

---

## 📈 Success Metrics

### Track These Numbers
- Talent acquisition speed and quality-of-hire metrics
- Employee experience scores and engagement levels
- Performance management consistency and completion rates
- Compliance accuracy and risk reduction measures
- HR operational efficiency and cost reduction

### Expect These Results
- 75% improvement in talent acquisition efficiency and quality
- 70% reduction in performance management administrative overhead
- 80% improvement in data-driven HR decision making
- 85% reduction in compliance administrative tasks
- 75% improvement in employee experience consistency

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
# Crisis Management & Rapid Response

Automatically detects potential brand crises, escalates urgent issues, coordinates rapid response efforts, and tracks crisis resolution for proactive reputation management.

## What This Does

Monitors for crisis indicators and escalating negative sentiment, assesses crisis severity and potential impact, automatically alerts crisis response team, coordinates response messaging, and tracks crisis resolution. Enables 95% faster crisis detection and response initiation.

**Who This Helps:** Brand managers, PR teams, crisis management specialists, executive communications  
**Tools Used:** n8n or Make.com, crisis monitoring tools, communication platforms, alert systems  
**Time Saved:** 10-15 hours per week during normal operations, critical time savings during crises  
**Results:** 95% faster crisis detection, coordinated rapid response, proactive reputation protection  

---

## How It Works

1. **Crisis Detection**: Monitors for crisis indicators and escalating negative sentiment patterns
2. **Severity Assessment**: Automatically evaluates potential impact and required response level
3. **Rapid Escalation**: Instantly alerts appropriate crisis response teams based on severity
4. **Response Coordination**: Activates pre-approved messaging and communication protocols
5. **Recovery Tracking**: Monitors sentiment recovery and crisis resolution progress

---

## What You Need

- Crisis management protocols and response plans
- Emergency contact lists and escalation procedures
- Pre-approved crisis response messaging templates
- Stakeholder communication channels
- Real-time monitoring and alert systems

---

## Step-by-Step n8n Setup

### 1. Create Crisis Management Workflow
- Start workflow called "Crisis Management & Rapid Response"
- Add "Schedule Trigger" for continuous crisis monitoring every 15 minutes

### 2. Crisis Detection & Assessment
Add **"OpenAI"** node for crisis analysis:
- Monitor for crisis keywords and escalating sentiment
- Assess potential impact and reputation threat level
- Identify crisis type (product, service, PR, legal, etc.)
- Evaluate urgency and required response time

### 3. Automated Escalation System
Use **"Switch"** node for crisis severity routing:
- **Level 1**: Minor issues to customer service team
- **Level 2**: Moderate issues to brand and PR team
- **Level 3**: Major issues to executive crisis team
- **Level 4**: Severe crises to CEO and legal team

### 4. Rapid Response Coordination
Add communication nodes for crisis response:
- Send immediate alerts to crisis response team via Slack/Teams
- Activate pre-approved response messaging across channels
- Coordinate simultaneous response across all communication platforms
- Track response timeline and team acknowledgment

### 5. Recovery Monitoring & Reporting
Use **"Code"** node for recovery tracking:
- Monitor sentiment recovery and brand health metrics
- Track crisis resolution progress and team actions
- Generate real-time crisis response reports
- Document lessons learned and process improvements

---

## Alternative: Make.com Setup

### 1. Create Crisis Response Scenario
- Name scenario "Crisis Management & Rapid Response"
- Add "Crisis > Monitor indicators" trigger for real-time detection

### 2. Detection and Assessment
- Add "Sentiment > Track escalation" for crisis identification
- Use "Impact > Assess severity" for appropriate response planning
- Include "Classification > Categorize crisis" for proper team routing

### 3. Response Coordination
- Add "Alert > Notify team" for immediate escalation alerts
- Use "Communication > Activate response" for coordinated crisis messaging
- Include "Tracking > Monitor resolution" for recovery management

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build crisis response scenarios faster.

---

## What You Get

- **Early Warning System**: 24/7 crisis detection with predictive sentiment analysis
- **Instant Escalation**: Automatic alerts to appropriate crisis response teams within minutes
- **Coordinated Response**: Synchronized crisis communication across all channels and stakeholders
- **Recovery Tracking**: Real-time monitoring of crisis resolution and brand sentiment recovery
- **Process Documentation**: Automated reporting and lessons learned for future crisis preparation

---

## 💰 Monthly Operating Costs

### Small Business (up to 250 employees, basic crisis management)
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Crisis monitoring: $100-300/month (sentiment tracking, alert systems)
- Communication tools: $50-150/month (Slack, Teams, emergency alerts)
- Alert systems: $25-75/month (SMS, phone, notification services)
- **Total: $175-545/month**

### Medium Business (250-1,000 employees, comprehensive crisis management)
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Crisis monitoring: $400-1,000/month (advanced sentiment analysis, predictive monitoring)
- Communication tools: $200-500/month (enterprise communication platforms)
- Alert systems: $100-250/month (multi-channel emergency notification)
- **Total: $750-1,849/month**

### Enterprise (1,000+ employees, enterprise crisis management)
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Crisis monitoring: $1,500+/month (enterprise crisis detection platforms)
- Communication tools: $800+/month (enterprise crisis communication systems)
- Alert systems: $400+/month (comprehensive emergency notification systems)
- **Total: $2,900+/month**

*Cost assumptions: Monitoring scope, response complexity, enterprise platform requirements*

---

## 🤖 LLM-Only Alternative

**If you just need this done once or occasionally...**

You can analyze potential crisis situations and develop response strategies in a single conversation with any AI assistant. Perfect for crisis planning or post-crisis analysis.

**Simple Multi-Step Prompt:**

```
I need help assessing a potential brand crisis situation and developing a response strategy.

Here's the situation:
[DESCRIBE THE CRISIS OR POTENTIAL CRISIS - negative publicity, product issues, social media backlash, etc.]

Current brand context:
- Company: [YOUR COMPANY NAME]
- Industry: [YOUR INDUSTRY]
- Key stakeholders: [CUSTOMERS, INVESTORS, EMPLOYEES, etc.]
- Brand values: [YOUR CORE VALUES]
- Recent company activities: [RELEVANT CONTEXT]

Please provide:

1. CRISIS ASSESSMENT
   - Severity level (low/medium/high/critical)
   - Potential impact on brand reputation
   - Likely spread and escalation patterns
   - Key risks and vulnerabilities

2. IMMEDIATE RESPONSE STRATEGY
   - First 24-hour action plan
   - Key messages for different audiences
   - Communication channels to prioritize
   - Internal team coordination needs

3. STAKEHOLDER COMMUNICATION
   - Messaging for customers/clients
   - Employee communication approach
   - Investor/partner messaging if needed
   - Media response strategy

4. MONITORING & NEXT STEPS
   - What to monitor for escalation
   - Success metrics for response effectiveness
   - Timeline for follow-up communications
   - Long-term reputation recovery plan

5. PREVENTION RECOMMENDATIONS
   - Process improvements to prevent similar issues
   - Early warning indicators to monitor
   - Team preparedness improvements

Format this as a crisis management brief for leadership review.
```

**JSON Template Option:**
```
Format as JSON:
{
  "crisis_assessment": {
    "severity": "medium",
    "impact_score": "6/10",
    "escalation_risk": "moderate",
    "response_urgency": "24 hours"
  },
  "immediate_actions": [
    {
      "priority": "1",
      "action": "issue public statement acknowledging concern",
      "timeline": "within 2 hours",
      "owner": "PR team"
    }
  ],
  "key_messages": {
    "customers": "We take this seriously and are investigating immediately",
    "employees": "Internal communication about our response plan",
    "media": "Transparent acknowledgment with commitment to resolution"
  },
  "monitoring_plan": {
    "metrics": ["sentiment tracking", "mention volume", "news coverage"],
    "escalation_triggers": ["viral social media spread", "major media pickup"]
  }
}
```

**What this approach can't do:**
- Won't monitor for crises automatically
- No real-time alerts or escalation
- Can't coordinate team response automatically
- Limited to current situation analysis

**When to upgrade to full automation:**
- You need 24/7 crisis monitoring and early detection
- You want automatic escalation to crisis teams
- You need coordinated response across multiple channels
- You have complex stakeholder communication requirements

---

## 🎯 Getting Started

### Develop Crisis Protocols
Create clear crisis response procedures with defined escalation levels, team roles, and communication templates.

### Identify Crisis Indicators
Define specific keywords, sentiment thresholds, and patterns that indicate potential crisis situations.

### Prepare Response Templates
Develop pre-approved messaging templates for different crisis types and severity levels.

### Test Your System
Regularly test crisis detection and response workflows to ensure rapid activation when needed.

---

## 🛡️ Best Practices

### Maintain Human Oversight
- Use automation for detection and initial response while ensuring human judgment for complex decisions
- Include executive approval checkpoints for major crisis communications
- Balance speed with accuracy in crisis response messaging

### Preserve Stakeholder Trust
- Focus on transparent, honest communication during crisis situations
- Use automation to ensure consistent messaging across all channels
- Maintain empathy and personal touch in crisis communications

### Focus on Prevention
- Use crisis monitoring data to identify potential issues before they escalate
- Continuously improve crisis prevention through pattern analysis
- Build stronger crisis preparedness through automated monitoring insights

---

## 📈 Success Metrics

### Track These Numbers
- **Detection speed**: Time from crisis emergence to team alert
- **Response time**: Duration from detection to initial response activation
- **Escalation accuracy**: Percentage of alerts requiring appropriate response level
- **Sentiment recovery**: Speed of brand sentiment improvement post-crisis
- **Team coordination**: Effectiveness of automated crisis response workflows

### Expect These Results
- **95% faster** crisis detection and response initiation
- **Real-time alerts** for potential reputation threats
- **Coordinated response** across all communication channels
- **Comprehensive crisis tracking** and resolution monitoring
- **Proactive reputation protection** through early intervention

---

## 🔗 More Brand Manager Automations

**Need different solutions?**
- **[🏠 Brand Manager Overview](Brand%20Manager%20Overview.md)** - All brand management automations
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
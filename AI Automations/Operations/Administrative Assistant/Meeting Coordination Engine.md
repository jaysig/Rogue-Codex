# Meeting Coordination Engine

Handles the back-and-forth of scheduling meetings, booking rooms, and sending all the right information to attendees.

## What This Does

**What It Does:** Handles the back-and-forth of scheduling meetings, booking rooms, and sending all the right information to attendees without endless email chains.

**How It Works:**
1. Receives meeting requests via email or calendar invites
2. Checks everyone's availability and suggests optimal times
3. Books conference rooms and sends calendar invites
4. Distributes agendas and materials before meetings
5. Sends follow-up reminders and post-meeting action items

**What You Need:**
- Calendar system (Google Calendar, Outlook)
- Room booking system
- Email access
- Document storage (Google Drive, SharePoint)

---

## Step-by-Step n8n Setup

### 1. Create Meeting Coordination Workflow
- Start new workflow called "Meeting Coordination Engine"
- Add "Email" trigger for meeting requests

### 2. Parse Meeting Requirements
- Add "OpenAI" node to extract from email:
  - Attendees needed
  - Preferred dates/times
  - Meeting duration and type
  - Room requirements (size, equipment)

### 3. Check Availability
- Add "Google Calendar" nodes to check each attendee's availability
- Find common free time slots
- Consider time zones for remote participants

### 4. Book Resources
- Add "Calendar" node to book selected time slot
- Connect "Room Booking" system to reserve conference room
- Send calendar invites with all details

### 5. Distribute Materials
- Add "Google Drive" node to share relevant documents
- Send "Email" with agenda and pre-reading materials
- Set reminders for day before and 30 minutes prior

---

## Alternative: Make.com Setup

### 1. Create Meeting Scheduling Scenario
- Name scenario "Meeting Coordination Engine"
- Add "Email > Watch emails" for scheduling requests

### 2. AI-Powered Parsing
- Add "OpenAI > Create a chat completion" to understand meeting needs
- Extract attendees, timeframes, and special requirements
- Identify priority level and urgency

### 3. Smart Scheduling
- Add "Google Calendar > List events" for availability checking
- Find optimal meeting slots considering all constraints
- Book "Google Calendar > Create event" with all attendees

### 4. Resource Management
- Add room booking integration if available
- Distribute materials via "Google Drive > Share file"
- Send "Email > Send email" with meeting details

💡 **Make MCP Tip**: Use the [Make MCP server](https://github.com/integromat/make-mcp-server) with Claude Code to build meeting coordination scenarios faster.

---

## What You Get

- No more email chains to find meeting times
- Rooms and resources booked automatically
- Everyone gets the right information at the right time
- Professional, consistent meeting coordination

---

## Cost Estimates

### Small Business (Moderate Meeting Coordination)
**Monthly Operating Cost: $110-1,220**

**Breakdown:**
- Automation platform: Free (n8n self-hosted) to $20/month (Make.com Standard)
- Calendar platform: $12-20/month per user (5-50 users: $60-1,000/month)
- Room booking: $25-100/month (multiple rooms, basic scheduling)
- AI processing: $25-100/month (moderate meeting volume)

**Assumptions:**
- 5-50 employees with moderate meeting coordination needs
- Basic room booking and calendar integration
- Standard meeting complexity and scheduling requirements
- Limited multi-location or complex scheduling needs

### Medium Business (High Meeting Volume)
**Monthly Operating Cost: $5,450-31,199**

**Breakdown:**
- Automation platform: $50/month (n8n Pro) to $99/month (Make.com Pro)
- Calendar platform: $20-30/month per user (250-1,000 users: $5,000-30,000/month)
- Room booking: $200-500/month (enterprise scheduling, multiple locations)
- AI processing: $200-600/month (high meeting coordination complexity)

**Assumptions:**
- 250-1,000 employees with high meeting volume
- Advanced room booking across multiple locations
- Complex scheduling requirements and executive coordination
- Advanced calendar integration and team collaboration

### Enterprise (Complex Multi-Location Coordination)
**Monthly Operating Cost: $32,200+**

**Breakdown:**
- Automation platform: $200+/month (enterprise n8n) to $400+/month (Make.com Enterprise)
- Calendar platform: $30+/month per user (1,000+ users: $30,000+/month)
- Room booking: $1,000+/month (enterprise scheduling, global locations)
- AI processing: $1,000+/month (complex enterprise coordination)

**Assumptions:**
- 1,000+ employees with complex global meeting coordination
- Enterprise room booking across multiple global locations
- Advanced integration with enterprise calendar and collaboration systems
- Complex executive scheduling and multi-timezone coordination

---

## Best Practices

### Executive Support Excellence
- Customize meeting preferences for each executive you support
- Include buffer time between meetings for travel or preparation
- Always confirm important meetings with human review before booking
- Maintain backup options for critical meetings in case of conflicts

### Communication Quality
- Use professional, consistent language in all automated communications
- Include all necessary meeting details (agenda, dial-in info, materials)
- Send reminders at appropriate intervals without overwhelming attendees
- Provide clear escalation path for meeting changes or issues

### Resource Management
- Monitor room booking patterns to optimize resource allocation
- Track meeting effectiveness and suggest improvements
- Maintain updated room capabilities and equipment information
- Include catering coordination for appropriate meeting types

---

## Common Questions

**Q: What if the automation can't find a time that works for everyone?**
A: Include fallback options like suggesting alternative attendees or proposing multiple time slots for manual decision-making.

**Q: How do we handle last-minute meeting changes?**
A: Set up change notification workflows and include manual override options for urgent modifications.

**Q: Can this handle complex meeting requirements like catering or special equipment?**
A: Yes, include special requirements parsing in the AI analysis and route complex requests to appropriate vendors or facilities teams.

**Q: What about confidential or sensitive meetings?**
A: Include classification options and route high-security meetings through manual review and approval processes.

---

## Success Metrics

### Track These Numbers
- Time saved on meeting coordination per week
- Reduction in scheduling email back-and-forth
- Meeting room utilization and booking efficiency
- Attendee satisfaction with meeting coordination quality
- Executive satisfaction with administrative support

### Expect These Results
- 70% reduction in meeting coordination time
- 80% decrease in scheduling email chains
- 90% improvement in meeting room booking accuracy
- 60% faster meeting setup from request to confirmation
- Significant improvement in professional meeting coordination consistency

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
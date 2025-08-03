# Client Brief & Project Intake System

Automatically captures client requirements, creates structured project briefs, and sets up organized design workflows.

## What This Does

**What It Does:** Transforms unstructured client requests into clear, actionable project briefs with automated workflow setup.

**How It Works:**
1. Captures client requirements through intake forms and conversations
2. Converts loose requirements into structured project briefs
3. Identifies scope, deliverables, and timeline automatically
4. Sets up project folders and workflow templates
5. Creates initial project timeline and milestone tracking

**What You Need:**
- Client intake form system (Google Forms, Typeform, or similar)
- Project management platform (Asana, Monday.com, or Trello)
- n8n automation platform
- File storage system (Google Drive, Dropbox, or Creative Cloud)

---

## Step-by-Step n8n Setup

### 1. Create Project Intake Workflow
- Start new workflow called "Client Brief & Project Intake System"
- Add "Form Trigger" to receive new client project requests

### 2. Capture Client Requirements
- Add "Form Parser" to extract key information:
  - **Project type**: Logo, website, branding, marketing materials
  - **Business context**: Industry, target audience, brand personality
  - **Deliverables**: Specific assets needed, file formats, sizes
  - **Timeline**: Launch date, key milestones, urgency level
  - **Budget**: Investment range, payment preferences
  - **References**: Style preferences, competitor examples, inspiration

### 3. Generate Structured Project Brief
- Add "OpenAI" node to create comprehensive brief:
  ```
  Create a professional design project brief from this client information:
  
  PROJECT OVERVIEW:
  - Project type and objectives
  - Target audience and brand positioning
  - Key success metrics
  
  DELIVERABLES:
  - Specific design assets required
  - File formats and technical specifications
  - Usage rights and licensing requirements
  
  CREATIVE DIRECTION:
  - Brand personality and visual style
  - Color preferences and restrictions
  - Typography and design approach
  
  PROJECT TIMELINE:
  - Key milestones and deadlines
  - Review and revision schedule
  - Final delivery date
  
  SCOPE AND BUDGET:
  - Included services and deliverables
  - Revision limits and additional work process
  - Payment schedule and terms
  ```

### 4. Set Up Project Organization
- Add "File Management" node to create project structure:
  - **Client folder**: Main project directory with client name
  - **Assets folder**: Organized by deliverable type
  - **References folder**: Client inspiration and brand materials
  - **Revisions folder**: Version control for design iterations
  - **Final files folder**: Approved deliverables and final assets

### 5. Create Project Timeline
- Add "Project Management" integration:
  - **Discovery phase**: Brand research and competitive analysis
  - **Concept phase**: Initial design concepts and presentations
  - **Development phase**: Design refinement and asset creation
  - **Review phase**: Client feedback and revision cycles
  - **Delivery phase**: Final asset preparation and handoff

### 6. Client Onboarding Communication
- Add "Email Automation" for professional client communication:
  - **Welcome email**: Project brief confirmation and next steps
  - **Expectations email**: Timeline, process, and communication guidelines
  - **Kick-off scheduling**: Discovery call or creative briefing session
  - **Resource request**: Brand assets, content, and reference materials

### 7. Team and Workflow Setup
- Add "Team Assignment" based on project type:
  - **Solo projects**: Assign to appropriate designer
  - **Team projects**: Creative director, designer, and account management
  - **Specialist needs**: Photography, copywriting, web development
  - **Review workflow**: Approval process and stakeholder involvement

---

## Alternative: Make.com Setup

### 1. Create Intake Management Scenario
- Name scenario "Client Brief & Project Intake System"
- Add "Google Forms > Watch responses" or "Typeform > Watch responses"

### 2. Brief Generation
- Add "OpenAI > Create completion" for structured brief creation
- Use "Google Docs > Create document" for professional brief formatting
- Connect "Email > Send" to deliver brief to client for approval

### 3. Project Setup
- Add "Google Drive > Create folder" for project organization
- Use "Asana > Create project" or similar for timeline management
- Set "Calendar > Create events" for key milestones and deadlines

### 4. Team Coordination
- Add "Slack > Send message" for team notification of new projects
- Use "Assignment rules" to route projects to appropriate team members
- Create "Status dashboard" for project pipeline visibility

### 5. Client Communication
- Send "Welcome email sequence" with project expectations
- Schedule "Follow-up reminders" for client material collection
- Set "Milestone notifications" for client update communications

---

## What You Get

- Professional project briefs from loose client requirements
- Standardized project organization and file structure
- Automated timeline creation with milestone tracking
- Consistent client onboarding and communication
- Clear scope documentation reducing revision conflicts

---

## Cost Estimates

### Small Business (Freelance Designer)
**Monthly Operating Cost: $30-80**

**Breakdown:**
- n8n: Free tier (sufficient for individual designer)
- Form platform: $10-30/month (Typeform or Google Forms premium)
- AI brief generation: $10-30/month (OpenAI API for project analysis)
- Project management: Free to $20/month (basic Asana, Trello)
- File storage: $10-20/month (expanded Google Drive or Dropbox)

**Assumptions:**
- 5-15 new projects per month
- Basic project brief generation and organization
- Individual designer workflow automation
- Standard client communication and file management

### Medium Business (Design Agency)
**Monthly Operating Cost: $200-500**

**Breakdown:**
- n8n Pro: $50/month (team collaboration features)
- Advanced form and intake system: $50-150/month (custom forms and client portals)
- AI analysis and brief generation: $50-150/month (comprehensive project analysis)
- Professional project management: $50-150/month (advanced Asana, Monday.com)
- Team collaboration tools: $50-100/month (Slack, file sharing, communication)

**Assumptions:**
- 20-50 new projects monthly across team
- Multi-designer project coordination
- Advanced client communication and project tracking
- Team workflow standardization and quality control

### Enterprise (Large Agency/In-House Team)
**Monthly Operating Cost: $800-2,000**

**Breakdown:**
- Enterprise automation platform: $300-600/month (n8n Enterprise or custom)
- Advanced client management: $200-600/month (CRM integration and client portals)
- Comprehensive project intelligence: $200-500/month (advanced analytics and reporting)
- Multi-team coordination: $200-400/month (cross-department project management)
- Integration platform: $100-300/month (design tool APIs and workflow integration)

**Assumptions:**
- 50+ projects monthly across multiple teams
- Complex client relationship management
- Integration with enterprise design and business systems
- Advanced analytics and project performance tracking

---

## Best Practices

### Brief Quality
- Always review AI-generated briefs before sending to clients
- Include client approval step before project work begins
- Maintain templates for different project types and industries
- Regular brief template updates based on successful project patterns

### Client Communication
- Set clear expectations about project process and timeline
- Use consistent communication style across all automated messages
- Provide multiple ways for clients to provide input and feedback
- Follow up on client material requests and resource needs

### Project Organization
- Establish consistent file naming conventions across all projects
- Maintain version control for all design iterations and client feedback
- Regular backup and archive procedures for completed projects
- Access control for client-specific materials and confidential information

---

## Common Questions

**Q: How detailed should the initial client intake form be?**
A: Include enough questions to create a useful brief, but not so many that clients abandon the form. 15-20 key questions usually work well.

**Q: What if clients don't provide complete information?**
A: Set up follow-up workflows to request missing information and schedule discovery calls for complex projects.

**Q: Can this work for rush projects with tight deadlines?**
A: Yes, create express workflow options for urgent projects with streamlined brief generation and faster setup.

**Q: How do I handle projects that don't fit standard templates?**
A: Build flexibility into the system with custom project type options and manual override capabilities.

---

## Success Metrics

### Track These Numbers
- Time saved on project setup and brief creation
- Percentage of projects that start with complete, clear briefs
- Reduction in scope creep and revision conflicts
- Client satisfaction with project clarity and communication
- Improvement in project timeline adherence from better setup

### Expect These Results
- 80% reduction in time spent on project setup and brief creation
- 90% of projects start with comprehensive, client-approved briefs
- 50% reduction in scope-related conflicts and misunderstandings
- 70% improvement in client satisfaction with project clarity
- 60% better project timeline adherence through proper initial setup

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-03*
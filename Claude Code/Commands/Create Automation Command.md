# Create Automation Command

**Comprehensive automation guide development with n8n/Make.com implementations and LLM alternatives**

## Command Syntax
```
/create-automation [role/function description]
```

## Purpose
Automates the creation of comprehensive automation guides that include multiple workflow implementations, cost estimates, LLM alternatives, and full integration with the AI Automations section structure.

## What It Does

### 1. Structure Setup
- Determines appropriate role category (Product, Marketing, Sales, Operations, etc.)
- Creates file with descriptive naming pattern following repository conventions
- Applies standard automation template with all required sections
- Establishes proper folder structure and navigation

### 2. Content Development
- Writes 3-5 specific automation workflows tailored to the role
- Includes both n8n and Make.com implementation steps for each workflow
- Adds cost estimates using standard business size definitions
- Provides detailed setup instructions and node/module specifications

### 3. LLM Alternative Assessment
- Evaluates which workflows qualify for LLM-only solutions
- Adds "LLM-Only Alternative" sections where appropriate
- Includes copy-paste prompt templates with JSON output options
- Explains when to upgrade from LLM to full automation

### 4. Pain Point Integration
- Checks if automation solves major, high-impact pain points
- Adds relevant workflows to Pain Point Solutions.md if applicable
- Cross-references with existing pain point solutions
- Uses emotional, searchable language for problem descriptions

### 5. Navigation and Updates
- Adds standard "More Automations" navigation section
- Updates main AI Automations Guide with new entry
- Updates role-based or problem-based index files
- Creates Recent Changes entry with public-facing language

### 6. Quality Control
- Ensures 8th grade reading level throughout
- Verifies cost estimate assumptions and calculations
- Confirms proper internal linking and cross-references
- Validates automation platform instructions accuracy

## Example Usage

### Single Role Automation
```
/create-automation Social Media Manager
```
**Result**: Creates comprehensive guide with 5 workflows covering content scheduling, engagement tracking, competitor analysis, hashtag research, and performance reporting.

### Multi-Tool Integration
```
/create-automation Social Media Manager using Hootsuite, Buffer, ChatGPT, Canva
```

**What happens:**
1. **Content Creation Workflow**: ChatGPT → Canva → Buffer → Analytics
2. **Scheduling Workflow**: Hootsuite + Buffer integration with AI optimization
3. **Visual Content Pipeline**: Canva AI + batch processing + multi-platform distribution
4. **Performance Analysis**: Combined analytics from all platforms with AI insights
5. **Competitor Monitoring**: Automated tracking and reporting across tools

**Generated file:**
`AI Automations/Marketing/Social Media Manager.md`

**Updated files:**
- `AI Automations/AI Automations Guide.md`
- `AI Automations/Automation Workflows by Job Role.md`
- `AI Automations/Automation Workflows by Problem.md` (if applicable)
- `AI Automations/Pain Point Solutions.md` (if workflows solve major pain points)
- `Recent Changes.md`

### Complex Professional Role
```
/create-automation Private Equity Analyst
```

**Result**: Creates specialized automation covering deal sourcing, due diligence workflows, portfolio monitoring, market research, and investor reporting with finance-specific tools and compliance considerations.

## Content Structure

### Required Sections
1. **Overview**: Purpose, target users, tools used, time/results expectations
2. **Individual Workflows**: 3-5 specific automation workflows with implementation details
3. **Dual-Platform Implementation**: Both n8n and Make.com setup instructions
4. **Cost Estimates**: Monthly operating costs using standard business size definitions
5. **Getting Started Guide**: Practical first steps and budget planning
6. **Best Practices**: Security, monitoring, and optimization guidelines
7. **Common Questions**: FAQ section addressing typical concerns
8. **Success Metrics**: Trackable results users can expect
9. **More Automations**: Standard navigation section

### Business Size Definitions
All cost estimates use consistent definitions:

**Small Business:**
- Up to 250 employees
- Annual revenue under $50 million
- Basic automation needs (< 10,000 operations/month)
- Self-service setup preferred

**Medium Business:**
- 250-1,000 employees
- Annual revenue $50M-$1B
- Moderate automation needs (10,000-100,000 operations/month)
- Some IT support available

**Enterprise:**
- 1,000+ employees
- Annual revenue $1B+
- Complex requirements (100,000+ operations/month)
- Dedicated automation team

### LLM-Only Solutions
When applicable, includes simplified alternatives for:
- Single conversation completion tasks
- Text-based analysis and recommendations
- One-time or infrequent automation needs
- Tasks not requiring real-time monitoring

**LLM Solution Format:**
- "Quick Solution" explanation
- Multi-step prompt examples
- JSON template options
- Limitations and upgrade criteria

## Platform Implementation Details

### n8n Workflows
- Specific node types and configurations
- API connection requirements
- Error handling and monitoring setup
- Testing and validation steps

### Make.com Scenarios
- Module names and setup instructions
- Connection establishment processes
- Scenario flow design
- Troubleshooting common issues

## Pain Point Integration Criteria

Workflows are added to Pain Point Solutions.md if they meet:
- **Time Impact**: Saves 4+ hours per week or prevents significant stress
- **Broad Appeal**: Affects people across multiple roles or industries
- **Search Behavior**: People actively search for solutions online
- **Emotional Impact**: Addresses genuinely frustrating problems

**Examples of Major Pain Points:**
- "Drowning in emails and messages"
- "My finances are a complete mess"
- "I can't keep track of my tasks and deadlines"
- "Manual data entry is killing my productivity"

## Quality Standards

### Content Accessibility
- 8th grade reading level for all technical explanations
- Clear step-by-step instructions with numbered lists
- Simple language explaining complex automation concepts
- Visual workflow descriptions where helpful

### Cost Accuracy
- Current 2025 pricing from official sources
- Realistic usage estimates for different business sizes
- Clear assumptions about what drives cost differences
- Monthly operating costs (no setup time estimates)

### Implementation Validity
- Tested workflow steps and configurations
- Current API availability and requirements
- Accurate platform-specific instructions
- Working integration examples

## Integration Benefits

### Automated Cross-Referencing
- Automatic addition to role-based and problem-based indexes
- Cross-references with related automation guides
- Integration with pain point solution mapping
- Consistent navigation structure

### Template Consistency
- Uniform structure across all automation guides
- Standardized cost estimation methodology
- Consistent LLM alternative formatting
- Universal navigation and cross-linking

### SEO Optimization
- Natural problem-focused language for search visibility
- Proper heading structure for search engines
- Internal linking supports content discoverability
- Problem-solution mapping for user intent matching

## Common Use Cases

1. **Role-Specific Guides**: Comprehensive automation for specific job functions
2. **Industry Solutions**: Specialized workflows for particular industries
3. **Tool Integration**: Multi-platform workflow development
4. **Problem Solving**: Automation targeting specific pain points

## Tips for Best Results

1. **Role Clarity**: Be specific about the target role and responsibilities
2. **Tool Selection**: Consider both popular and specialized tools for the role
3. **Workflow Variety**: Include different types of automation (data, communication, analysis)
4. **Real-World Testing**: Ensure all workflow steps are practically achievable

---

*Last Updated: 2025-08-04*
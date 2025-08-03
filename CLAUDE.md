# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

Rogue Codex is a knowledge base and documentation site built using Obsidian and published with Obsidian Publish. It contains curated collections of lessons learned, practical guides, and actionable insights across various domains including AI, personal development, business, and technology.

## Architecture & Structure

### Core Organization
- **Modular Knowledge Sections**: Each top-level directory represents a distinct knowledge domain with its own README.md
- **Template-Based Structure**: Consistent use of templates for lessons learned, tools evaluation, and project tracking
- **Obsidian-Native**: Uses Obsidian markdown format with double-bracket linking `[[link]]` between notes
- **Living Documentation**: Content is designed to evolve with checkboxes `- [ ]` for tracking progress and pending items

### Key Directories
- `100 TUF/` - 100-day personal development journey with phase-based structure
- `Lessons Learned/` - Structured template-based knowledge capture with categories
- `Tools/` - Tool evaluations with systematic criteria and workflow recommendations
- `Company Registry/` - Industry-organized company database with individual company files
- `AI Regulation/`, `AI Risk/` - AI policy and safety content sections
- `AI Automations/` - Role-based automation workflows organized by function
- `Coding Setup/` - Non-technical user guides for coding tools
- `Thai Project/` - Real estate project documentation with changelog tracking

### Content Patterns
- Each section uses consistent README.md as entry point with overview and structure
- Template-driven content creation (see Lessons Learned template)
- Checkbox-based tracking for progress and todo items
- Date stamps and review cycles for content freshness
- Cross-linking between related concepts and sections

## Common Development Tasks

### Content Management
Since this is a documentation repository without build tools, primary tasks involve:

- **Adding New Content**: Follow existing template structures in each section
- **Updating READMEs**: Maintain consistent format across all section README files
- **Cross-Linking**: Use Obsidian's `[[link]]` format to connect related content
- **Progress Tracking**: Update checkbox items `- [ ]` to `- [x]` as tasks complete

### Content Quality Standards
- Maintain practical, actionable focus over theoretical concepts
- Include specific templates and frameworks for replicability
- Regular review cycles noted in footer timestamps
- Consistent categorization and tagging approach
- **8th Grade Reading Level**: Write all content at an 8th grade reading level for clarity and accessibility. Use simple words, short sentences, and explain technical terms in plain language
- **Lesson Formatting**: When creating lessons learned files, maintain at least 2 line spaces between the last section in a group and the next group for better readability and visual separation

### RC Changes and Public Documentation
- **Recent Changes.md**: Public-facing changelog with recent updates (last 4-5 weeks)
- **Archived Changes.md**: Historical archive of older changelog entries
- **Monthly archiving**: At end of each month, move entries to archive except last week of previous month (for continuity)
- **Append-only editing**: Always add new entries at bottom of Recent Changes.md (token efficient)
- **Exclude folder**: Internal working folder for tasks, drafts, and temporary items
- **Changelog entries**: Should only include public-facing information, never reference exclude folder operations or internal workflow details (e.g., avoid "removed from companies to add list" - focus on the actual addition/update)

### File Naming Conventions
- Use spaces in directory names (e.g., "Lessons Learned", "AI Regulation")
- URL-encode spaces in markdown links (e.g., `[link](Lessons%20Learned/Lessons%20Overview.md)`)
- **Minimize README.md files**: Avoid creating README.md files as they make file tracking difficult. Use descriptive filenames instead (e.g., "Gaming Companies Overview.md" rather than "README.md")
- **Descriptive filenames**: All markdown files should have descriptive names that clearly identify their content
  - ✅ Good: `Netflix.md`, `AI Infrastructure Overview.md`, `Tool Evaluation Template.md`
  - ❌ Bad: `README.md` (in subdirectories), `index.md`, `main.md`, `content.md`
- **Subsection files**: When creating subsections or rankings, use descriptive names that make it easy to identify the file's purpose
  - Examples: `Traditional Studios Overview.md`, `AI-Native Gaming Companies.md`, `Q1 2025 Tool Rankings.md`

### File Management and Git Operations
- **Preserve file history**: When restructuring or moving files, use `git mv` instead of creating new files to maintain version history and track changes over time
- **File moves**: Use `git mv "old/path/file.md" "new/path/file.md"` for reorganization tasks
- **Batch operations**: For multiple file moves, use git mv for each file individually to preserve individual file histories

## Working with Obsidian Content

### Markdown Specifics
- Use Obsidian-style double-bracket links: `[[filename]]` or `[[Section/filename]]`
- Maintain checkbox syntax for task tracking: `- [ ] Task` and `- [x] Completed`
- Include date stamps and review cycles in content footers
- Use emoji prefixes for visual organization in README sections

### Content Templates
When adding new content, reference existing templates:
- **Lessons Learned**: Use the template structure in `Lessons Learned/Lessons Overview.md`
- **Tool Evaluations**: Follow the criteria structure in `Tools/Tool Guide.md`
- **Company Registry**: Use the company file template in `Company Registry/CompanyGuide.md`
- **Project Tracking**: Use checkbox-based progress tracking like in `100 TUF/100 TUF Journey Overview.md`

## Working with Company Registry

### File Structure and Naming
- **Company files**: Always use the actual company name as the filename (e.g., `Netflix.md`, `Character AI.md`)
- **No README files**: Never create README.md files within Company Registry subdirectories
- **Descriptive organization**: Directory structure should be self-explanatory through naming
- **Consistent paths**: All company files go directly in their appropriate subcategory folder

### Adding New Companies
When adding companies to the Company Registry:

1. **Categorization**: Determine the appropriate industry category for the company. If no existing category fits, ask the user to confirm the creation of a new category.

2. **File Creation**: Create individual company file using the company template with the actual company name as filename (e.g., `Company Name.md`)

3. **Information Population**: Search for and gather comprehensive company information to fully populate all template sections, ensuring accuracy and completeness

4. **Perplexity Query URLs**: Create standardized Perplexity search URLs for each company:
   - Use format: `https://www.perplexity.ai/search/[encoded-query-text]`
   - **Latest Company News Query**: "Summarize the latest news about [Company Name], focusing on recent developments and announcements. Include information from reputable sources such as news articles and press releases. Provide a list with sources and summaries for each piece of news."
   - **Industry AI News Query**: "Latest AI news for [Company Name] and the [Industry] industry. Provide a list of recent AI-related developments, initiatives, or products from [Company Name] and other companies in the [Industry] industry. Include sources and brief summaries for each item."
   - **URL Encoding**: Convert spaces to hyphens, remove special characters appropriately (& becomes -, commas removed, etc.)
   - **Claude Code Generation**: When creating company files, Claude Code will automatically generate the properly formatted URLs matching Perplexity's search URL structure

5. **AI News Section**: Include AI-related developments when available:
   - Use "Latest AI News" section header
   - If no AI news available, use "No AI News" as placeholder
   - Include date in MM/DD/YYYY format
   - Provide context about AI adoption or industry impact

6. **Date Updates**: Always update the "Last Updated" timestamp at the bottom of files:
   - Format: `*Last Updated: YYYY-MM-DD*`
   - Use the current date when making changes
   - Update both the individual company file and the main Company Registry README

7. **Registry Updates**: Update the Company Registry guide to include the new company in both the category section and alphabetical listing

8. **Template Usage**: Use the company file template below for consistency across all company files

### Company File Template

```markdown
# Company Name

**Industry:** [Primary Industry]  
**Type:** [Public/Private]  
**Founded:** [Year]  
**Headquarters:** [Location]  
**Website:** [Company website]

*Brief tagline or description of the company*

## Latest AI News
*[Section header - if no AI news, use "No AI News" as placeholder]*

### [News Title]
**Date:** MM/DD/YYYY

[Brief summary of AI-related news, developments, or initiatives. Include context about how this relates to AI adoption or impact on the industry.]

## Overview
Brief description of the company's primary business and market position.

## Key Products/Services
- Product/service 1
- Product/service 2
- Product/service 3

## Recent Developments
- Latest funding rounds
- Major partnerships or acquisitions
- New product launches
- Executive changes

## Financial Information
- Revenue (if public)
- Valuation (if available)
- Funding rounds and investors

## Leadership
- CEO: [Name]
- Key executives and founders

## Competitive Landscape
- Main competitors
- Market position
- Differentiators

## Perplexity Queries
### Latest Company News
[Summarize the latest news about [Company Name], focusing on recent developments and announcements. Include information from reputable sources such as news articles and press releases. Provide a list with sources and summaries for each piece of news.](https://www.perplexity.ai/search/[encoded-query-text])

### Industry AI News
[Latest AI news for [Company Name] and the [Industry] industry. Provide a list of recent AI-related developments, initiatives, or products from [Company Name] and other companies in the [Industry] industry. Include sources and brief summaries for each item.](https://www.perplexity.ai/search/[encoded-query-text])

**Note:** Replace `[encoded-query-text]` with the query text where spaces become hyphens and special characters are handled appropriately. Claude Code will generate the properly formatted URLs when creating company files.

## Tags
#[industry] #[type] #[relevant-tags]

---
*Last Updated: [YYYY-MM-DD]*
```

### Company Registry Maintenance
- Keep company information current and accurate
- Update financial information, leadership changes, and recent developments
- Maintain consistent formatting across all company files
- Use appropriate tags for categorization and searchability

## Working with Tools Section

### File Structure and Naming for Tools
- **Tool files**: Use descriptive names that clearly identify the tool (e.g., `ChatGPT.md`, `Adobe Photoshop.md`)
- **Category organization**: Tools organized by primary category with clear folder structure
- **No README proliferation**: Avoid creating multiple README files in tool subcategories
- **Ranking files**: When creating rankings, use descriptive names like `AI Tools Q1 2025 Rankings.md`

### Adding New Tools or Updates
When adding or updating tools in the Tools section:

1. **Primary Category**: Each tool has one primary category where the main file resides:
   - `Tools/[Primary Category]/Tool Name.md`
   - Examples: `Tools/AI Automations/ChatGPT.md`, `Tools/Design/Figma.md`

2. **File Creation**: Create individual tool files using the tool evaluation template from `Tools/Tool Evaluation Template.md`

3. **Multi-Category Tools**: If a tool fits multiple categories:
   - Create the main file in the PRIMARY category only
   - Add cross-references in secondary category README files under "Additional Tools" sections
   - Use format: `- [[Primary Category/Tool Name]] - Brief description`

4. **Automatic README Updates**: When adding/updating tools:
   - The tool should automatically appear in the primary category's README
   - Update the category README to include the new tool link
   - Use format: `- [[Tool Name]] - Brief description and key features`

5. **Date Management**: Always update timestamps consistently:
   - Update the individual tool file: `*Last Updated: YYYY-MM-DD*`
   - Update the primary category README: `*Last Updated: YYYY-MM-DD*`
   - Update the main Tools README only if structural changes are made
   - Use current date (2025-07-27) for all updates

6. **Tool Updates vs New Additions**: 
   - For existing tool updates: modify the existing file and update dates
   - For new tools: create new file and add to appropriate README
   - Avoid duplicate README updates - one update per tool addition/modification

### Tool Page Structure
When creating individual tool pages, follow this structure:

#### Required Sections
1. **Header**: Tool name, category, company, type
2. **Overview**: Brief description of the tool's purpose
3. **Links & Resources**: Official website, documentation, social media links
4. **Tool Evaluation**: Reference to evaluation template with "Not reviewed" or "*Coming soon*"
5. **Key Features**: List of core features (no checkboxes, just bullet points)
6. **Use Cases**: Primary applications
7. **Potential Workflow Integration Ideas**: Suggested integration scenarios
8. **Pricing**: Current pricing with publicly available information
9. **Pros & Cons**: Clear advantages and disadvantages
10. **Notes & Updates**: Recent changes (*Coming soon* for new tools)
11. **Recommended For**: Target user groups
12. **Related Tools**: Ecosystem and alternatives with proper linking
13. **Rankings**: Placeholder for "*Coming soon*"

#### Tool Evaluation Guidelines
- **Reference Template**: Link to `Tool Evaluation Template.md` instead of full criteria
- **Status Indicators**: Use "Not reviewed" or "*Coming soon*" for incomplete evaluations
- **Key Features**: Simple bullet list without checkboxes
- **No Testing Status**: Remove testing status sections entirely

#### Pricing Research
- **Public Information**: Research and include publicly available pricing
- **Current Rates**: Use 2025 pricing when available
- **Subscription Tiers**: List all available plans with costs
- **Student/Enterprise**: Include special pricing when available

#### Related Tools Linking
- **Ecosystem Tools**: Link to external resources if internal pages not available
- **Alternatives**: Prioritize internal tool reviews when available, then external links
- **Format**: `- [Tool Name](URL) - Brief description`
- **Coming Soon**: Use "*Coming soon* - Internal tool reviews" for planned internal coverage

#### Rankings Integration
- **Section Required**: Include "Rankings" section in all tool pages
- **Placeholder**: Use "*Coming soon*" until rankings are developed
- **Future Structure**: Will contain comparative rankings within categories

### Tools Section Maintenance
- Keep tool evaluations current with latest features and pricing
- Maintain consistent evaluation criteria across all tool files
- Update individual tool files and category READMEs with current timestamps
- Regular review cycles for tool effectiveness and alternatives
- **No "Next Review" dates**: Never add "Next Review" dates to any files in the repository - only use "Last Updated" timestamps

## General File Management Guidelines

### README.md Usage Policy
- **Main sections only**: README.md files should ONLY exist at the top level of main sections
- **Prohibited locations**: Never create README.md in subdirectories, subcategories, or subsections
- **Exceptions**: None - this rule is absolute to avoid confusion
- **Alternative approach**: Use descriptive filenames for any organizational or overview content

### Descriptive File Naming Requirements
- **Self-documenting**: Filenames should immediately convey their content and purpose
- **Avoid generic names**: Never use generic names like `index.md`, `main.md`, `content.md`, `overview.md`
- **Use specific descriptors**: Include relevant details like dates, categories, or specific focus areas
- **Examples of good naming**:
  - `Netflix Q4 2024 AI Strategy.md`
  - `Gaming Industry AI Adoption Trends.md`
  - `Music Streaming Platform Comparison.md`
  - `Traditional vs AI-Native Studios Analysis.md`

### Working with Subsections and Rankings
- **Descriptive titles**: All subsection files must have names that clearly identify their scope
- **Date specificity**: Include time periods in ranking or analysis files
- **Category clarity**: Make the subject matter obvious from the filename
- **Avoid ambiguity**: Never use names that could apply to multiple different files

### Date Management
- **"Last Updated" only**: All files should only include "Last Updated: YYYY-MM-DD" timestamps
- **No "Next Review" dates**: Never add "Next Review" dates to any files - they create unnecessary maintenance overhead
- **Current date usage**: Always use current date when making updates
- **Consistent format**: Use YYYY-MM-DD format for all dates

### Site Publishing
The repository is published using Obsidian Publish, so:
- All content should be Obsidian-compatible markdown
- Internal links use Obsidian's double-bracket format
- Content structure supports Obsidian's graph view and search functionality
- Descriptive filenames improve navigation and discoverability in Obsidian

## Working with AI Automations Section

### Organization and Structure
- **Role-based organization**: Product Management, Marketing, Sales, Operations, Research
- **Main files**: `AI Automations Guide.md` (main hub), `Automation Workflows by Job Role.md`, `Automation Workflows by Problem.md`, `Automation Best Practices.md`
- **File naming**: Use descriptive names like `[Role] [Company] Automations.md` or `[Platform] [Function].md`

### Business Size Definitions for Cost Estimates
All automation cost estimates use consistent business size definitions:

**Small Business:**
- Up to 250 employees
- Annual revenue under $50 million
- Basic to moderate automation needs (< 10,000 operations/month)
- Limited integrations and straightforward workflows
- Self-service setup preferred

**Medium Business:**
- 250-1,000 employees  
- Annual revenue $50M-$1B
- Moderate to complex automation needs (10,000-100,000 operations/month)
- Multiple integrations and advanced workflows
- Some IT support available

**Enterprise:**
- 1,000+ employees
- Annual revenue $1B+
- Complex automation requirements (100,000+ operations/month)
- Extensive integrations and custom workflows
- Dedicated IT/automation team

*Note: For role-specific guides (e.g., Job Researcher, College Student), size refers to scope of individual use rather than organization size.*

### Adding New Automations
1. **Categorize** by primary function (Product, Marketing, Sales, etc.)
2. **Create file** in appropriate role folder with descriptive filename
3. **Required Content Structure**: Each automation file must include:
   - **Overview**: Purpose, target users, tools used, time/results expectations
   - **Individual Workflows**: 3-5 specific automation workflows with step-by-step implementation
   - **Dual-Platform Implementation**: Both n8n and Make.com setup instructions for each workflow
   - **Cost Estimates**: Monthly operating costs using standard business size definitions above
   - **Getting Started Guide**: Practical first steps and budget planning
   - **Best Practices**: Security, monitoring, and optimization guidelines
   - **Common Questions**: FAQ section addressing typical concerns
   - **Success Metrics**: Trackable results users can expect
4. **Cost Estimation Requirements**:
   - Use standard Small/Medium/Enterprise definitions consistently
   - Focus on monthly operating costs only (no setup time or ROI estimates)
   - Include clear assumptions about what drives cost differences
   - Account for automation platform, required integrations, and processing volume
5. **Pain Point Integration**: Evaluate if the automation solves a common, high-impact problem:
   - **Major pain points**: Add to `Pain Point Solutions.md` if it addresses widespread frustrations (job search stress, financial chaos, communication overwhelm, etc.)
   - **If unsure, use these criteria as reference:**
     - **Time Impact**: Saves 4+ hours per week or prevents significant stress/frustration
     - **Broad Appeal**: Affects people across multiple roles, industries, or life stages  
     - **Search Behavior**: People actively search online for solutions to this problem
     - **When in doubt, use your best judgment** - err on the side of inclusion for genuinely frustrating problems
   - **Cross-reference existing**: Link to existing pain point sections if the automation provides an alternative solution
   - **Avoid minor issues**: Don't add niche or minor problems - keep the pain point file focused on significant, relatable frustrations
   - **Use emotional language**: Frame problems in natural, conversational terms people actually think and search for
6. **Navigation Section**: Every automation file must include a "More Automations" section at the end with these standard links:
   ```markdown
   ## 🔗 More Automations

   **Need different solutions?**
   - **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
   - **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
   - **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
   - **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals
   ```
7. **Update main directory files**: Add new automation to appropriate sections in `AI Automations Guide.md` and either `Automation Workflows by Job Role.md` or `Automation Workflows by Problem.md`
8. **Cross-Reference**: Link related automations and ensure they appear in both n8n and Make.com platform sections

### LLM-Only Solution Guidelines
When evaluating automations for LLM-only alternatives, include simplified solutions for tasks that can be accomplished through conversation alone:

**Include LLM-Only Solutions When:**
- **Single conversation completion**: Task can be fully completed in one conversation session
- **No real-time monitoring**: Doesn't require ongoing alerts, scheduled tasks, or monitoring
- **No data integration**: Doesn't need to connect multiple systems or APIs
- **Manual input acceptable**: User can provide necessary data through conversation
- **One-time or infrequent use**: Task doesn't require constant automation
- **Text-based output**: Result is content, analysis, or recommendations (not system actions)

**LLM-Only Solution Criteria:**
- **Time Impact**: Can save 1+ hours per use or significant mental effort
- **Simplicity Test**: Can be explained in 2-3 sentences to an 8th grader
- **Immediate Value**: User gets useful results in the same conversation
- **Standalone**: Doesn't require external tool setup or technical configuration

**Content Structure for LLM-Only Sections:**
Each qualifying automation should include an "LLM-Only Alternative" section with:
- **"Quick Solution" header**: "If you just need this done once or occasionally..."
- **Simple explanation**: What the LLM can do in plain language
- **Multi-step prompt example**: Clear, copy-pasteable prompt format
- **JSON template option**: When structured output helps organize results
- **Limitations note**: What this approach can't do compared to full automation
- **When to upgrade**: Clear criteria for when automation becomes worth the setup

**Writing Style for LLM Solutions:**
- Use 8th grade reading level
- Conversational, encouraging tone
- Focus on immediate results over technical details
- Include copy-paste prompts with placeholder brackets [like this]
- Explain why each step matters in simple terms

## MCP (Model Context Protocol) Setup and Management

### Understanding MCP Integration
MCP enables Claude Code to connect with external tools and services, significantly expanding capabilities beyond basic file operations. The repository includes comprehensive MCP documentation in the `MCP/` section with guides organized by server type.

### MCP Setup Workflow
When setting up or recommending MCP servers for this repository:

1. **Assessment**: First assess what the user is trying to accomplish and recommend appropriate MCP servers
2. **Reference Guide**: Always reference the comprehensive setup guide at `[[MCP/README]]`
3. **Security First**: Follow security best practices outlined in the guide
4. **Documentation**: Document any MCP servers used in project-specific documentation
5. **Update Most Used.md**: When adding/removing MCP servers, update the "MCP Servers (Currently Active)" section in `Most Used.md`

### Common MCP Servers for Rogue Codex
Based on the repository's nature as a knowledge base and documentation site:

**Recommended MCP Servers:**
- **Memory**: For persistent context across Claude Code sessions, remembering user preferences, project conventions, and documentation patterns
- **Puppeteer**: For web automation, taking screenshots of referenced sites, and testing web-based workflows
- **SQLite**: For managing structured data if needed (company information, tool evaluations)
- **GitHub**: For repository management and automation workflows

**Installation Pattern:**
```bash
# Check current status
claude mcp list

# Install recommended server (example: Puppeteer)
npm install -g puppeteer-mcp-claude

# Configure in .claude/settings.local.json
# Test functionality
```

### MCP Best Practices for Documentation Workflows
- **Security**: Store API keys in environment variables, never commit to repository
- **Configuration**: Use local settings (`.claude/settings.local.json`) for project-specific MCP configs
- **Documentation**: Update project documentation when MCP servers are required for workflows
- **Testing**: Verify MCP functionality before documenting workflows that depend on external tools

### Memory Server Usage for Rogue Codex
When Memory server is configured, Claude Code can:

**User Context Management:**
- Remember user's role, expertise level, and preferred documentation style
- Track which sections/topics user works on most frequently
- Store project-specific terminology and conventions
- Maintain user preferences for file naming, formatting, and organization patterns

**Project Continuity:**
- Remember ongoing documentation projects and their current status
- Track relationships between different sections (Company Registry, Tools, etc.)
- Store user's preferred workflows for different types of content creation
- Maintain context about recent changes and areas needing attention

**Workflow Optimization:**
- Learn user's preferred templates and automatically suggest appropriate structures
- Remember successful patterns for content organization and reuse them
- Track which tools and MCP servers work best for specific documentation tasks
- Store custom automation preferences and frequently used commands

**Privacy and Control:**
- All memory data stored locally in project `.claude/` directory or custom location
- User can review, edit, or delete memory data at any time
- No external transmission of personal or project information
- Memory can be reset or customized per project needs

### MCP Scoping Guidelines for New Servers

When adding new MCP servers to Rogue Codex, follow this decision framework:

**Global Scope (User-level) - Use when:**
- Server provides utility across ALL projects
- Lightweight, always-useful functionality
- No sensitive project-specific data
- Examples: Puppeteer, Time, Context7

**Project Scope - Use when:**
- Server contains project-specific data or configuration
- Tool is specific to this project's domain/requirements
- Should be shared with project collaborators
- Examples: Project Memory, Project Database

**Local Scope - Use when:**
- Personal development preferences only
- Contains sensitive API keys or personal data
- Temporary or experimental configurations

**Memory Implementation:**
- **Project Memory**: Single memory system storing both general patterns and project-specific context
- **File Location**: `.claude/project-memory.json` (local to this project)
- **Content**: User preferences, Rogue Codex terminology, section relationships, workflows
- **Scope**: Project-level due to current MCP memory scoping limitations

### MCP Troubleshooting
When MCP servers aren't working:
1. Check installation: `npm list -g [package-name]`
2. Verify configuration in settings files
3. Restart Claude Code after configuration changes
4. Reference troubleshooting section in the MCP Setup Guide
5. Use `claude mcp list` to verify server status

### Using MCP Servers with the Gemini CLI

The MCP servers configured for Claude can also be used with the Gemini CLI. To enable them, you need to add the same `mcpServers` configuration to your Gemini settings file. The `Gemini.md` file in this repository provides detailed instructions on how to set up MCP scopes for the Gemini CLI. It is recommended to keep the configurations synchronized between both tools.

## Personal/Custom Instructions

For personal preferences and custom instructions that should remain private:

1. **Location**: Store in `Exclude/Custom Instructions.md` (not tracked in public documentation)
2. **Usage**: Reference as needed for personal workflow preferences
3. **Updates**: Only update when manually requested - never proactively modify personal instructions
4. **Privacy**: Keep all personal configurations and preferences separate from public documentation

When working with custom instructions, always check `Exclude/Custom Instructions.md` for user-specific preferences before proceeding with documentation tasks.


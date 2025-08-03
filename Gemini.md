# Gemini.md

This file provides guidance to the Gemini CLI when working with code in this repository.

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
- `Company Spotlight/` - Featured companies making AI news across entertainment, media, and tech
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

## Version Control
- **DO NOT COMMIT**: Never commit any changes to the Git repository. All version control is handled manually by the user.

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
- **Company Spotlight**: Use the company file template in `Company Spotlight/CompanyGuide.md`
- **Project Tracking**: Use checkbox-based progress tracking like in `100 TUF/100 TUF Journey Overview.md`

## Working with Company Spotlight

### File Structure and Naming
- **Company files**: Always use the actual company name as the filename (e.g., `Netflix.md`, `Character AI.md`)
- **No README files**: Never create README.md files within Company Spotlight subdirectories
- **Descriptive organization**: Directory structure should be self-explanatory through naming
- **Consistent paths**: All company files go directly in their appropriate subcategory folder

### Adding New Companies
When adding companies to the Company Spotlight:

1. **Categorization**: Determine the appropriate industry category for the company. If no existing category fits, ask the user to confirm the creation of a new category.

2. **File Creation**: Create individual company file using the company template with the actual company name as filename (e.g., `Company Name.md`)

3. **Information Population**: Search for and gather comprehensive company information to fully populate all template sections, ensuring accuracy and completeness

4. **Perplexity Query URLs**: Create standardized Perplexity search URLs for each company:
   - Use format: `https://www.perplexity.ai/search/[encoded-query-text]`
   - **Latest Company News Query**: "Summarize the latest news about [Company Name], focusing on recent developments and announcements. Include information from reputable sources such as news articles and press releases. Provide a list with sources and summaries for each piece of news."
   - **Industry AI News Query**: "Latest AI news for [Company Name] and the [Industry] industry. Provide a list of recent AI-related developments, initiatives, or products from [Company Name] and other companies in the [Industry] industry. Include sources and brief summaries for each item."
   - **URL Encoding**: Convert spaces to hyphens, remove special characters appropriately (& becomes -, commas removed, etc.)
   - **Gemini Generation**: When creating company files, Gemini will automatically generate the properly formatted URLs matching Perplexity's search URL structure

5. **AI News Section**: Include AI-related developments when available:
   - Use "Latest AI News" section header
   - If no AI news available, use "No AI News" as placeholder
   - Include date in MM/DD/YYYY format
   - Provide context about AI adoption or industry impact

6. **Date Updates**: Always update the "Last Updated" timestamp at the bottom of files:
   - Format: `*Last Updated: YYYY-MM-DD*`
   - Use the current date when making changes
   - Update both the individual company file and the main Company Spotlight README

7. **Spotlight Updates**: Update the Company Spotlight guide to include the new company in both the category section and alphabetical listing

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

**Note:** Replace `[encoded-query-text]` with the query text where spaces become hyphens and special characters are handled appropriately. Gemini will generate the properly formatted URLs when creating company files.

## Tags
#[industry] #[type] #[relevant-tags]

---
*Last Updated: [YYYY-MM-DD]*
```

### Company Spotlight Maintenance
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
MCP enables the Gemini CLI to connect with external tools and services, significantly expanding its capabilities beyond built-in tools.

### MCP Scopes and Configuration

MCP servers can be configured at different "scopes," which determine when they are available. Understanding these scopes is key to managing your tools effectively.

**1. Project Scope (This Project Only)**
- **What it is**: Servers that are specific to this `Rogue Codex` project.
- **Configuration File**: `/Users/proyogi/Documents/HODL/Rogue Codex/.gemini/settings.json`
- **Use For**: Tools that read or write project-specific data or are essential to the project's workflows.
- **Example**: `project-memory` is configured here because it needs access to this project's `.claude/project-memory.json` file.

**2. Global Scope (All Projects)**
- **What it is**: General-purpose servers that you want available in any project you work on.
- **Configuration File**: `~/.gemini/settings.json` (i.e., `/Users/proyogi/.gemini/settings.json`)
- **Use For**: Universal utilities like web scraping or time functions.
- **Action Required**: To make general-purpose tools like `puppeteer`, `context7`, and `time` available everywhere, you should move their configurations from the project's `.gemini/settings.json` to your global `~/.gemini/settings.json` file.

**3. Local Scope (Private to You)**
- **What it is**: A place for your personal, private configurations that should not be shared.
- **Configuration File**: A local settings file that you would add to `.gitignore`.
- **Use For**: Servers that require sensitive API keys or experimental tools you are testing.

### Recommended MCP Configuration

Based on the tools you have, here is the recommended setup:

**Project-Scoped Servers (`/Users/proyogi/Documents/HODL/Rogue Codex/.gemini/settings.json`):**
```json
{
  "mcpServers": {
    "project-memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"],
      "env": {
        "MEMORY_FILE_PATH": ".claude/project-memory.json"
      }
    }
  }
}
```

**Globally-Scoped Servers (`/Users/proyogi/.gemini/settings.json`):**
```json
{
  "mcpServers": {
    "puppeteer-mcp-claude": {
      "command": "node",
      "args": ["/Users/proyogi/.nvm/versions/node/v22.17.0/lib/node_modules/puppeteer-mcp-claude/dist/index.js"]
    },
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "time": {
      "command": "python3",
      "args": ["-m", "mcp_server_time"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "playwright-mcp"]
    },
    "read-website-fast": {
      "command": "npx",
      "args": ["-y", "@just-every/mcp-read-website-fast"]
    },
    "mermaid": {
      "command": "npx",
      "args": ["-y", "mermaid-mcp-server"]
    }
  }
}
```

### MCP Configuration Best Practices

**1. Package Name Verification**
- Always verify package names before adding to configuration
- Use `npm search [package-name]` to find correct package names
- Common corrections:
  - `@modelcontextprotocol/read-website-fast` → `@just-every/mcp-read-website-fast`
  - `@modelcontextprotocol/mermaid-mcp` → `mermaid-mcp-server`

**2. Server Testing**
- Test each MCP server individually before adding to configuration
- Use `npx -y [package-name] --help` to verify server accessibility
- Check for proper command-line argument support

**3. Error Handling**
- Monitor MCP server startup logs for connection issues
- Common errors include:
  - Package not found (404 errors)
  - Incorrect command paths
  - Missing dependencies
  - Port conflicts (for web-based servers)

**4. Configuration Validation**
- Ensure JSON syntax is valid
- Verify file paths exist and are accessible
- Check environment variable requirements
- Test server connectivity after configuration changes

### MCP Troubleshooting Guide

**Common Issues and Solutions:**

**1. Server Connection Failures**
```
MCP STDERR: Package not found or server failed to start
```
**Solution:**
- Verify package name with `npm search [package-name]`
- Check if package is installed: `npm list -g [package-name]`
- Test server manually: `npx -y [package-name] --help`

**2. API Parameter Format Errors**
```
GenerateContentRequest.tools[0].function_declarations[32].parameters.properties[url].format: only 'enum' and 'date-time' are supported for STRING type
```
**Solution:**
- This indicates a tool parameter format incompatibility
- May require updating to a newer version of the MCP server
- Check server documentation for parameter format requirements
- Consider using alternative MCP servers with similar functionality

**3. Port Conflicts**
```
Port 5174 is in use, skipping web server
```
**Solution:**
- This is usually non-critical for MCP functionality
- Servers often fall back to stdio transport automatically
- Check if multiple instances are running

**4. Path Resolution Issues**
```
Script location: /path/to/node_modules/package/dist/index.js
```
**Solution:**
- Verify the exact path exists on your system
- Update paths to match your Node.js installation
- Use `which node` to confirm Node.js location

### Managing MCP Servers

**1. Server Discovery**
- Use `gemini --help` to see available command-line options
- Check MCP server logs for connection status
- Monitor startup messages for successful connections

**2. Configuration Updates**
- Edit settings files directly: `~/.gemini/settings.json` (global) or `./.gemini/settings.json` (project)
- Restart Gemini CLI after configuration changes
- Test server functionality after updates

**3. Server Maintenance**
- Keep MCP servers updated: `npm update -g [package-name]`
- Monitor for deprecation notices
- Replace servers that are no longer maintained

**4. Performance Optimization**
- Limit active servers to those actually needed
- Use project-scoped servers for project-specific tools
- Consider server resource usage for complex operations

### Built-in vs External MCP Servers

**Current Gemini CLI Version (0.1.9) Status:**
- **External MCP servers**: Fully supported and working
- **Built-in servers**: May be in development or require different configuration
- **Functionality**: External servers provide equivalent or superior capabilities

**Recommended Approach:**
- Use external MCP servers for immediate functionality
- Monitor Gemini CLI updates for built-in server improvements
- Maintain configuration for both approaches as needed

### Security Considerations

**1. API Key Management**
- Store sensitive keys in environment variables
- Use local scope for private configurations
- Never commit API keys to version control

**2. Server Permissions**
- Review server capabilities before installation
- Limit server access to necessary functions
- Monitor server behavior for unexpected actions

**3. Network Security**
- Be cautious with servers requiring network access
- Verify server sources and maintainers
- Use HTTPS for all external connections

### Advanced Configuration

**1. Environment Variables**
```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "package-name"],
      "env": {
        "API_KEY": "your-api-key",
        "CONFIG_PATH": "/path/to/config"
      }
    }
  }
}
```

**2. Custom Server Paths**
```json
{
  "mcpServers": {
    "custom-server": {
      "command": "/full/path/to/executable",
      "args": ["--config", "/path/to/config.json"]
    }
  }
}
```

**3. Server Dependencies**
- Ensure all required dependencies are installed
- Check for Python packages: `pip list | grep mcp`
- Verify Node.js packages: `npm list -g | grep mcp`

### Monitoring and Debugging

**1. Log Analysis**
- Monitor MCP STDERR output for error messages
- Check server-specific log files when available
- Use debug mode for detailed troubleshooting

**2. Server Health Checks**
- Test basic server functionality regularly
- Verify tool availability and response times
- Monitor for performance degradation

**3. Configuration Validation**
- Validate JSON syntax before applying changes
- Test server connections after configuration updates
- Maintain backup configurations for rollback

### Managing MCP Servers
- Use the `/mcp` command in the Gemini CLI to see which servers are connected and from which configuration file they were loaded.
- To apply the scope changes, you will need to manually create or edit the files listed above with the provided content.

## Personal/Custom Instructions

For personal preferences and custom instructions that should remain private:

1. **Location**: Store in `Exclude/Custom Instructions.md` (not tracked in public documentation)
2. **Usage**: Reference as needed for personal workflow preferences
3. **Updates**: Only update when manually requested - never proactively modify personal instructions
4. **Privacy**: Keep all personal configurations and preferences separate from public documentation

When working with custom instructions, always check `Exclude/Custom Instructions.md` for user-specific preferences before proceeding with documentation tasks.
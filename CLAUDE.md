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
- `AI Regulation/`, `AI Risk/`, `AI Automations/` - AI-focused content sections
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

### File Naming Conventions
- Use spaces in directory names (e.g., "Lessons Learned", "AI Regulation")
- URL-encode spaces in markdown links (e.g., `[link](Lessons%20Learned/README.md)`)
- **README.md files**: Only use at the top level of each main section - NEVER create README.md files in subdirectories or subcategories
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
- **Lessons Learned**: Use the template structure in `Lessons Learned/README.md`
- **Tool Evaluations**: Follow the criteria structure in `Tools/README.md`
- **Company Registry**: Use the company file template in `Company Registry/README.md`
- **Project Tracking**: Use checkbox-based progress tracking like in `100 TUF/README.md`

## Working with Company Registry

### File Structure and Naming
- **Company files**: Always use the actual company name as the filename (e.g., `Netflix.md`, `Character AI.md`)
- **No README files**: Never create README.md files within Company Registry subdirectories
- **Descriptive organization**: Directory structure should be self-explanatory through naming
- **Consistent paths**: All company files go directly in their appropriate subcategory folder

### Adding New Companies
When adding companies to the Company Registry:

1. **File Location**: Create individual company files in the appropriate industry and subcategory folder:
   - `Company Registry/AI Infrastructure/Company Name.md`
   - `Company Registry/Film and Streaming/Traditional Studios/Company Name.md`
   - `Company Registry/Film and Streaming/AI-Native Studios/Company Name.md`
   - `Company Registry/Gaming and Interactive/Traditional Studios/Company Name.md`
   - `Company Registry/Gaming and Interactive/AI-Native Studios/Company Name.md`
   - `Company Registry/Music and Entertainment/Traditional Companies/Company Name.md`
   - `Company Registry/Music and Entertainment/AI-Native Companies/Company Name.md`
   - etc.

2. **Company Categorization**: Determine whether companies belong in Traditional or AI-Native subcategories:
   - **Traditional Studios/Companies**: Established companies that existed before AI and are adapting AI into existing workflows
     - Examples: Disney, Netflix, Electronic Arts, Sony Music
     - Focus: Track AI adoption strategies, partnerships, internal AI development
   - **AI-Native Studios/Companies**: Companies built from the ground up with AI as core technology
     - Examples: Decart, Staircase, Promise, Runway
     - Focus: Track core AI technology developments, funding, market penetration strategies

3. **File Naming**: Use the actual company name as the filename (e.g., `OpenAI.md`, `Netflix.md`)

4. **Template Usage**: Use the company file template from `Company Registry/README.md` for consistency

5. **README Linking**: After creating a company file, update the relevant industry and subcategory section in `Company Registry/README.md`:
   - Replace "*No companies added yet*" with a link to the new company file
   - Use format: `- [Company Name](Industry%20Folder/Subcategory%20Folder/Company%20Name.md)`
   - Examples: 
     - `- [Netflix](Film%20and%20Streaming/Traditional%20Studios/Netflix.md)`
     - `- [Staircase](Film%20and%20Streaming/AI-Native%20Studios/Staircase.md)`
   - Add additional companies as new bullet points under the appropriate subcategory

6. **Perplexity Query URLs**: Create standardized Perplexity search URLs for each company:
   - Use format: `https://www.perplexity.ai/search/[encoded-query-text]`
   - **Latest Company News Query**: "Summarize the latest news about [Company Name], focusing on recent developments and announcements. Include information from reputable sources such as news articles and press releases. Provide a list with sources and summaries for each piece of news."
   - **Industry AI News Query**: "Latest AI news for [Company Name] and the [Industry] industry. Provide a list of recent AI-related developments, initiatives, or products from [Company Name] and other companies in the [Industry] industry. Include sources and brief summaries for each item."
   - **URL Encoding**: Convert spaces to hyphens, remove special characters appropriately (& becomes -, commas removed, etc.)
   - **Claude Code Generation**: When creating company files, Claude Code will automatically generate the properly formatted URLs matching Perplexity's search URL structure

7. **AI News Section**: Include AI-related developments when available:
   - Use "Latest AI News" section header
   - If no AI news available, use "No AI News" as placeholder
   - Include date in MM/DD/YYYY format
   - Provide context about AI adoption or industry impact

8. **Date Updates**: Always update the "Last Updated" timestamp at the bottom of files:
   - Format: `*Last Updated: YYYY-MM-DD*`
   - Use the current date when making changes
   - Update both the individual company file and the main Company Registry README

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

2. **File Creation**: Create individual tool files using the tool evaluation template from `Tools/README.md`

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
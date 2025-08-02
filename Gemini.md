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
- URL-encode spaces in markdown links (e.g., `[link](Lessons%20Learned/README.md)`)
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
- **Lessons Learned**: Use the template structure in `Lessons Learned/README.md`
- **Tool Evaluations**: Follow the criteria structure in `Tools/README.md`
- **Company Registry**: Use the company file template in `Company Registry/README.md`
- **Project Tracking**: Use checkbox-based progress tracking like in `100 TUF/README.md`

## Working with Company Registry

### Adding New Companies
When creating company files in the Company Registry:

1. **Perplexity Query URLs**: Create standardized Perplexity search URLs for each company:
   - Use format: `https://www.perplexity.ai/search/[encoded-query-text]`
   - **Latest Company News Query**: "Summarize the latest news about [Company Name], focusing on recent developments and announcements. Include information from reputable sources such as news articles and press releases. Provide a list with sources and summaries for each piece of news."
   - **Industry AI News Query**: "Latest AI news for [Company Name] and the [Industry] industry. Provide a list of recent AI-related developments, initiatives, or products from [Company Name] and other companies in the [Industry] industry. Include sources and brief summaries for each item."
   - **URL Encoding**: Convert spaces to hyphens, remove special characters appropriately (& becomes -, commas removed, etc.)
   - **Gemini Generation**: When creating company files, Gemini will automatically generate the properly formatted URLs matching Perplexity's search URL structure

2. **AI News Section**: Include AI-related developments when available:
   - Use "Latest AI News" section header
   - If no AI news available, use "No AI News" as placeholder
   - Include date in MM/DD/YYYY format
   - Provide context about AI adoption or industry impact

3. **Date Updates**: Always update the "Last Updated" timestamp at the bottom of files:
   - Format: `*Last Updated: YYYY-MM-DD*`
   - Use the current date when making changes
   - Update both the individual company file and the main Company Registry README

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
    }
  }
}
```

### Managing MCP Servers
- Use the `/mcp` command in the Gemini CLI to see which servers are connected and from which configuration file they were loaded.
- To apply the scope changes, you will need to manually create or edit the files listed above with the provided content.

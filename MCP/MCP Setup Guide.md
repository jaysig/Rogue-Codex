# MCP (Model Context Protocol)

**Model Context Protocol** enables Claude Code to connect with external tools and services, dramatically expanding capabilities beyond basic file operations. MCP gives Claude Code "superpowers" to control web browsers, access databases, manage cloud services, and integrate with productivity tools.

## Quick Start

1. **Check Status**: `claude mcp list` - See currently configured servers
2. **Add Server**: `claude mcp add server-name -- command args` 
3. **Remove Server**: `claude mcp remove server-name`
4. **Test**: Ask Claude Code to use the new MCP tools

## Server Categories

### 🔧 [Core](Core/)
**Essential servers for basic functionality**
- **Memory** - Persistent context and knowledge management (Global + Project)
- **Memory Plus** - Enhanced memory with pattern recognition and knowledge graphs
- **Time** - Timezone handling and accurate timestamps
- **Puppeteer** - Web browser automation and screenshots
- **Nexus** - MCP server orchestration and management
- **OpenAPI Schema Explorer** - API schema analysis and documentation
- **MCP Aggregator** - Combine multiple MCP servers into single interface (solves Cursor's 2-server limit)

### 💻 [Development](Development/)
**Coding and development tools**
- **GitHub** - Repository management and automation
- **SQLite/PostgreSQL** - Database integration
- **Filesystem** - Enhanced file operations
- **Docker** - Container management
- **SEO MCP Server** - Website analysis and optimization
- **Browser-use MCP** - Browser automation and RPA
- **Vectorize Document Search** - Vector search and document analysis
- **Browser MCP** - Local browser control with privacy focus
- **Excel MCP Server** - Excel file processing and data analysis
- **JSON MCP** - JSON data manipulation and validation
- **Mermaid MCP** - Diagram generation and visualization
- **MySQL MCP Server** - MySQL database integration
- **Playwright MCP** - Advanced browser automation (multi-engine)
- **Read Website Fast** - High-speed web content extraction
- **Homebrew Package Manager** - macOS system package management (no API key required)
- **SchemaCrawler Database Analysis** - Database schema discovery and analysis (details only)
- **SchemaFlow Database Schema** - Real-time PostgreSQL/Supabase schema access (details only)

### 🏢 [Company APIs](Company%20APIs/)
**External service integrations**
- **Context7** - Knowledge search and semantic retrieval
- **CoinGecko** - Cryptocurrency market data
- **AWS/Azure** - Cloud service integrations
- **Atlassian** - Jira and Confluence integration
- **Exa AI Search** - AI-powered web search and research
- **Facebook Ads MCP Server** - Facebook Marketing API integration
- **Facebook Ads Library MCP** - Public Facebook ads research (no API required)
- **Google Ads MCP Server** - Google Ads API for campaign management
- **Google News Search** - Google News intelligence via SerpAPI (requires API key)
- **Google Search Console MCP** - Search performance and SEO analytics (requires Google Cloud setup)
- **Hetzner MCP** - Hetzner Cloud infrastructure management
- **Lingo.dev Translation** - Translation and localization services
- **Mailgun Email Service** - Email automation and marketing
- **Make Automation** - Workflow automation and integration
- **Mapbox Geospatial** - Mapping and location intelligence
- **Notion MCP Server** - Notion API for knowledge management
- **OpenAI MCP Server** - OpenAI API integration for AI workflows
- **Perplexity Search** - Real-time web search and research
- **Perplexity MCP Server** - Direct Perplexity AI API integration (requires API key)
- **Rember Flashcards** - Spaced repetition learning platform
- **Scrapeless Web Automation** - Advanced web scraping and automation
- **Supabase Database** - Backend-as-a-service and database operations
- **Stripe Payments** - Payment processing and financial services

### 🗂️ [Project Management](Project%20Management/)
**Project coordination and task management**
- **Jina Reader MCP** - Advanced document reading and analysis
- **Jira Context MCP** - Comprehensive Jira integration with context
- **Jira MCP** - Lightweight Jira integration for basic operations

## Configuration Scopes

⚠️ **CRITICAL: Scope Selection for MCP Servers**

**Default scope is LOCAL** - servers will only work in the current folder unless you specify otherwise!

### User Scope (Global Access) - RECOMMENDED FOR MOST TOOLS
```bash
# ✅ CORRECT - Works everywhere on your computer
claude mcp add puppeteer --scope user -- node /path/to/puppeteer
claude mcp add context7 --scope user -- npx -y @upstash/context7-mcp
claude mcp add time --scope user -- python3 -m mcp_server_time
```
**Use for:** Utility servers you want everywhere (Puppeteer, Time, Context7, Playwright, etc.)

### Project Scope (Team Sharing)
```json
// .mcp.json (shared with team)
{
  "mcpServers": {
    "project-memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"],
      "env": { "MEMORY_FILE_PATH": ".claude/project-memory.json" }
    }
  }
}
```
**Use for:** Project-specific tools that should be shared with collaborators

### Local Scope (Folder-Specific) - USE SPARINGLY
```bash
# ❌ AVOID - Only works in current folder
claude mcp add local-tool -- npx some-package
```
**Use for:** Temporary tools specific to one project only

## Scope Selection Guide

**Rule of Thumb:**
- **User scope**: General utility tools (web automation, time, diagrams, etc.)
- **Project scope**: Memory systems and project-specific configurations
- **Local scope**: Rare - only for folder-specific temporary tools

**Common Mistake:** Adding utility servers without `--scope user` flag, which defaults to local scope and limits access to the current folder only.

## Memory Architecture

**Current Implementation:**
- **Project Memory**: Stores both project-specific patterns and general preferences in `.claude/project-memory.json`
- Single memory system per project for simplicity and reliability

**⚠️ Memory Scoping Limitations:**
Current MCP memory servers work best at project scope. While the concept of global vs project memory is appealing, practical implementation faces scoping challenges:
- Global memory servers don't inherit properly into project contexts
- Configuration format differences between global and project scopes
- MCP server discovery limitations across scope boundaries

**Future Considerations:**
If MCP memory scoping improves, we may revisit dual memory architecture. For now, project-level memory handles both general patterns and project-specific context effectively.

## Security Best Practices

- **API Keys**: Store in environment variables, never in config files
- **File Permissions**: Add `.claude/settings.local.json` to `.gitignore`
- **Least Privilege**: Use minimal required permissions for each server
- **Regular Audits**: Review server permissions and usage periodically

## Troubleshooting

**Server Not Connecting:**
1. Check installation: `npm list -g [package-name]` or `pip list | grep [package]`
2. Verify configuration syntax in settings files
3. Restart Claude Code after configuration changes
4. Check server logs for specific error messages

**Performance Issues:**
- Monitor server resource usage with `claude mcp list`
- Consider moving resource-intensive servers to project scope
- Clean up unused servers periodically

**Configuration Conflicts:**
- Project scope overrides global scope
- Local scope overrides both global and project
- Use specific server names to avoid conflicts

## Explore-Plan-Code Workflow

**Claude Code Best Practice:** Use the Explore-Plan-Code approach for complex tasks to improve quality and reduce revisions.

### What It Is
Instead of jumping straight into implementation, explicitly structure work into three phases:

1. **EXPLORE**: Read existing files, understand context, identify patterns
2. **PLAN**: Create a comprehensive implementation plan before coding
3. **CODE**: Execute the plan incrementally with clear documentation

### When To Use Explore-Plan-Code

**✅ Perfect For:**
- **Multi-file updates** - Changes affecting several related files
- **New feature development** - Adding significant functionality to existing systems
- **Workflow automation** - Building complex multi-step processes  
- **Integration projects** - Connecting different systems or APIs
- **Documentation restructuring** - Major organizational changes
- **System setup** - Configuring new tools or environments

**Example Scenarios:**
- Setting up a new MCP server with multiple configuration files
- Building automated workflows that span different tools
- Restructuring documentation across multiple projects
- Integrating new APIs with existing systems

### When NOT To Use It

**❌ Skip For:**
- **Simple edits** - Single file changes or minor updates
- **Quick fixes** - Obvious bugs or typos
- **Routine tasks** - Well-established patterns you've done many times
- **Exploratory work** - When you just want to understand something
- **Emergency fixes** - Time-sensitive problems requiring immediate action

### Implementation Example

**Instead of:**
> "Set up the newsletter automation with MCP integration"

**Use this structured approach:**
```
EXPLORE PHASE:
"First, help me explore the current newsletter workflow files, 
existing MCP configurations, and related documentation to 
understand the current state and patterns."

PLAN PHASE:
"Based on that exploration, create a detailed implementation 
plan for MCP integration including which servers to use, 
how to structure the workflow, and what files need updating."

CODE PHASE:
"Now implement the plan step by step, following the established 
patterns we identified."
```

### Benefits
- **Reduces revisions** - Better understanding before implementation
- **Maintains consistency** - Follows established patterns and conventions
- **Improves quality** - Thoughtful approach leads to better solutions
- **Saves time** - Less backtracking and rework
- **Better documentation** - Plan serves as implementation guide

### Integration with MCP Workflows
The Explore-Plan-Code approach works especially well with MCP server setup and automation workflows:

1. **Explore** existing MCP configurations and workflow patterns
2. **Plan** the integration points and server dependencies  
3. **Code** the MCP connections and automation logic

This structured approach is particularly valuable when working with multiple MCP servers that need to coordinate together.

## Current Rogue Codex Setup

**Active Servers:**
- ✅ **Global Memory** - Cross-project learning
- ✅ **Project Memory** - Rogue Codex-specific context
- ✅ **Time** - Timezone handling
- ✅ **Puppeteer** - Web automation
- ✅ **Context7** - Knowledge search

**Next Steps:**
- Explore individual server guides in subfolders
- Set up additional servers based on workflow needs
- Develop automation patterns for common documentation tasks
- Apply Explore-Plan-Code approach for complex integrations

---

*MCP transforms Claude Code from a helpful assistant into a powerful automation and integration platform. Start with the core servers and gradually build sophisticated workflows.*

---

*Last Updated: 2025-08-02*
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

### Global Scope (All Projects)
```bash
# Add to user config (~/.claude.json)
claude mcp add global-memory -- npx -y @modelcontextprotocol/server-memory
```
**Use for:** Utility servers used across ALL projects (Puppeteer, Time, Context7)

### Project Scope (This Project)
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
**Use for:** Project-specific tools and data

### Local Scope (Personal)
```json
// .claude/settings.local.json (private)
{
  "mcpServers": {
    "personal-tool": { "command": "...", "env": { "API_KEY": "secret" } }
  }
}
```
**Use for:** Personal preferences and sensitive API keys

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

---

*MCP transforms Claude Code from a helpful assistant into a powerful automation and integration platform. Start with the core servers and gradually build sophisticated workflows.*

---

*Last Updated: 2025-08-02*
# Perplexity MCP Server

**Repository:** https://github.com/tanigami/mcp-server-perplexity  
**Category:** Company APIs  
**Scope:** Local (recommended)  
**Type:** AI-Powered Search & Research  
**⚠️ Requires:** Perplexity API key (paid service)

Perplexity MCP Server provides integration with Perplexity AI's search capabilities, enabling Claude Code to perform AI-powered web search and research with real-time information access and intelligent summarization.

## Key Features

- **AI-Powered Search**: Intelligent web search with AI summarization
- **Real-Time Information**: Access to current web content and news
- **Source Citations**: Proper attribution and source tracking
- **Contextual Results**: Search results tailored to specific contexts
- **Multi-Query Support**: Handle complex research queries
- **Follow-Up Questions**: Iterative research and exploration

## Installation

### Local Installation (Recommended for API Keys)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "perplexity": {
      "command": "npx",
      "args": ["-y", "mcp-server-perplexity"],
      "env": {
        "PERPLEXITY_API_KEY": "${PERPLEXITY_API_KEY}"
      }
    }
  }
}
```

## Use Cases

### Research & Intelligence
- Real-time company news and updates for registry maintenance
- Industry trend research for content planning
- Competitive intelligence and market analysis
- Technology and tool research for evaluations

### Content Verification
- Fact-checking and information validation
- Source verification for documentation claims
- Current status updates for companies and tools
- Real-time pricing and feature information

### Market Analysis
- Industry trend monitoring and analysis
- Competitive landscape research
- Emerging technology identification
- Market opportunity assessment

## Typical Workflows

1. **Company Research**: "Find the latest news and updates about companies in our AI tools registry"
2. **Market Analysis**: "Research current trends in productivity automation tools"
3. **Fact Verification**: "Verify the current pricing and features of this tool"
4. **Industry Intelligence**: "What are the latest developments in the AI automation industry?"

## Configuration Requirements

Required environment variables:
- `PERPLEXITY_API_KEY`: Perplexity AI API key

Optional settings:
- Search result limits and filtering
- Source preference configuration
- Response format customization

## Security Considerations

- **API Key Security**: Store keys securely in environment variables
- **Rate Limiting**: Respect Perplexity's API rate limits
- **Data Privacy**: Be aware of search queries sent to Perplexity
- **Source Validation**: Verify information from search results
- **Usage Monitoring**: Track API usage and costs

## Advantages

**Perplexity MCP Server:**
- Real-time information access
- AI-powered summarization
- Proper source attribution
- Contextual search results
- Current and accurate data

**Compared to Existing Perplexity Search:**
- Direct API integration vs. web interface
- Programmatic access for automation
- Better integration with documentation workflows
- Consistent formatting and structure

## Search Capabilities

- **Current Events**: Real-time news and information
- **Academic Research**: Access to scholarly sources
- **Technical Documentation**: Developer and technical resources
- **Market Intelligence**: Business and industry information
- **Fact Checking**: Verification of claims and statements

## Related Tools

- **Existing Perplexity Search MCP**: May provide complementary functionality
- **Context7 MCP**: For knowledge base search and retrieval
- **Read Website Fast**: For follow-up content extraction

## Rogue Codex Applications

**Extremely High Value for:**
- Real-time updates for company information in the registry
- Current pricing and feature verification for tool evaluations
- Industry trend research for content planning and strategy
- Fact-checking and validation of documentation claims

**Research Applications:**
- Keep company profiles current with latest news and developments
- Verify tool features and pricing information for accuracy
- Research emerging trends for new content opportunities
- Gather competitive intelligence for industry analysis

**Recommended Priority**: Very High - Essential for maintaining current and accurate information across all documentation.

---

*Last Updated: 2025-08-02*
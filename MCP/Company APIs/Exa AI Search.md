# Exa AI Search MCP Server

**Repository:** https://github.com/exa-labs/exa-mcp-server  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** AI-Powered Web Search & Research  
**API Required:** Yes (Exa AI API Key)

The Exa MCP Server enables AI assistants like Claude to perform real-time web searches using the Exa AI Search API, providing a safe and controlled way for AI models to access current web information with AI-optimized search results.

## Key Features

- **AI-Optimized Web Search**: Real-time web searches with results tailored for AI consumption
- **Company Research**: Comprehensive business information gathering
- **Content Crawling**: Extract content from specific URLs
- **LinkedIn Search**: Search for companies and people on LinkedIn
- **Deep Research**: Advanced AI-powered research capabilities
- **Structured Results**: Search results formatted for AI understanding

## Installation

### Global Installation (Recommended)
```bash
# Install the package globally
npm install -g exa-mcp-server

# Add to global MCP configuration with API key
claude mcp add exa-search -- exa-mcp-server --api-key YOUR_EXA_API_KEY
```

### Remote Configuration
```json
// Alternative: Use hosted MCP server
{
  "mcpServers": {
    "exa-search": {
      "command": "curl",
      "args": [
        "-X", "POST",
        "https://mcp.exa.ai/mcp?exaApiKey=YOUR_EXA_API_KEY"
      ]
    }
  }
}
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "exa-search": {
      "command": "npx",
      "args": ["-y", "exa-mcp-server", "--api-key", "YOUR_EXA_API_KEY"],
      "env": {
        "EXA_API_KEY": "YOUR_EXA_API_KEY"
      }
    }
  }
}
```

## Setup Requirements

### 1. Get Exa API Key
1. Visit https://dashboard.exa.ai/api-keys
2. Sign up for an Exa AI account
3. Generate API key
4. Note usage limits and pricing

### 2. Configuration
Store API key securely:
```bash
# Environment variable (recommended)
export EXA_API_KEY="your-api-key-here"

# Or in local settings
```

## Available Tools

### web_search_exa
Real-time web searches optimized for AI consumption
```
Usage: "Search for latest developments in AI regulation"
```

### company_research
Comprehensive business information gathering
```
Usage: "Research OpenAI company information and recent news"
```

### crawling
Extract content from specific URLs
```
Usage: "Extract the main content from this article URL"
```

### linkedin_search
Search for companies and people on LinkedIn
```
Usage: "Find LinkedIn profiles for AI startup founders"
```

### deep_researcher_start/check
Advanced AI-powered research workflows
```
Usage: "Start deep research on quantum computing trends"
```

## Use Cases

### Real-Time Information
- Current events and breaking news
- Market data and financial updates
- Technology trend analysis
- Regulatory changes and updates

### Company Intelligence
- Competitive analysis
- Market positioning research
- Leadership and team information
- Recent funding and partnerships

### Content Research
- Academic paper discovery
- Industry report analysis
- Expert opinion gathering
- Trend identification

### Due Diligence
- Background research
- Verification of claims
- Source validation
- Comprehensive fact-checking

## Configuration Options

### Tool Selection
```bash
# Specify specific tools only
exa-mcp-server --tools web_search_exa,company_research
```

### Search Parameters
- Result count limits
- Content filtering
- Domain restrictions
- Recency filters

## Cost Analysis

*Pricing as of August 3rd, 2025*

### EXA API Pricing Structure
**Pay-as-You-Go Model:**
- **Free Tier**: $10 in credits (no credit card required)
- **Neural Search**: $5-25 per 1,000 requests (depending on result count)
- **Keyword Search**: $2.50 per 1,000 requests
- **Content Extraction**: $1 per 1,000 pages (text/highlights/summary each)
- **Answers Service**: $5 per 1,000 answers
- **Research Tasks**: $5-10 per task (depending on complexity)

### Monthly Cost Estimates for Rogue Codex Workflow
**Research Usage Pattern:**
- **Company research** (50 searches): ~$0.125-1.25
- **Tool research** (20 searches): ~$0.05-0.50
- **Content extraction** (100 pages): ~$0.30
- **Total Monthly Cost**: **~$0.48-2.05**

### Cost Comparison
**EXA vs Perplexity:**
- **EXA**: $0.48-2.05/month (significantly cheaper)
- **Perplexity**: $3.25-5.25/month
- **EXA Advantage**: 2-3x more cost-effective for your workflow

**Free Tier Strategy:**
- Start with $10 free credit to test effectiveness
- No credit card required for initial testing
- Enough credits for ~400-2,000 searches depending on type

### Pricing Considerations

- **API Costs**: Pay-per-use model with volume discounts available
- **Rate Limits**: Monitor usage to avoid exceeding limits
- **Plan Selection**: Choose appropriate tier based on usage volume
- **Enterprise Options**: Custom pricing for high-volume users

## Security Best Practices

- **API Key Storage**: Use environment variables, never commit keys
- **Rate Limiting**: Implement usage monitoring
- **Data Privacy**: Be mindful of sensitive search queries
- **Access Control**: Limit who can trigger searches

## Integration Examples

### Research Workflow
1. Use `company_research` for initial company overview
2. Follow with `web_search_exa` for recent developments
3. Use `crawling` to extract specific article content
4. Compile comprehensive research report

### Content Creation
1. Search for latest industry trends
2. Extract key insights from top sources
3. Verify information across multiple sources
4. Create data-driven content

## Related Tools

- **Context7**: For library and framework documentation
- **Browser-use MCP**: For manual web interaction when needed
- **Memory MCP**: For storing research findings

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key is valid and properly configured
- **Rate Limiting**: Check usage limits and consider upgrading plan
- **Search Quality**: Refine search queries for better results
- **Network Issues**: Ensure stable internet connection

---

*Last Updated: 2025-08-03*
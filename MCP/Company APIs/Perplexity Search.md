# Perplexity Search MCP Server

**Repository:** https://github.com/ppl-ai/modelcontextprotocol  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** Real-Time Web Search & Research  
**API Required:** Yes (Perplexity Sonar API Key)  
**License:** MIT

An MCP server that integrates the Perplexity Sonar API, enabling Claude to perform real-time web searches directly within its ecosystem with unparalleled research capabilities.

## Key Features

- **Live Web Search**: Real-time web search through Perplexity's Sonar API
- **Research Enhancement**: Extends Claude's knowledge with current web information
- **Configurable Parameters**: Customizable search settings and filters
- **Multiple Deployment**: Supports Docker and NPX deployment methods
- **Cross-Application**: Works with Claude Desktop and Cursor

## Installation

### Prerequisites
- Perplexity API key (Sonar API access)
- Node.js environment
- MCP-compatible client

### NPX Installation
```bash
# Install via NPX
npx -y @ppl-ai/mcp-server --api-key YOUR_SONAR_API_KEY
```

### Docker Installation
```bash
# Clone repository
git clone https://github.com/ppl-ai/modelcontextprotocol

# Build Docker image
docker build -t perplexity-mcp .

# Run with environment variables
docker run -e SONAR_API_KEY=your_key perplexity-mcp
```

### Configuration
```json
// claude_desktop_config.json
{
  "mcpServers": {
    "perplexity": {
      "command": "npx",
      "args": ["-y", "@ppl-ai/mcp-server"],
      "env": {
        "SONAR_API_KEY": "YOUR_SONAR_API_KEY"
      }
    }
  }
}
```

## Use Cases

### Real-Time Research
- Current events and breaking news
- Market analysis and trends
- Academic research assistance
- Fact-checking and verification

### Enhanced AI Capabilities
- Extending Claude's knowledge cutoff
- Providing current web context
- Supplementing training data with live information
- Dynamic knowledge retrieval

### Professional Research
- Industry analysis and reports
- Competitive intelligence gathering
- Technology trend monitoring
- Regulatory and compliance updates

### Content Creation
- Blog post research and fact-checking
- Social media content inspiration
- News article verification
- Academic paper references

## API Setup

### Getting Sonar API Key
1. Visit Perplexity's developer portal
2. Sign up for API access
3. Generate Sonar API key
4. Note rate limits and pricing

### Rate Limiting
- Monitor API usage to avoid limits
- Implement caching for repeated queries
- Consider API tier upgrades for high usage

## Configuration Options

### Search Parameters
- Query refinement settings
- Result count limits
- Source filtering options
- Recency preferences

### Security Settings
- API key encryption
- Access control configurations
- Usage monitoring setup

## Integration Benefits

### Compared to Static Knowledge
- **Current Information**: Access to latest web content
- **Dynamic Context**: Real-time data for decision making
- **Comprehensive Coverage**: Broader information sources
- **Fact Verification**: Cross-reference multiple sources

### AI Enhancement
- **Knowledge Extension**: Beyond training data cutoffs
- **Contextual Accuracy**: Current and relevant information
- **Research Depth**: Multi-source information synthesis
- **Real-Time Insights**: Live data for analysis

## Best Practices

### Query Optimization
- Use specific, focused search terms
- Leverage natural language queries
- Combine multiple search strategies
- Filter results by relevance and recency

### Usage Management
- Monitor API consumption
- Cache frequently accessed information
- Implement query optimization
- Balance thoroughness with efficiency

## Security Considerations

- **API Key Protection**: Store keys securely, never commit to repositories
- **Rate Limiting**: Respect API usage limits
- **Data Privacy**: Be mindful of sensitive search queries
- **Cost Management**: Monitor usage to control API costs

## Related Tools

- **Exa AI Search**: Alternative AI-powered search
- **Context7**: For library and framework documentation
- **Memory MCP**: Store search results and preferences
- **Browser-use MCP**: For direct web interaction when needed

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key validity and permissions
- **Rate Limiting**: Check usage limits and consider upgrading
- **Search Quality**: Refine queries for better results
- **Configuration**: Ensure proper MCP client setup

---

*Last Updated: 2025-08-02*
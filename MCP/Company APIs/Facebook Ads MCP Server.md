# Facebook Ads MCP Server

**Repository:** https://github.com/gomarble-ai/facebook-ads-mcp-server  
**Category:** Company APIs  
**Scope:** Local (recommended)  
**Type:** Marketing & Advertising Platform

Facebook Ads MCP Server enables Claude Code to interact with Facebook's Marketing API for campaign management, audience insights, and advertising analytics within automation workflows.

## Key Features

- **Campaign Management**: Create, update, and monitor Facebook ad campaigns
- **Audience Analytics**: Access demographic and behavioral insights
- **Performance Metrics**: Retrieve detailed campaign performance data
- **Ad Creative Management**: Manage ad content and creative assets
- **Budget Control**: Monitor and adjust campaign budgets
- **Targeting Options**: Configure audience targeting and optimization

## Installation

### Local Installation (Recommended for API Keys)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "facebook-ads": {
      "command": "npx",
      "args": ["-y", "facebook-ads-mcp-server"],
      "env": {
        "FACEBOOK_ACCESS_TOKEN": "${FACEBOOK_ACCESS_TOKEN}",
        "FACEBOOK_APP_ID": "${FACEBOOK_APP_ID}",
        "FACEBOOK_APP_SECRET": "${FACEBOOK_APP_SECRET}",
        "FACEBOOK_AD_ACCOUNT_ID": "${FACEBOOK_AD_ACCOUNT_ID}"
      }
    }
  }
}
```

### Project Installation (Non-sensitive Config)
```json
// .mcp.json
{
  "mcpServers": {
    "facebook-ads": {
      "command": "npx",
      "args": ["-y", "facebook-ads-mcp-server"],
      "env": {
        "FACEBOOK_API_VERSION": "v18.0"
      }
    }
  }
}
```

## Use Cases

### Marketing Analysis
- Competitor ad research and analysis
- Industry advertising trend monitoring
- Creative strategy insights
- Audience behavior analysis

### Campaign Research
- Ad performance benchmarking
- Market research through ad insights
- Industry-specific advertising patterns
- Creative and messaging analysis

### Business Intelligence
- Market size estimation through ad reach data
- Competitor spending analysis
- Industry trend identification
- Audience segmentation insights

## Typical Workflows

1. **Competitor Analysis**: "Analyze the advertising strategy of companies in our registry"
2. **Market Research**: "What are the trending ad formats in the AI tools industry?"
3. **Audience Insights**: "Get demographic data for the target audience of productivity tools"
4. **Performance Benchmarking**: "Compare ad performance metrics across industry competitors"

## Configuration Requirements

Required environment variables:
- `FACEBOOK_ACCESS_TOKEN`: Facebook Marketing API access token
- `FACEBOOK_APP_ID`: Facebook application ID
- `FACEBOOK_APP_SECRET`: Facebook application secret
- `FACEBOOK_AD_ACCOUNT_ID`: Target ad account ID

Optional settings:
- `FACEBOOK_API_VERSION`: API version (default: latest)
- Rate limiting configurations
- Request timeout settings

## Security Considerations

- **Token Security**: Store access tokens securely in environment variables
- **Permission Management**: Use minimal required API permissions
- **Rate Limiting**: Respect Facebook's API rate limits
- **Data Privacy**: Comply with data usage policies and regulations
- **Access Logs**: Monitor API usage for security auditing

## API Limitations

- **Rate Limits**: Facebook enforces strict API rate limiting
- **Data Access**: Limited to authorized ad accounts and pages
- **Permission Requirements**: Requires appropriate app permissions
- **Compliance**: Must follow Facebook's advertising policies

## Related Tools

- **Facebook Ads Library MCP**: Alternative Facebook ads research tool
- **Google Ads MCP**: Comparative advertising platform analysis
- **Perplexity Search**: Complementary market research capabilities

## Rogue Codex Applications

**Medium Value for:**
- Company advertising strategy research for registry entries
- Market analysis for tools and services
- Understanding target audiences for different software categories
- Competitive intelligence for business analysis

**Best Use Cases:**
- Research-focused teams analyzing market trends
- Business analysts studying competitor strategies
- Marketing teams understanding industry advertising patterns
- Companies needing competitive intelligence

**Considerations:**
- Requires Facebook Business account and API approval
- Subject to strict rate limiting and usage policies
- Primarily valuable for marketing and business analysis use cases
- May be overkill for basic documentation needs

---

*Last Updated: 2025-08-02*
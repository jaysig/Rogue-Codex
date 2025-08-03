# Google Ads MCP Server

**Repository:** https://github.com/gomarble-ai/google-ads-mcp-server  
**Category:** Company APIs  
**Scope:** Local (recommended)  
**Type:** Marketing & Advertising Platform

Google Ads MCP Server enables Claude Code to interact with Google Ads API for campaign management, keyword research, and advertising analytics within automation workflows.

## Key Features

- **Campaign Management**: Create, update, and monitor Google Ads campaigns
- **Keyword Research**: Access keyword planning and search volume data
- **Performance Analytics**: Retrieve detailed campaign and ad group metrics
- **Audience Insights**: Analyze audience demographics and behavior
- **Budget Management**: Monitor and optimize advertising spend
- **Competitive Intelligence**: Access auction insights and competitor data

## Installation

### Local Installation (Recommended for API Keys)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "google-ads": {
      "command": "npx",
      "args": ["-y", "google-ads-mcp-server"],
      "env": {
        "GOOGLE_ADS_CUSTOMER_ID": "${GOOGLE_ADS_CUSTOMER_ID}",
        "GOOGLE_ADS_DEVELOPER_TOKEN": "${GOOGLE_ADS_DEVELOPER_TOKEN}",
        "GOOGLE_ADS_CLIENT_ID": "${GOOGLE_ADS_CLIENT_ID}",
        "GOOGLE_ADS_CLIENT_SECRET": "${GOOGLE_ADS_CLIENT_SECRET}",
        "GOOGLE_ADS_REFRESH_TOKEN": "${GOOGLE_ADS_REFRESH_TOKEN}"
      }
    }
  }
}
```

## Use Cases

### Market Research
- Keyword search volume analysis for industry terms
- Competitor advertising spend and strategy research
- Market size estimation through search data
- Industry trend identification through search patterns

### Content Strategy
- SEO keyword research for documentation optimization
- Content gap analysis through search volume data
- Industry terminology and language research
- Market demand validation for new content areas

### Competitive Analysis
- Competitor advertising strategies and spend patterns
- Market positioning through ad copy analysis
- Industry bidding patterns and competition levels
- Audience targeting strategies research

## Typical Workflows

1. **Keyword Research**: "Find high-volume keywords related to AI automation tools"
2. **Market Analysis**: "Analyze search trends for productivity software categories"
3. **Competitor Research**: "Research advertising strategies of companies in our registry"
4. **Content Planning**: "Identify content opportunities based on search volume data"

## Configuration Requirements

Required environment variables:
- `GOOGLE_ADS_CUSTOMER_ID`: Google Ads customer account ID
- `GOOGLE_ADS_DEVELOPER_TOKEN`: Developer token for API access
- `GOOGLE_ADS_CLIENT_ID`: OAuth client ID
- `GOOGLE_ADS_CLIENT_SECRET`: OAuth client secret
- `GOOGLE_ADS_REFRESH_TOKEN`: OAuth refresh token

## Security Considerations

- **API Token Security**: Store all credentials in environment variables
- **OAuth Management**: Secure refresh token handling
- **Permission Scope**: Use minimal required API permissions
- **Rate Limiting**: Respect Google Ads API quotas and limits
- **Audit Logging**: Monitor API usage and access patterns

## API Capabilities

- **Keyword Planner**: Search volume and competition data
- **Campaign Reports**: Performance metrics and analytics
- **Auction Insights**: Competitor analysis and market data
- **Audience Research**: Demographic and interest data
- **Geographic Data**: Location-based search and performance insights

## Related Tools

- **Facebook Ads MCP**: Comparative platform advertising analysis
- **Google Search Console MCP**: Complementary search performance data
- **SEO MCP Server**: Integration with SEO analysis workflows

## Rogue Codex Applications

**High Value for:**
- Keyword research for content optimization and SEO
- Market demand analysis for new content areas
- Competitive intelligence for company and tool analysis
- Industry trend identification through search data

**Research Applications:**
- Validate content topics through search volume data
- Understand market demand for different tool categories
- Research competitor positioning and messaging
- Identify emerging trends in AI and automation sectors

**Recommended Priority**: Medium-High - Excellent for SEO-focused content optimization and market research.

---

*Last Updated: 2025-08-02*
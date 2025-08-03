# Google Search Console MCP

**Repository:** https://github.com/ahonn/mcp-server-gsc  
**Category:** Company APIs  
**Scope:** Local (recommended)  
**Type:** SEO & Search Analytics  
**⚠️ Requires:** Google Cloud API setup and service account credentials

Google Search Console MCP enables Claude Code to access search performance data, indexing status, and SEO insights from Google Search Console for website optimization and analytics.

## Key Features

- **Search Performance**: Access search queries, impressions, clicks, and CTR data
- **Indexing Status**: Monitor page indexing and crawl errors
- **Core Web Vitals**: Retrieve page experience and performance metrics
- **Search Appearance**: Analyze rich results and search features
- **URL Inspection**: Check individual page indexing and performance
- **Sitemap Management**: Monitor sitemap submission and processing status

## Installation

### Local Installation (Recommended for API Keys)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "google-search-console": {
      "command": "npx",
      "args": ["-y", "mcp-server-gsc"],
      "env": {
        "GOOGLE_CLIENT_ID": "${GOOGLE_CLIENT_ID}",
        "GOOGLE_CLIENT_SECRET": "${GOOGLE_CLIENT_SECRET}",
        "GOOGLE_REFRESH_TOKEN": "${GOOGLE_REFRESH_TOKEN}",
        "GSC_SITE_URL": "${GSC_SITE_URL}"
      }
    }
  }
}
```

## Use Cases

### SEO Optimization
- Monitor search performance for Rogue Codex content
- Identify top-performing keywords and pages
- Track indexing status and fix crawl errors
- Optimize content based on search query data

### Content Strategy
- Discover high-performing search queries
- Identify content gaps through search data
- Monitor content performance trends
- Optimize existing content for better search visibility

### Technical SEO
- Track Core Web Vitals and page experience
- Monitor indexing status and coverage issues
- Analyze mobile usability and performance
- Check rich results and search features

## Typical Workflows

1. **Performance Analysis**: "Show me the top-performing search queries for our AI tools content"
2. **Indexing Check**: "Check the indexing status of recently published company profiles"
3. **Content Optimization**: "Identify underperforming pages that need optimization"
4. **SEO Monitoring**: "Track search performance trends for our automation guides"

## Configuration Requirements

Required environment variables:
- `GOOGLE_CLIENT_ID`: OAuth client ID for Google API access
- `GOOGLE_CLIENT_SECRET`: OAuth client secret
- `GOOGLE_REFRESH_TOKEN`: OAuth refresh token
- `GSC_SITE_URL`: Target website URL (e.g., https://roguecodex.com)

## Security Considerations

- **OAuth Token Security**: Store credentials securely in environment variables
- **Site Access**: Ensure proper Search Console property verification
- **Permission Management**: Use minimal required API scopes
- **Data Privacy**: Handle search data according to privacy policies

## Data Insights

- **Search Queries**: Understand what users search for to find your content
- **Page Performance**: Identify top and underperforming pages
- **Geographic Data**: Analyze search performance by country/region
- **Device Data**: Compare performance across mobile, desktop, and tablet
- **Temporal Trends**: Track performance changes over time

## Related Tools

- **Google Ads MCP**: Complementary keyword and market research
- **SEO MCP Server**: Enhanced SEO analysis and optimization
- **Perplexity Search**: Competitive search research

## Rogue Codex Applications

**Extremely High Value for:**
- Monitoring search performance of published content
- Identifying successful content topics and formats
- Optimizing content based on actual search queries
- Tracking indexing and technical SEO health

**Optimization Applications:**
- Identify which company profiles and tool reviews perform best in search
- Discover new content opportunities through search query data
- Monitor the impact of content updates on search performance
- Track seasonal trends in different content categories

**Recommended Priority**: Very High - Essential for data-driven content optimization and SEO success.

---

*Last Updated: 2025-08-02*
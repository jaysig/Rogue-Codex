# SEO MCP Server

**Repository:** https://github.com/cnych/seo-mcp  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** SEO Analysis & Optimization

The SEO MCP Server is designed for SEO optimization scenarios, allowing AI to automatically analyze website structures, keyword distribution, backlinks, and more to help webmasters and marketers improve search rankings.

## Key Features

- **Site Crawling**: Comprehensive website structure analysis
- **Keyword Analysis**: Distribution and density evaluation
- **Backlink Monitoring**: Link profile assessment and tracking
- **SEO Audit Reports**: Automated optimization recommendations
- **Competitor Analysis**: Comparative SEO performance insights

## Installation

### Global Installation (Recommended)
```bash
# Install the package
npm install -g seo-mcp

# Add to global MCP configuration
claude mcp add seo-server -- seo-mcp
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "seo-server": {
      "command": "npx",
      "args": ["-y", "seo-mcp"]
    }
  }
}
```

## Use Cases

### Website SEO Audits
- Comprehensive site structure analysis
- Technical SEO issue identification
- Performance bottleneck detection
- Mobile-friendliness assessment

### Content Optimization
- Keyword density analysis
- Content gap identification
- Meta tag optimization
- Internal linking suggestions

### Competitor Analysis
- Comparative keyword performance
- Backlink profile comparison
- Content strategy insights
- Market positioning analysis

## Typical Workflows

1. **Site Audit**: "Analyze the SEO health of example.com"
2. **Keyword Research**: "Find keyword opportunities for [topic]"
3. **Competitor Analysis**: "Compare SEO metrics between our site and competitor.com"
4. **Content Optimization**: "Optimize this page content for [target keywords]"

## Configuration

The server may require additional configuration for:
- API rate limiting
- Crawl depth settings
- Specific SEO tools integration
- Custom reporting parameters

## Security Considerations

- Be mindful of crawling rate limits
- Respect robots.txt files
- Consider API usage costs for external SEO tools
- Avoid crawling sites without permission

## Related Tools

- **Browser-use MCP**: For automated web interactions
- **Puppeteer MCP**: For screenshot-based SEO analysis
- **Make MCP**: For SEO workflow automation

---

*Last Updated: 2025-08-02*
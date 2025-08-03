# SEO MCP Server

**Category:** Development  
**Scope:** Global (recommended)  
**Type:** SEO Analysis & Optimization

SEO MCP servers enable AI to automatically analyze website structures, keyword distribution, backlinks, and more to help webmasters and marketers improve search rankings.

## Available SEO MCP Servers

### ⚠️ Original SEO MCP (Limited Availability)
**Repository:** https://github.com/cnych/seo-mcp  
**Status:** Repository exists but not available via npm
**Installation:** May require `pip install` and manual setup
**Cost:** Free (if functional)

### ✅ FetchSERP MCP Server (Recommended)
**Package:** `fetchserp-mcp-server`  
**Status:** Fully functional and well-maintained
**API Required:** Yes - FetchSERP API key needed
**Repository:** Available on npm

## Key Features

- **Site Crawling**: Comprehensive website structure analysis
- **Keyword Analysis**: Distribution and density evaluation  
- **Backlink Monitoring**: Link profile assessment and tracking
- **SEO Audit Reports**: Automated optimization recommendations
- **Competitor Analysis**: Comparative SEO performance insights
- **SERP Data**: Search engine results page analysis
- **Domain Analytics**: Domain authority and performance metrics

## Installation Options

### Option 1: FetchSERP MCP Server (Recommended)
```bash
# Install the package
npm install -g fetchserp-mcp-server

# Add to global MCP configuration
claude mcp add fetchserp --scope user -- npx -y fetchserp-mcp-server
```

**API Setup Required:**
1. Sign up at [FetchSERP.com](https://www.fetchserp.com)
2. Get API key (starts with 250 free credits)
3. Configure API key in environment variables

### Option 2: Original SEO MCP (Experimental)
```bash
# May require Python/pip installation
# Repository: https://github.com/cnych/seo-mcp
# Status: Availability not confirmed
```

## Cost Analysis for FetchSERP MCP

*Pricing as of August 3rd, 2025*

### Understanding API Credits
- **250 free credits** provided on signup
- Each API call (SERP query, keyword lookup, backlink check) consumes credits
- Pricing structure not publicly disclosed on main site

### Example Cost Estimate: Analyzing a Website
Let's estimate costs for analyzing a typical documentation site (like this repository's published site):

**Initial SEO Audit:**
- Site crawl and structure analysis: ~50-100 credits
- Keyword analysis for main pages: ~25-50 credits  
- Backlink profile check: ~20-40 credits
- Competitor analysis (3 competitors): ~30-60 credits
- **Total Initial Cost:** ~125-250 credits (could use entire free tier)

**Ongoing Monthly Monitoring:**
- Weekly SERP position tracking: ~40 credits/month
- Monthly backlink updates: ~20 credits/month
- Content optimization checks: ~30 credits/month
- **Total Monthly Cost:** ~90 credits/month

### Cost Planning Recommendations
1. **Start with free tier** to understand actual usage patterns
2. **Monitor credit consumption** during first audit to gauge ongoing needs
3. **Consider batching queries** to optimize credit usage
4. **Focus on high-impact pages** rather than entire site for ongoing monitoring

**Note:** Contact FetchSERP sales for detailed pricing tiers and volume discounts. Free tier may be sufficient for occasional SEO analysis of smaller sites.

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

*Last Updated: 2025-08-03*
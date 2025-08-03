# Google News Search MCP Server

**Repository:** https://github.com/ChanMeng666/server-google-news  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** News Intelligence & Research  
**API Required:** Yes (SerpAPI Key)  
**License:** MIT

A Model Context Protocol server that provides Google News search capabilities through SerpAPI integration, offering flexible and intelligent news retrieval with automatic categorization and multi-language support.

## Key Features

- **Comprehensive Search Options**: Search across topics, publications, and stories
- **Multi-Language Support**: International news coverage with automatic language fallback
- **Intelligent Categorization**: Automatic categorization (AI, Business, Science, Healthcare)
- **Flexible Parameters**: Date ranges, regions, publication filters
- **Robust Error Handling**: Graceful handling of API failures and rate limits

## Installation

### Prerequisites
- Node.js environment
- SerpAPI account and API key

### API Setup Requirements
```
🔑 API KEY REQUIRED: SerpAPI Key
```

**Get SerpAPI Key:**
1. Visit https://serpapi.com and create account
2. Navigate to API Key section
3. Copy your API key

**Usage Limits:**
- **Free Tier**: 250 searches per month
- **Paid Plans**: Starting at $50/month for 5,000 searches
- **Rate Limiting**: 1 request per second on free tier

### Global Installation (Recommended)
```bash
# Install the package
npm install -g @chanmeng666/server-google-news

# Add to global MCP configuration
claude mcp add google-news -- npx -y @chanmeng666/server-google-news --api-key YOUR_SERPAPI_KEY
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "google-news": {
      "command": "npx",
      "args": ["-y", "@chanmeng666/server-google-news"],
      "env": {
        "SERPAPI_API_KEY": "YOUR_SERPAPI_KEY"
      }
    }
  }
}
```

## Available Tools

### News Search
- **Topic Search**: Find news by keywords and topics
- **Publication Search**: Search specific news sources
- **Story Search**: Find related articles and follow-up stories
- **Trending Topics**: Discover what's currently trending

### Search Parameters
- **Date Ranges**: Filter by publication date
- **Geographic Regions**: Country and region-specific news
- **Language Filtering**: Multi-language news retrieval
- **Source Filtering**: Specific publication or source types

## Use Cases

### Company Intelligence
- **Company News Monitoring**: Track mentions and developments
- **Competitor Analysis**: Monitor competitor news and announcements
- **Industry Trends**: Stay current with sector developments
- **Crisis Management**: Rapid response to negative news coverage

### Content Research
- **Article Research**: Find supporting information and sources
- **Trend Analysis**: Identify emerging topics and patterns
- **Market Intelligence**: Track market-moving news and events
- **Regulatory Updates**: Monitor policy and regulatory changes

### Automation Workflows
- **Daily Briefings**: Automated news summaries for specific topics
- **Alert Systems**: Notification when specific companies or topics appear
- **Content Creation**: News-based content generation and curation
- **Research Reports**: Automated compilation of recent developments

## Integration Examples

### Company Spotlight Updates
```
User: "Find recent AI news for OpenAI"
AI: Searches Google News for OpenAI AI developments
Result: Latest funding, product launches, and strategic announcements
```

### Industry Intelligence
```
User: "What's trending in fintech this week?"
AI: Retrieves recent fintech news with automatic categorization
Result: Comprehensive industry update with key developments
```

## Configuration Options

### Search Customization
- **Result Count**: Control number of articles returned
- **Freshness**: Prioritize recent vs. comprehensive results
- **Source Quality**: Filter by publication authority and credibility
- **Content Type**: News articles, press releases, opinion pieces

### API Management
- **Rate Limiting**: Built-in respect for SerpAPI limits
- **Error Handling**: Automatic retries and fallback strategies
- **Caching**: Optional result caching to conserve API calls
- **Usage Monitoring**: Track API consumption and costs

## Cost Management

### Free Tier Strategy
- **250 searches/month**: Plan searches strategically
- **Batch Queries**: Combine related searches when possible
- **Cache Results**: Store frequently accessed information
- **Monitor Usage**: Track API calls to avoid overages

### Scaling Options
- **Paid Plans**: $50-200+/month for higher volumes
- **Team Plans**: Multi-user access and management
- **Enterprise**: Custom pricing for large-scale usage

## Security Considerations

- **API Key Protection**: Store keys in environment variables only
- **Rate Limiting**: Respect SerpAPI usage policies
- **Data Privacy**: Be mindful of news content usage rights
- **Cost Control**: Monitor API usage to prevent unexpected charges

## Related Tools

- **Perplexity Search**: For AI-powered news analysis
- **Exa AI Search**: For broader web search capabilities
- **Browser-use MCP**: For direct news site interaction
- **Memory MCP**: Store important news findings and trends

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify SerpAPI key validity and account status
- **Rate Limiting**: Check usage limits and consider upgrading plan
- **Search Quality**: Refine search terms for better results
- **Regional Results**: Adjust geographic parameters for local news

**Best Practices:**
- Use specific, focused search terms for better results
- Combine with other research tools for comprehensive analysis
- Monitor API usage to manage costs effectively
- Cache important results to reduce redundant searches

---

*Last Updated: 2025-08-02*
# Jina Reader MCP

**Repository:** https://github.com/wong2/mcp-jina-reader  
**Category:** Project Management  
**Scope:** Global (recommended)  
**Type:** Document Reading & Analysis

Jina Reader MCP provides advanced document reading and content extraction capabilities, leveraging Jina AI's reader technology for clean, structured content processing from various sources.

## Key Features

- **Universal Reader**: Process documents, web pages, and structured content
- **Clean Extraction**: Remove ads, navigation, and unnecessary elements
- **Multiple Formats**: Support for HTML, PDF, markdown, and text files
- **API Integration**: Leverage Jina AI's reading infrastructure
- **Structured Output**: Consistent formatting and content organization
- **Batch Processing**: Handle multiple documents simultaneously

## Installation

### Global Installation (Recommended)
```bash
# Install the package
npm install -g mcp-jina-reader

# Add to global MCP configuration
claude mcp add jina-reader -- mcp-jina-reader
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "jina-reader": {
      "command": "npx",
      "args": ["-y", "mcp-jina-reader"],
      "env": {
        "JINA_API_KEY": "${JINA_API_KEY}"
      }
    }
  }
}
```

## Use Cases

### Research & Documentation
- Academic paper and report analysis
- Technical documentation processing
- Web content extraction and summarization
- Multi-format document integration

### Content Processing
- Blog post and article analysis
- News monitoring and summarization
- Knowledge base content extraction
- Reference material compilation

### Project Management
- Requirements document analysis
- Specification processing and review
- Documentation quality assessment
- Content organization and structuring

## Typical Workflows

1. **Document Analysis**: "Extract key insights from this project specification"
2. **Content Summarization**: "Summarize the main points from these research papers"
3. **Multi-Source Research**: "Process and organize content from these various documents"
4. **Documentation Review**: "Analyze the structure and completeness of this documentation"

## API Configuration

Required environment variables:
- `JINA_API_KEY`: Your Jina AI API key for reader service access

Optional settings:
- Request timeout and retry configuration
- Output format preferences
- Content filtering rules

## Security Considerations

- Secure API key storage in environment variables
- Respect document access permissions and copyright
- Validate input sources before processing
- Monitor API usage and rate limits

## Performance Features

- Efficient content extraction algorithms
- Scalable processing for large documents
- Optimized for structured content output
- Minimal preprocessing requirements

## Related Tools

- **Read Website Fast**: For lightweight web content extraction
- **Playwright MCP**: For complex document interaction
- **Jira Context MCP**: For project-specific document integration

## Rogue Codex Applications

**High Value for:**
- Processing external research documents for content creation
- Extracting insights from industry reports and whitepapers
- Standardizing document formatting across different sources
- Content quality analysis and improvement recommendations

**Integration Opportunities:**
- Combine with Company Spotlight for processing company reports
- Use with Tools section for documentation analysis
- Support AI Automations content research workflows

**Recommended Priority**: Medium - Valuable for research-heavy documentation workflows.

---

*Last Updated: 2025-08-02*
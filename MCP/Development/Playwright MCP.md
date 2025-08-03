# Playwright MCP

**Repository:** https://github.com/executeautomation/mcp-playwright  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** Browser Automation & Testing

Playwright MCP provides advanced browser automation capabilities, enabling Claude Code to interact with web pages, perform testing, and automate web-based workflows with multiple browser engines.

## Key Features

- **Multi-Browser Support**: Chrome, Firefox, Safari, and Edge automation
- **Cross-Platform**: Windows, macOS, and Linux compatibility
- **Mobile Testing**: Mobile browser simulation and testing
- **Screenshot Capture**: Full page and element-specific screenshots
- **Performance Monitoring**: Page load times and resource analysis
- **Interaction Automation**: Click, type, scroll, and form submission

## Installation

### Global Installation (Recommended)
```bash
# Install the package
npm install -g mcp-playwright

# Install browser engines
npx playwright install

# Add to global MCP configuration
claude mcp add playwright-server -- mcp-playwright
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "playwright-server": {
      "command": "npx",
      "args": ["-y", "mcp-playwright"]
    }
  }
}
```

## Use Cases

### Content Research & Verification
- Company website analysis and data extraction
- Tool feature verification and documentation
- Competitive analysis and benchmarking
- Link validation and content auditing

### Automation & Testing
- Form submission and workflow testing
- User experience validation
- Performance monitoring and optimization
- Cross-browser compatibility testing

### Data Collection
- Website screenshot generation for documentation
- Dynamic content scraping and analysis
- Social media content monitoring
- Real-time data gathering for research

## Typical Workflows

1. **Company Research**: "Take screenshots of the top 5 AI companies' homepages"
2. **Tool Verification**: "Test the signup flow for this productivity tool"
3. **Content Validation**: "Check if all links in our documentation are working"
4. **Competitive Analysis**: "Compare the feature pages of these three tools"

## Browser Engine Options

- **Chromium**: Fast, widely compatible, good for general automation
- **Firefox**: Alternative rendering engine, good for cross-browser testing
- **WebKit**: Safari engine, essential for Apple ecosystem testing
- **Chrome**: Full Chrome browser with extensions support

## Configuration

The server may support configuration for:
- Default browser engine selection
- Viewport size and device simulation
- Screenshot quality and format
- Timeout and retry settings
- Proxy and network configuration

## Security Considerations

- Be respectful of website rate limits and robots.txt
- Avoid automated interactions that violate terms of service
- Use headless mode for better performance and security
- Implement proper error handling for failed requests

## Performance Optimization

- Use headless mode when screenshots aren't needed
- Implement request filtering to reduce resource usage
- Cache browser instances for repeated operations
- Set appropriate timeouts for different operation types

## Related Tools

- **Puppeteer MCP**: Alternative browser automation (Chrome-focused)
- **Read Website Fast**: For content extraction without interaction
- **SEO MCP**: For technical website analysis

## Rogue Codex Applications

**Extremely High Value for:**
- Company website screenshot generation for registry entries
- Tool interface documentation and verification
- Automated link checking across all documentation
- Research automation for content gathering
- Competitive analysis for tools and companies

**Advantages over Puppeteer:**
- Multi-browser testing capabilities
- Better mobile simulation
- More robust for cross-platform testing
- Enhanced performance monitoring

**Recommended Priority**: High - Superior alternative to Puppeteer for comprehensive web automation needs.

---

*Last Updated: 2025-08-02*
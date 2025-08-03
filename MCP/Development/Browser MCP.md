# Browser MCP

**Repository:** https://github.com/browsermcp/mcp  
**Website:** https://browsermcp.io  
**Documentation:** https://docs.browsermcp.io  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** Browser Automation & Local Control  
**License:** Apache-2.0  
**Status:** Early Development (No releases yet)

Browser MCP is an MCP server + Chrome extension that allows you to automate your browser using AI applications like VS Code, Claude, Cursor, and Windsurf with local execution and privacy-focused design.

## Key Features

- **⚡ Local Automation**: No network latency, all operations execute locally
- **🔒 Privacy-Focused**: Browser activity stays on your device
- **👤 Profile Integration**: Uses existing browser profile and logged-in sessions
- **🥷🏼 Anti-Detection**: Uses real browser fingerprint to avoid bot detection
- **🔧 Real Browser Control**: Direct control of actual browser instance

## Technical Foundation

- **Base Technology**: Adapted from Microsoft's Playwright MCP server
- **Primary Language**: TypeScript (89.2%)
- **Architecture**: MCP server + Chrome extension combination
- **Browser Integration**: Works with actual user browser, not headless instances

## Installation

### Prerequisites
- Chrome browser with extension support
- Node.js environment
- MCP-compatible client (VS Code, Claude, Cursor, Windsurf)

### Current Status
```
⚠️ Early Development Stage
- No published releases yet
- Requires additional dependencies from monorepo
- Documentation and setup in progress
```

### Expected Installation (When Released)
```bash
# Install MCP server component
npm install -g browser-mcp

# Install Chrome extension from store
# Configure MCP client integration
```

## Use Cases

### Development Automation
- **Testing Workflows**: Automate web application testing
- **Form Filling**: Automate repetitive form submissions
- **UI Interaction**: Test user interface elements
- **Screenshot Collection**: Capture visual states for documentation

### Productivity Enhancement
- **Research Automation**: Automate information gathering
- **Data Entry**: Fill forms across multiple sites
- **Monitoring**: Track changes on web pages
- **Workflow Automation**: Streamline repetitive browser tasks

### AI-Enhanced Browsing
- **Intelligent Navigation**: AI-guided web browsing
- **Content Analysis**: AI analysis of web page content
- **Task Completion**: Complex multi-step web tasks
- **Data Extraction**: Intelligent content extraction

## Advantages Over Headless Solutions

### Session Persistence
- **Logged-in State**: Maintains existing login sessions
- **Cookies and Storage**: Preserves browser state and preferences
- **Extensions**: Works with installed browser extensions
- **Bookmarks**: Access to user bookmarks and history

### Anti-Detection Benefits
- **Real Fingerprint**: Uses actual browser's fingerprint
- **Human Patterns**: Natural interaction patterns
- **Extension Environment**: Behaves like real user interaction
- **No Headless Markers**: Avoids headless browser detection

### Performance Advantages
- **Local Execution**: No network round trips for commands
- **Resource Sharing**: Uses existing browser instance
- **Extension APIs**: Access to full Chrome extension capabilities
- **Real-Time Response**: Immediate command execution

## Technical Architecture

### Components
- **MCP Server**: Handles AI communication and command processing
- **Chrome Extension**: Provides browser control interface
- **Communication Layer**: Secure local communication between components
- **Command Processor**: Translates AI requests to browser actions

### Security Model
- **Local-Only**: All operations remain on user's machine
- **Permission Model**: Extension-based permission system
- **Data Privacy**: No external data transmission
- **User Control**: Full user control over automation actions

## Integration Support

### AI Development Environments
- **VS Code**: Development environment integration
- **Claude**: AI assistant browser control
- **Cursor**: AI-powered code editor integration
- **Windsurf**: Additional development tool support

### Future Integrations
- **Custom AI Agents**: API for custom automation agents
- **Workflow Tools**: Integration with automation platforms
- **Testing Frameworks**: Enhanced testing tool integration

## Development Status

### Current State
- **Alpha Development**: Core functionality being built
- **No Public Releases**: Still in development phase
- **Documentation WIP**: Setup guides and API docs in progress
- **Community Building**: Early community and contributor engagement

### Planned Features
- **Enhanced Automation**: More sophisticated browser control
- **Visual Recognition**: AI-powered element identification
- **Workflow Recording**: Record and replay automation sequences
- **Plugin System**: Extensible automation capabilities

## Related Tools

- **Puppeteer MCP**: Alternative headless browser automation
- **Browser-use MCP**: Alternative browser automation approach
- **SEO MCP**: For SEO-focused browser analysis
- **Scrapeless MCP**: For advanced web scraping needs

## Monitoring Development

### Stay Updated
- **GitHub Repository**: Watch for updates and releases
- **Website**: Check browsermcp.io for announcements
- **Documentation**: Follow docs.browsermcp.io for setup guides
- **Community**: Join discussions and contribute feedback

### Contributing
- **Open Source**: Apache-2.0 license allows contributions
- **Early Feedback**: Provide input during development phase
- **Testing**: Help test early releases when available
- **Documentation**: Contribute to setup and usage guides

---

*Last Updated: 2025-08-02*
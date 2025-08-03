# Lingo.dev Translation MCP Server

**Repository:** https://github.com/lingodotdev/lingo.dev/blob/main/mcp.md  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** Translation & Localization  
**API Required:** Yes (Lingo.dev API Key)

The Lingo.dev MCP Server provides translation capabilities for apps, websites, and content directly through AI tools like Claude and Cursor. It implements the Model Context Protocol standard for connecting LLMs to external translation services.

## Key Features

- **Multi-Platform Translation**: Translate apps, websites, and content
- **AI Tool Integration**: Works with Cursor, Claude desktop, and Cline for VS Code
- **Standardized Protocol**: Uses MCP standard for consistent integration
- **Project-Based**: API keys are project-specific for organized workflow
- **Real-Time Translation**: Direct translation through AI conversations

## Installation

### Global Installation (Recommended)
```bash
# Install and configure with your API key
npx -y lingo.dev mcp YOUR_API_KEY

# Add to Claude MCP configuration
claude mcp add lingo-translate -- npx -y lingo.dev mcp YOUR_API_KEY
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "lingo-translate": {
      "command": "npx",
      "args": ["-y", "lingo.dev", "mcp", "YOUR_API_KEY"],
      "env": {
        "LINGO_API_KEY": "YOUR_API_KEY"
      }
    }
  }
}
```

## Setup Requirements

### 1. Get Lingo.dev API Key
1. Visit Lingo.dev and create an account
2. Navigate to your project settings
3. Generate or copy your project-specific API key
4. Note: Each project has its own API key

### 2. Configuration
Store API key securely:
```bash
# Environment variable (recommended)
export LINGO_API_KEY="your-project-api-key"
```

## Supported AI Tools

### Claude Desktop
Configure in Claude settings with MCP server details

### Cursor
Add MCP server in Cursor Settings under MCP configuration

### Cline for VS Code
Configure MCP server in Cline extension settings

## Use Cases

### App Localization
- Mobile app string translation
- UI element localization
- Multi-language app development
- Dynamic content translation

### Website Translation
- Web page content translation
- Multi-language website development
- Blog post localization
- E-commerce product descriptions

### Content Translation
- Documentation translation
- Marketing material localization
- User guides and manuals
- Technical content translation

### Development Workflow
- Code comment translation
- README file localization
- API documentation translation
- Error message localization

## Integration Examples

### Translation Workflow
```
User: "Translate this English text to Spanish"
AI: Uses Lingo.dev MCP to process translation request
Result: Accurate Spanish translation with context awareness
```

### Multi-Language Development
```
User: "Translate these UI strings for my React app"
AI: Processes multiple strings through Lingo.dev
Result: Structured translation output ready for implementation
```

## Configuration Options

### Project-Specific Keys
- Each Lingo.dev project has unique API key
- Allows for organized translation workflows
- Separate billing and usage tracking per project

### Language Support
- Multiple source and target languages
- Context-aware translations
- Technical terminology handling

## Pricing Considerations

- **API Usage**: Charged per translation request or character count
- **Project-Based**: Billing organized by Lingo.dev project
- **Volume Discounts**: Potential savings for high-volume usage

## Security Best Practices

- **API Key Management**: Store keys in environment variables
- **Project Isolation**: Use separate keys for different projects
- **Access Control**: Limit API key access to authorized team members
- **Usage Monitoring**: Track translation usage for cost management

## Workflow Integration

### Development Process
1. Set up Lingo.dev project and get API key
2. Configure MCP server in your AI tool
3. Use natural language to request translations
4. Implement translated content directly in your project

### Quality Assurance
1. Use AI tool to translate content
2. Review translations for accuracy and context
3. Implement feedback loop for improvements
4. Maintain translation consistency across project

## Related Tools

- **Memory MCP**: Store translation preferences and glossaries
- **GitHub MCP**: Integrate with version control for localized content
- **Make MCP**: Automate translation workflows

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key is project-specific and valid
- **Configuration Issues**: Check MCP server setup in AI tool settings
- **Translation Quality**: Provide context for better results
- **Rate Limiting**: Monitor usage limits per project

**Best Practices:**
- Provide context for technical terms
- Use consistent terminology across translations
- Test translations in target language environment
- Maintain translation glossaries for complex projects

---

*Last Updated: 2025-08-02*
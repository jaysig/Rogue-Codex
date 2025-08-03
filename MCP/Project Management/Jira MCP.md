# Jira MCP

**Repository:** https://github.com/ahmetbarut/jira-mcp  
**Category:** Project Management  
**Scope:** Project (recommended)  
**Type:** Jira Integration & Automation

Jira MCP provides streamlined Jira integration focused on essential project management operations, offering a lightweight alternative for teams needing core Jira functionality with Claude Code.

## Key Features

- **Core Operations**: Essential create, read, update operations for issues
- **Simplified Setup**: Streamlined configuration and authentication
- **Project Focus**: Project-centric operations and data access
- **Lightweight**: Minimal overhead for basic Jira integration needs
- **Issue Tracking**: Efficient issue management and status updates
- **Search & Filter**: Query issues with JQL and custom filters

## Installation

### Project Installation (Recommended)
```json
// .mcp.json
{
  "mcpServers": {
    "jira-simple": {
      "command": "npx",
      "args": ["-y", "jira-mcp"],
      "env": {
        "JIRA_URL": "https://your-domain.atlassian.net",
        "JIRA_USERNAME": "your-email@example.com",
        "JIRA_API_TOKEN": "${JIRA_API_TOKEN}"
      }
    }
  }
}
```

### Local Configuration (Sensitive Data)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "jira-simple": {
      "command": "npx",
      "args": ["-y", "jira-mcp"],
      "env": {
        "JIRA_URL": "https://your-domain.atlassian.net",
        "JIRA_USERNAME": "your-email@example.com",
        "JIRA_API_TOKEN": "${JIRA_API_TOKEN}"
      }
    }
  }
}
```

## Use Cases

### Basic Project Management
- Simple issue creation and tracking
- Status updates and progress monitoring
- Basic project coordination
- Essential workflow operations

### Documentation Tasks
- Track documentation updates and reviews
- Create tasks for content creation
- Monitor completion of content milestones
- Simple project reporting

### Team Coordination
- Assign and track team responsibilities
- Basic communication through issue comments
- Simple project status tracking
- Essential workflow management

## Typical Workflows

1. **Task Creation**: "Create a simple task for updating the Tools section"
2. **Status Check**: "What's the current status of content-related issues?"
3. **Assignment**: "Assign this documentation task to the content team"
4. **Progress Update**: "Update the status of this content creation task"

## Configuration Requirements

Required environment variables:
- `JIRA_URL`: Full URL to your Jira instance
- `JIRA_USERNAME`: Your Jira username/email
- `JIRA_API_TOKEN`: API token for authentication

## Security Considerations

- **Token Management**: Secure API token storage
- **Minimal Permissions**: Use least privilege access
- **Environment Variables**: Keep credentials in local settings
- **Access Logging**: Monitor API usage patterns

## Comparison with Jira Context MCP

**Jira MCP (ahmetbarut):**
- Lightweight and simple
- Core functionality focus
- Easier setup and maintenance
- Best for basic project management needs

**Jira Context MCP:**
- More comprehensive features
- Advanced workflow integration
- Complex reporting capabilities
- Better for enterprise requirements

## Related Tools

- **Jira Context MCP**: For advanced Jira integration needs
- **Jina Reader MCP**: For processing project documents
- **Notion MCP**: For alternative project documentation

## Rogue Codex Applications

**Low to Medium Value for:**
- Simple task tracking for content updates
- Basic coordination of documentation projects
- Individual project management needs
- Lightweight integration with existing Jira workflows

**Best Use Cases:**
- Teams already using Jira but needing simple integration
- Individual contributors tracking their documentation tasks
- Basic project coordination without complex workflows
- Getting started with Jira integration before scaling up

**Recommendations:**
- Choose this over Jira Context MCP for simple needs
- Good starting point before implementing more complex Jira workflows
- Ideal for teams wanting minimal Jira integration overhead

---

*Last Updated: 2025-08-02*
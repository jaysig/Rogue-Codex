# Jira Context MCP

**Repository:** https://github.com/rahulthedevil/Jira-Context-MCP  
**Category:** Project Management  
**Scope:** Project (recommended)  
**Type:** Project Management Integration

Jira Context MCP provides comprehensive Jira integration capabilities, enabling Claude Code to interact with Jira issues, projects, and workflows for enhanced project management and documentation coordination.

## Key Features

- **Issue Management**: Create, update, and track Jira issues
- **Project Integration**: Access project data and metadata
- **Workflow Automation**: Automate common Jira operations
- **Context Retrieval**: Pull relevant project context and history
- **Reporting**: Generate reports from Jira data
- **Custom Fields**: Work with custom fields and configurations

## Installation

### Project Installation (Recommended)
```json
// .mcp.json
{
  "mcpServers": {
    "jira-context": {
      "command": "npx",
      "args": ["-y", "jira-context-mcp"],
      "env": {
        "JIRA_HOST": "your-domain.atlassian.net",
        "JIRA_EMAIL": "your-email@example.com",
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
    "jira-context": {
      "command": "npx",
      "args": ["-y", "jira-context-mcp"],
      "env": {
        "JIRA_HOST": "your-domain.atlassian.net",
        "JIRA_EMAIL": "your-email@example.com",
        "JIRA_API_TOKEN": "${JIRA_API_TOKEN}"
      }
    }
  }
}
```

## Use Cases

### Documentation Coordination
- Link documentation updates to Jira tickets
- Track content creation progress in project management
- Coordinate documentation reviews and approvals
- Generate documentation status reports

### Project Tracking
- Monitor content delivery milestones
- Track tool evaluation and implementation tasks
- Coordinate team assignments for content sections
- Manage documentation backlog and priorities

### Workflow Integration
- Automate task creation for content updates
- Synchronize project status with documentation progress
- Generate project reports and dashboards
- Track dependencies between documentation tasks

## Typical Workflows

1. **Issue Creation**: "Create a Jira ticket for updating the Company Spotlight"
2. **Progress Tracking**: "Get the status of all documentation-related tickets"
3. **Report Generation**: "Generate a report of completed content tasks this sprint"
4. **Context Retrieval**: "Pull the requirements from this Jira epic for our documentation plan"

## Configuration Requirements

Required environment variables:
- `JIRA_HOST`: Your Jira instance URL (e.g., company.atlassian.net)
- `JIRA_EMAIL`: Your Jira account email
- `JIRA_API_TOKEN`: API token for authentication

Project-specific settings:
- Default project keys
- Custom field mappings
- Workflow state configurations

## Security Considerations

- **API Token Security**: Store tokens in environment variables
- **Permission Management**: Use appropriate Jira permissions
- **Access Control**: Limit access to relevant projects only
- **Audit Trail**: Monitor API usage and operations

## Integration Capabilities

- **Custom Fields**: Access project-specific data fields
- **Workflows**: Interact with custom workflow states
- **Reports**: Generate custom reports and dashboards
- **Notifications**: Set up automated notifications and updates

## Related Tools

- **Jina Reader MCP**: For processing project documents
- **Jira MCP (ahmetbarut)**: Alternative Jira integration
- **Notion MCP**: For cross-platform project documentation

## Rogue Codex Applications

**Medium Value for:**
- Coordinating large-scale content updates across sections
- Project management for complex documentation initiatives
- Team collaboration on content creation and review
- Tracking milestones for major Rogue Codex enhancements

**Best Use Cases:**
- Organizations using Jira for project management
- Teams requiring formal documentation tracking
- Projects with complex approval workflows
- Large-scale content coordination efforts

**Considerations:**
- Requires existing Jira infrastructure
- May be overkill for individual documentation maintenance
- Best suited for team-based or enterprise documentation projects

---

*Last Updated: 2025-08-02*
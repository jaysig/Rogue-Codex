# MySQL MCP Server

**Repository:** https://github.com/designcomputer/mysql_mcp_server  
**Category:** Development  
**Scope:** Project (recommended)  
**Type:** Database Integration

MySQL MCP Server provides comprehensive MySQL database integration, enabling Claude Code to execute queries, manage schemas, and perform database operations directly.

## Key Features

- **Query Execution**: Run SELECT, INSERT, UPDATE, DELETE operations
- **Schema Management**: Create and modify tables, indexes, and constraints
- **Data Migration**: Import/export data between formats
- **Performance Analysis**: Query optimization and execution planning
- **Transaction Support**: Manage database transactions and rollbacks
- **Connection Pooling**: Efficient database connection management

## Installation

### Project Installation (Recommended)
```json
// .mcp.json
{
  "mcpServers": {
    "mysql-server": {
      "command": "npx",
      "args": ["-y", "mysql-mcp-server"],
      "env": {
        "MYSQL_HOST": "localhost",
        "MYSQL_PORT": "3306",
        "MYSQL_DATABASE": "rogue_codex",
        "MYSQL_USER": "your_user",
        "MYSQL_PASSWORD": "your_password"
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
    "mysql-server": {
      "command": "npx",
      "args": ["-y", "mysql-mcp-server"],
      "env": {
        "MYSQL_HOST": "localhost",
        "MYSQL_PORT": "3306",
        "MYSQL_DATABASE": "rogue_codex",
        "MYSQL_USER": "${MYSQL_USER}",
        "MYSQL_PASSWORD": "${MYSQL_PASSWORD}"
      }
    }
  }
}
```

## Use Cases

### Structured Data Management
- Company Registry database backend
- Tool evaluation metrics storage
- Content performance analytics
- User interaction tracking

### Data Analysis & Reporting
- Complex queries across structured data
- Performance metrics calculation
- Trend analysis and reporting
- Data aggregation and summarization

### Integration & Automation
- Data synchronization between systems
- Automated report generation
- Backup and migration operations
- API data persistence

## Typical Workflows

1. **Data Query**: "Find all companies in the AI industry with funding over $100M"
2. **Analytics**: "Generate a report of tool adoption trends by category"
3. **Data Migration**: "Import company data from Excel into the database"
4. **Performance Analysis**: "Analyze content engagement metrics by section"

## Database Schema Considerations

For Rogue Codex implementation:
- **Companies Table**: Store company registry data
- **Tools Table**: Tool evaluation and categorization
- **Content Metrics**: Page views, engagement data
- **User Preferences**: Personalization and settings

## Configuration

Required environment variables:
- `MYSQL_HOST`: Database server hostname
- `MYSQL_PORT`: Database server port (default: 3306)
- `MYSQL_DATABASE`: Target database name
- `MYSQL_USER`: Database username
- `MYSQL_PASSWORD`: Database password

Optional settings:
- Connection pool size and timeout
- Query execution limits
- SSL/TLS configuration

## Security Considerations

- **Credential Management**: Store sensitive data in environment variables
- **SQL Injection Prevention**: Use parameterized queries
- **Access Control**: Implement proper user permissions
- **Connection Security**: Use SSL/TLS for remote connections
- **Audit Logging**: Track database operations and access

## Related Tools

- **Excel MCP**: For data import/export operations
- **JSON MCP**: For data format transformation
- **Notion MCP**: For structured data presentation

## Rogue Codex Applications

**High Value for:**
- Implementing structured storage for Company Registry
- Analytics and metrics for content performance
- Advanced search and filtering capabilities
- Data-driven insights for content optimization

**Considerations:**
- Requires database setup and maintenance
- Best suited for projects with significant structured data needs
- May be overkill for current markdown-based documentation approach

---

*Last Updated: 2025-08-02*
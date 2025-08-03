# Supabase Database MCP Server

**Repository:** https://github.com/supabase-community/supabase-mcp  
**Category:** Company APIs  
**Scope:** Project (recommended for security)  
**Type:** Database & Backend-as-a-Service  
**API Required:** Yes (Supabase Personal Access Token)  
**Status:** Pre-1.0 (Breaking changes possible)

The Supabase MCP Server connects AI assistants like Cursor and Claude directly to Supabase projects, enabling database management, querying, and backend operations through natural language.

## Key Features

- **Database Operations**: Manage tables, query data, generate TypeScript types
- **Account Management**: Access project configurations and settings
- **Edge Functions**: Deploy and manage serverless functions
- **Real-Time Integration**: Work with Supabase real-time features
- **Security Controls**: Read-only mode and project scoping options

## Installation

### Prerequisites
- Node.js installed
- Supabase personal access token
- MCP-compatible client (Cursor, Claude Desktop)

### Quick Installation
```bash
# Install via NPX with configuration
npx @supabase/mcp-server-supabase@latest \
  --read-only \
  --project-ref=YOUR_PROJECT_REF
```

### Project Configuration
```json
// .mcp.json
{
  "mcpServers": {
    "supabase": {
      "command": "npx",
      "args": [
        "@supabase/mcp-server-supabase@latest",
        "--read-only",
        "--project-ref=YOUR_PROJECT_REF"
      ],
      "env": {
        "SUPABASE_ACCESS_TOKEN": "YOUR_PERSONAL_ACCESS_TOKEN"
      }
    }
  }
}
```

## Setup Requirements

### 1. Supabase Access Token
1. Log into Supabase dashboard
2. Navigate to Account Settings > Access Tokens
3. Generate new personal access token
4. Store token securely in environment variables

### 2. Project Reference
1. Find project reference in project settings
2. Use project-specific configuration for security
3. Limit access to development projects only

## Security Recommendations

### Development Use Only
```
⚠️ RECOMMENDED: Use with development projects only
```

**Security Measures:**
- **Read-Only Mode**: Enable `--read-only` flag to prevent data modifications
- **Project Scoping**: Use `--project-ref` to limit access to specific projects
- **Manual Review**: Review all tool calls before execution
- **Environment Isolation**: Never use with production databases

### Configuration Options
```bash
# Maximum security configuration
npx @supabase/mcp-server-supabase@latest \
  --read-only \
  --project-ref=dev-project-ref \
  --manual-approve
```

## Use Cases

### Application Development
- **Schema Design**: Create and modify database tables
- **Data Modeling**: Design relationships and constraints
- **Query Development**: Test and optimize database queries
- **Type Generation**: Generate TypeScript types from schema

### Testing and Debugging
- **Data Inspection**: Query and analyze database contents
- **Performance Testing**: Analyze query performance
- **Schema Validation**: Verify database structure
- **Integration Testing**: Test application database interactions

### Backend Management
- **Edge Functions**: Deploy and manage serverless functions
- **Configuration**: Manage project settings and environment variables
- **Authentication**: Configure auth providers and policies
- **Real-Time**: Set up real-time subscriptions

## Available Tools

### Database Operations
- **Table Management**: Create, modify, and query tables
- **Data Operations**: Insert, update, delete operations (if not read-only)
- **Schema Introspection**: Analyze database structure
- **Query Execution**: Run SQL queries and analyze results

### Project Management
- **Configuration Access**: View project settings
- **Environment Variables**: Manage environment configuration
- **API Keys**: Access project API credentials
- **Usage Monitoring**: View project usage statistics

### Development Tools
- **Type Generation**: Generate TypeScript interfaces
- **Migration Management**: Handle database migrations
- **Seed Data**: Manage test data for development
- **Backup Operations**: Export and import data

## Integration Examples

### Schema Development
```
User: "Create a users table with email and profile fields"
AI: Generates appropriate SQL schema and creates table
Result: New table created with proper constraints and relationships
```

### Data Analysis
```
User: "Show me the user signup trends for the last month"
AI: Queries user table and analyzes signup patterns
Result: Comprehensive analysis with insights and trends
```

## Configuration Management

### Environment Variables
```bash
# Required configuration
export SUPABASE_ACCESS_TOKEN="your-personal-access-token"
export SUPABASE_PROJECT_REF="your-project-reference"
```

### Security Flags
- `--read-only`: Prevents data modifications
- `--project-ref`: Limits access to specific project
- `--manual-approve`: Requires manual approval for operations

## Version Considerations

**⚠️ Pre-1.0 Status:**
- Expect potential breaking changes between versions
- Pin to specific version for production-like environments
- Monitor updates and changelog for compatibility
- Test thoroughly after version updates

## Best Practices

### Security First
- Always use read-only mode for exploration
- Limit to development projects only
- Review operations before execution
- Use project-specific tokens when possible

### Development Workflow
- Start with schema exploration
- Use TypeScript generation for type safety
- Test queries in safe environment
- Monitor usage and performance

## Related Tools

- **Memory MCP**: Store database schemas and preferences
- **GitHub MCP**: Integrate with version control for schema changes
- **Make MCP**: Automate database operations
- **Browser-use MCP**: For Supabase dashboard interaction

## Troubleshooting

**Common Issues:**
- **Token Errors**: Verify personal access token validity
- **Project Access**: Ensure token has access to specified project
- **Version Conflicts**: Pin to stable version to avoid breaking changes
- **Permission Issues**: Check token permissions and project roles

**Best Practices:**
- Use development projects only
- Enable read-only mode by default
- Monitor API usage limits
- Keep tokens secure and rotated regularly

---

*Last Updated: 2025-08-02*
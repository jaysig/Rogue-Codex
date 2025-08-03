# SchemaFlow Database Schema MCP Server

**Repository:** https://github.com/CryptoRadi/schemaflow-mcp-server  
**Category:** Company APIs  
**Scope:** Project (database-specific)  
**Type:** Real-Time PostgreSQL & Supabase Schema Access  
**API Required:** Yes (SchemaFlow Token)  
**Status:** Details Only - Niche Use Case  
**License:** MIT

Real-time PostgreSQL and Supabase schema access for AI-IDEs via Model Context Protocol, providing live database schema context for smarter AI code generation.

## Key Features

- **Live Schema Access**: Real-time database schema information
- **Multi-Database Support**: PostgreSQL and Supabase databases
- **AI-IDE Integration**: Supports Cursor, Windsurf, VS Code + Cline
- **Three Core Tools**: Schema retrieval, analysis, and alignment checking
- **Security Focus**: Metadata-only access with encrypted connections
- **Platform Integration**: Part of larger SchemaFlow ecosystem

## API Requirements

### SchemaFlow Token Required
```
🔑 API KEY REQUIRED: SchemaFlow Token
```

**Get SchemaFlow Token:**
1. Visit SchemaFlow Dashboard
2. Create account and project
3. Generate MCP token for your database
4. Configure AI-IDE with token and server URL

**Access Model:**
- **Token-based Authentication**: Secure API access
- **User-specific Access**: Schema access limited to user permissions
- **Metadata Only**: No actual data access, only schema information

## Available Tools

### 1. get_schema
**Purpose:** Retrieve comprehensive database schema details
- **Schema Structure**: Tables, columns, relationships
- **Data Types**: Column types and constraints
- **Indexes**: Database indexing information
- **Permissions**: Access control information

### 2. analyze_database
**Purpose:** Perform database performance and security analysis
- **Performance Metrics**: Query performance insights
- **Security Assessment**: Potential security issues
- **Optimization Suggestions**: Performance improvement recommendations
- **Best Practice Validation**: Schema design best practices

### 3. check_schema_alignment
**Purpose:** Validate schema against best practices
- **Design Patterns**: Check against common design patterns
- **Naming Conventions**: Validate naming consistency
- **Relationship Integrity**: Verify foreign key relationships
- **Normalization**: Check database normalization levels

## Supported AI-IDEs

### Integration Options
- **Cursor**: Enhanced code completion with schema context
- **Windsurf**: AI-powered development with database awareness
- **VS Code + Cline**: Schema-aware coding assistance
- **Custom Integrations**: API available for other AI tools

### Configuration Example
```json
{
  "mcpServers": {
    "schemaflow": {
      "command": "schemaflow-mcp",
      "args": ["--token", "YOUR_SCHEMAFLOW_TOKEN"],
      "env": {
        "SCHEMAFLOW_TOKEN": "YOUR_TOKEN",
        "DATABASE_URL": "your-database-connection"
      }
    }
  }
}
```

## Use Cases

### AI-Enhanced Development
- **Smart Code Generation**: AI generates database-aware code
- **Relationship Understanding**: AI understands table relationships
- **Type Safety**: AI suggests correct data types and constraints
- **Query Optimization**: AI recommends optimized database queries

### Database Development
- **Schema Documentation**: Real-time schema context during development
- **Migration Planning**: Understand impact of schema changes
- **API Development**: Generate database-aware API endpoints
- **ORM Configuration**: AI assistance with ORM setup and configuration

### Team Collaboration
- **Schema Awareness**: All team members have current schema context
- **Consistent Development**: Shared understanding of database structure
- **Onboarding**: New developers quickly understand database design
- **Code Reviews**: Schema-aware code review assistance

## Security Features

### Data Protection
- **Metadata Only**: No access to actual data, only schema information
- **Encrypted Connections**: All communications encrypted in transit
- **Token-Based Auth**: Secure authentication without password sharing
- **User Scoping**: Access limited to user's database permissions

### Access Control
- **Granular Permissions**: Control access to specific schemas or tables
- **Audit Logging**: Track all schema access and usage
- **Session Management**: Secure session handling and timeout
- **Compliance**: Meet data protection and privacy requirements

## Limitations

### Scope Considerations
- **Database-Specific**: Only useful for PostgreSQL/Supabase projects
- **Commercial Dependency**: Requires SchemaFlow platform account
- **Limited Database Types**: PostgreSQL and Supabase only
- **Token Management**: Additional API key management overhead

### Alternative Solutions
- **Supabase MCP**: For broader Supabase operations beyond schema
- **SchemaCrawler**: For offline schema analysis
- **Database IDEs**: Traditional database development tools
- **Native Database Tools**: Built-in database documentation tools

## When to Use

### Recommended For
- **AI-Heavy Development**: Projects leveraging AI code generation extensively
- **Complex Database Projects**: Applications with intricate schema designs
- **Team Database Development**: Collaborative database-centric development
- **Real-Time Schema Needs**: When live schema context is critical

### Not Recommended For
- **Simple Applications**: Projects with minimal database complexity
- **Non-PostgreSQL Projects**: Applications using other database systems
- **Documentation Projects**: Content-focused projects without database work
- **Cost-Sensitive Projects**: When additional API costs aren't justified

## Pricing Considerations

- **Platform Dependency**: Requires SchemaFlow platform subscription
- **Token Usage**: May have usage-based pricing
- **Team Scaling**: Consider costs for team access
- **ROI Assessment**: Evaluate AI development productivity gains

## Related Tools

- **Supabase MCP**: For comprehensive Supabase operations
- **SchemaCrawler MCP**: For offline database schema analysis
- **Memory MCP**: Store schema insights and patterns
- **GitHub MCP**: Version control for schema-related code changes

## Future Considerations

- **Database Support**: Potential expansion to other database systems
- **Feature Enhancement**: Additional analysis and validation tools
- **Integration Expansion**: Support for more AI development environments
- **Pricing Evolution**: Monitor platform pricing and feature changes

---

*Last Updated: 2025-08-02*
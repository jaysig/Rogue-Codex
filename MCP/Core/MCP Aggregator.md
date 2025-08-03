# MCP Aggregator (Combine MCP)

**Repository:** https://github.com/nazar256/combine-mcp  
**Category:** Core  
**Scope:** Global (recommended)  
**Type:** MCP Server Management & Aggregation  
**API Required:** No (manages other MCP servers)  
**License:** Not specified

A Model Context Protocol aggregator that combines multiple MCP servers into a single interface, specifically designed to overcome Cursor's limitation of supporting only two MCP servers simultaneously.

## Key Features

- **Server Aggregation**: Combine unlimited MCP servers into single interface
- **Cursor Optimization**: Specifically designed to work around Cursor's 2-server limit
- **Tool Filtering**: Selective exposure of tools to stay within limits
- **Automatic Sanitization**: Clean tool names for compatibility
- **Flexible Configuration**: Environment variables and JSON config support
- **No API Keys Required**: Pure aggregation service, no external dependencies

## Installation

### Prerequisites
- Multiple MCP servers you want to combine
- Go 1.19+ (for manual build) or Docker

### API Setup Requirements
```
✅ NO API KEY REQUIRED
Aggregates existing MCP servers - uses their configurations
```

### Recommended Installation
```bash
# Install via script (recommended)
curl -sSL https://raw.githubusercontent.com/nazar256/combine-mcp/main/install.sh | bash

# Add to global MCP configuration
claude mcp add mcp-aggregator -- combine-mcp
```

### Alternative Installation Methods

#### Go Install
```bash
go install github.com/nazar256/combine-mcp@latest
```

#### Docker
```bash
docker run --rm -it ghcr.io/nazar256/combine-mcp:latest
```

#### Manual Build
```bash
git clone https://github.com/nazar256/combine-mcp.git
cd combine-mcp
make build
```

## Configuration

### Basic Configuration
```json
// .mcp.json
{
  "mcpServers": {
    "aggregator": {
      "command": "combine-mcp",
      "args": ["--config", "aggregator-config.json"]
    }
  }
}
```

### Aggregator Configuration File
```json
// aggregator-config.json
{
  "servers": [
    {
      "name": "puppeteer",
      "command": "node",
      "args": ["/path/to/puppeteer-mcp/dist/index.js"]
    },
    {
      "name": "memory",
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    {
      "name": "time",
      "command": "python3",
      "args": ["-m", "mcp_server_time"]
    }
  ],
  "toolFiltering": {
    "include": ["puppeteer_*", "memory_*", "time_*"],
    "exclude": ["debug_*", "test_*"]
  }
}
```

## Use Cases

### Cursor Limitation Workaround
- **Beyond 2 Servers**: Access unlimited MCP servers in Cursor
- **Tool Consolidation**: Combine related tools from multiple servers
- **Workflow Optimization**: Use best tools from different servers simultaneously
- **Development Efficiency**: Access full MCP ecosystem without switching configurations

### Multi-Server Management
- **Centralized Access**: Single interface for all MCP capabilities
- **Load Distribution**: Spread workload across multiple backend servers
- **Failover Capability**: Automatic fallback if individual servers fail
- **Resource Optimization**: Efficient resource usage across servers

### Tool Organization
- **Selective Exposure**: Only expose needed tools to avoid clutter
- **Name Standardization**: Consistent tool naming across servers
- **Category Management**: Organize tools by function or source
- **Limit Management**: Stay within AI assistant tool limits

## Configuration Options

### Server Management
- **Dynamic Server List**: Add/remove servers without restart
- **Health Monitoring**: Track individual server status
- **Load Balancing**: Distribute requests across servers
- **Error Handling**: Graceful degradation when servers fail

### Tool Filtering
- **Include Patterns**: Specify which tools to expose
- **Exclude Patterns**: Hide unwanted or dangerous tools
- **Name Prefixing**: Add server prefixes to avoid conflicts
- **Tool Limits**: Respect AI assistant tool count limits

### Performance Tuning
- **Request Routing**: Intelligent request distribution
- **Caching Strategy**: Cache responses for performance
- **Timeout Management**: Handle slow server responses
- **Resource Monitoring**: Track server resource usage

## Integration Examples

### Cursor Multi-Server Setup
```
Backend Servers: Puppeteer + Memory + Time + Context7 + Exa
Aggregator: Combines all into single interface
Cursor: Sees one "server" with tools from all backends
Result: Full MCP ecosystem access within Cursor's limitations
```

### Development Workflow
```
User: "Take a screenshot of example.com and save the URL to memory"
Aggregator: Routes screenshot to Puppeteer, memory save to Memory server
Result: Seamless multi-server operation through single interface
```

## Advanced Configuration

### Environment Variables
```bash
# Server configuration
export MCP_SERVERS_CONFIG="path/to/servers.json"
export MCP_TOOL_PREFIX="true"
export MCP_MAX_TOOLS="40"

# Performance settings
export MCP_TIMEOUT="30s"
export MCP_CACHE_SIZE="100"
export MCP_LOG_LEVEL="info"
```

### Tool Name Sanitization
- **Automatic Prefixing**: Add server name to tool names
- **Conflict Resolution**: Handle duplicate tool names
- **Character Sanitization**: Clean special characters for compatibility
- **Mapping Tables**: Custom tool name mappings

## Best Practices

### Server Selection
- **Complementary Tools**: Choose servers with different capabilities
- **Performance Balance**: Mix fast and slow servers appropriately
- **Reliability**: Include backup servers for critical functionality
- **Resource Awareness**: Monitor combined resource usage

### Tool Management
- **Strategic Filtering**: Only expose frequently used tools
- **Clear Naming**: Use descriptive prefixes for tool identification
- **Regular Cleanup**: Remove unused tools to stay within limits
- **Documentation**: Maintain tool catalog for team usage

## Troubleshooting

### Common Issues
- **Server Connection**: Individual server connectivity problems
- **Tool Conflicts**: Duplicate tool names across servers
- **Performance**: Slow response from aggregated servers
- **Configuration**: JSON config syntax errors

### Performance Optimization
- **Server Health**: Monitor individual server performance
- **Tool Selection**: Optimize tool filtering for speed
- **Caching**: Implement response caching where appropriate
- **Load Balancing**: Distribute load evenly across servers

## Related Tools

- **All MCP Servers**: This tool aggregates any MCP server
- **Cursor**: Primary beneficiary of aggregation capability
- **VS Code**: Can benefit from multi-server access
- **Claude Desktop**: Alternative client for aggregated servers

## Security Considerations

- **Server Trust**: Only aggregate trusted MCP servers
- **Tool Exposure**: Carefully filter exposed tools for security
- **Access Control**: Implement appropriate access controls
- **Monitoring**: Log all requests for security audit

## Future Considerations

- **Server Discovery**: Automatic detection of available servers
- **Load Balancing**: Intelligent request routing
- **Monitoring Dashboard**: Visual server health monitoring
- **Plugin System**: Extensible server management

---

*Last Updated: 2025-08-02*
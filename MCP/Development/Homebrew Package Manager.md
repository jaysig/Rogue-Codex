# Homebrew Package Manager MCP Server

**Repository:** https://github.com/jeannier/homebrew-mcp  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** System Package Management  
**API Required:** No (uses local Homebrew installation)  
**License:** MIT  
**Platform:** macOS only

A Model Context Protocol server designed for managing Homebrew packages on macOS through AI assistants, providing direct package management capabilities without requiring external API keys.

## Key Features

- **Complete Package Management**: Install, update, remove, and search packages
- **System Information**: Check system health and package status
- **Real Homebrew Commands**: Runs actual `brew` commands via subprocess
- **AI-Friendly Interface**: Exposes Homebrew functionality through MCP tools
- **Request Logging**: All operations logged to `homebrew_mcp.log`
- **No API Keys Required**: Works entirely with local Homebrew installation

## Installation

### Prerequisites
- macOS with Homebrew already installed
- Python 3.13
- UV (for virtual environment management)

### API Setup Requirements
```
✅ NO API KEY REQUIRED
Uses local Homebrew installation - works immediately after setup
```

### Global Installation (Recommended)
```bash
# Install via UV (recommended method)
uvx --from homebrew-mcp homebrew-mcp

# Add to global MCP configuration
claude mcp add homebrew -- uvx --from homebrew-mcp homebrew-mcp
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "homebrew": {
      "command": "uvx",
      "args": ["--from", "homebrew-mcp", "homebrew-mcp"]
    }
  }
}
```

### Alternative Installation
```bash
# Clone and install manually
git clone https://github.com/jeannier/homebrew-mcp.git
cd homebrew-mcp
uv sync
uv run python -m homebrew_mcp
```

## Available Tools

### Package Management
- **brew install**: Install new packages
- **brew uninstall**: Remove packages
- **brew upgrade**: Update packages
- **brew search**: Find available packages
- **brew info**: Get detailed package information

### System Operations
- **brew update**: Update Homebrew itself
- **brew doctor**: Check system health
- **brew list**: Show installed packages
- **brew outdated**: Check for package updates
- **brew cleanup**: Remove old package versions

### Service Management
- **brew services**: Manage background services
- **brew services start/stop**: Control individual services

## Use Cases

### Development Environment Setup
- **Automated Installation**: AI-guided package installation for development stacks
- **Environment Replication**: Set up consistent development environments
- **Dependency Management**: Install and manage project dependencies
- **Tool Discovery**: Find and install development tools

### System Maintenance
- **Health Checks**: Regular system health monitoring
- **Update Management**: Automated package updates and cleanup
- **Package Auditing**: Review installed packages and versions
- **Service Management**: Control background services and daemons

### Productivity Workflows
- **Quick Installation**: Rapid software installation through conversation
- **Batch Operations**: Install multiple packages in sequence
- **System Optimization**: Clean up unused packages and versions
- **Documentation**: Generate lists of installed software

## Integration Examples

### Conversational Package Management
```
User: "Install the latest version of Node.js and Python"
AI: Uses brew install to install node and python packages
Result: Both packages installed with version confirmation
```

### System Health Check
```
User: "Check if my system needs any updates"
AI: Runs brew doctor and brew outdated
Result: Comprehensive system health report with recommendations
```

### Development Setup
```
User: "Set up a web development environment"
AI: Installs git, node, npm, code editors, and development tools
Result: Complete development environment ready for use
```

## Configuration Options

### Logging Configuration
- **Log File**: All operations logged to `homebrew_mcp.log`
- **Request Tracking**: Complete history of all package operations
- **Error Logging**: Detailed error messages for troubleshooting

### Safety Features
- **Confirmation Prompts**: AI can ask for confirmation on destructive operations
- **Dry Run Options**: Preview changes before execution
- **Rollback Capability**: Uninstall recently installed packages if needed

## Workflow Integration

### Automated Development Setup
1. **Environment Detection**: Analyze project requirements
2. **Package Planning**: Determine required tools and dependencies
3. **Batch Installation**: Install all required packages efficiently
4. **Verification**: Confirm successful installation and configuration

### System Maintenance Routine
1. **Health Check**: Run brew doctor for system issues
2. **Update Check**: Identify outdated packages
3. **Selective Updates**: Update critical packages first
4. **Cleanup**: Remove old versions and clear cache

## Best Practices

### Package Management
- **Regular Updates**: Keep Homebrew and packages current
- **Selective Installation**: Only install needed packages
- **Version Awareness**: Understand package version implications
- **Documentation**: Keep track of installed packages for projects

### System Health
- **Periodic Cleanup**: Regular cleanup to free disk space
- **Service Monitoring**: Monitor background services for performance
- **Dependency Tracking**: Understand package dependencies
- **Backup Considerations**: Document installed packages for system recovery

## Troubleshooting

### Common Issues
- **Permission Errors**: Ensure proper Homebrew permissions
- **Python Version**: Verify Python 3.13 compatibility
- **UV Installation**: Ensure UV is properly installed
- **Homebrew Health**: Run `brew doctor` for system issues

### Performance Optimization
- **Cache Management**: Regular cleanup of Homebrew cache
- **Service Optimization**: Manage unnecessary background services
- **Disk Space**: Monitor and clean up old package versions
- **Network Issues**: Handle package download failures gracefully

## Related Tools

- **Memory MCP**: Store package preferences and installation lists
- **GitHub MCP**: Manage development dependencies for repositories
- **Context7 MCP**: Search for package documentation and usage examples

## Security Considerations

- **Package Verification**: Homebrew handles package verification
- **System Access**: MCP server requires system-level package management permissions
- **Service Management**: Be cautious with service start/stop operations
- **Regular Updates**: Keep Homebrew updated for security patches

---

*Last Updated: 2025-08-02*
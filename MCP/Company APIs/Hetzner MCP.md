# Hetzner MCP

**Repository:** https://github.com/dkruyt/mcp-hetzner  
**Category:** Company APIs  
**Scope:** Local (recommended)  
**Type:** Cloud Infrastructure & Hosting

Hetzner MCP enables Claude Code to interact with Hetzner Cloud API for server management, infrastructure automation, and cloud resource monitoring within development workflows.

## Key Features

- **Server Management**: Create, manage, and monitor cloud servers
- **Infrastructure as Code**: Automate server provisioning and configuration
- **Resource Monitoring**: Track server performance and resource usage
- **Network Management**: Configure firewalls, load balancers, and networking
- **Backup Management**: Automate backup creation and management
- **Cost Optimization**: Monitor and optimize cloud infrastructure costs

## Installation

### Local Installation (Recommended for API Keys)
```json
// .claude/settings.local.json
{
  "mcpServers": {
    "hetzner": {
      "command": "npx",
      "args": ["-y", "mcp-hetzner"],
      "env": {
        "HETZNER_API_TOKEN": "${HETZNER_API_TOKEN}"
      }
    }
  }
}
```

## Use Cases

### Infrastructure Management
- Automated server provisioning for development environments
- Infrastructure monitoring and maintenance
- Resource scaling and optimization
- Disaster recovery and backup management

### Development Workflows
- Automated testing environment setup
- CI/CD pipeline infrastructure management
- Development server provisioning
- Performance testing infrastructure

### Cost Management
- Infrastructure cost monitoring and reporting
- Resource optimization recommendations
- Automated scaling based on usage patterns
- Budget tracking and alerts

## Typical Workflows

1. **Server Provisioning**: "Create a development server for testing new MCP integrations"
2. **Resource Monitoring**: "Check the current resource usage of our documentation servers"
3. **Backup Management**: "Schedule automated backups for our critical infrastructure"
4. **Cost Analysis**: "Generate a cost report for our current cloud infrastructure"

## Configuration Requirements

Required environment variables:
- `HETZNER_API_TOKEN`: Hetzner Cloud API token

Optional settings:
- Default server configurations
- Backup schedules and retention policies
- Monitoring thresholds and alerts

## Security Considerations

- **API Token Security**: Store tokens securely in environment variables
- **Access Control**: Use appropriate API permissions and scopes
- **Network Security**: Configure firewalls and security groups properly
- **Backup Security**: Encrypt backups and manage access controls
- **Audit Logging**: Monitor infrastructure changes and access

## Hetzner Cloud Features

- **Competitive Pricing**: Cost-effective cloud infrastructure
- **European Data Centers**: GDPR-compliant hosting in Germany
- **High Performance**: Fast NVMe SSDs and modern hardware
- **Simple API**: Straightforward REST API for automation
- **Transparent Pricing**: Clear, predictable pricing structure

## Related Tools

- **Docker MCP**: For containerized application deployment
- **GitHub MCP**: For CI/CD pipeline integration
- **MySQL MCP**: For database deployment and management

## Rogue Codex Applications

**Low to Medium Value for:**
- Hosting development environments for testing new features
- Infrastructure for running automated content generation workflows
- Backup solutions for critical documentation and data
- Cost-effective hosting for web-based tools and services

**Best Use Cases:**
- Teams needing European-based hosting for compliance
- Development teams requiring automated infrastructure management
- Organizations seeking cost-effective cloud infrastructure
- Projects requiring GDPR-compliant hosting solutions

**Considerations:**
- Requires cloud infrastructure needs beyond basic documentation
- Most valuable for teams managing development environments
- May be unnecessary for simple documentation-focused workflows
- Best suited for organizations with active cloud infrastructure requirements

---

*Last Updated: 2025-08-02*
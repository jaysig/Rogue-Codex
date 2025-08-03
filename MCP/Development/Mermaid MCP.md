# Mermaid MCP

**Repository:** https://github.com/hustcc/mcp-mermaid  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** Documentation & Visualization

Mermaid MCP enables Claude Code to generate, validate, and manipulate Mermaid diagrams for documentation, workflow visualization, and technical communication.

## Key Features

- **Diagram Generation**: Create flowcharts, sequence diagrams, and organizational charts
- **Syntax Validation**: Validate Mermaid syntax and structure
- **Multiple Formats**: Support for various Mermaid diagram types
- **Export Capabilities**: Generate SVG, PNG, and other formats
- **Live Preview**: Real-time diagram rendering and editing
- **Template Support**: Pre-built diagram templates and patterns

## Installation

### Global Installation (Recommended)
```bash
# Install the package
npm install -g mcp-mermaid

# Add to global MCP configuration
claude mcp add mermaid-server -- mcp-mermaid
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "mermaid-server": {
      "command": "npx",
      "args": ["-y", "mcp-mermaid"]
    }
  }
}
```

## Use Cases

### Documentation Enhancement
- Workflow diagrams for automation processes
- Organizational charts for company structures
- Process flows for content creation
- System architecture diagrams

### Content Visualization
- Tool relationship mapping
- Company ecosystem diagrams
- Learning path visualization
- Decision tree creation

### Process Documentation
- MCP integration workflows
- Content review processes
- User journey mapping
- Technical implementation flows

## Typical Workflows

1. **Workflow Diagram**: "Create a Mermaid flowchart for our content creation process"
2. **Company Structure**: "Generate an org chart for the companies in our registry"
3. **Process Flow**: "Create a sequence diagram for MCP server setup"
4. **Tool Mapping**: "Visualize the relationships between our tools categories"

## Supported Diagram Types

- **Flowcharts**: Process flows and decision trees
- **Sequence Diagrams**: Interaction and communication flows
- **Class Diagrams**: Object relationships and structures
- **State Diagrams**: System state transitions
- **Entity Relationship**: Database and data relationships
- **User Journey**: Experience mapping and touchpoints
- **Gantt Charts**: Project timelines and dependencies

## Configuration

The server may support configuration for:
- Default diagram themes and styling
- Export format preferences
- Rendering engine options
- Custom template libraries

## Security Considerations

- Validate Mermaid syntax to prevent injection
- Limit diagram complexity to prevent resource exhaustion
- Sanitize user input in diagram labels
- Control export file permissions

## Related Tools

- **Puppeteer MCP**: For diagram screenshot generation
- **Notion MCP**: For embedding diagrams in documentation
- **Excel MCP**: For data-driven diagram generation

## Rogue Codex Applications

**Extremely High Value for:**
- Visualizing automation workflows in AI Automations section
- Creating company relationship diagrams for Company Spotlight
- Tool ecosystem mapping for Tools section
- Process documentation for content creation workflows
- MCP integration architecture diagrams

**Recommended Priority**: High - Essential for improving documentation clarity and visual communication in Rogue Codex.

---

*Last Updated: 2025-08-02*
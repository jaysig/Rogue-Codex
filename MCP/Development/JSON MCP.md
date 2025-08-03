# JSON MCP

**Repository:** https://github.com/VadimNastoyashchy/json-mcp  
**Category:** Development  
**Scope:** Global (recommended)  
**Type:** Data Processing & Manipulation

JSON MCP provides comprehensive JSON data manipulation capabilities, enabling Claude Code to process, validate, transform, and analyze JSON data structures efficiently.

## Key Features

- **JSON Parsing & Validation**: Parse and validate JSON structure and syntax
- **Data Transformation**: Convert between JSON and other formats
- **Schema Validation**: Validate JSON against predefined schemas
- **Query Operations**: Extract specific data using JSONPath or similar queries
- **Manipulation Tools**: Add, modify, delete JSON properties and arrays
- **Pretty Printing**: Format and beautify JSON output

## Installation

### Global Installation (Recommended)
```bash
# Install the package
npm install -g json-mcp

# Add to global MCP configuration
claude mcp add json-server -- json-mcp
```

### Project Installation
```json
// .mcp.json
{
  "mcpServers": {
    "json-server": {
      "command": "npx",
      "args": ["-y", "json-mcp"]
    }
  }
}
```

## Use Cases

### Configuration Management
- MCP server configuration processing
- Settings file validation and transformation
- API configuration management
- Environment variable handling

### Data Processing
- API response processing and analysis
- Data migration between formats
- Content structure validation
- Metadata management for documentation

### Integration Tasks
- Format conversion for tool integrations
- Data pipeline processing
- API testing and validation
- Configuration file generation

## Typical Workflows

1. **Data Validation**: "Validate this JSON configuration file"
2. **Format Conversion**: "Convert this JSON to YAML format"
3. **Data Extraction**: "Extract all company names from this JSON array"
4. **Schema Validation**: "Check if this API response matches our expected schema"

## Configuration

The server may support configuration for:
- JSON schema validation rules
- Output formatting preferences
- Performance limits for large files
- Custom transformation templates

## Security Considerations

- Validate JSON input to prevent parsing attacks
- Limit file size and nesting depth
- Sanitize extracted data before use
- Be cautious with dynamic JSON evaluation

## Related Tools

- **Excel MCP**: For JSON to spreadsheet conversion
- **Notion MCP**: For structured data integration
- **OpenAPI Schema Explorer**: For API schema validation

## Rogue Codex Applications

**High Value for:**
- MCP configuration management and validation
- Tool evaluation data processing
- API integration configuration
- Metadata management for documentation structure

---

*Last Updated: 2025-08-02*
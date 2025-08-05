# Claude Code Overview

**Comprehensive guide to using Claude Code effectively with the Rogue Codex documentation system**

*Learn how to leverage custom commands, automation workflows, and best practices for maximum productivity*

## What is Claude Code?

Claude Code is Anthropic's official CLI tool that provides AI-powered assistance for software engineering and documentation tasks. For Rogue Codex, we use Claude Code primarily for:

- **Content Creation**: Adding companies, tools, and automation guides
- **Quality Assurance**: Ensuring consistency and readability standards
- **Workflow Automation**: Streamlining repetitive documentation tasks
- **Cross-Reference Management**: Maintaining accurate internal linking

## Custom Commands System

### Command Structure
Claude Code supports custom slash commands stored in `.claude/commands/` that automate complex workflows:

```bash
# Basic command usage
/command-name arguments

# Multi-argument commands
/add-company Runway, Pika Labs, Luma AI
/create-workflow Content Pipeline: Perplexity + ChatGPT + Canva
```

### Command Categories

**Content Creation Commands:**
- `/add-company` - Research and add companies to Company Spotlight
- `/add-tool` - Add and evaluate tools with full integration
- `/create-automation` - Build comprehensive automation guides

**Quality Assurance Commands:**
- `/quality-check` - Comprehensive content quality assessment
- `/sync-changes` - Update changelogs and cross-references

**Advanced Workflow Commands:**
- `/batch-company-update` - Update multiple companies simultaneously
- `/competitive-analysis` - Create comparative analysis documents
- `/create-workflow` - Design multi-tool integration workflows

## Best Practices for Rogue Codex

### Documentation Standards
1. **8th Grade Reading Level**: All content must be accessible and clear
2. **Template Consistency**: Use established templates for all content types
3. **SEO Optimization**: Structure content for search engine visibility
4. **Cross-Linking**: Maintain accurate internal references

### Workflow Efficiency
1. **Batch Operations**: Use commands to handle multiple items simultaneously
2. **Quality First**: Always run quality checks before publishing
3. **Changelog Management**: Keep Recent Changes.md current with all updates
4. **Timestamp Accuracy**: Maintain consistent "Last Updated" formats

### Command Usage Guidelines
1. **Research Phase**: Commands automatically gather comprehensive information
2. **Template Application**: All commands enforce template compliance
3. **Integration Updates**: Commands handle cross-referencing automatically
4. **Quality Assurance**: Built-in checks for readability and consistency

## Command Integration with Repository Structure

### Company Spotlight Workflow
```
/add-company → Research → Template → Category Placement → README Updates → Changelog
```

### Tool Evaluation Workflow
```
/add-tool → Research → Evaluation → Category Integration → Cross-References → Updates
```

### Automation Development Workflow
```
/create-automation → Structure → n8n/Make.com → LLM Alternatives → Pain Points → Navigation
```

## Advanced Features

### Multi-Tool Workflows
Commands can coordinate between multiple tools and platforms:
- Research with Perplexity and web search
- Content creation with AI assistance
- File management with proper organization
- Quality assurance with automated checks

### Automation Integration
Commands integrate with the repository's automation philosophy:
- **n8n Implementation**: Technical automation paths
- **Make.com Implementation**: User-friendly alternatives  
- **LLM-Only Solutions**: Simple conversation-based alternatives

### SEO and Discoverability
Commands automatically optimize content for:
- Search engine visibility
- Internal linking structure
- Cross-reference accuracy
- Navigation consistency

## Getting Started

1. **Install Claude Code**: Follow Anthropic's installation guide
2. **Navigate to Rogue Codex**: Ensure you're in the repository root
3. **Use Commands**: Commands are available immediately in `.claude/commands/`
4. **Check Results**: Review generated content for accuracy and completeness

## Command Reference

See individual command guides in the [`Commands/`](Commands/) folder for detailed usage instructions and examples.

## Performance Benefits

Custom commands provide significant productivity improvements:
- **Time Savings**: 70-80% reduction in manual documentation time
- **Consistency**: Automated template compliance and quality standards
- **Error Reduction**: Built-in validation and cross-reference checking
- **SEO Optimization**: Automatic search engine visibility improvements

---

*Last Updated: 2025-08-04*
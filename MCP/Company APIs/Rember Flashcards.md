# Rember Flashcards MCP Server

**Repository:** https://github.com/rember/rember-mcp  
**Category:** Company APIs  
**Scope:** Global (recommended)  
**Type:** Learning & Spaced Repetition  
**API Required:** Yes (Rember API Key)

An MCP server that allows Claude to create flashcards for Rember, a spaced repetition learning platform, transforming conversations and documents into active recall study materials.

## Key Features

- **Conversation-to-Flashcards**: Generate flashcards directly from chat conversations
- **PDF Processing**: Create flashcards from PDF documents
- **AI-Assisted Generation**: Intelligent flashcard creation with optimal question-answer pairs
- **Spaced Repetition Integration**: Direct integration with Rember learning platform

## Installation

### Quick Installation
```bash
# Install via NPX with API key
npx -y @getrember/mcp --api-key=YOUR_REMBER_API_KEY
```

### Configuration
```json
// claude_desktop_config.json
{
  "mcpServers": {
    "rember": {
      "command": "npx",
      "args": ["-y", "@getrember/mcp", "--api-key=YOUR_REMBER_API_KEY"]
    }
  }
}
```

## Setup Requirements

### 1. Rember Account
1. Create account at Rember platform
2. Navigate to API settings
3. Generate API key for MCP integration
4. Note usage limits and subscription tier

### 2. API Key Configuration
```bash
# Environment variable (recommended)
export REMBER_API_KEY="your-rember-api-key"
```

## Available Tools

### create_flashcards
Primary tool for generating flashcards from conversation notes and context.

## Use Cases

### Study Material Creation
- **Lecture Notes**: Convert lecture discussions into flashcards
- **Reading Comprehension**: Transform reading sessions into review materials
- **Meeting Notes**: Create flashcards from important meeting points
- **Research Sessions**: Generate study cards from research conversations

### Learning Enhancement
- **Concept Reinforcement**: Create cards for key concepts discussed
- **Terminology Learning**: Generate vocabulary and definition cards
- **Process Steps**: Break down procedures into sequential flashcards
- **Problem-Solving**: Create cards for common problem patterns

### Document Processing
- **PDF Study Guides**: Extract key information from PDF documents
- **Academic Papers**: Create flashcards from research papers
- **Textbook Chapters**: Generate review materials from textbook content
- **Technical Documentation**: Create cards for technical procedures

## Natural Language Triggers

Users can naturally request flashcard creation with phrases like:
- "Help me remember this"
- "Create a few flashcards"
- "Add to Rember"
- "Make flashcards from this conversation"
- "Generate study materials"

## Integration Examples

### Conversation Learning
```
User: [Discusses complex topic with Claude]
User: "Help me remember this"
AI: Creates targeted flashcards covering key concepts from conversation
Result: Flashcards automatically added to Rember for spaced repetition study
```

### Document Study
```
User: [Shares PDF or document content]
User: "Create flashcards from this material"
AI: Analyzes content and generates appropriate question-answer pairs
Result: Comprehensive flashcard set ready for study
```

## Best Practices

### Effective Flashcard Design
- **Clear Questions**: Ensure questions are specific and unambiguous
- **Concise Answers**: Keep answers focused and memorable
- **Progressive Difficulty**: Start with basic concepts, build complexity
- **Context Inclusion**: Provide enough context for understanding

### Learning Optimization
- **Spaced Review**: Leverage Rember's spaced repetition algorithm
- **Regular Updates**: Continuously add new flashcards from ongoing learning
- **Topic Organization**: Group related flashcards for coherent study sessions
- **Performance Tracking**: Monitor retention rates and adjust study patterns

## Workflow Integration

### Study Session Enhancement
1. Have learning conversation with Claude
2. Request flashcard creation from key points
3. Review generated flashcards in Rember
4. Use spaced repetition for optimal retention

### Research Documentation
1. Conduct research with AI assistance
2. Generate flashcards for important findings
3. Build comprehensive knowledge base
4. Review regularly for long-term retention

## Related Tools

- **Memory MCP**: Store learning preferences and study patterns
- **Browser-use MCP**: Research topics for flashcard creation
- **Exa AI Search**: Gather additional context for comprehensive flashcards

## Security Considerations

- **API Key Protection**: Store keys securely, never expose in client code
- **Learning Privacy**: Be mindful of sensitive study content
- **Usage Monitoring**: Track API usage to manage costs
- **Data Backup**: Ensure flashcards are backed up appropriately

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key validity and Rember account status
- **Flashcard Quality**: Provide clear context for better question generation
- **Sync Issues**: Check Rember platform for flashcard synchronization
- **Rate Limiting**: Monitor API usage limits

**Optimization Tips:**
- Provide rich context for better flashcard generation
- Use specific, focused conversations for targeted flashcards
- Review and edit generated flashcards for optimal learning
- Combine with other learning tools for comprehensive study approach

---

*Last Updated: 2025-08-02*
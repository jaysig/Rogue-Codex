# Gemini CLI Setup Guide

A comprehensive guide to setting up and using Google Gemini CLI for AI-powered development workflows.

## Overview

Google Gemini CLI is a command-line interface for Google's Gemini AI models, allowing you to interact with AI directly from your terminal for code generation, analysis, and automation tasks.

## Installation

### Prerequisites
- Python 3.8 or higher
- Google Cloud account with Gemini API access
- API key for Gemini

### Step 1: Install Gemini CLI
```bash
# Install via pip
pip install google-generativeai

# Or install the official CLI tool
pip install gemini-cli
```

### Step 2: Set Up Authentication
```bash
# Set your API key as environment variable
export GOOGLE_API_KEY="your-gemini-api-key"

# Or add to your shell profile
echo 'export GOOGLE_API_KEY="your-gemini-api-key"' >> ~/.zshrc
source ~/.zshrc
```

### Step 3: Verify Installation
```bash
# Test the installation
gemini --version
gemini --help
```

## Basic Usage

### Simple Queries
```bash
# Basic text generation
gemini "Write a Python function to calculate fibonacci numbers"

# Code generation
gemini "Create a React component for a todo list"

# Code explanation
gemini "Explain this code: def quicksort(arr): ..."
```

### File Operations
```bash
# Process a file
gemini --file input.txt "Summarize this content"

# Generate code from description
gemini --output app.py "Create a Flask web application"

# Code review
gemini --file code.py "Review this code for best practices"
```

## Advanced Configuration

### Model Selection
```bash
# Use specific Gemini model
gemini --model gemini-1.5-pro "Your prompt"

# Available models
gemini --list-models
```

### Configuration File
Create `~/.gemini/config.json`:
```json
{
  "api_key": "your-api-key",
  "default_model": "gemini-1.5-pro",
  "temperature": 0.7,
  "max_tokens": 4000,
  "safety_settings": {
    "HARM_CATEGORY_HARASSMENT": "BLOCK_MEDIUM_AND_ABOVE",
    "HARM_CATEGORY_HATE_SPEECH": "BLOCK_MEDIUM_AND_ABOVE",
    "HARM_CATEGORY_SEXUALLY_EXPLICIT": "BLOCK_MEDIUM_AND_ABOVE",
    "HARM_CATEGORY_DANGEROUS_CONTENT": "BLOCK_MEDIUM_AND_ABOVE"
  }
}
```

## Development Workflows

### Code Generation
```bash
# Generate complete functions
gemini "Write a Python function that validates email addresses"

# Generate classes
gemini "Create a JavaScript class for managing user sessions"

# Generate tests
gemini "Write unit tests for this function: def calculate_tax(income): ..."
```

### Code Review
```bash
# Review specific files
gemini --file src/main.py "Review this code for security issues"

# Review entire directories
gemini --directory src/ "Review all Python files for best practices"
```

### Documentation
```bash
# Generate README
gemini --file src/ "Generate a comprehensive README for this project"

# Generate API documentation
gemini --file api.py "Generate OpenAPI documentation for this API"
```

## Integration with Development Tools

### Git Integration
```bash
# Generate commit messages
git diff | gemini "Generate a concise commit message"

# Review pull requests
git diff main | gemini "Review these changes for potential issues"
```

### IDE Integration
```bash
# VS Code/Cursor integration
# Add to settings.json
{
  "terminal.integrated.env.osx": {
    "GOOGLE_API_KEY": "your-api-key"
  }
}
```

### CI/CD Integration
```bash
# GitHub Actions example
- name: Code Review
  run: |
    gemini --file src/ "Review code for security and quality issues"
```

## Best Practices

### Prompt Engineering
```bash
# Be specific
gemini "Write a Python function that validates email addresses using regex, includes error handling, and returns a boolean"

# Provide context
gemini "Given this React component structure, create a similar component for user profiles"

# Use examples
gemini "Create a function like this: def add(a, b): return a + b, but for multiplication"
```

### Error Handling
```bash
# Check API limits
gemini --check-limits

# Handle rate limiting
gemini --retry 3 "Your prompt"

# Validate outputs
gemini "Generate valid JSON only: create a user object"
```

## Troubleshooting

### Common Issues

#### API Key Problems
```bash
# Check if API key is set
echo $GOOGLE_API_KEY

# Test API connection
gemini --test-connection
```

#### Rate Limiting
```bash
# Check usage
gemini --usage

# Implement backoff
gemini --backoff 1000 "Your prompt"
```

#### Model Availability
```bash
# Check available models
gemini --list-models

# Use fallback model
gemini --fallback gemini-1.0-pro "Your prompt"
```

### Getting Help
```bash
# View all options
gemini --help

# Get specific help
gemini --help models
gemini --help configuration
```

## Advanced Features

### Batch Processing
```bash
# Process multiple files
for file in *.py; do
  gemini --file "$file" "Add type hints to this function"
done

# Process with different prompts
gemini --batch prompts.txt files/
```

### Custom Scripts
```bash
#!/bin/bash
# code-review.sh
gemini --file "$1" "Review this code for:
- Security vulnerabilities
- Performance issues
- Best practices
- Readability improvements"
```

### API Integration
```python
import google.generativeai as genai

genai.configure(api_key='your-api-key')
model = genai.GenerativeModel('gemini-1.5-pro')

response = model.generate_content("Your prompt")
print(response.text)
```

## Security Considerations

### API Key Security
```bash
# Never commit API keys
echo "GOOGLE_API_KEY=your-key" >> .env
echo ".env" >> .gitignore

# Use environment variables
export GOOGLE_API_KEY="your-key"
```

### Content Safety
```bash
# Enable safety filters
gemini --safety-filters "Your prompt"

# Custom safety settings
gemini --safety-config safety.json "Your prompt"
```

## Performance Optimization

### Caching
```bash
# Enable response caching
gemini --cache "Your prompt"

# Clear cache
gemini --clear-cache
```

### Parallel Processing
```bash
# Process multiple requests
gemini --parallel 5 "Prompt 1" "Prompt 2" "Prompt 3"
```

## Resources

### Documentation
- [Gemini API Documentation](https://ai.google.dev/docs)
- [Gemini CLI GitHub](https://github.com/google/generative-ai-python)
- [Google AI Studio](https://aistudio.google.com/)

### Community
- [Google AI Discord](https://discord.gg/googleai)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/gemini)
- [Reddit r/GoogleAI](https://reddit.com/r/GoogleAI)

---

*Last Updated: July 27, 2025* 
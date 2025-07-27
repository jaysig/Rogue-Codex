# n8n Setup Guide

A comprehensive guide to setting up and using n8n for workflow automation and AI integration.

## Overview

n8n is a powerful workflow automation tool that allows you to connect different services and create automated workflows. It's particularly useful for integrating AI services and automating repetitive tasks.

## Installation

### Prerequisites
- Node.js 16 or higher
- npm or yarn package manager
- Database (PostgreSQL, MySQL, or SQLite)

### Step 1: Install n8n
```bash
# Install n8n globally
npm install n8n -g

# Or using yarn
yarn global add n8n
```

### Step 2: Start n8n
```bash
# Start n8n
n8n start

# Start with custom port
n8n start --port 5678

# Start with database
n8n start --db-type postgresdb --db-host localhost --db-port 5432 --db-name n8n --db-user n8n --db-password password
```

### Step 3: Access n8n
1. Open your browser
2. Navigate to `http://localhost:5678`
3. Complete the initial setup

## Core Features Setup

### Workflow Creation

#### Visual Workflow Builder
- **Drag-and-Drop Interface**: Create workflows visually
- **Node Library**: Access 200+ pre-built nodes
- **Conditional Logic**: Add if/then conditions
- **Error Handling**: Configure error handling and retries

#### Basic Workflow Example
```json
{
  "name": "AI Content Generation",
  "nodes": [
    {
      "id": "trigger",
      "type": "n8n-nodes-base.webhook",
      "position": [240, 300],
      "parameters": {
        "httpMethod": "POST",
        "path": "generate-content"
      }
    },
    {
      "id": "openai",
      "type": "n8n-nodes-base.openAi",
      "position": [460, 300],
      "parameters": {
        "operation": "completion",
        "model": "gpt-4",
        "prompt": "{{$json.prompt}}",
        "maxTokens": 1000
      }
    },
    {
      "id": "slack",
      "type": "n8n-nodes-base.slack",
      "position": [680, 300],
      "parameters": {
        "operation": "postMessage",
        "channel": "#content",
        "text": "{{$json.choices[0].text}}"
      }
    }
  ],
  "connections": {
    "trigger": {
      "main": [["openai"]]
    },
    "openai": {
      "main": [["slack"]]
    }
  }
}
```

### AI Integration

#### OpenAI Integration
```json
{
  "id": "openai_node",
  "type": "n8n-nodes-base.openAi",
  "parameters": {
    "operation": "completion",
    "model": "gpt-4",
    "prompt": "Write a blog post about {{$json.topic}}",
    "temperature": 0.7,
    "maxTokens": 2000,
    "apiKey": "{{$env.OPENAI_API_KEY}}"
  }
}
```

#### Claude Integration
```json
{
  "id": "claude_node",
  "type": "n8n-nodes-base.httpRequest",
  "parameters": {
    "url": "https://api.anthropic.com/v1/messages",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "x-api-key": "{{$env.CLAUDE_API_KEY}}",
      "anthropic-version": "2023-06-01"
    },
    "body": {
      "model": "claude-3-sonnet-20240229",
      "max_tokens": 1000,
      "messages": [
        {
          "role": "user",
          "content": "{{$json.prompt}}"
        }
      ]
    }
  }
}
```

## Advanced Configuration

### Environment Variables
```bash
# Create .env file
cat > .env << EOF
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=your-password
OPENAI_API_KEY=your-openai-key
CLAUDE_API_KEY=your-claude-key
DATABASE_URL=postgresql://user:password@localhost:5432/n8n
EOF

# Start with environment file
n8n start --env-file .env
```

### Database Configuration
```bash
# PostgreSQL setup
n8n start \
  --db-type postgresdb \
  --db-host localhost \
  --db-port 5432 \
  --db-name n8n \
  --db-user n8n \
  --db-password your-password

# MySQL setup
n8n start \
  --db-type mysqldb \
  --db-host localhost \
  --db-port 3306 \
  --db-name n8n \
  --db-user n8n \
  --db-password your-password
```

### Docker Deployment
```yaml
# docker-compose.yml
version: '3.8'
services:
  n8n:
    image: n8nio/n8n
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=your-password
      - DATABASE_TYPE=postgresdb
      - DB_POSTGRESDB_HOST=postgres
      - DB_POSTGRESDB_PORT=5432
      - DB_POSTGRESDB_DATABASE=n8n
      - DB_POSTGRESDB_USER=n8n
      - DB_POSTGRESDB_PASSWORD=your-password
    volumes:
      - n8n_data:/home/node/.n8n
    depends_on:
      - postgres

  postgres:
    image: postgres:13
    environment:
      - POSTGRES_DB=n8n
      - POSTGRES_USER=n8n
      - POSTGRES_PASSWORD=your-password
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  n8n_data:
  postgres_data:
```

## Use Case Examples

### Content Creation Workflow

#### Blog Post Generation
```json
{
  "name": "Blog Post Creator",
  "nodes": [
    {
      "id": "webhook",
      "type": "n8n-nodes-base.webhook",
      "parameters": {
        "httpMethod": "POST",
        "path": "create-blog"
      }
    },
    {
      "id": "research",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "https://api.example.com/research",
        "method": "GET",
        "qs": {
          "topic": "{{$json.topic}}"
        }
      }
    },
    {
      "id": "generate_content",
      "type": "n8n-nodes-base.openAi",
      "parameters": {
        "operation": "completion",
        "model": "gpt-4",
        "prompt": "Write a blog post about {{$json.topic}} using this research: {{$json.research}}"
      }
    },
    {
      "id": "wordpress",
      "type": "n8n-nodes-base.wordpress",
      "parameters": {
        "operation": "createPost",
        "title": "{{$json.title}}",
        "content": "{{$json.content}}",
        "status": "draft"
      }
    }
  ]
}
```

#### Social Media Automation
```json
{
  "name": "Social Media Manager",
  "nodes": [
    {
      "id": "schedule",
      "type": "n8n-nodes-base.cron",
      "parameters": {
        "rule": {
          "hour": 9,
          "minute": 0
        }
      }
    },
    {
      "id": "generate_post",
      "type": "n8n-nodes-base.openAi",
      "parameters": {
        "operation": "completion",
        "model": "gpt-4",
        "prompt": "Create a social media post about technology trends"
      }
    },
    {
      "id": "twitter",
      "type": "n8n-nodes-base.twitter",
      "parameters": {
        "operation": "tweet",
        "text": "{{$json.choices[0].text}}"
      }
    },
    {
      "id": "linkedin",
      "type": "n8n-nodes-base.linkedIn",
      "parameters": {
        "operation": "createPost",
        "text": "{{$json.choices[0].text}}"
      }
    }
  ]
}
```

### Data Processing Workflow

#### Market Research
```json
{
  "name": "Market Research",
  "nodes": [
    {
      "id": "manual_trigger",
      "type": "n8n-nodes-base.manualTrigger"
    },
    {
      "id": "scrape_data",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "https://api.example.com/market-data",
        "method": "GET"
      }
    },
    {
      "id": "analyze_data",
      "type": "n8n-nodes-base.openAi",
      "parameters": {
        "operation": "completion",
        "model": "gpt-4",
        "prompt": "Analyze this market data and provide insights: {{$json.data}}"
      }
    },
    {
      "id": "send_report",
      "type": "n8n-nodes-base.emailSend",
      "parameters": {
        "toEmail": "team@company.com",
        "subject": "Market Research Report",
        "text": "{{$json.choices[0].text}}"
      }
    }
  ]
}
```

## Best Practices

### Workflow Design

#### Modular Design
- **Break Down Tasks**: Split complex workflows into smaller, manageable steps
- **Reusable Components**: Create reusable nodes for common tasks
- **Error Handling**: Add proper error handling at each step
- **Monitoring**: Include monitoring and logging throughout

#### Performance Optimization
- **Parallel Processing**: Run independent steps in parallel
- **Caching**: Cache expensive operations
- **Resource Management**: Monitor and optimize resource usage
- **Scaling**: Design workflows to scale with demand

### Security

#### API Key Management
```bash
# Use environment variables
export OPENAI_API_KEY="your-key"
export CLAUDE_API_KEY="your-key"

# Or use n8n's credential system
# Go to Settings > Credentials to add API keys securely
```

#### Access Control
- **Authentication**: Enable basic auth or OAuth
- **API Rate Limiting**: Configure rate limits for external APIs
- **Data Encryption**: Encrypt sensitive data
- **Audit Logging**: Log all access and modifications

## Troubleshooting

### Common Issues

#### Connection Problems
```bash
# Check n8n status
n8n status

# Check logs
n8n logs

# Restart n8n
n8n restart
```

#### Database Issues
```bash
# Check database connection
n8n start --db-type postgresdb --db-host localhost --db-port 5432 --db-name n8n --db-user n8n --db-password password

# Reset database (WARNING: This will delete all data)
n8n start --reset-db
```

#### Performance Issues
- **Monitor Resource Usage**: Check CPU, memory, and database usage
- **Optimize Queries**: Review and optimize database queries
- **Cache Results**: Implement caching for expensive operations
- **Scale Resources**: Increase resources if needed

### Debugging

#### Enable Debug Mode
```bash
# Start with debug logging
n8n start --log-level debug

# Or set environment variable
export N8N_LOG_LEVEL=debug
n8n start
```

#### Test Individual Nodes
- Use the "Test" button in each node
- Check the execution log for detailed information
- Use the "Execute Workflow" feature to test specific nodes

## Integration Examples

### Development Tools Integration

#### Git Integration
```json
{
  "id": "github_webhook",
  "type": "n8n-nodes-base.github",
  "parameters": {
    "operation": "getIssues",
    "repository": "owner/repo",
    "state": "open"
  }
}
```

#### CI/CD Integration
```json
{
  "id": "jenkins",
  "type": "n8n-nodes-base.jenkins",
  "parameters": {
    "operation": "build",
    "jobName": "deploy-to-staging"
  }
}
```

### AI Service Integration

#### Multi-AI Provider
```json
{
  "id": "ai_router",
  "type": "n8n-nodes-base.switch",
  "parameters": {
    "rules": {
      "rules": [
        {
          "conditions": {
            "options": {
              "caseSensitive": true,
              "leftValue": "",
              "typeValidation": "strict"
            },
            "conditions": [
              {
                "id": "provider",
                "leftValue": "{{$json.provider}}",
                "rightValue": "openai",
                "operator": {
                  "type": "string",
                  "operation": "equals"
                }
              }
            ],
            "combinator": "and"
          },
          "output": 0
        }
      ]
    }
  }
}
```

## Resources

### Documentation
- [n8n Documentation](https://docs.n8n.io)
- [API Reference](https://docs.n8n.io/api)
- [Tutorial Videos](https://n8n.io/tutorials)

### Community
- [n8n Discord](https://discord.gg/n8n)
- [Community Forum](https://community.n8n.io)
- [GitHub Examples](https://github.com/n8n-io/n8n/tree/master/packages/cli/templates)

### Support
- [Help Center](https://help.n8n.io)
- [Contact Support](https://n8n.io/support)
- [Status Page](https://status.n8n.io)

---

*Last Updated: July 27, 2025* 
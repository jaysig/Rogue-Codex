# Stripe Payments MCP Server

**Repository:** https://github.com/stripe/agent-toolkit  
**Category:** Company APIs  
**Scope:** Project (recommended for security)  
**Type:** Payment Processing & Financial Services  
**API Required:** Yes (Stripe API Key)  
**Languages:** Python, TypeScript

The Stripe Agent Toolkit enables integration of Stripe APIs with AI agent frameworks through function calling, supporting comprehensive payment operations and usage-based billing for AI interactions.

## Key Features

- **Multi-Framework Support**: OpenAI Agent SDK, LangChain, CrewAI, Vercel AI SDK
- **Function Calling**: Direct Stripe API integration through AI functions
- **Context-Based Operations**: Support for connected accounts and marketplace
- **Model Context Protocol**: Full MCP support for AI assistants
- **Metered Billing**: Usage-based billing for AI interactions
- **Remote MCP Server**: Hosted server option available

## Installation

### Python Installation
```bash
# Install Python package
pip install stripe-agent-toolkit

# Requirements: Python 3.11+
```

### TypeScript Installation
```bash
# Install Node package
npm install @stripe/agent-toolkit

# Requirements: Node 18+
```

### MCP Configuration
```json
// .mcp.json
{
  "mcpServers": {
    "stripe": {
      "command": "stripe-agent-toolkit",
      "args": ["--api-key", "sk_test_..."],
      "env": {
        "STRIPE_SECRET_KEY": "sk_test_..."
      }
    }
  }
}
```

## Setup Requirements

### 1. Stripe Account
1. Create Stripe account at stripe.com
2. Access dashboard and API keys section
3. Generate test and live API keys
4. Configure webhook endpoints if needed

### 2. API Key Configuration
```python
# Python configuration example
stripe_agent_toolkit = StripeAgentToolkit(
    secret_key="sk_test_...",
    configuration={
        "actions": {
            "payment_links": {
                "create": True
            },
            "customers": {
                "create": True,
                "update": True
            }
        }
    }
)
```

## Available Operations

### Customer Management
- **Create Customers**: New customer account creation
- **Update Profiles**: Modify customer information
- **Payment Methods**: Manage stored payment methods
- **Billing History**: Access customer transaction history

### Product and Pricing
- **Product Creation**: Set up products and services
- **Price Management**: Configure pricing models and tiers
- **Subscription Plans**: Create recurring billing plans
- **Discount Codes**: Generate and manage coupons

### Payment Processing
- **Payment Links**: Generate shareable payment links
- **Invoice Management**: Create and send invoices
- **Subscription Handling**: Manage recurring payments
- **Refund Processing**: Handle payment reversals

### Advanced Features
- **Connected Accounts**: Marketplace and platform operations
- **Usage-Based Billing**: Track and bill for API usage
- **Webhook Handling**: Process real-time payment events
- **Analytics**: Payment and revenue analytics

## Use Cases

### E-Commerce Integration
- **Payment Processing**: Handle one-time payments
- **Shopping Cart**: Integrate payment flows
- **Order Management**: Track and fulfill orders
- **Customer Accounts**: Manage customer payment data

### SaaS Billing
- **Subscription Management**: Recurring billing for software
- **Usage Metering**: Track and bill for usage
- **Plan Upgrades**: Handle subscription changes
- **Trial Periods**: Manage free trial conversions

### Marketplace Operations
- **Multi-Party Payments**: Split payments between parties
- **Connected Accounts**: Manage seller accounts
- **Commission Tracking**: Calculate and distribute fees
- **Payout Management**: Handle seller payments

### AI Billing Integration
- **Token Usage Billing**: Bill for AI API consumption
- **Conversation Metering**: Track AI interaction costs
- **Dynamic Pricing**: Adjust pricing based on usage patterns
- **Cost Attribution**: Track costs per user or project

## Configuration Examples

### Basic Payment Setup
```python
# Create payment link for product
payment_link = stripe_toolkit.create_payment_link(
    price_data={
        "currency": "usd",
        "product_data": {"name": "AI Consultation"},
        "unit_amount": 5000  # $50.00
    }
)
```

### Subscription Configuration
```python
# Set up recurring subscription
subscription = stripe_toolkit.create_subscription(
    customer_id="cus_...",
    price_id="price_...",
    metadata={"ai_usage_tier": "premium"}
)
```

## Security Best Practices

### API Key Management
- **Test vs Live Keys**: Use test keys for development
- **Environment Variables**: Store keys securely
- **Key Rotation**: Regularly update API keys
- **Restricted Keys**: Use keys with minimal required permissions

### PCI Compliance
- **No Card Storage**: Never store card data directly
- **Secure Transmission**: Use HTTPS for all communications
- **Token Usage**: Use Stripe tokens for sensitive data
- **Audit Trails**: Maintain payment operation logs

## Framework Integration

### OpenAI Agent SDK
```python
from openai import OpenAI
from stripe_agent_toolkit import StripeAgentToolkit

client = OpenAI()
stripe_toolkit = StripeAgentToolkit(secret_key="sk_test_...")

# Use toolkit in OpenAI function calls
```

### LangChain Integration
```python
from langchain.agents import AgentExecutor
from stripe_agent_toolkit import StripeAgentToolkit

# Integrate Stripe tools with LangChain agents
```

## Middleware Features

### Usage-Based Billing
- **API Call Tracking**: Monitor AI interaction costs
- **Automatic Billing**: Bill customers based on usage
- **Cost Analytics**: Analyze cost per interaction
- **Budget Controls**: Set spending limits and alerts

### Remote MCP Server
- **Hosted Option**: Use Stripe's hosted MCP server
- **Reduced Setup**: Minimal local configuration
- **Scalability**: Handle high-volume operations
- **Reliability**: Enterprise-grade uptime

## Related Tools

- **Memory MCP**: Store customer preferences and payment history
- **Make MCP**: Automate payment workflows
- **Supabase MCP**: Store payment metadata and analytics
- **Browser-use MCP**: Test payment flows

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key validity and permissions
- **Webhook Issues**: Check endpoint configuration and SSL
- **Rate Limiting**: Monitor API usage limits
- **Test Mode**: Ensure using correct environment keys

**Best Practices:**
- Start with test environment
- Use idempotency keys for critical operations
- Implement proper error handling
- Monitor webhook delivery and retry failed events

---

*Last Updated: 2025-08-02*
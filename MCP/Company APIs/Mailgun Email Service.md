# Mailgun Email Service MCP Server

**Repository:** https://github.com/mailgun/mailgun-mcp-server  
**Category:** Company APIs  
**Scope:** Project (recommended for security)  
**Type:** Email Service & Marketing  
**API Required:** Yes (Mailgun API Key)  
**License:** Apache-2.0

A Model Context Protocol (MCP) server implementation for Mailgun, enabling MCP-compatible AI clients like Claude Desktop to interact with Mailgun email services for sending emails and retrieving delivery statistics.

## Key Features

- **Email Sending**: Send customized emails through Mailgun API
- **Delivery Statistics**: Fetch email delivery and engagement metrics
- **AI Integration**: Direct Mailgun integration with AI workflows
- **Statistical Analysis**: Email performance data retrieval
- **Transactional Email**: Support for automated email workflows

## Installation

### Prerequisites
- Node.js (v18 or higher)
- Git
- Claude Desktop
- Active Mailgun account with API key

### Manual Installation
```bash
# Clone the repository
git clone https://github.com/mailgun/mailgun-mcp-server.git

# Navigate to directory
cd mailgun-mcp-server

# Install dependencies
npm install
```

### Project Configuration
```json
// .mcp.json
{
  "mcpServers": {
    "mailgun": {
      "command": "node",
      "args": ["/path/to/mailgun-mcp-server/src/index.js"],
      "env": {
        "MAILGUN_API_KEY": "YOUR_MAILGUN_API_KEY",
        "MAILGUN_DOMAIN": "YOUR_MAILGUN_DOMAIN"
      }
    }
  }
}
```

## Setup Requirements

### 1. Mailgun Account Setup
1. Create account at https://mailgun.com
2. Add and verify your domain
3. Generate API key from Mailgun dashboard
4. Note your domain name for configuration

### 2. API Key Configuration
```bash
# Environment variables (recommended)
export MAILGUN_API_KEY="your-mailgun-api-key"
export MAILGUN_DOMAIN="your-verified-domain.com"
```

## Available Capabilities

### Email Sending
- Send transactional emails
- Custom email templates
- Recipient management
- Attachment support

### Statistics Retrieval
- Email delivery rates
- Open and click tracking
- Bounce and complaint data
- Campaign performance metrics

## Use Cases

### Automated Email Workflows
- Order confirmations and receipts
- Welcome email sequences
- Password reset notifications
- System alerts and notifications

### Marketing Automation
- Newsletter distribution
- Promotional campaign management
- Customer engagement tracking
- A/B testing for email content

### Business Communication
- Customer support responses
- Meeting reminders and follow-ups
- Invoice and billing notifications
- Product update announcements

### Analytics and Reporting
- Email performance monitoring
- Delivery success tracking
- Engagement metric analysis
- Campaign ROI calculation

## Integration Examples

### Send Email Workflow
```
User: "Send a welcome email to new user@example.com"
AI: Uses Mailgun MCP to compose and send welcome email
Result: Email sent with delivery confirmation
```

### Performance Analysis
```
User: "Get email statistics for last week's campaign"
AI: Retrieves delivery and engagement data via Mailgun
Result: Comprehensive campaign performance report
```

## Testing and Development

### Run Tests
```bash
# Run test suite
NODE_ENV=test npm test
```

### Debugging
- Server communicates over stdio
- Reference MCP debugging documentation
- Monitor Mailgun dashboard for delivery status

## Security Considerations

- **API Key Protection**: Store keys in environment variables only
- **Domain Verification**: Ensure domains are properly verified
- **Rate Limiting**: Monitor API usage limits
- **Email Compliance**: Follow CAN-SPAM and GDPR regulations

## Current Status

**⚠️ Early Stage Project**
- Limited functionality in current version
- Potential restrictions on email sending capabilities
- Active development with ongoing improvements
- Open to community contributions

## Pricing Considerations

- **Mailgun API Costs**: Pay per email sent
- **Free Tier**: Limited free emails per month
- **Volume Pricing**: Discounts for high-volume senders
- **Additional Features**: Advanced analytics may require higher tiers

## Configuration Options

### Email Settings
- Custom from addresses
- Reply-to configuration
- Email templates
- Tracking preferences

### Delivery Options
- Send scheduling
- Priority levels
- Retry mechanisms
- Webhook notifications

## Related Tools

- **Memory MCP**: Store email templates and recipient lists
- **Make MCP**: Automate email workflow triggers
- **Browser-use MCP**: For email verification and testing

## Troubleshooting

**Common Issues:**
- **API Key Errors**: Verify key is valid and has proper permissions
- **Domain Issues**: Ensure domain is verified in Mailgun
- **Delivery Problems**: Check recipient addresses and spam settings
- **Rate Limiting**: Monitor usage against Mailgun limits

**Best Practices:**
- Test with small recipient lists first
- Monitor delivery rates and engagement
- Keep email lists clean and updated
- Follow email marketing best practices

## Contributing

- Apache-2.0 license allows modifications
- Pull requests welcome for improvements
- Follow Mailgun's contribution guidelines
- Test thoroughly before submitting changes

---

*Last Updated: 2025-08-02*
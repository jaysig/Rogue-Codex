# Product Marketer Automations

Easy automation workflows to help product marketers create content, track campaigns, and understand customers using simple AI tools.

## What This Is

These automations help product marketers spend less time on repetitive tasks and more time on creative strategy. Like having a marketing assistant that works 24/7.

**Who This Helps:** Product marketers, marketing coordinators, brand managers  
**Tools Used:** n8n (free automation tool), social media platforms, AI writing tools  
**Time Saved:** 15-20 hours per week  

---

## 📱 Social Media Content Factory

**What It Does:** Creates and posts content across all your social media platforms automatically.

**How It Works:**
1. You write one basic idea or product update
2. AI creates different versions for each platform
3. Automatically posts at the best times
4. Tracks which posts perform well
5. Suggests improvements for next time

**What You Need:**
- Social media accounts (LinkedIn, Twitter, Instagram, Facebook)
- n8n automation account
- AI writing tool (ChatGPT or similar)
- Content calendar template

**Step-by-Step n8n Setup:**

1. **Create New Workflow**
   - Go to n8n and click "New workflow"
   - Name it "Social Media Content Factory"

2. **Add Your Starting Point**
   - Add a "Manual Trigger" node (this lets you start the workflow when ready)
   - Or add a "Schedule Trigger" to post automatically every day

3. **Connect Social Media Accounts**
   - Add nodes for each platform you use:
     - "Twitter" node for X/Twitter posts
     - "LinkedIn" node for LinkedIn posts  
     - "Facebook" node for Facebook posts
   - Click each node and connect your accounts (n8n will walk you through this)

4. **Add AI Writing Helper**
   - Add an "OpenAI" node or "ChatGPT" node
   - Write a simple prompt like: "Turn this idea into a Twitter post: {{ $json.idea }}"
   - Copy this node for each platform with different prompts

5. **Set Up Content Input**
   - Add a "Set" node at the start
   - Create a field called "idea" where you type your content idea
   - This feeds into all your AI writing nodes

6. **Connect Everything Together**
   - Link the nodes with lines (drag from one dot to another)
   - Test by clicking "Execute workflow" with a sample idea

7. **Add Smart Timing**
   - Use "Schedule Trigger" set to post at your best times
   - Most businesses: 9 AM, 1 PM, 5 PM work well

**Alternative: Make.com Setup**

If you prefer Make.com instead of n8n:

1. **Create New Scenario**
   - Go to Make.com and click "Create a new scenario"
   - Name it "Social Media Content Factory"

2. **Add Trigger Module**
   - Add "Webhooks > Custom webhook" for manual triggering
   - Or use "Schedule" module for automatic posting

3. **Connect Social Platforms**
   - Add modules for each platform:
     - "Twitter > Create a Tweet"
     - "LinkedIn > Create a Share"
     - "Facebook > Create a Post"
   - Connect your accounts when prompted

4. **Add AI Content Creation**
   - Add "OpenAI > Create a Chat Completion"
   - Set prompt: "Turn this idea into a Twitter post: {{1.idea}}"
   - Duplicate for each platform with platform-specific prompts

5. **Set Up Data Flow**
   - Use "Set Variable" to capture your content idea
   - Route data through AI modules, then to social platforms
   - Test scenario with sample content

💡 **Make MCP Tip**: If using Claude Code, install the [Make MCP server](https://github.com/integromat/make-mcp-server) to build scenarios directly in your conversation.

**What You Get:**
- 5 different posts from 1 idea
- Consistent posting every day
- 80% less time writing posts
- Better engagement from timing

### 🤖 LLM-Only Alternative

**If you just need this done once or occasionally...**

You can create social media content for all your platforms in a single conversation with any AI assistant (ChatGPT, Claude, Gemini, etc.). This works great for one-off campaigns or when you're just getting started.

**What an LLM can do:**
Turn one content idea into posts for every platform you use, each written in the right style and length for that platform.

**Simple Multi-Step Prompt:**

```
I need to create social media posts for [CONTENT IDEA/ANNOUNCEMENT]. 

Please create posts for these platforms:
- LinkedIn (professional, 150-200 words)
- Twitter/X (engaging, under 280 characters) 
- Instagram (visual-focused with hashtags)
- Facebook (conversational, 100-150 words)

For each platform:
1. Match the tone to that platform's style
2. Include relevant hashtags
3. Suggest the best posting time
4. Add a call-to-action if appropriate

My brand voice is: [DESCRIBE YOUR STYLE: friendly/professional/casual/etc.]
My target audience is: [WHO YOU'RE TALKING TO]
```

**JSON Template Option:**
If you want organized output, add this to your prompt:

```
Please format the response as JSON like this:
{
  "linkedin": {
    "post": "content here",
    "hashtags": ["#hashtag1", "#hashtag2"],
    "best_time": "Tuesday 9 AM",
    "call_to_action": "suggested CTA"
  },
  "twitter": { ... },
  "instagram": { ... },
  "facebook": { ... }
}
```

**What this approach can't do:**
- Won't automatically post for you
- No scheduling or timing optimization
- Can't track what content performs best
- No automated posting consistency

**When to upgrade to full automation:**
- You're posting daily or multiple times per week
- You want automatic posting while you sleep
- You need performance tracking and optimization
- You have multiple content themes to rotate through

---

## 🎯 Lead Scoring Machine

**What It Does:** Automatically finds and ranks your best potential customers.

**How It Works:**
1. Watches who visits your website
2. Tracks email opens and clicks
3. Checks social media engagement
4. Gives each person a "hotness" score
5. Alerts sales team about ready-to-buy leads

**What You Need:**
- Website analytics access
- Email marketing platform
- CRM system (like HubSpot)
- n8n automation tool

**Step-by-Step n8n Setup:**

1. **Create Lead Scoring Workflow**
   - Start new workflow called "Lead Scoring Machine"
   - Add "Webhook" node to receive data from your website

2. **Connect Your Data Sources**
   - Add "Google Analytics" node to track website visits
   - Add "Mailchimp" or "ConvertKit" node for email data
   - Add "HubSpot" or your CRM node to store scores

3. **Build the Scoring System**
   - Add "Code" node with simple scoring rules:
     - Website visit = 5 points
     - Email open = 10 points  
     - Email click = 20 points
     - Downloaded content = 30 points

4. **Set Up the Points Calculator**
   - Use "Set" node to add up all the points
   - Create formula: "{{ $json.websitePoints + $json.emailPoints }}"
   - Set "hot lead" threshold (like 50+ points)

5. **Create Alert System**
   - Add "IF" node: "If score is greater than 50"
   - Connect "Slack" or "Email" node to alert sales team
   - Include person's name, score, and recent actions

6. **Test Your Scoring**
   - Use "Manual Trigger" to test with sample data
   - Check if points calculate correctly
   - Make sure alerts go to the right people

7. **Connect to Your Website**
   - Add the webhook URL to your website forms
   - Every new visitor automatically gets scored

**Alternative: Make.com Setup**

1. **Create Lead Scoring Scenario**
   - Start new scenario called "Lead Scoring Machine"
   - Add "Webhooks > Custom webhook" to receive data

2. **Connect Data Sources**
   - Add "Google Analytics" module for website tracking
   - Add "Mailchimp" or "ConvertKit" module for email data
   - Add "HubSpot" or CRM module for storing scores

3. **Build Scoring Logic**
   - Add "Math > Perform a function" modules to calculate points:
     - Website visit = 5 points
     - Email open = 10 points
     - Email click = 20 points
   - Use "Add" function to total the score

4. **Create Conditional Alerts**
   - Add "Filter" module: only continue if score > 50
   - Connect "Slack" or "Email" module for hot lead alerts
   - Include lead details and score in message

**What You Get:**
- Know who's interested before they buy
- Sales team focuses on best prospects
- Higher conversion rates
- Less time chasing cold leads

---

## 🕵️ Competitor Watch System

**What It Does:** Keeps track of what your competitors are doing so you don't have to.

**How It Works:**
1. Monitors competitor websites for changes
2. Tracks their social media posts
3. Watches for new product launches
4. Compares their prices to yours
5. Sends weekly summary reports

**What You Need:**
- List of competitors to watch
- Web monitoring service
- n8n automation platform
- Simple reporting template

**Step-by-Step n8n Setup:**

1. **Start Competitor Tracking Workflow**
   - Create workflow named "Competitor Watch System"
   - Add "Schedule Trigger" to check daily at 9 AM

2. **Monitor Competitor Websites**
   - Add "HTTP Request" node for each competitor's website
   - Set to "GET" method with their homepage URL
   - Add "HTML Extract" node to grab specific content (like prices, new products)

3. **Track Social Media**
   - Add "Twitter" node to search for competitor mentions
   - Use search terms like "CompanyName OR @competitorhandle"
   - Add "LinkedIn" node if competitors are B2B focused

4. **Set Up Change Detection**
   - Add "Compare Datasets" node or "Code" node
   - Compare today's data with yesterday's data
   - Flag anything that's different (new posts, price changes, etc.)

5. **Create Smart Alerts**
   - Add "IF" node: "If changes detected"
   - Connect "Slack" or "Email" node for immediate alerts
   - Include what changed and why it matters

6. **Build Weekly Reports**
   - Add "Google Sheets" node to store all findings
   - Use "Set" node to create summary every Friday
   - Email report to marketing team automatically

7. **Store Competitor Data**
   - Use "MySQL" or "Google Sheets" node to save history
   - Track trends over time (pricing, posting frequency, etc.)

**Alternative: Make.com Setup**

1. **Create Competitor Monitoring Scenario**
   - Name scenario "Competitor Watch System"
   - Add "Schedule" module to run daily

2. **Monitor Websites**
   - Add "HTTP > Make a request" for each competitor website
   - Set to GET method with competitor URLs
   - Use "Text parser" to extract specific content

3. **Track Social Media**
   - Add "Twitter > Search tweets" with competitor names
   - Add "LinkedIn > Search posts" for B2B competitors

4. **Detect Changes**
   - Add "Google Sheets" module to compare with yesterday's data
   - Use "Filter" to only continue if changes detected
   - Store new findings automatically

5. **Send Alerts**
   - Add "Slack" or "Email" module for immediate notifications
   - Include what changed and competitor details

**What You Get:**
- Never miss competitor moves
- Spot market trends early
- Better positioning decisions
- Weekly competitive intelligence reports

---

## 📊 Campaign Performance Tracker

**What It Does:** Automatically collects data from all your marketing campaigns in one place.

**How It Works:**
1. Pulls data from email, social media, ads
2. Calculates important metrics automatically
3. Creates easy-to-read reports
4. Compares this month to last month
5. Highlights what's working best

**What You Need:**
- Access to all your marketing platforms
- Google Sheets or similar spreadsheet
- n8n for data collection
- 30 minutes to set up templates

**Step-by-Step n8n Setup:**

1. **Create Performance Dashboard Workflow**
   - Start workflow called "Campaign Performance Tracker"
   - Add "Schedule Trigger" to pull data daily at 8 AM

2. **Connect All Your Marketing Tools**
   - Add "Google Analytics" node for website traffic data
   - Add "Facebook Ads" node for social media ad performance
   - Add "Mailchimp" node for email campaign stats
   - Add "Google Ads" node for search advertising data

3. **Pull Key Numbers Automatically**
   - Set each node to grab yesterday's data
   - Focus on important metrics:
     - Website visitors, conversions, email opens
     - Ad spend, clicks, cost per lead
     - Social media reach and engagement

4. **Calculate Important Ratios**
   - Add "Code" node to calculate:
     - Cost per lead: "{{ $json.adSpend / $json.leads }}"
     - Email open rate: "{{ $json.opens / $json.sent * 100 }}"
     - Website conversion rate: "{{ $json.conversions / $json.visitors * 100 }}"

5. **Create Your Dashboard**
   - Add "Google Sheets" node to store all data
   - Set up automatic chart creation
   - Include week-over-week comparisons

6. **Set Up Smart Alerts**
   - Add "IF" nodes for concerning changes:
     - "If cost per lead increased by 20%"
     - "If email open rate dropped below 15%"
   - Send alerts to Slack or email automatically

7. **Generate Weekly Reports**
   - Use "Set" node to summarize weekly performance
   - Email automated report every Monday morning
   - Highlight wins and areas needing attention

**Alternative: Make.com Setup**

1. **Create Performance Tracking Scenario**
   - Name scenario "Campaign Performance Tracker"
   - Add "Schedule" module for daily data collection

2. **Connect Marketing Platforms**
   - Add "Google Analytics" module for website data
   - Add "Facebook > Get ad insights" for social ad performance
   - Add "Mailchimp > Get campaign reports" for email stats

3. **Calculate Key Metrics**
   - Add "Math > Perform a function" modules:
     - Cost per lead: Ad spend ÷ leads
     - Open rate: Opens ÷ emails sent × 100
     - Conversion rate: Conversions ÷ visitors × 100

4. **Store and Visualize Data**
   - Add "Google Sheets" module to save daily metrics
   - Use "Charts" module or Google Sheets for visualization

5. **Set Up Performance Alerts**
   - Add "Filter" modules for concerning changes
   - Send alerts when metrics drop below thresholds

**What You Get:**
- All campaign data in one place
- Automatic report creation
- Clear picture of what works
- Data to prove marketing success

---

## 💬 Customer Feedback Collector

**What It Does:** Gathers and organizes customer opinions from everywhere they share them.

**How It Works:**
1. Monitors social media mentions
2. Collects survey responses
3. Tracks review site feedback
4. Organizes by positive/negative sentiment
5. Creates summary reports with action items

**What You Need:**
- Social media monitoring tool
- Survey platform (Google Forms works)
- Review site access
- n8n automation setup

**Step-by-Step n8n Setup:**

1. **Create Feedback Collection Workflow**
   - Start workflow called "Customer Feedback Collector"
   - Add "Schedule Trigger" to check for new feedback every hour

2. **Monitor Social Media Mentions**
   - Add "Twitter" node to search for your company name
   - Add "LinkedIn" node for B2B mentions
   - Use search terms like "YourCompany OR @yourhandle OR #yourbrand"

3. **Connect Review Sites**
   - Add "HTTP Request" nodes for:
     - Google My Business reviews
     - Yelp reviews (if applicable)
     - App store reviews (for mobile apps)
   - Set up to pull new reviews automatically

4. **Collect Survey Responses**
   - Add "Typeform" or "Google Forms" node
   - Connect to your existing customer surveys
   - Pull responses as they come in

5. **Analyze Sentiment Automatically**
   - Add "OpenAI" or sentiment analysis node
   - Use prompt: "Rate this feedback as positive, negative, or neutral: {{ $json.feedback }}"
   - Also ask: "What is the main concern or praise?"

6. **Organize Feedback by Type**
   - Add "Switch" node to sort feedback:
     - Positive feedback → save for testimonials
     - Negative feedback → alert customer service
     - Product suggestions → send to product team

7. **Create Action Items**
   - Use "IF" nodes for urgent issues
   - Send negative feedback to support team immediately
   - Create weekly summary reports for management

**Alternative: Make.com Setup**

1. **Create Feedback Collection Scenario**
   - Name scenario "Customer Feedback Collector"
   - Add "Schedule" module to check hourly

2. **Monitor Multiple Sources**
   - Add "Twitter > Search tweets" for brand mentions
   - Add "Google Forms > Watch responses" for surveys
   - Add "HTTP > Make a request" for review sites

3. **Analyze Sentiment**
   - Add "OpenAI > Create a chat completion"
   - Use prompt: "Rate this feedback as positive, negative, or neutral and explain why"

4. **Route by Sentiment**
   - Add "Router" module to sort feedback:
     - Positive → testimonials folder
     - Negative → support team alerts
     - Neutral → general feedback log

5. **Take Action**
   - Add "Email" or "Slack" for urgent negative feedback
   - Create weekly summary reports automatically

**What You Get:**
- Know what customers really think
- Spot problems before they get big
- Find happy customers for testimonials
- Data-driven product improvements

### 🤖 LLM-Only Alternative

**If you just need this done once or occasionally...**

You can analyze customer feedback and get insights in a single conversation with an AI assistant. Perfect for one-time feedback analysis or small amounts of customer feedback.

**What an LLM can do:**
Analyze any customer feedback you paste into the conversation, categorize it by theme, identify sentiment, and suggest action items.

**Simple Multi-Step Prompt:**

```
I have customer feedback to analyze. Please help me understand what customers are saying and what I should do about it.

Here's the feedback:
[PASTE YOUR CUSTOMER FEEDBACK HERE - emails, reviews, survey responses, social media mentions, etc.]

Please analyze this and give me:

1. SENTIMENT BREAKDOWN
   - What percentage is positive/negative/neutral
   - Overall mood and tone

2. MAIN THEMES
   - Group similar feedback into categories
   - Show which issues come up most often
   - Highlight any urgent problems

3. CUSTOMER INSIGHTS
   - What customers love most
   - Biggest pain points or complaints
   - Feature requests or suggestions

4. ACTION ITEMS
   - Quick wins to improve customer satisfaction
   - Problems that need immediate attention
   - Long-term improvements to consider

5. TESTIMONIAL OPPORTUNITIES
   - Pull out positive quotes I could use
   - Identify happy customers to ask for reviews

Make this actionable for a product marketer who needs to report to their team.
```

**JSON Template Option:**
For organized analysis, add this:

```
Format the analysis as JSON:
{
  "sentiment_summary": {
    "positive_percentage": "60%",
    "negative_percentage": "25%",
    "neutral_percentage": "15%",
    "overall_mood": "cautiously optimistic"
  },
  "themes": [
    {
      "category": "Pricing",
      "frequency": "mentioned 15 times",
      "sentiment": "mostly negative",
      "sample_quote": "..."
    }
  ],
  "action_items": [
    {
      "priority": "high",
      "action": "Fix login issues",
      "reason": "mentioned by 8 customers"
    }
  ],
  "testimonial_quotes": [
    "This product saved me 10 hours a week!"
  ]
}
```

**What this approach can't do:**
- Won't monitor feedback automatically
- Can't track sentiment changes over time
- No real-time alerts for negative feedback
- Limited by how much text you can paste at once

**When to upgrade to full automation:**
- You get customer feedback daily across multiple channels
- You need real-time alerts for negative reviews
- You want to track sentiment trends over time
- You have a team that needs automatic feedback routing

---

## 📧 Email Marketing Automation

**What It Does:** Sends the right email to the right person at the right time, automatically.

**How It Works:**
1. Tracks what people do on your website
2. Sends welcome emails to new visitors
3. Follows up with relevant content
4. Reminds people about abandoned purchases
5. Celebrates customer milestones

**What You Need:**
- Email marketing platform (Mailchimp, ConvertKit)
- Website tracking setup
- n8n automation tool
- Pre-written email templates

**Step-by-Step n8n Setup:**

1. **Create Email Automation Workflow**
   - Start workflow called "Smart Email Marketing"
   - Add "Webhook" node to receive customer actions from your website

2. **Set Up Behavior Triggers**
   - Connect website tracking to send data to n8n when:
     - Someone signs up for newsletter
     - Downloads a file
     - Abandons shopping cart
     - Visits pricing page multiple times

3. **Create Email Templates**
   - Add "Email" or "Mailchimp" nodes for different scenarios:
     - Welcome email for new subscribers
     - Product tips for downloaders  
     - Cart reminder for abandoned purchases
     - Special offer for price page visitors

4. **Add Smart Delays**
   - Use "Wait" nodes between emails:
     - Send welcome email immediately
     - Wait 2 days, then send helpful tips
     - Wait 1 week, then send customer stories
     - Wait 1 hour for cart abandonment, then send reminder

5. **Personalize Each Email**
   - Use "Set" node to include personal details:
     - "Hi {{ $json.firstName }}"
     - "Based on your interest in {{ $json.productViewed }}"
     - Reference their specific actions

6. **Track Email Performance**
   - Add tracking for opens and clicks
   - Use "IF" node: "If email opened, add to engaged list"
   - Send follow-up emails only to engaged subscribers

7. **Create Customer Milestone Celebrations**
   - Track customer anniversaries and achievements
   - Send automatic "happy birthday" or "1 year customer" emails
   - Include special offers or thank you notes

**Alternative: Make.com Setup**

1. **Create Email Automation Scenario**
   - Name scenario "Smart Email Marketing"
   - Add "Webhooks > Custom webhook" for customer actions

2. **Set Up Behavioral Triggers**
   - Configure website to send webhook data for:
     - Newsletter signups
     - File downloads
     - Cart abandonment
     - Multiple page visits

3. **Create Email Sequences**
   - Add "Email" modules for different scenarios:
     - Welcome series for new subscribers
     - Educational content for downloaders
     - Cart recovery for abandoners

4. **Add Smart Delays**
   - Use "Sleep" modules between emails:
     - Immediate welcome
     - 2-day helpful tips
     - 1-week customer stories
     - 1-hour cart reminder

5. **Personalize Messages**
   - Use customer data variables: {{name}}, {{product_interest}}
   - Reference specific behaviors and preferences

6. **Track and Optimize**
   - Monitor email opens and clicks
   - Use "Filter" to segment engaged vs. non-engaged subscribers

**What You Get:**
- Emails that feel personal and timely
- Higher open and click rates
- More sales from automated follow-ups
- Customers who feel valued

---

## 🎯 Getting Started Guide

### Start With One Automation
Pick the one that would save you the most time right now. Master it before adding others.

### Use What You Have
- Start with tools you already use
- Connect familiar platforms first
- Use free versions to learn
- Upgrade only when you need more features

### Learn Step by Step
- Watch beginner YouTube tutorials
- Join n8n community forums
- Practice with test data first
- Ask questions when stuck

### Budget Planning
- n8n: Free for basic use, $20/month for teams
- AI writing tools: $10-30/month
- Social media tools: Often free tiers available
- Total: Usually $50-100/month for full setup

---

## 🛡️ Best Practices

### Keep Your Brand Voice
- Write templates that sound like you
- Review AI content before posting
- Train AI with your best examples
- Always add human touch to important content

### Test Everything First
- Try automations with small audiences
- Check all connections work properly
- Have backup plans for when things break
- Monitor results and adjust as needed

### Stay Compliant
- Follow platform rules for automation
- Respect customer privacy settings
- Include unsubscribe options in emails
- Keep customer data secure

---

## 📞 Common Questions

**Q: Will this make my content sound robotic?**
A: Only if you let it! Always review and personalize AI content to match your brand voice.

**Q: How do I know what to automate first?**
A: Track your time for a week. Automate whatever takes the most repetitive time.

**Q: What if customers notice it's automated?**
A: Good automation feels helpful, not robotic. Focus on providing value, not just efficiency.

**Q: Can I still be creative with automation?**
A: Yes! Automation handles boring tasks so you have more time for creative strategy.

---

## 📈 Success Metrics

### Track These Numbers
- Time saved per week
- Content pieces created vs. manual work
- Lead quality scores
- Email open rates
- Social media engagement

### Expect These Results
- 60% reduction in content creation time
- 30% increase in lead quality
- 25% improvement in email performance
- 40% more consistent posting schedule

---

## 🔗 More Automations

**Need different solutions?**
- **[🏠 All Automation Guides](../AI%20Automations%20Guide.md)** - Main directory and getting started
- **[🎯 Find by Problem](../Automation%20Workflows%20by%20Problem.md)** - "I'm drowning in emails" or "My finances are a mess"
- **[👔 Find by Job Role](../Automation%20Workflows%20by%20Job%20Role.md)** - Browse by your profession
- **[📚 Automation Best Practices](../Automation%20Best%20Practices.md)** - Learn the fundamentals

---

*Last Updated: 2025-08-02*
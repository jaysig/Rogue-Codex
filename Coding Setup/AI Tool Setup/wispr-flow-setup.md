# WISPR Flow Setup Guide

A comprehensive guide to setting up and using WISPR Flow for AI-powered speech-to-text dictation across all your applications.

## Overview

WISPR Flow is an AI-powered dictation app that converts speech to text 4x faster than typing, with automatic editing and AI commands. It works seamlessly across all applications on Mac, Windows, and iPhone.

## Installation

### Prerequisites
- macOS 10.15+ (for Mac app)
- Windows 10+ (for Windows app)
- iOS 14+ (for iPhone app)
- Microphone access
- Internet connection for AI features

### Step 1: Download WISPR Flow
```bash
# Visit the official website
# https://flow.wispr.ai/

# Or download directly
# Mac: https://flow.wispr.ai/download/mac
# Windows: https://flow.wispr.ai/download/windows
# iPhone: App Store search "WISPR Flow"
```

### Step 2: Install and Setup
1. **Download the app** for your platform
2. **Install the application**
3. **Grant microphone permissions** when prompted
4. **Create an account** or sign in
5. **Complete the initial setup** wizard

### Step 3: Verify Installation
```bash
# Check if Flow is running (Mac)
ps aux | grep -i flow

# Check microphone permissions (Mac)
system_profiler SPAudioDataType

# Test microphone access
# Open any text application and try dictation
```

## Core Features Setup

### Speech-to-Text Configuration

#### Microphone Setup
```bash
# Mac: System Preferences > Sound > Input
# Select your preferred microphone
# Adjust input volume to optimal level

# Windows: Settings > System > Sound > Input
# Select your preferred microphone
# Test microphone levels
```

#### Language Configuration
```bash
# Flow supports 100+ languages automatically
# The app detects your language automatically
# You can switch between languages seamlessly

# Supported languages include:
# 🇺🇸 English, 🇨🇳 Chinese, 🇩🇪 German, 🇯🇵 Japanese
# 🇮🇳 Hindi, 🇬🇧 British English, 🇫🇷 French, 🇮🇹 Italian
# 🇨🇦 Canadian English, 🇧🇷 Portuguese, 🇷🇺 Russian
# 🇰🇷 Korean, 🇦🇺 Australian English, 🇪🇸 Spanish
# 🇲🇽 Mexican Spanish, 🇮🇩 Indonesian, 🇹🇷 Turkish, 🇳🇱 Dutch
```

### AI Auto-Edits

#### Automatic Editing Features
- **Grammar correction**: Automatically fixes grammar mistakes
- **Punctuation**: Adds proper punctuation marks
- **Capitalization**: Corrects capitalization automatically
- **Filler word removal**: Removes "um", "uh", "like", etc.
- **Sentence structure**: Improves sentence flow and clarity

#### Personal Dictionary
```bash
# Flow learns your unique words automatically
# Add custom words to your personal dictionary
# Examples of learned words:
# - Names: Valerio, Nora, Benton, Mackey, Zoltan, Vishal
# - Technical terms: EMT, API, SDK, etc.
# - Industry-specific terminology
```

### App-Specific Tones

#### Automatic Tone Adjustment
```bash
# Flow automatically adjusts tone based on the app you're using:
# - Professional tone for work emails
# - Casual tone for messaging apps
# - Formal tone for documents
# - Technical tone for coding environments
```

## Advanced Configuration

### Keyboard Shortcuts

#### Default Shortcuts (Mac)
```bash
# Start/Stop dictation: Cmd + Shift + D
# Pause/Resume: Cmd + Shift + P
# Clear text: Cmd + Shift + C
# Undo last edit: Cmd + Z
# Redo edit: Cmd + Shift + Z
```

#### Custom Shortcuts
```bash
# Mac: System Preferences > Keyboard > Shortcuts > App Shortcuts
# Add custom shortcuts for Flow

# Windows: Settings > Devices > Keyboard > Advanced keyboard settings
# Customize shortcuts for Flow
```

### Voice Commands

#### Basic Commands
```bash
# Navigation commands:
"new line" - Creates a new line
"new paragraph" - Creates a new paragraph
"go back" - Moves cursor back
"go forward" - Moves cursor forward
"select all" - Selects all text
"delete that" - Deletes last spoken text
```

#### Editing Commands
```bash
# Formatting commands:
"bold that" - Makes text bold
"italicize that" - Makes text italic
"underline that" - Underlines text
"capitalize that" - Capitalizes text
"lowercase that" - Makes text lowercase
"delete word" - Deletes last word
"delete sentence" - Deletes last sentence
```

#### Punctuation Commands
```bash
# Punctuation:
"period" - Adds a period
"comma" - Adds a comma
"question mark" - Adds a question mark
"exclamation mark" - Adds an exclamation mark
"quote" - Adds quotation marks
"open parenthesis" - Adds opening parenthesis
"close parenthesis" - Adds closing parenthesis
```

## Use Case Examples

### Professional Writing

#### Email Composition
```bash
# Example workflow:
1. Open your email client
2. Click in the compose field
3. Press Cmd + Shift + D (Mac) or Ctrl + Shift + D (Windows)
4. Speak naturally: "Hi John, I hope this email finds you well. I wanted to follow up on our meeting from yesterday regarding the project timeline."
5. Flow automatically edits: "Hi John, I hope this email finds you well. I wanted to follow up on our meeting from yesterday regarding the project timeline."
```

#### Document Writing
```bash
# For reports, proposals, and documents:
1. Open your word processor
2. Start dictation
3. Speak your thoughts naturally
4. Flow converts to polished text
5. Make any final edits manually
```

### Content Creation

#### Blog Writing
```bash
# Content creation workflow:
1. Open your blog editor
2. Start dictation
3. Speak your ideas freely
4. Flow handles grammar and structure
5. Review and refine as needed
```

#### Social Media Posts
```bash
# Quick social media content:
1. Open your social media app
2. Start dictation
3. Speak your post naturally
4. Flow formats appropriately for the platform
5. Post immediately or save as draft
```

### Accessibility

#### For Users with Disabilities
```bash
# Flow is particularly helpful for:
# - Users with motor disabilities
# - Users with repetitive strain injuries
# - Users with Parkinson's disease
# - Users who stutter (Flow handles this well)
# - Users with slower typing speeds
```

#### Multilingual Users
```bash
# For users working in multiple languages:
1. Flow automatically detects language
2. Switch between languages seamlessly
3. Maintains personal dictionary across languages
4. Handles accents and dialects
```

## Best Practices

### Speaking Techniques

#### Optimal Speaking
```bash
# Best practices for accuracy:
- Speak at a natural pace (not too fast or slow)
- Use clear pronunciation
- Take natural pauses for punctuation
- Speak in complete sentences when possible
- Use the personal dictionary for unique terms
```

#### Environment Setup
```bash
# Optimal recording environment:
- Use a good quality microphone
- Minimize background noise
- Speak at consistent volume
- Position microphone correctly
- Test in your typical work environment
```

### Workflow Integration

#### Daily Workflow
```bash
# Integrate Flow into your daily routine:
1. Morning emails and messages
2. Meeting notes and documentation
3. Content creation and writing
4. Quick responses and updates
5. End-of-day summaries
```

#### Productivity Tips
```bash
# Maximize productivity:
- Use voice commands for editing
- Leverage the personal dictionary
- Take advantage of app-specific tones
- Use Flow for brainstorming sessions
- Combine with other productivity tools
```

## Troubleshooting

### Common Issues

#### Microphone Problems
```bash
# Check microphone permissions:
# Mac: System Preferences > Security & Privacy > Microphone
# Windows: Settings > Privacy > Microphone

# Test microphone:
# Mac: System Preferences > Sound > Input
# Windows: Settings > System > Sound > Input
```

#### Accuracy Issues
```bash
# Improve accuracy:
- Speak more clearly and slowly
- Reduce background noise
- Update personal dictionary
- Check microphone quality
- Practice with the app regularly
```

#### Performance Issues
```bash
# Optimize performance:
- Close unnecessary applications
- Check internet connection
- Restart the Flow application
- Update to latest version
- Clear app cache if available
```

### Getting Help

#### Support Resources
```bash
# Official support:
- Visit: https://flow.wispr.ai/support
- Email: support@wispr.ai
- In-app help and tutorials
- User guide and documentation
```

#### Community
```bash
# Community resources:
- User forums and discussions
- Social media groups
- YouTube tutorials and reviews
- Reddit communities
```

## Integration Examples

### Development Workflow

#### Code Documentation
```bash
# Use Flow for:
- Writing README files
- Documenting code comments
- Creating technical specifications
- Writing commit messages
- Creating user guides
```

#### Communication
```bash
# Development team communication:
- Slack messages and updates
- Email communications
- Meeting notes and summaries
- Bug reports and descriptions
- Project documentation
```

### Content Creation Workflow

#### Writing Projects
```bash
# Content creation:
- Blog posts and articles
- Social media content
- Marketing copy
- Technical documentation
- Creative writing projects
```

## Resources

### Documentation
- [WISPR Flow Official Site](https://flow.wispr.ai/)
- [User Guide](https://flow.wispr.ai/guide)
- [Download Page](https://flow.wispr.ai/download)

### Community
- [WISPR Flow Twitter](https://twitter.com/wisprflow)
- [User Reviews and Testimonials](https://flow.wispr.ai/testimonials)
- [Product Hunt](https://www.producthunt.com/posts/wispr-flow)

### Support
- [Help Center](https://flow.wispr.ai/help)
- [Contact Support](https://flow.wispr.ai/support)
- [Feature Requests](https://flow.wispr.ai/feedback)

---

*Last Updated: July 27, 2025* 
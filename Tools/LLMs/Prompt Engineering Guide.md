# Prompt Engineering Guide

**Master the art of crafting effective prompts for AI models including ChatGPT, Claude, Gemini, and Perplexity**

*Comprehensive guide to prompt optimization, meta-prompting techniques, and model-specific best practices*

## Overview

Prompt engineering is the practice of crafting optimal text inputs to get the best possible responses from AI language models. This guide covers everything from basic techniques to advanced meta-prompting strategies for maximizing AI performance across different platforms.

## Quick Start: Universal Prompting Principles

### The CLEAR Framework
- **C**ontext: Provide necessary background information
- **L**ength: Specify desired output length explicitly  
- **E**xamples: Include relevant examples when helpful
- **A**udience: Define who the response is for
- **R**ole: Assign a specific persona or expertise level

### Basic Template
```
You are a [ROLE] with expertise in [DOMAIN].

Context: [BACKGROUND INFORMATION]

Task: [SPECIFIC REQUEST]

Format: [DESIRED OUTPUT STRUCTURE]

Examples: [IF HELPFUL]

Constraints: [LIMITATIONS OR REQUIREMENTS]
```

## Model-Specific Optimization

### ChatGPT (OpenAI)
**Best Format:** JSON with structured outputs or clear markdown

**Optimization Tips:**
- Use explicit format requests: "Respond in JSON format"
- Leverage system prompts for consistent behavior
- Include "step-by-step" for complex reasoning
- Use function calling for structured data

**Sample Meta-Prompt:**
```
You are an expert prompt engineer for ChatGPT. Help me improve this prompt:

[USER'S ORIGINAL PROMPT]

Please:
1. Identify areas for improvement
2. Suggest specific optimizations for ChatGPT
3. Provide the improved version
4. Explain why the changes will work better

Focus on: clarity, specificity, format optimization, and ChatGPT's strengths.
```

### Claude (Anthropic)
**Best Format:** XML tags with hierarchical structure

**Optimization Tips:**
- Use XML tags: `<instructions>`, `<examples>`, `<output>`
- Nest tags for complex structure: `<analysis><step1></step1></analysis>`
- Place long documents at the top of prompts
- Use `<thinking>` tags for chain-of-thought

**Sample Meta-Prompt:**
```xml
<role>You are a master prompt engineer specializing in Claude optimization</role>

<task>
Help me improve this prompt for better Claude performance:

<original_prompt>
[USER'S ORIGINAL PROMPT]
</original_prompt>

Please provide:
1. Analysis of current prompt structure
2. Specific improvements using Claude's XML preferences
3. Optimized version with proper tag hierarchy
4. Explanation of why these changes enhance Claude's performance
</task>

<focus_areas>
- XML tag structure and nesting
- Clear instruction hierarchy  
- Context placement optimization
- Chain-of-thought integration
</focus_areas>
```

### Gemini (Google)
**Best Format:** XML structure with JSON schema configuration

**Optimization Tips:**
- Use XML for prompt organization with clear delimiters
- Configure response schemas for reliable JSON output
- Maintain consistent formatting across examples
- Use descriptive field names in schemas

**Sample Meta-Prompt:**
```xml
<role>Expert prompt engineer specialized in Google Gemini optimization</role>

<current_prompt>
[USER'S ORIGINAL PROMPT]
</current_prompt>

<improvement_request>
Analyze and optimize this prompt for Gemini, focusing on:

<structure>XML organization with clear delimiters</structure>
<output_format>JSON schema configuration when appropriate</output_format>
<examples>Consistent formatting across all examples</examples>
<clarity>Unambiguous field names and instructions</clarity>

Provide:
1. Structural analysis of current prompt
2. Gemini-optimized version using XML + JSON schema approach
3. Explanation of improvements and why they work for Gemini
4. Response schema if structured output is needed
</improvement_request>
```

### Perplexity AI
**Best Format:** Structured collections with search optimization

**Optimization Tips:**
- Use Collection-level prompts for consistency
- Be explicit about source types and recency requirements
- Focus on publicly indexed, searchable information
- Request specific citation formats

**Sample Meta-Prompt:**
```
You are a Perplexity AI expert specializing in research-optimized prompts.

Original prompt to improve:
[USER'S ORIGINAL PROMPT]

Please optimize this prompt for Perplexity's search-powered AI, considering:

**Search Integration:**
- How to leverage real-time web search effectively
- Source type specifications (news, academic, official reports)
- Recency requirements and date ranges

**Collection Setup:**
- System-level prompt recommendations
- Consistency across multiple queries
- Format specifications for citations

**Output Optimization:**
- Clear formatting requests (bullets, headers, links)
- Source integration within content
- Structure for research-heavy responses

Provide:
1. Analysis of current prompt's search effectiveness
2. Collection-level system prompt
3. Optimized user query
4. Explanation of search optimization strategies
```

## Advanced Meta-Prompting Techniques

### The Iterative Improvement Method
1. **Start with basic prompt**
2. **Test with target AI model**
3. **Use model to analyze its own response**
4. **Apply suggested improvements**
5. **Repeat until optimal**

### Self-Evaluation Prompt Template
```
Please evaluate your previous response and suggest improvements:

1. **Accuracy**: Was the information correct and complete?
2. **Clarity**: Was the explanation clear and well-structured?
3. **Completeness**: What important points were missed?
4. **Format**: How could the format be improved?
5. **Specificity**: Where could more specific details help?

Based on this evaluation, provide an improved version of your response.
```

### Chain-of-Thought Meta-Prompting
```
You are an expert prompt engineer. Analyze this prompt step-by-step:

[ORIGINAL PROMPT]

Think through this systematically:

<analysis>
Step 1: Identify the core objective
Step 2: Evaluate current clarity and specificity  
Step 3: Assess format and structure
Step 4: Consider model-specific optimizations
Step 5: Identify missing elements
</analysis>

<improvements>
Based on your analysis, provide:
1. Specific problems with current prompt
2. Detailed improvements for each issue
3. Complete optimized version
4. Expected performance improvements
</improvements>
```

## Prompt Optimization Strategies

### Length Optimization Triggers
For longer, more comprehensive responses, use these phrases:
- "Comprehensive analysis with extensive detail"
- "In-depth examination covering all aspects"
- "Detailed step-by-step breakdown"
- "Include multiple examples and case studies"
- "Provide thorough background and context"

### Specificity Enhancement
**Instead of:** "Write about marketing"
**Use:** "Create a 2,000-word email marketing strategy for B2B SaaS companies with 50-200 employees, focusing on lead nurturing sequences and conversion optimization"

### Format Control
**For structured output:**
```
Respond in this exact format:

## Executive Summary
[2-3 sentences]

## Key Points
1. [Point 1 with explanation]
2. [Point 2 with explanation]
3. [Point 3 with explanation]

## Recommendations
- [Actionable item 1]
- [Actionable item 2]

## Next Steps
[Specific actions to take]
```

## Common Optimization Patterns

### The Expert Persona Pattern
```
You are a [SPECIFIC EXPERT] with [YEARS] years of experience in [DOMAIN].

Your expertise includes:
- [Specific skill 1]
- [Specific skill 2]  
- [Specific skill 3]

Based on your experience, [SPECIFIC REQUEST]
```

### The Constraint Pattern
```
Create [OUTPUT] with these specific constraints:
- Length: [EXACT REQUIREMENT]
- Audience: [TARGET GROUP]
- Tone: [SPECIFIC STYLE]
- Format: [STRUCTURE REQUIREMENT]
- Exclude: [WHAT TO AVOID]
- Include: [MUST-HAVE ELEMENTS]
```

### The Multi-Step Pattern
```
Complete this task in phases:

Phase 1: [RESEARCH/ANALYSIS]
Phase 2: [PLANNING/STRATEGY]  
Phase 3: [EXECUTION/CREATION]
Phase 4: [REVIEW/OPTIMIZATION]

For each phase, provide [SPECIFIC DELIVERABLE]
```

## Quality Assurance Framework

### Prompt Testing Checklist
- [ ] Does the prompt clearly state the desired outcome?
- [ ] Is the context sufficient but not excessive?
- [ ] Are examples provided when helpful?
- [ ] Is the format explicitly specified?
- [ ] Are constraints and requirements clear?
- [ ] Is the prompt optimized for the target AI model?

### Performance Metrics
Track these elements in your prompt effectiveness:
- **Accuracy**: Correct information and facts
- **Completeness**: Addresses all aspects of request
- **Relevance**: Stays on topic and focused
- **Format**: Follows specified structure
- **Actionability**: Provides useful, implementable advice

## Quick Reference: Model Preferences

| Model | Preferred Structure | Key Optimization | Best For |
|-------|-------------------|------------------|----------|
| **ChatGPT** | JSON/Markdown | Structured outputs, function calling | Structured data, step-by-step processes |
| **Claude** | XML tags | Hierarchical structure, thinking tags | Complex analysis, long-form content |
| **Gemini** | XML + JSON schema | Response schema configuration | Reliable structured output |
| **Perplexity** | Collections format | Search optimization, citations | Research, current information |

## Related Resources

- [[AI Model Format Preferences Research]] - Detailed technical analysis
- [[ChatGPT]] - Model-specific guide and features
- [[Claude]] - Anthropic's AI assistant optimization
- [[Gemini]] - Google AI prompting strategies
- [[Perplexity]] - Search-powered AI techniques

## Tags
#prompt-engineering #ai-optimization #meta-prompting #chatgpt #claude #gemini #perplexity

---

*Last Updated: 2025-01-06*
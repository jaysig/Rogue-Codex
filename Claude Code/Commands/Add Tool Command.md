# Add Tool Command

**Comprehensive tool evaluation and integration with category placement and cross-referencing**

## Command Syntax
```
/add-tool [tool names separated by commas]
```

## Purpose
Automates the complete process of researching, evaluating, and documenting new tools in the Tools section. This command handles everything from initial research to category integration and README updates.

## What It Does

### 1. Tool Research
- Gathers comprehensive tool information (features, pricing, use cases)
- Determines primary category placement based on tool functionality
- Researches competitive landscape and alternative solutions
- Verifies current 2025 pricing and subscription options

### 2. File Creation
- Creates individual tool files using the Tool Evaluation Template
- Includes current pricing information and subscription tiers
- Adds "Coming soon" placeholders for incomplete evaluation sections
- Applies consistent formatting and structure

### 3. Category Integration
- Places tool in appropriate primary category folder
- Updates category README with new tool link and description
- Adds cross-references in secondary categories when applicable
- Maintains alphabetical ordering in all listings

### 4. Documentation Updates
- Updates main Tool Guide.md with new tool entries
- Adds timestamp updates to all modified files
- Creates Recent Changes entry documenting additions
- Ensures proper internal linking throughout

### 5. Quality Assurance
- Verifies proper Obsidian linking format
- Ensures consistent template usage across all tool files
- Confirms 8th grade reading level compliance
- Validates pricing accuracy and completeness

## Example Usage

### Single Tool
```
/add-tool Figma
```
**Result**: Adds Figma to Design category with comprehensive evaluation, pricing research, and integration updates.

### Multiple Design Tools
```
/add-tool Figma, Adobe Firefly, Canva AI
```

**What happens:**
1. **Figma** → Design category (collaborative design platform with AI features)
2. **Adobe Firefly** → Design category (AI-powered creative suite)
3. **Canva AI** → Design category (AI design assistance in Canva)

**Generated files:**
- `Tools/Design/Figma.md`
- `Tools/Design/Adobe Firefly.md`
- `Tools/Design/Canva AI.md`

**Updated files:**
- `Tools/Design/README.md` (category overview)
- `Tools/Tool Guide.md` (main directory)
- `Recent Changes.md` (changelog entry)

### Cross-Category Example
```
/add-tool ChatGPT, Claude Code, Perplexity
```

**Result**: 
- **ChatGPT** → LLMs category (conversational AI)
- **Claude Code** → Developer Tools category (AI coding assistant) 
- **Perplexity** → Business Productivity category (AI search engine)

Each tool placed in its primary category with cross-references added where relevant.

## Tool File Structure

Each tool file includes:

### Required Sections
1. **Header**: Tool name, category, company, type
2. **Overview**: Brief description of tool's purpose and functionality
3. **Links & Resources**: Official website, documentation, social media
4. **Tool Evaluation**: Reference to evaluation template with status
5. **Key Features**: Core functionality (bullet points, no checkboxes)
6. **Use Cases**: Primary applications and scenarios
7. **Potential Workflow Integration Ideas**: Suggested integration scenarios
8. **Pricing**: Current 2025 pricing with publicly available information
9. **Pros & Cons**: Clear advantages and disadvantages
10. **Notes & Updates**: Recent changes (*Coming soon* for new tools)
11. **Recommended For**: Target user groups and skill levels
12. **Related Tools**: Ecosystem and alternatives with proper linking
13. **Rankings**: Placeholder for "*Coming soon*"

### Pricing Research Standards
- **Public Information**: Only publicly available pricing included
- **Current Rates**: 2025 pricing when available
- **Subscription Tiers**: All available plans with costs
- **Special Pricing**: Student, enterprise, and nonprofit rates when available

### Related Tools Linking
- **Ecosystem Tools**: Links to external resources if internal pages not available
- **Alternatives**: Prioritizes internal tool reviews, then external links
- **Format**: `- [Tool Name](URL) - Brief description`
- **Coming Soon**: "*Coming soon* - Internal tool reviews" for planned coverage

## Category Assignment Logic

### Primary Categories
Tools are assigned to categories based on their primary function:
- **AI Automations**: Workflow automation and AI-powered productivity
- **Audio**: Music generation, voice synthesis, audio processing
- **Business Productivity**: General business tools and productivity platforms
- **Design**: Visual design, graphics, and creative tools
- **Developer Tools**: Programming, coding, and development platforms
- **Education**: Learning platforms and educational technology
- **Finance**: Financial analysis, trading, and money management tools

### Multi-Category Tools
For tools that span multiple categories:
- Create main file in PRIMARY category only
- Add cross-references in secondary category READMEs under "Additional Tools"
- Use format: `- [[Primary Category/Tool Name]] - Brief description`

## Integration Benefits

### Automated Updates
- Category README automatically includes new tools
- Main Tool Guide maintains alphabetical integration
- Cross-references established between related tools
- Consistent timestamp management across all files

### Template Consistency
- All tools follow identical evaluation structure
- Uniform pricing information format
- Consistent linking and cross-reference patterns
- Standardized "Coming soon" placeholders

### SEO Optimization
- Descriptive filenames improve search visibility
- Proper heading structure for search engines
- Natural keyword integration in tool descriptions
- Internal linking supports search engine crawling

## Quality Standards

### Information Accuracy
- Current 2025 pricing from official sources
- Verified feature lists and capabilities
- Accurate competitive positioning
- Up-to-date company and product information

### Content Standards
- 8th grade reading level for all descriptions
- Clear explanations of technical features
- Practical use case examples
- Honest pros and cons assessment

### Evaluation Consistency
- Reference to Tool Evaluation Template for criteria
- "Not reviewed" or "*Coming soon*" for incomplete sections
- Standardized feature presentation format
- Consistent recommendation frameworks

## Common Use Cases

1. **Competitive Analysis**: Adding multiple tools in same category for comparison
2. **Ecosystem Mapping**: Documenting tool integrations and workflows
3. **Market Research**: Tracking new tools and platform launches
4. **User Guidance**: Building comprehensive tool recommendation systems

## Tips for Best Results

1. **Tool Names**: Use official product names for accurate research
2. **Category Planning**: Consider primary vs. secondary category placement
3. **Pricing Verification**: Double-check pricing from official sources
4. **Integration Testing**: Verify all internal links work properly

---

*Last Updated: 2025-08-04*
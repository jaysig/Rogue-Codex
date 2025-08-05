# Add Company Command

**Streamlined company addition to Company Spotlight with comprehensive research and integration**

## Command Syntax
```
/add-company [company names separated by commas]
```

## Purpose
Automates the complex process of researching, documenting, and integrating new companies into the Company Spotlight section. This command handles everything from initial research to file creation and cross-reference updates.

## What It Does

### 1. Research Phase
- Searches for basic company information (industry, type, founded, headquarters, website)
- Finds latest AI-related news and developments
- Gathers financial information, leadership, and competitive landscape data
- Verifies information accuracy from multiple sources

### 2. Category Assignment
- Determines appropriate industry category based on company's primary business
- Creates new category if none exists (with user confirmation)
- Considers both primary and secondary category placements

### 3. File Creation
- Uses the standard company template from CompanyGuide.md
- Generates properly encoded Perplexity search URLs for ongoing research
- Creates individual company files with descriptive naming

### 4. Integration
- Updates Company Spotlight main guide with new entries
- Adds companies to appropriate category README files
- Creates Recent Changes.md entry documenting additions

### 5. Quality Check
- Verifies all template sections are completed
- Ensures 8th grade reading level compliance
- Confirms proper internal linking format

## Example Usage

### Single Company
```
/add-company Runway
```
**Result**: Adds Runway (AI video generation platform) to AI Infrastructure category with full research and documentation.

### Multiple Companies
```
/add-company Runway, Pika Labs, Luma AI
```

**What happens:**
1. **Runway** → AI Infrastructure category (video generation platform)
2. **Pika Labs** → AI Content & Media category (text-to-video tool)
3. **Luma AI** → AI Infrastructure category (3D capture and AI video)

**Generated files:**
- `Company Spotlight/AI Infrastructure/Runway.md`
- `Company Spotlight/AI Content & Media/Pika Labs.md` 
- `Company Spotlight/AI Infrastructure/Luma AI.md`

**Updated files:**
- `Company Spotlight/CompanyGuide.md` (main directory)
- `Company Spotlight/AI Infrastructure/README.md` (category page)
- `Company Spotlight/AI Content & Media/README.md` (category page)
- `Recent Changes.md` (changelog entry)

### Cross-Industry Example
```
/add-company Sunday, Stripe, Square
```

**Result**: Adds three FinTech companies to FinTech and Payment category, researching each company's AI adoption and payment innovation strategies.

## Template Applied

Each company file includes:
- **Header**: Company name, industry, type, founded, headquarters, website
- **Latest AI News**: Recent AI-related developments and initiatives
- **Overview**: Business description and market position
- **Key Products/Services**: Primary offerings
- **Recent Developments**: Funding, partnerships, launches
- **Financial Information**: Revenue, valuation, funding rounds
- **Leadership**: CEO and key executives
- **Competitive Landscape**: Competitors and differentiators
- **Perplexity Queries**: Pre-formatted research URLs
- **Tags**: Categorization and searchability

## Perplexity URL Generation

The command automatically creates two research URLs for each company:

### Latest Company News Query
```
https://www.perplexity.ai/search/Summarize-the-latest-news-about-[Company-Name]-focusing
```

### Industry AI News Query  
```
https://www.perplexity.ai/search/Latest-AI-news-for-[Company-Name]-and-the-[Industry]-industry
```

URLs are properly encoded with spaces converted to hyphens and special characters handled appropriately.

## Quality Standards

### Information Accuracy
- Multiple source verification for basic company information
- Current financial data from reliable sources
- Verified leadership information and recent changes

### Content Standards
- 8th grade reading level for all descriptions
- Clear, jargon-free explanations of business models
- Consistent formatting across all company files

### SEO Optimization
- Descriptive filenames for search visibility
- Proper heading structure for search engines
- Natural keyword integration in content

## Integration Benefits

### Automated Cross-Referencing
- Automatic addition to main Company Spotlight guide
- Category README updates with proper alphabetical ordering
- Cross-references between competing companies

### Changelog Management
- Single Recent Changes entry for batch additions
- Public-facing language avoiding internal workflow references
- Proper date stamping and categorization

### Template Consistency
- Ensures all company files follow identical structure
- Maintains visual consistency across the entire section
- Supports Obsidian's graph view and search functionality

## Common Use Cases

1. **Industry Analysis**: Adding multiple competitors in the same sector
2. **News Coverage**: Adding companies making AI headlines
3. **Investment Research**: Documenting funded companies in AI space
4. **Market Mapping**: Building comprehensive industry landscapes

## Tips for Best Results

1. **Company Names**: Use official company names for best research results
2. **Batch Processing**: Add related companies together for efficiency
3. **Verification**: Review generated content for accuracy before publishing
4. **Follow-Up**: Use generated Perplexity URLs for ongoing news monitoring

---

*Last Updated: 2025-08-04*
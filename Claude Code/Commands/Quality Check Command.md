# Quality Check Command

**Comprehensive content quality assurance for documentation files and sections**

## Command Syntax
```
/quality-check [file paths or section names]
```

## Purpose
Performs thorough quality assurance on documentation files, ensuring they meet Rogue Codex standards for readability, structure, linking, SEO optimization, and consistency. This command identifies issues and provides specific improvement recommendations.

## What It Does

### 1. Reading Level Assessment
- Checks for 8th grade reading level compliance using vocabulary and sentence structure analysis
- Identifies complex terms that need simplification
- Suggests improvements for clarity and accessibility
- Flags technical jargon that requires plain language explanations

### 2. Structure Validation
- Verifies template compliance for different content types (companies, tools, automations)
- Checks that all required sections are present and complete
- Confirms proper heading hierarchy (H1 → H2 → H3 progression)
- Validates consistent formatting across similar content

### 3. Linking Audit
- Verifies all internal links work correctly
- Checks cross-references are accurate and up-to-date
- Ensures proper Obsidian link format `[[filename]]` or `[[folder/filename]]`
- Identifies broken or missing links that need repair

### 4. SEO Optimization
- Reviews content for natural keyword integration
- Checks heading structure supports search engine indexing
- Verifies descriptive filename usage for search visibility
- Assesses content structure for user intent matching

### 5. Timestamp and Changelog
- Updates "Last Updated" dates to current date (YYYY-MM-DD format)
- Suggests Recent Changes entry if significant updates are found
- Removes any "Next Review" dates that may have been added
- Ensures consistent date formatting throughout

## Example Usage

### Single File Check
```
/quality-check Company Spotlight/AI Infrastructure/OpenAI.md
```
**Result**: Comprehensive quality assessment of OpenAI company profile with specific improvement recommendations.

### Category-Wide Audit
```
/quality-check Company Spotlight/AI Infrastructure/, Tools/Design/
```

**What happens:**
1. **AI Infrastructure Companies**: Quality check on all company files in the category
2. **Design Tools**: Assessment of all tool evaluations in Design category
3. **Cross-Reference Validation**: Verification of links between categories
4. **Consistency Check**: Ensures uniform standards across both sections

**Assessment covers:**
- Reading level consistency across all files
- Template compliance for each content type
- Internal linking accuracy between companies and tools
- SEO optimization opportunities
- Timestamp synchronization

### Multi-Section Analysis
```
/quality-check AI Automations/Marketing/, Lessons Learned/AI Tool Lessons.md
```

**Result**: Quality assessment across different content types with specific recommendations for:
- Automation guide readability and structure
- Lessons learned formatting and accessibility
- Cross-section linking opportunities
- Overall content consistency

## Quality Assessment Areas

### Content Readability
**8th Grade Reading Level Checks:**
- Average sentence length (15-20 words maximum)
- Syllable count in words (prefer 1-2 syllable words)
- Technical term explanations in simple language
- Clear, direct sentence structure

**Common Issues Identified:**
- Overly complex technical explanations
- Long, run-on sentences that need breaking up
- Jargon without plain language alternatives
- Passive voice that could be active

### Template Compliance
**Company Files:**
- All required sections present (Overview, Key Products, Recent Developments, etc.)
- Proper Perplexity URL formatting
- Latest AI News section updated
- Leadership and financial information current

**Tool Files:**
- Tool Evaluation Template reference included
- Pricing information current and accurate
- Related Tools section properly linked
- Rankings section with "*Coming soon*" placeholder

**Automation Files:**
- Both n8n and Make.com implementations included
- Cost estimates using standard business size definitions
- LLM-only alternatives where applicable
- Standard navigation section present

### Linking and Cross-References
**Internal Link Validation:**
- All `[[wikilinks]]` resolve to existing files
- Cross-references between related content accurate
- Navigation links in automation guides functional
- Category README files include all relevant items

**Common Link Issues:**
- Broken links to moved or renamed files
- Missing cross-references between related tools/companies
- Incorrect file paths in navigation sections
- URL encoding issues in markdown links

### SEO and Discoverability
**Search Optimization:**
- Descriptive filenames that indicate content
- Natural keyword usage in headings and content
- Proper heading hierarchy for search engines
- Internal linking supports content discovery

**Filename Standards:**
- No generic names like "README.md" in subdirectories
- Overview files use leading space for top-of-folder visibility
- Descriptive names that clearly identify content purpose
- Consistent naming patterns within categories

## Quality Improvement Recommendations

### Reading Level Improvements
```
❌ "This sophisticated AI-powered platform facilitates comprehensive automation workflows..."
✅ "This AI tool helps you automate work tasks easily..."

❌ "Utilize advanced machine learning algorithms to optimize performance metrics..."
✅ "Use AI to make your work faster and better..."
```

### Structure Enhancements
- Add missing template sections with appropriate placeholders
- Reorganize content for better logical flow
- Improve heading hierarchy for clearer navigation
- Standardize formatting across similar content types

### Linking Fixes
- Update broken internal links to correct file paths
- Add missing cross-references between related content
- Improve navigation sections in automation guides
- Verify all external links are current and functional

### SEO Optimizations
- Improve filename descriptiveness for search visibility
- Enhance heading structure for search engine indexing
- Add natural keyword integration without keyword stuffing
- Optimize internal linking for content discoverability

## Integration with Repository Standards

### CLAUDE.md Compliance
- Ensures all content meets repository-wide standards
- Validates Obsidian-compatible formatting
- Confirms proper checkbox usage for task tracking
- Maintains consistency with established templates

### Content Quality Standards
- 8th grade reading level requirement enforcement
- Template consistency across all content types
- Proper timestamp management (Last Updated only)
- SEO optimization for search visibility

### File Management Standards
- Descriptive filename validation
- Proper folder structure maintenance
- Internal linking accuracy verification
- Cross-reference consistency checking

## Benefits of Regular Quality Checks

### User Experience
- Improved content accessibility and readability
- Better navigation and content discovery
- Consistent experience across all sections
- Reliable internal linking structure

### Search Performance
- Enhanced search engine visibility
- Better user intent matching
- Improved content discoverability
- Natural keyword optimization

### Maintenance Efficiency
- Early identification of content issues
- Automated compliance checking
- Consistent quality standards enforcement
- Reduced manual review requirements

## Common Use Cases

1. **Pre-Publication Review**: Quality check before adding new content
2. **Section Audits**: Comprehensive review of entire content categories
3. **Template Compliance**: Ensuring new content follows established patterns
4. **SEO Optimization**: Improving search visibility and discoverability
5. **Link Maintenance**: Regular validation of internal linking structure

## Tips for Best Results

1. **Regular Checks**: Run quality checks before publishing new content
2. **Section Focus**: Check entire categories for consistency
3. **Template Updates**: Verify compliance when templates change
4. **SEO Reviews**: Regular assessment for search optimization opportunities

---

*Last Updated: 2025-08-04*
# Sync Changes Command

**Automated changelog and cross-reference updates after content additions**

## Command Syntax
```
/sync-changes [description of changes made]
```

## Purpose
Automates the post-content creation workflow by updating changelogs, cross-references, timestamps, and navigation links. This command ensures all documentation changes are properly integrated and discoverable throughout the repository.

## What It Does

### 1. Changelog Management
- Adds entry to Recent Changes.md (appends at bottom for token efficiency)
- Uses public-facing language that avoids internal workflow references
- Includes proper date stamp and clear description of changes
- Maintains professional tone suitable for public documentation

### 2. Cross-Reference Updates
- Updates all relevant README files with new content links
- Adds navigation links where appropriate for content discovery
- Verifies alphabetical ordering in category listings
- Maintains consistency across all reference points

### 3. Timestamp Synchronization
- Updates "Last Updated" timestamps on all modified files
- Ensures consistent YYYY-MM-DD format throughout
- Removes any "Next Review" dates that may have been added
- Synchronizes dates across related files

### 4. Link Validation
- Checks all new internal links for accuracy
- Verifies proper encoding for spaces in file paths
- Confirms Obsidian compatibility for all wikilinks
- Tests navigation between related content sections

### 5. Archive Management
- Manages changelog archiving at month-end when needed
- Moves old entries to Archived Changes.md
- Maintains continuity with previous month's final week
- Keeps Recent Changes focused on current period

## Example Usage

### Single Content Addition
```
/sync-changes Added Runway AI video generation company to AI Infrastructure category
```
**Result**: Updates Recent Changes.md, Company Spotlight guide, AI Infrastructure README, and all related timestamps.

### Multiple Company Additions
```
/sync-changes Added three AI video companies: Runway, Pika Labs, and Luma AI across AI Infrastructure and AI Content categories
```

**What happens:**
1. **Recent Changes Entry**: Professional description of the three company additions
2. **Company Spotlight Updates**: Main guide updated with all three companies
3. **Category Updates**: Both AI Infrastructure and AI Content & Media READMEs updated
4. **Timestamp Sync**: All modified files receive current date stamps
5. **Link Validation**: All new internal links tested for accuracy

**Updated files:**
- `Recent Changes.md` (new entry appended)
- `Company Spotlight/CompanyGuide.md` (main directory)
- `Company Spotlight/AI Infrastructure/README.md` (if exists)
- `Company Spotlight/AI Content & Media/README.md` (if exists)
- Individual company files (timestamp updates)

### Complex Multi-Section Changes
```
/sync-changes Major AI Automations restructuring: created Finance, Consulting, Legal sections with 15 new professional automation guides
```

**Result**: Comprehensive update across multiple directories, READMEs, navigation files, and changelog with professional summary suitable for public documentation.

## Changelog Entry Standards

### Public-Facing Language
✅ **Good changelog entries:**
- "Added three AI video generation companies to Company Spotlight"
- "Created comprehensive Finance automation section with 5 professional guides"
- "Updated AI Risk section with individual risk assessment pages"

❌ **Avoid internal references:**
- "Moved files from companies to add list to main directory"
- "Removed internal TODO items and workflow notes"
- "Updated exclude folder with temporary content"

### Professional Tone
- Clear, descriptive language about what was added or changed
- Focus on user-visible improvements and additions
- Include specific numbers when relevant (companies added, guides created)
- Maintain consistency with existing changelog style

### Date Formatting
All changelog entries use consistent format:
```
### 2025-08-04

**Section Name Updates:**
- Specific change description with relevant details
- Additional change with context and scope
```

## Cross-Reference Management

### README File Updates
**Automatic Updates:**
- Main section READMEs (Company Spotlight, Tools, AI Automations)
- Category-specific READMEs within each section
- Navigation files (Automation Workflows by Job Role, etc.)
- Overview pages with alphabetical listings

**Alphabetical Ordering:**
- Maintains consistent alphabetical order in all listings
- Handles special characters and spacing appropriately
- Preserves existing formatting and structure
- Updates both main listings and category subsections

### Navigation Link Management
**Standard Navigation Sections:**
- Automation guides: "More Automations" section with standard links
- Company files: Integration with category and main guides
- Tool files: Cross-references in related tools sections
- Lesson learned files: Integration with main index and categories

**Link Format Consistency:**
- Uses proper Obsidian wikilink format `[[filename]]`
- Handles URL encoding for spaces in paths appropriately
- Maintains consistent description formats
- Verifies all links resolve correctly

## Timestamp Management

### Standard Format
All "Last Updated" timestamps use format: `*Last Updated: YYYY-MM-DD*`

### Files Updated
- **Primary Content**: The main files that were created or modified
- **Navigation Files**: READMEs and index files that now reference the new content
- **Cross-Referenced Content**: Related files that gained new links or references

### Date Consistency
- All related files receive the same current date
- No staggered or historical dates for batch updates
- Consistent formatting across all timestamp locations
- Removal of any "Next Review" dates found

## Archive Management

### Monthly Archiving Process
**End of Month Tasks:**
- Move older entries from Recent Changes.md to Archived Changes.md
- Retain last week of previous month for continuity
- Maintain chronological order in archived content
- Update archive file timestamps

**Archive Structure:**
```
## 2025-07 Archive

### 2025-07-31
[Final entries from July]

### 2025-07-30
[Previous entries]
```

### Continuity Maintenance
- Keep final week of previous month in Recent Changes
- Ensure smooth transition between monthly archives
- Maintain readable timeline for users
- Preserve all historical information in archives

## Quality Assurance

### Link Validation
**Internal Link Checks:**
- All new wikilinks resolve to existing files
- Cross-references between sections work correctly
- Navigation links in automation guides functional
- Category integration links accurate

**Common Issues Prevented:**
- Broken links from file moves or renames
- Incorrect path encoding for files with spaces
- Missing cross-references in related content
- Navigation loops or dead-end links

### Content Integration
**Consistency Checks:**
- New content appears in all relevant locations
- Alphabetical ordering maintained throughout
- Template compliance across similar content
- Professional language in all public-facing text

## Integration Benefits

### Automated Maintenance
- Eliminates manual changelog entry creation
- Ensures consistent cross-referencing
- Maintains accurate timestamp synchronization
- Prevents broken links and missing references

### Documentation Quality
- Professional changelog entries suitable for public view
- Consistent formatting across all reference points
- Reliable navigation structure throughout repository
- Up-to-date cross-references between related content

### Search Optimization
- Proper internal linking supports search engine crawling
- Consistent navigation aids content discoverability
- Updated timestamps signal content freshness
- Cross-references improve content relationship mapping

## Common Use Cases

1. **Content Publication**: Final step after adding new companies, tools, or guides
2. **Section Restructuring**: Major organizational changes requiring widespread updates
3. **Batch Additions**: Multiple related content items added simultaneously
4. **Cross-Section Integration**: Content that spans multiple repository sections

## Tips for Best Results

1. **Descriptive Summaries**: Provide clear, specific descriptions of changes made
2. **Professional Language**: Use terminology appropriate for public documentation
3. **Scope Clarity**: Include relevant details about extent and impact of changes
4. **Verification**: Review generated changelog entries for accuracy and tone

---

*Last Updated: 2025-08-04*
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

Rogue Codex is a knowledge base and documentation site built using Obsidian and published with Obsidian Publish. It contains curated collections of lessons learned, practical guides, and actionable insights across various domains including AI, personal development, business, and technology.

## Architecture & Structure

### Core Organization
- **Modular Knowledge Sections**: Each top-level directory represents a distinct knowledge domain with its own README.md
- **Template-Based Structure**: Consistent use of templates for lessons learned, tools evaluation, and project tracking
- **Obsidian-Native**: Uses Obsidian markdown format with double-bracket linking `[[link]]` between notes
- **Living Documentation**: Content is designed to evolve with checkboxes `- [ ]` for tracking progress and pending items

### Key Directories
- `100 TUF/` - 100-day personal development journey with phase-based structure
- `Lessons Learned/` - Structured template-based knowledge capture with categories
- `Tools/` - Tool evaluations with systematic criteria and workflow recommendations
- `AI Regulation/`, `AI Risk/`, `AI Automations/` - AI-focused content sections
- `Coding Setup/` - Non-technical user guides for coding tools
- `Thai Project/` - Real estate project documentation with changelog tracking

### Content Patterns
- Each section uses consistent README.md as entry point with overview and structure
- Template-driven content creation (see Lessons Learned template)
- Checkbox-based tracking for progress and todo items
- Date stamps and review cycles for content freshness
- Cross-linking between related concepts and sections

## Common Development Tasks

### Content Management
Since this is a documentation repository without build tools, primary tasks involve:

- **Adding New Content**: Follow existing template structures in each section
- **Updating READMEs**: Maintain consistent format across all section README files
- **Cross-Linking**: Use Obsidian's `[[link]]` format to connect related content
- **Progress Tracking**: Update checkbox items `- [ ]` to `- [x]` as tasks complete

### Content Quality Standards
- Maintain practical, actionable focus over theoretical concepts
- Include specific templates and frameworks for replicability
- Regular review cycles noted in footer timestamps
- Consistent categorization and tagging approach

### File Naming Conventions
- Use spaces in directory names (e.g., "Lessons Learned", "AI Regulation")
- URL-encode spaces in markdown links (e.g., `[link](Lessons%20Learned/README.md)`)
- Consistent README.md naming for section entry points

## Working with Obsidian Content

### Markdown Specifics
- Use Obsidian-style double-bracket links: `[[filename]]` or `[[Section/filename]]`
- Maintain checkbox syntax for task tracking: `- [ ] Task` and `- [x] Completed`
- Include date stamps and review cycles in content footers
- Use emoji prefixes for visual organization in README sections

### Content Templates
When adding new content, reference existing templates:
- **Lessons Learned**: Use the template structure in `Lessons Learned/README.md`
- **Tool Evaluations**: Follow the criteria structure in `Tools/README.md`
- **Project Tracking**: Use checkbox-based progress tracking like in `100 TUF/README.md`

### Site Publishing
The repository is published using Obsidian Publish, so:
- All content should be Obsidian-compatible markdown
- Internal links use Obsidian's double-bracket format
- Content structure supports Obsidian's graph view and search functionality
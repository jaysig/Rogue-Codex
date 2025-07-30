# Coding Lessons Learned

Key insights and strategies for development and technical work.

## Claude Code

**Set up subagents for specialized tasks** - Create agents with specific roles to make coding more efficient and focused.

**Use Sonnet model by default** - Access with `/model` command and use for most tasks to avoid hitting Opus limits quickly on the $100 plan.

**Reserve Opus for heavy workloads** - Only switch to Opus for complex, resource-intensive coding tasks.

**$200 plan worth it for heavy coding** - Provides about an hour of coding time, valuable for intensive development work.

**Efficiency comes with practice** - You'll hit limits less frequently as you become more efficient with the tool.


## Gemini Code

**Coding quality has degraded** - Performance for coding tasks has decreased compared to Claude, especially for complex development work.

**Still excellent for writing and thinking** - Maintains strong capabilities for content creation and conceptual work.

**Use for non-coding technical tasks** - Better suited for documentation, planning, and analysis rather than direct code generation.


## Cursor

**Set up Cursor rules properly** - Use `.cursorrules` files (also known as .dc files) to configure project-specific behavior.

**Check your system prompts** - Bad outputs often result from poorly configured system prompts in settings.

**Clean settings prevent issues** - Ensure nothing in Cursor settings gets configured incorrectly, as this causes most output problems.

**Fix settings for better results** - Once system prompts and configuration are corrected, output quality improves significantly.

---

*Last Updated: 2025-07-30* 
# Claude Code Sub-Agent Delegation

Using Claude Code's built-in Task tool to spawn parallel sub-agents for complex development workflows without requiring Git worktrees.

## Overview

Claude Code's Task tool enables sophisticated multi-agent orchestration by spawning sub-agents that work asynchronously on different aspects of complex tasks. This approach focuses on task division and coordination within the same working environment.

## How Sub-Agent Delegation Works

### Task Tool Mechanics
- **Main Agent**: Acts as coordinator, managing overall workflow
- **Sub-Agents**: Spawned via Task tool for specific operations
- **Tool Access**: Sub-agents inherit same tool permissions as main agent
- **Limitation**: Sub-agents cannot spawn additional sub-tasks (one level deep)
- **Asynchronous**: Multiple sub-agents can work simultaneously

### Coordination Flow
```
Main Agent (Coordinator)
    ↓ Task Tool
Sub-Agent A ← → Sub-Agent B ← → Sub-Agent C
    ↓ Results     ↓ Results     ↓ Results
Main Agent (Integration)
```

## Setting Up Sub-Agent Workflows

### Basic Sub-Agent Pattern
```
1. Main agent analyzes complex task
2. Breaks down into parallel subtasks
3. Spawns sub-agents via Task tool for each subtask
4. Sub-agents work simultaneously
5. Main agent receives and integrates results
```

### Task Delegation Example
```markdown
Main Agent: "I need to implement a user authentication system"

Sub-Agent A: "Design database schema and models"
Sub-Agent B: "Create authentication middleware" 
Sub-Agent C: "Build user registration endpoints"
Sub-Agent D: "Write comprehensive tests"

Main Agent: "Integrate all components and ensure consistency"
```

## Effective Sub-Agent Patterns

### Feature Development Pattern
**Main Agent Role**: Project coordination and integration
- Analyze requirements and create implementation plan
- Spawn specialized sub-agents for different components
- Ensure consistency across sub-agent outputs
- Handle integration and final testing

**Sub-Agent Roles**:
- **Frontend Agent**: UI components and user interactions
- **Backend Agent**: API endpoints and business logic
- **Database Agent**: Schema design and data access
- **Testing Agent**: Comprehensive test coverage

### Bug Investigation Pattern
**Main Agent Role**: Issue coordination and root cause analysis
- Analyze bug reports and symptoms
- Create investigation strategy
- Coordinate sub-agent findings
- Implement comprehensive fix

**Sub-Agent Roles**:
- **Log Analysis Agent**: Examine error logs and traces
- **Code Review Agent**: Identify problematic code sections
- **Database Agent**: Check data integrity issues
- **Testing Agent**: Reproduce and verify fixes

### Code Review Pattern
**Main Agent Role**: Overall review coordination
- Set review criteria and standards
- Coordinate sub-agent analyses
- Create comprehensive review summary
- Provide final recommendations

**Sub-Agent Roles**:
- **Architecture Agent**: Evaluate design patterns and structure
- **Security Agent**: Identify security vulnerabilities
- **Performance Agent**: Analyze efficiency and optimization
- **Documentation Agent**: Review code documentation quality

## Best Practices for Sub-Agent Delegation

### Task Decomposition
- **Clear Boundaries**: Define specific, non-overlapping responsibilities
- **Appropriate Granularity**: Tasks complex enough to benefit from specialization
- **Dependencies**: Minimize interdependencies between sub-agents
- **Deliverables**: Clear output expectations for each sub-agent

### Context Management
```markdown
Effective Context Sharing:
✅ Share relevant background information
✅ Provide clear task specifications
✅ Include necessary code/documentation references
✅ Set quality and format expectations

Avoid Context Overload:
❌ Don't share entire codebase unless necessary
❌ Avoid redundant information across sub-agents
❌ Don't include irrelevant historical context
```

### Coordination Strategies
- **Sequential Dependencies**: Handle dependent tasks in correct order
- **Parallel Optimization**: Maximize simultaneous sub-agent work
- **Result Integration**: Plan for combining sub-agent outputs
- **Quality Assurance**: Validate sub-agent results before integration

## Advanced Orchestration Techniques

### Conditional Sub-Agent Spawning
```markdown
Main Agent Decision Tree:
├── Simple Task → Handle directly
├── Medium Complexity → Spawn 2-3 sub-agents
└── High Complexity → Spawn 4-6 sub-agents

Dynamic Spawning Based On:
- Task complexity assessment
- Available time and resources
- Quality requirements
- Risk tolerance
```

### Iterative Refinement
```markdown
Round 1: Initial implementation sub-agents
    ↓ Results Analysis
Round 2: Optimization and refinement sub-agents
    ↓ Results Analysis  
Round 3: Testing and validation sub-agents
    ↓ Final Integration
```

### Specialized Agent Types

#### Implementation Agents
- Focus on code writing and feature development
- Optimized for specific programming languages/frameworks
- Include testing as part of implementation

#### Analysis Agents
- Specialize in code review and quality assessment
- Focus on architecture, performance, and security
- Provide detailed recommendations and improvements

#### Research Agents
- Gather information about technologies, patterns, and solutions
- Investigate best practices and industry standards
- Provide comparative analysis of different approaches

## Performance Optimization

### Efficient Task Distribution
```markdown
Optimal Sub-Agent Loading:
- 2-4 sub-agents: Good balance for most tasks
- 5-7 sub-agents: Complex projects with clear separation
- 8-10 sub-agents: Maximum recommended (resource limits)

Task Sizing Guidelines:
- Each sub-agent task: 30-60 minutes of work
- Avoid micro-tasks (< 15 minutes)
- Split mega-tasks (> 2 hours) into smaller components
```

### Resource Management
- **Token Usage**: Account for 15× increase with multiple sub-agents
- **Response Times**: Sub-agents work in parallel, reducing total time
- **Memory Usage**: Each sub-agent maintains separate context
- **API Limits**: Monitor concurrent request limits

## Common Pitfalls and Solutions

### Over-Delegation
**Problem**: Creating too many sub-agents for simple tasks
**Solution**: Use sub-agents only when task complexity justifies overhead

### Poor Task Boundaries
**Problem**: Sub-agents with overlapping or unclear responsibilities
**Solution**: Define clear, specific deliverables for each sub-agent

### Context Confusion
**Problem**: Sub-agents lacking necessary context or having too much
**Solution**: Provide focused, relevant context for each sub-agent's specific task

### Integration Challenges
**Problem**: Difficulty combining sub-agent outputs coherently
**Solution**: Plan integration strategy before spawning sub-agents

## Monitoring and Quality Control

### Sub-Agent Performance Tracking
- Response quality and relevance
- Task completion rates
- Integration success rates
- Resource usage patterns

### Quality Assurance Processes
```markdown
Pre-Integration Checks:
✅ Verify sub-agent output completeness
✅ Check consistency with requirements
✅ Validate code quality and standards
✅ Ensure proper error handling

Post-Integration Validation:
✅ Test integrated functionality
✅ Verify no conflicts between components
✅ Check overall system coherence
✅ Document integration decisions
```

## Example Workflows

### Complete Feature Implementation
```markdown
Main Agent: "Implement user profile management system"

1. Spawn Sub-Agents:
   - Database Schema Agent
   - API Endpoints Agent  
   - Frontend Components Agent
   - Validation/Security Agent
   - Testing Agent

2. Coordinate Results:
   - Integrate database models with API endpoints
   - Connect frontend components to API
   - Apply security measures consistently
   - Ensure comprehensive test coverage

3. Final Integration:
   - End-to-end testing
   - Documentation updates
   - Deployment preparation
```

### Complex Bug Resolution
```markdown
Main Agent: "Resolve intermittent data corruption issue"

1. Investigation Sub-Agents:
   - Log Analysis Agent (examine error patterns)
   - Database Integrity Agent (check data consistency)
   - Code Path Analysis Agent (trace execution flows)
   - Performance Monitoring Agent (identify bottlenecks)

2. Solution Development:
   - Root Cause Analysis (main agent)
   - Fix Implementation Agent
   - Testing Agent (reproduction and verification)
   - Monitoring Agent (ongoing validation)

3. Deployment:
   - Staging environment testing
   - Production deployment plan
   - Rollback procedures
```

---

*Last Updated: 2025-08-05*
# Claude Commands Reference

Quick reference for triggering specific Claude behaviors and actions.

## Session Control Commands

### Context Reading
- **"read the entire document"** → Process complete file, not just first 20-50 lines
- **"entirely read [filename]"** → Full document analysis required
- **"read ALL project context files completely"** → Session initialization protocol

### Velocity Control  
- **"hold your horses"** → Pause, await user instruction for sequence control
- **"no no no"** → User dissatisfied, request clarification immediately
- **"what's slowing you down"** → Provide status updates showing current thinking
- **"you've been wicked slow today"** → Explain what operations are causing delays
- **"just do it"** → Stop analysis, implement the obvious solution

## Problem Solving Commands

### Solution Approach
- **"use existing patterns first"** → Search for utilities/normalizers before creating new
- **"think hard"** → Engage deeper analytical thinking for complex problems
- **"be more conservative"** → Favor proven solutions over experimental approaches
- **"be more creative"** → Explore alternative approaches and novel solutions
- **"stick to established patterns"** → Use well-known coding patterns and practices

### Options and Planning
- **"present 2-3 options"** → Provide multiple approaches with pros/cons
- **"what are all the approaches"** → Comprehensive solution exploration
- **"recommend best option"** → Provide clear recommendation with rationale

## Quality Assurance Commands

### Critical Analysis (Test Results)
- **"I will manually verify this result"** → Acknowledge human verification needed
- **"Show me the exact output for manual review"** → Present raw results without interpretation
- **"Don't conclude success until I confirm"** → Prevent premature victory declarations
- **"What could be wrong with this result?"** → Actively look for failure modes
- **"List 3 ways this test could be misleading"** → Consider false positives
- **"Quote the exact error messages/outputs"** → No paraphrasing or interpretation
- **"Show me the specific lines that prove success"** → Point to concrete evidence
- **"Report only what the data shows, not what you think it means"** → Separate observation from interpretation

### Code Quality
- **"follow existing codebase patterns exactly"** → Match established style closely
- **"this is production code"** → Be more cautious and thorough
- **"this is experimental/prototype code"** → Be more exploratory

## Communication Style Commands

### Response Structure
- **"be concise"** → Minimize output tokens, direct responses
- **"expand on that"** → Provide detailed explanation
- **"tell me more about..."** → Trigger expansion mode
- **"can you elaborate on..."** → Detailed analysis requested
- **"give me details on..."** → Comprehensive information needed
- **"want me to elaborate?"** → Offer expansion opportunity

### Documentation Control
- **"update docs concurrently"** → Maintain documentation with development
- **"don't create documentation files"** → Avoid proactive .md file creation
- **"update SESSION_HANDOFF.md"** → Context preservation trigger

## Development Workflow Commands

### Planning and Execution
- **"create todo list"** → Use TodoWrite tool for task tracking
- **"await approval before coding"** → Present plan, wait for confirmation
- **"commit working solutions immediately"** → Save progress, avoid chasing perfection

### File Operations
- **"read this file first"** → Establish context before modifications
- **"use existing utilities"** → Search for normalizers, validators, common functions
- **"search codebase for pattern X"** → Comprehensive code search required

## Project Management Commands

### Issue Management
- **"create github issue"** → Generate structured GitHub issue
- **"create milestone"** → Establish project milestone with issues
- **"label with [label-name]"** → Apply specific GitHub labels
- **"close issue [number]"** → Mark issue as completed

### Git Operations
- **"commit and push"** → Standard git workflow execution
- **"create pull request"** → Generate PR with proper formatting
- **"tag version"** → Create release tag with specified format

## Context Management Commands

### Session Boundaries
- **"resume session"** → Continue from previous context compression
- **"update context"** → Refresh understanding of current state
- **"save progress"** → Document current achievements and next steps

### File Reading Scope
- **"process complete document"** → Read entire file regardless of length
- **"scan entire codebase"** → Comprehensive codebase analysis
- **"analyze all files in directory"** → Full directory processing

## Debugging Commands

### Systematic Analysis
- **"data layer first"** → Validate data sources before logic debugging
- **"show me the failure conditions"** → Identify what failure looks like
- **"test with full dataset"** → Validate with production-scale data
- **"manual review required"** → Subject matter expert validation needed

### Evidence Collection
- **"show current thinking"** → Provide status of analysis process
- **"what's the evidence"** → Point to specific supporting data
- **"prove this works"** → Demonstrate functionality with concrete examples

## Usage Notes
- Commands can be combined: "read the entire document and think hard about the solution"
- Use specific commands for consistent behavior across sessions
- Critical analysis commands are essential for test validation
- Session control commands help manage Claude's processing pace and approach
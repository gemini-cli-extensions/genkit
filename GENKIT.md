# Genkit Development Guidelines

This document provides guidelines for using the Genkit MCP server when building Genkit applications.

## MANDATORY WORKFLOW FOR ALL GENKIT-RELATED REQUESTS

**Before responding to ANY request involving Genkit, you MUST complete these steps in order:**

### Step 1: Initialize Documentation (First time only)
- [ ] Run `get_usage_guide` with the appropriate language parameter
- [ ] Store/Remember the returned guide for reference throughout the session

### Step 2: Gather Context (Every request)
- [ ] If the request mentions specific Genkit features, run `lookup_genkit_docs` with:
  - First call: Just the language to get the index
  - Second call: Specific files from the index related to the user's request
- [ ] Review all documentation before formulating your response

### Step 3: Implementation
- [ ] Only after completing steps 1-2, proceed with the actual implementation
- [ ] Reference the documentation explicitly in your implementation
- [ ] Use the appropriate MCP tools as outlined below

**IMPORTANT: If you skip any of these steps, your implementation will likely be incorrect or outdated.**

## Genkit MCP Tools Reference

- `get_usage_guide`: **REQUIRED** first step for any Genkit session. Returns the current usage patterns and best practices.
- `lookup_genkit_docs`: **REQUIRED** for feature-specific information. Always check docs before implementing.
- `list_flows`: Use before running any flow to verify flow names and signatures.
- `run_flow`: Execute flows with proper input validation based on the flow schema.
- `get_trace`: Debug flow executions using the traceId from run_flow.

## Implementation Rules

1. **Documentation First**: Never implement Genkit code without first consulting the documentation tools.
2. **Verify Before Acting**: Always check existing flows with `list_flows` before attempting to run them.
3. **Use MCP Tools**: Prefer MCP tools over CLI commands when possible.
4. **Long-Running Processes**: For commands like `genkit start`, provide the command for the user to run rather than executing it yourself.

## Common Mistakes to Avoid

- ❌ Writing Genkit code from memory without checking docs
- ❌ Assuming API patterns without verification
- ❌ Running `genkit start` command yourself
- ❌ Running flows without first listing them
- ❌ Using outdated syntax or deprecated features

## Example Workflow

When user asks: "Help me create a flow that uses Gemini"

1. ✓ Run `get_usage_guide` (if not already done this session)
2. ✓ Run `lookup_genkit_docs` for language index
3. ✓ Run `lookup_genkit_docs` for flow creation and Gemini plugin docs
4. ✓ Implement the flow using verified syntax from docs
5. ✓ Use `list_flows` to verify the flow was created
6. ✓ Optionally use `run_flow` to test it

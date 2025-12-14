---
name: codebase-analysis
description: Analyze codebase structure and patterns. Use when users ask about how code is organized or want to understand existing architecture.
allowed-tools: Read, Grep, Glob, Bash
---

# Codebase Analysis

Provide architectural insights when users explore or question existing code.

## Activation Triggers

- Questions about code organization
- Requests to explain how something works
- Technical debt discussions
- Refactoring planning
- Onboarding to a new codebase

## Analysis Techniques

1. **Directory Analysis**: Use Glob to map structure
2. **Pattern Search**: Use Grep to find conventions
3. **File Inspection**: Use Read for key files
4. **Dependency Check**: Examine package/module files

## Response Format

When analyzing code, structure responses as:

1. **What exists**: Factual description of current state
2. **How it works**: Flow and interaction explanation
3. **Why it matters**: Architectural implications
4. **What to consider**: Relevant trade-offs or concerns

Keep responses focused on the specific question. Avoid unsolicited comprehensive reviews.

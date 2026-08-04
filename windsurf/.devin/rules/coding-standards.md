---
trigger: always_on
description: "Core coding standards, security, and error handling conventions"
---

# Coding Standards

## General

- Follow existing project patterns and conventions before introducing new ones
- Read existing code before writing new code
- Match the project's style, libraries, and architecture
- Keep changes minimal and focused on what was asked

## TypeScript / JavaScript

- Use TypeScript strict mode when available
- Prefer explicit types on exported functions
- Use `const` over `let`; never use `var`
- Use template literals instead of string concatenation
- Prefer early returns to reduce nesting

## Error handling

- Handle all errors with try/catch and appropriate user feedback
- Use typed errors where possible
- Never swallow errors silently

## Security

- Never commit secrets: `.env`, `.env.local`, API keys, tokens, credentials
- Use environment variables for all secrets
- Use parameterized queries — never string concatenation for SQL
- Validate and sanitize all external inputs
- Prefer pinned dependency versions over open ranges

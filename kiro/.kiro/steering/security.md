---
inclusion: always
---

# Security

- Never commit secrets: `.env`, `.env.local`, API keys, tokens, credentials
- Never log or echo sensitive values in output
- Use environment variables for all secrets
- Use parameterized queries — never string concatenation for SQL/queries
- Validate and sanitize user input
- Prefer pinned dependency versions over open ranges

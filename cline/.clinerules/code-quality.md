# Code Quality

- Follow existing project patterns and conventions before introducing new ones
- Use TypeScript strict mode when available
- Prefer explicit types on exported functions
- Use `const` over `let`; never use `var`
- Use template literals instead of string concatenation
- Prefer early returns to reduce nesting
- Handle all errors with try/catch and appropriate user feedback
- Use typed errors where possible
- Never swallow errors silently
- Validate all external inputs (API params, user input, env vars)

# style-minimize-admonitions

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Callout boxes (Note, Warning, Important, Caution) are designed to draw attention to critical information. When overused, they create visual noise and readers learn to ignore them — including the ones that actually matter. If everything is a warning, nothing is.

## Incorrect

```markdown
> **Note**: You need an API key to continue.

> **Important**: The API key must have write permissions.

> **Warning**: Don't share your API key publicly.

> **Caution**: Rate limits apply to all API calls.

> **Note**: See the API reference for all endpoints.
```

Five callouts in a row. The reader's eye skips all of them.

## Correct

```markdown
You need an API key with write permissions to continue.
See [API Keys](/reference/api-keys) for setup instructions.

> **Warning**: Never expose your API key in client-side code
> or public repositories. Use environment variables instead.

Rate limits apply to all API calls. See [rate limits](/reference/rate-limits).
```

One callout for the genuinely critical security concern. Everything else flows as regular text.

## Guidelines

- Maximum 2-3 admonitions per page
- Use **Warning** only for data loss or security risks
- Use **Note** only for genuinely surprising or non-obvious information
- If the information is expected or routine, write it as regular text
- If a page needs many warnings, the product has a UX problem, not a docs problem

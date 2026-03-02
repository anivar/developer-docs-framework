# write-explanation-no-steps

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Explanation documentation provides the "why" — design decisions, architectural context, trade-offs, and conceptual foundations. When step-by-step procedures creep in, the document loses its reflective purpose. Readers of explanation are thinking, not doing. They're away from the keyboard, building mental models. Procedures break that flow.

## Incorrect

```markdown
# Understanding Rate Limiting

Rate limiting protects our API from abuse. Here's how to
configure it:

1. Set your rate limit in the dashboard
2. Add the X-RateLimit-Remaining header check to your code
3. Implement exponential backoff

When you hit a rate limit, you'll get a 429 response. The
algorithm uses a token bucket approach where...
```

This starts as explanation, shifts to a how-to guide, then returns to explanation.

## Correct

```markdown
# Understanding Rate Limiting

## Why rate limiting exists

Rate limiting protects API stability by preventing any single
client from consuming disproportionate resources. Without it,
a misconfigured integration could degrade service for all users.

## How the token bucket works

Our rate limiter uses a token bucket algorithm. Each API key
receives a bucket with a fixed capacity. Each request consumes
one token. Tokens regenerate at a fixed rate...

## Why token bucket over alternatives

We considered fixed windows (simpler but causes thundering
herd at window boundaries) and sliding windows (smoother but
more memory per client). Token buckets balance fairness with
implementation simplicity.

**Related**: [How to handle rate limits](/guides/rate-limiting) |
[Rate limit API reference](/reference/rate-limits)
```

## Principle

Explanation discusses, contextualizes, and illuminates. It never says "do this." If you find yourself writing numbered steps, you're writing a how-to guide — move those steps to a separate document and link to it.

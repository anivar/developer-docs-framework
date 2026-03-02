# style-tone-matches-type

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Each Diataxis content type serves a reader in a different mental state. The tone must match. A tutorial reader needs encouragement. A reference reader needs precision. A how-to reader needs efficiency. Using the wrong tone creates friction — an overly casual reference doc feels unreliable, an overly formal tutorial feels intimidating.

## Incorrect

A tutorial with reference tone:

```markdown
# Authentication Tutorial

The `authenticate()` method accepts a `credentials` parameter
of type `AuthCredentials`. It returns a `Promise<AuthResult>`.
The method throws `AuthError` if credentials are invalid.
```

And reference docs with tutorial tone:

```markdown
# POST /v1/auth/token

Let's learn about the token endpoint! First, we'll explore
what happens when you send a request...
```

Both are mismatched.

## Correct

**Tutorial** — encouraging, collaborative:
```markdown
Let's build your first authenticated request. We'll start
by creating an API key, then use it to fetch some data.
You should see a JSON response like this:
```

**How-to guide** — direct, efficient:
```markdown
Configure the storage bucket to serve files over CDN.

1. Navigate to **Settings > Distribution**
2. Enable the CDN toggle for your bucket
```

**Reference** — precise, neutral:
```markdown
### POST /v1/auth/token

Creates an authentication token. Returns a `Token` object
with `access_token` and `expires_at` fields.
```

**Explanation** — conversational, exploratory:
```markdown
The system uses eventually consistent replication because
strong consistency would add 200ms latency to every write.
This trade-off favors throughput over immediate consistency...
```

## Quick Reference

| Type | Tone | Example Phrasing |
|------|------|-----------------|
| Tutorial | Encouraging, patient | "Let's create...", "You should see..." |
| How-to | Direct, efficient | "Configure the...", "Run the command..." |
| Reference | Neutral, precise | "Returns a...", "Accepts a string..." |
| Explanation | Thoughtful, exploratory | "The reason for...", "This means that..." |
| Troubleshooting | Calm, reassuring | "If you see this error...", "This usually means..." |

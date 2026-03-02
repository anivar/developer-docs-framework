# write-one-purpose-per-doc

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

The single most impactful rule in documentation. Every document must serve exactly one of the four Diataxis purposes: learning (tutorial), task completion (how-to), information lookup (reference), or understanding (explanation). Mixing purposes creates documents that serve no audience well — too procedural for learners, too explanatory for practitioners, too incomplete for reference.

## Incorrect

A single page that mixes tutorial, reference, and explanation:

```markdown
# Authentication

## Overview
Authentication in our system uses OAuth 2.0 because it provides
delegated authorization without sharing credentials... (explanation)

## Getting Started
1. First, let's create an API key. Go to the dashboard...
2. Now let's make our first authenticated request... (tutorial)

## API Reference
### POST /auth/token
| Parameter | Type | Required |
|-----------|------|----------|
| grant_type | string | yes | (reference)

## Why OAuth 2.0?
We chose OAuth 2.0 over API keys because... (explanation again)
```

This page forces every reader to scan past content they don't need. The learner skips the reference table. The practitioner skips the explanation. Nobody finds what they need quickly.

## Correct

Split into four focused documents:

```
docs/
├── tutorials/authentication.md        → "Build authenticated requests step by step"
├── guides/add-oauth-to-your-app.md    → "How to add OAuth to your app"
├── reference/auth-api.md              → POST /auth/token parameters, responses, errors
└── concepts/why-oauth.md              → "Understanding our authentication architecture"
```

Each document serves one audience in one mental state. Cross-link between them:

```markdown
# How to Add OAuth to Your App

[1-2 sentences, then straight to steps]

**Prerequisites**: Complete the [authentication tutorial](../tutorials/authentication.md)

## Steps
...

**Related**: [Authentication API reference](../reference/auth-api.md) |
[Why we use OAuth 2.0](../concepts/why-oauth.md)
```

## Decision Table

| If you're writing... | It belongs in... |
|---------------------|-----------------|
| Step-by-step learning with visible results | Tutorial |
| Steps to accomplish a specific goal | How-to guide |
| Complete parameter/endpoint/config details | Reference |
| "Why" and design decisions | Explanation |
| A mix of two or more | Split into separate documents |

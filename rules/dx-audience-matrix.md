# dx-audience-matrix

**Priority**: HIGH
**Category**: Developer Experience

## Why It Matters

Enterprise products serve multiple audiences with different goals, knowledge levels, and time constraints. Writing for "developers" as a monolithic audience creates documentation that's too basic for experts and too advanced for beginners. Mapping audiences to content types ensures every reader finds content written for their specific needs.

## The Matrix

| Audience | Mental State | Primary Goal | Key Content Types |
|----------|-------------|-------------|-------------------|
| **New developers** | Curious, uncertain | "Can I use this?" | Quickstart, Tutorial |
| **Building developers** | Focused, time-pressed | "How do I do X?" | How-to guides, API reference |
| **Evaluating developers** | Analytical, comparing | "Is this the right choice?" | Explanation, Architecture |
| **Partner integrators** | External, different context | "How does this fit?" | Integration guide, SDK reference |
| **Internal engineers** | Operational, on-call | "How do I fix this?" | Runbook, Config reference |
| **Decision makers** | Strategic, non-coding | "What does this enable?" | Architecture overview, Explanation |

## How to Apply

1. **Identify your audiences** — which rows apply to your product?
2. **Check coverage** — does each audience have their key content types?
3. **Don't mix** — a quickstart optimized for new developers should not include operator-level configuration
4. **Create entry points** — each audience should have a clear landing path ("I'm a partner" → integration docs)

## Incorrect

A single "Getting Started" page that tries to serve everyone:

```markdown
# Getting Started

For developers: install the SDK...
For operators: configure the cluster...
For partners: set up your integration...
```

## Correct

Separate entry points per audience, linked from a landing page:

```markdown
# Documentation

- **[Quickstart](/quickstart)** — Make your first API call in 5 minutes
- **[Partner Integration](/partners/getting-started)** — Connect your platform
- **[Operations Guide](/ops/setup)** — Deploy and configure for production
```

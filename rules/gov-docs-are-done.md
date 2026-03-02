# gov-docs-are-done

**Priority**: MEDIUM
**Category**: Governance & Lifecycle

## Why It Matters

When documentation is optional, it becomes perpetually "we'll write it later." Stripe's approach — a feature isn't shipped until its documentation is written, reviewed, and published — is the single most effective way to prevent documentation debt. They reinforce this by including documentation in engineering career ladders and performance reviews.

## Incorrect

```
Feature PR: ✅ Code complete
Feature PR: ✅ Tests passing
Feature PR: ✅ Code review approved
Feature PR: ❌ Documentation: "Will add later"

Release: Ship it anyway.
```

## Correct

```
Feature PR: ✅ Code complete
Feature PR: ✅ Tests passing
Feature PR: ✅ Code review approved
Feature PR: ✅ Documentation PR linked and approved

Release: Ship code + docs together.
```

## Implementation

1. **Definition of done** includes documentation
2. **PR template** has a documentation checklist
3. **Release checklist** includes docs verification
4. **Career ladders** include documentation expectations
5. **Performance reviews** assess documentation contributions

## What "Documentation" Means Per Change

| Change Type | Documentation Required |
|------------|----------------------|
| New feature | How-to guide + API reference updates |
| Breaking change | Migration guide + changelog entry |
| Bug fix | Troubleshooting update (if user-facing) |
| Deprecation | Deprecation notice + migration path |
| Configuration change | Config reference update |

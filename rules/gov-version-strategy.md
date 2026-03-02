# gov-version-strategy

**Priority**: MEDIUM
**Category**: Governance & Lifecycle

## Why It Matters

Versioning documentation incorrectly creates maintenance burden (too many versions) or confusion (outdated docs for current users). The key insight: version documentation that describes versioned behavior, don't version documentation that's version-independent.

## What to Version

| Content Type | Version? | Reason |
|-------------|----------|--------|
| API reference | **Yes** | Endpoints differ between API versions |
| SDK reference | **Yes** | Methods differ between SDK versions |
| Migration guides | **Yes** | Each is tied to a specific version transition |
| Configuration reference | **Yes** | Options change between versions |
| How-to guides | **Usually yes** | Steps may differ between versions |
| Tutorials | **Sometimes** | Only if the tutorial uses version-specific features |
| Explanation | **No** | Concepts rarely change between versions |
| Architecture guide | **No** | Unless architecture fundamentally changes |
| Glossary | **No** | Terms are version-independent |

## Lifecycle

```
Preview → Current → Supported → Deprecated → Archived
```

- **Preview**: Pre-release docs, labeled as draft, may change
- **Current**: Latest stable version, default for all users
- **Supported**: Previous versions still receiving security updates
- **Deprecated**: End-of-life, link prominently to migration guide
- **Archived**: Read-only, clearly marked, may be removed

## Principle

Always link deprecated docs to migration guides. A deprecation notice without a migration path is an abandonment notice.

# style-consistent-terminology

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

When documentation alternates between "workspace," "project," and "environment" for the same concept, readers waste time figuring out whether these are different things or the same thing with different names. Consistent terminology reduces cognitive load and builds confidence. One term, one concept, everywhere.

## Incorrect

```markdown
Create a new workspace from the dashboard. Once your project
is ready, configure the environment settings. Your workspace
will then be accessible via the project URL.
```

Are "workspace," "project," and "environment" the same thing? Different things? The reader can't tell.

## Correct

```markdown
Create a new workspace from the dashboard. Once your workspace
is ready, configure its settings. Your workspace is accessible
at `https://app.example.com/workspaces/{id}`.
```

One concept, one term, consistently.

## Practice

- Maintain a glossary and reference it during writing and review
- If the UI calls it a "workspace," call it a "workspace" in the docs
- Use industry-standard terms for established concepts (webhook, not "notification callback")
- Define product-specific terms on first use or link to the glossary
- When renaming a concept, update all documentation, not just new pages

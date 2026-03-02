# arch-cross-link-strategy

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Documentation without cross-links creates dead ends. A developer finishes a tutorial and doesn't know where to go next. A how-to guide mentions a concept without linking to the explanation. Cross-links create a navigable web that guides developers through the documentation based on their evolving needs.

## Incorrect

```markdown
# How to Deploy a Container

1. Build the Docker image
2. Push to the registry
3. Create a deployment

The container restarts automatically on failure.
```

No prerequisites. No next steps. No links to related content. A dead end.

## Correct

```markdown
# How to Deploy a Container

**Prerequisites**: [Install the CLI](/guides/cli-setup) |
[Configure your registry credentials](/guides/registry-auth)

1. Build the Docker image
2. Push to the registry
3. Create a deployment

The container restarts automatically on failure.

## Next steps

- [Configure autoscaling](/guides/autoscaling)
- [Troubleshoot failed deployments](/troubleshooting/deployments)

## Related

- [Deployments API reference](/reference/deployments)
- [Understanding container orchestration](/concepts/orchestration)
```

## Link Pattern

Every document should include:

| Section | Links To |
|---------|---------|
| **Prerequisites** | What the reader must know/have done first |
| **Inline** | Terms, APIs, and concepts mentioned in the text |
| **Next steps** | Where to go after this document |
| **Related** | Same topic, different content types (reference ↔ how-to ↔ explanation) |

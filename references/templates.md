# Documentation Templates

Ready-to-use structural templates for each content type. Copy the relevant template and fill in the sections. Guided by Good Docs Project templates and patterns from Stripe, AWS, and Google documentation.

## How to Use These Templates

1. Choose the template matching your content type
2. Copy the structure into your document
3. Replace placeholder text (marked with `[brackets]`) with your content
4. Remove any optional sections that don't apply
5. Follow the inline guidance comments (marked with `<!-- -->`)

---

## Tutorial Template

```markdown
# Build [a concrete thing] with [product]

<!-- Tutorials are learning-oriented. The reader is a student, not a practitioner. -->
<!-- Success = the reader gained confidence and skills, not just task completion. -->

## What you'll build

[1-2 sentence description of the end result with a screenshot or diagram]

## Before you begin

<!-- List ONLY what the reader must have. Don't explain these — link to setup docs. -->

- [Prerequisite 1, with link to setup]
- [Prerequisite 2, with link to setup]

**Time to complete**: [estimated time, e.g., "About 15 minutes"]

## Step 1: [Action verb + what this step accomplishes]

[1-2 sentences of context — what this step does and why]

```[language]
[code for this step]
```

You should see:

```
[exact expected output]
```

<!-- Every step must produce a visible result. If a step has no output, combine it with the next step. -->

## Step 2: [Action verb + what this step accomplishes]

[Continue pattern: brief context → code → expected output]

## Step 3: [Action verb + what this step accomplishes]

[Continue pattern]

## What you've learned

<!-- Summarize what skills the reader acquired, not just what they built. -->

You've built [what they built]. Along the way, you learned how to:

- [Skill or concept 1]
- [Skill or concept 2]
- [Skill or concept 3]

## Next steps

- [Link to next tutorial or how-to guide]
- [Link to relevant explanation doc for deeper understanding]
- [Link to API reference for the resources used]
```

---

## Quickstart Template

```markdown
# Quickstart

<!-- Quickstarts are for experienced developers who want the fastest path to "hello world." -->
<!-- Target: under 5 minutes. Strip everything non-essential. -->

## Prerequisites

- [Prerequisite 1]
- [Prerequisite 2]

## Install

```[shell]
[installation command]
```

## Configure

<!-- Show the minimum configuration needed. -->

```[language]
[minimum configuration code]
```

## Make your first [API call / operation]

```[language]
[code for the simplest meaningful operation]
```

Response:

```json
[expected response]
```

## Next steps

- [Tutorial for deeper learning]
- [How-to guide for common tasks]
- [API reference for all endpoints]
```

---

## How-to Guide Template

```markdown
# How to [accomplish specific goal]

<!-- How-to guides are task-oriented. The reader has a specific goal and wants to achieve it. -->
<!-- Don't teach. Don't explain theory. Get to the solution. -->

[1 sentence: what this guide helps you do and when you'd need it]

## Prerequisites

- [What must be in place before starting]

## Steps

### 1. [Action step]

[Brief instruction with code example]

```[language]
[code]
```

### 2. [Action step]

[Brief instruction with code example]

### 3. [Action step]

[Brief instruction with code example]

## Verify

<!-- How to confirm the task completed successfully -->

[Verification steps or expected outcome]

## Related guides

- [Link to related how-to guide]
- [Link to troubleshooting if something goes wrong]
```

---

## Integration Guide Template

```markdown
# Integrate [product] with [partner system / use case]

## Overview

[2-3 sentences: what this integration enables and the high-level architecture]

<!-- Include a simple architecture diagram showing the interaction between systems -->

```
[Your System] ---> [Product API] ---> [Partner System]
```

## Prerequisites

- [Account / credential requirements]
- [Environment requirements]
- [Dependencies]

## Authentication

<!-- How to authenticate requests between systems -->

[Authentication setup steps with code]

## Step 1: [First integration step]

<!-- Show both sides of the integration where relevant -->

[Steps with code examples]

## Step 2: [Second integration step]

[Steps with code examples]

## Error handling

<!-- Cover errors the partner will actually encounter -->

| Error | Cause | Resolution |
|-------|-------|------------|
| [Error code/message] | [Why it happens] | [How to fix] |

## Testing

<!-- How to verify the integration works end-to-end -->

### Sandbox testing

[How to test without affecting production]

### Production verification

[How to confirm production integration works]

## Going to production checklist

- [ ] [Security review item]
- [ ] [Configuration item]
- [ ] [Monitoring item]
- [ ] [Support contact established]

## Support

[How to get help: support channels, SLAs, escalation paths]
```

---

## Migration Guide Template

```markdown
# Migrate from v[X] to v[Y]

## Overview

<!-- Lead with impact assessment so readers can plan -->

**Estimated effort**: [time estimate for typical integration]
**Breaking changes**: [count]
**Deprecations**: [count]

### Key changes

- [Most important change, one sentence]
- [Second most important change]
- [Third most important change]

## Before you begin

- [ ] Back up your current configuration
- [ ] Review the [changelog](/changelog/vY) for full details
- [ ] Ensure you're on v[X] (migration from earlier versions requires [link to previous migration guide])

## Automated migration

<!-- If available, show automated migration tools first -->

```shell
[codemod or migration script command]
```

This handles: [what the automated tool migrates]

You'll still need to manually address: [what it doesn't handle]

## Breaking changes

### [Change 1: descriptive title]

**What changed**: [One sentence description]
**Why**: [Brief rationale]

Before (v[X]):
```[language]
[old code pattern]
```

After (v[Y]):
```[language]
[new code pattern]
```

### [Change 2: descriptive title]

[Same pattern: what, why, before, after]

## Deprecations

<!-- These still work but will be removed in a future version -->

| Deprecated | Replacement | Removal Target |
|-----------|-------------|----------------|
| [old API/feature] | [new API/feature] | v[Z] |

## New features (optional adoption)

<!-- Features available in v[Y] that users can adopt at their own pace -->

- [New feature 1]: [one sentence + link to docs]
- [New feature 2]: [one sentence + link to docs]

## Verification

After migration, verify by:

1. [Verification step]
2. [Verification step]
3. [Run test suite]

## Rollback

If something goes wrong:

1. [Rollback step]
2. [Rollback step]

## Getting help

[Support channels for migration issues]
```

---

## API Reference Template (per endpoint)

```markdown
## [Method] [Path]

<!-- e.g., POST /v1/payments -->

[One sentence: what this endpoint does]

### Authentication

[Required authentication method]

### Parameters

#### Path parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `[name]` | [type] | [description] |

#### Query parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `[name]` | [type] | [yes/no] | [default] | [description] |

#### Request body

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `[name]` | [type] | [yes/no] | [description] |

### Request example

```[shell/language]
[complete request example with realistic values]
```

### Response

#### Success (200)

```json
[complete response example]
```

| Field | Type | Description |
|-------|------|-------------|
| `[name]` | [type] | [description] |

#### Errors

| Status | Code | Description |
|--------|------|-------------|
| 400 | `invalid_request` | [what's wrong and how to fix] |
| 401 | `unauthorized` | [what's wrong and how to fix] |
| 404 | `not_found` | [what's wrong and how to fix] |
```

---

## Changelog Template

```markdown
# Changelog

## [Version] — [Date]

<!-- One sentence summary of the most significant change -->

### Added
- [New feature with link to documentation]

### Changed
- [Changed behavior with migration note if needed]

### Deprecated
- [Deprecated feature with link to replacement]

### Removed
- [Removed feature with link to migration guide]

### Fixed
- [Bug fix with specific description]

### Security
- [Security fix with severity note]
```

---

## Explanation Template

```markdown
# Understanding [concept]

<!-- or: "How [system/feature] works" -->
<!-- Explanation is understanding-oriented. Don't include steps or reference details. -->

## Overview

[2-3 sentences: why this topic matters and what the reader will understand after reading]

## [Core concept 1]

[Explain the concept using analogies, examples, and connections to familiar ideas]

<!-- Use diagrams to show relationships and architecture -->

## [Core concept 2]

[Continue explaining, building on the previous section]

## Design decisions

<!-- What was chosen and why — the trade-offs involved -->

[Explain the reasoning behind key design choices]

**Why not [alternative approach]?** [Brief explanation of what was considered and rejected]

## Trade-offs

| Choice | Benefit | Cost |
|--------|---------|------|
| [Design choice] | [What you gain] | [What you give up] |

## Further reading

- [Link to related explanation doc]
- [Link to external resource that provides additional context]
- [Link to relevant how-to guide for practical application]
```

---

## Troubleshooting Template

```markdown
# Troubleshooting [area/feature]

<!-- Organize by symptom (what the user sees), not by cause (what's wrong). -->

## [Error message or symptom]

**Symptom**: [What the user observes — include exact error messages]

**Diagnosis**:
[How to confirm this specific problem]

```[shell]
[diagnostic command if applicable]
```

**Solution**:

1. [Fix step 1]
2. [Fix step 2]

**Why this happens**: [Brief explanation, link to deeper docs]

---

## [Next error message or symptom]

[Same pattern: symptom → diagnosis → solution → explanation]
```

---

## Runbook Template

```markdown
# [Service/System] Runbook

**Owner**: [Team name]
**Last verified**: [Date]
**Escalation**: [Contact/channel]

## Access

| System | How to Access |
|--------|--------------|
| [Dashboard] | [URL + access instructions] |
| [Logs] | [URL + query pattern] |
| [Metrics] | [URL + key dashboards] |

## Monitoring

| Alert | Severity | Meaning |
|-------|----------|---------|
| [Alert name] | [P1/P2/P3] | [What it means] |

## Scenarios

### [Scenario: descriptive title]

**Symptoms**: [What you observe]
**Impact**: [What's affected]

**Resolution**:

1. [Exact command or action]
2. [Exact command or action]
3. [Verification step]

**Escalation**: If unresolved after [time], escalate to [team/person].

### [Next scenario]

[Same pattern]

## Post-incident

- [ ] Update this runbook with any new learnings
- [ ] File post-incident review
- [ ] Update monitoring if gaps were identified
```

---

## Architecture Decision Record (ADR) Template

```markdown
# ADR-[number]: [Title]

**Status**: [Proposed | Accepted | Deprecated | Superseded by ADR-XXX]
**Date**: [Date]
**Decision makers**: [Names/teams]

## Context

[What is the situation that motivates this decision? What problem are we trying to solve?]

## Decision

[What is the decision that was made?]

## Consequences

### Positive

- [Benefit 1]
- [Benefit 2]

### Negative

- [Trade-off 1]
- [Trade-off 2]

### Neutral

- [Side effect that's neither good nor bad]

## Alternatives considered

### [Alternative 1]

[Brief description and why it was rejected]

### [Alternative 2]

[Brief description and why it was rejected]
```

---

## Glossary Entry Template

```markdown
## [Term]

[Clear, concise definition as it applies to your product]

**Also known as**: [Aliases or abbreviations, if any]
**Related**: [Links to related terms]
**See**: [Links to relevant documentation]
```

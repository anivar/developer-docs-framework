# arch-adoption-funnel

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Documentation drives adoption through a natural funnel. Most documentation teams write what's easy (reference) and skip what's impactful (quickstart, tutorials). The adoption funnel tells you where your docs are failing and what to prioritize fixing. If developers can't get started, writing more reference docs won't help.

## The Funnel

```
Stage       Question                    Content Types Needed
──────────  ────────────────────────    ──────────────────────
Discover    "What is this?"             README, Explanation
Evaluate    "Should I use this?"        Architecture, Comparison
Start       "How do I begin?"           Quickstart, Tutorial
Build       "How do I do X?"            How-to guides, API reference
Operate     "How do I keep it going?"   Runbook, Troubleshooting, Config ref
Upgrade     "How do I move forward?"    Migration guide, Changelog
```

## How to Use

1. **Identify the bottleneck.** Where are developers dropping off? If signup is high but API calls are low, the Start stage is broken.

2. **Fix the bottleneck first.** Don't write Explanation docs when developers can't complete the quickstart.

3. **Measure by stage.** Track metrics that correspond to each stage: page views on quickstart (Start), time to first API call (Start → Build), support tickets by topic (Operate).

## Incorrect Prioritization

```markdown
Sprint 1: Write API reference for all 47 endpoints
Sprint 2: Write API reference for all error codes
Sprint 3: Write API reference for all webhook events
Sprint 4: Maybe write a getting started guide?
```

Reference without onboarding. Developers have a complete map of a city they can't enter.

## Correct Prioritization

```markdown
Sprint 1: Quickstart (5 minutes to first API call)
Sprint 2: Top 5 how-to guides (most common tasks)
Sprint 3: Core API reference (most-used endpoints)
Sprint 4: Tutorial for primary use case
```

Unblock each funnel stage in order.

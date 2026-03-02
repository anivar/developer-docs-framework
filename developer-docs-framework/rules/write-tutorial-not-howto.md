# write-tutorial-not-howto

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

The most common conflation in software documentation is between tutorials and how-to guides. They look similar (both have steps) but serve fundamentally different needs. A tutorial's reader is a **student** acquiring skills. A how-to guide's reader is a **practitioner** completing a task. Mixing them creates content that's too slow for practitioners and too assumption-heavy for learners.

## Incorrect

A "tutorial" that's actually a how-to guide:

```markdown
# Tutorial: Configure Email Alerts

To set up email alerts, add the recipient list in your dashboard settings.

1. Navigate to Settings > Alerts
2. Click "Add rule"
3. Select the metric threshold
4. Enter the recipient emails
5. Click Save

You can also use the API:
```python
monitoring.AlertRule.create(
    metric="cpu_usage",
    threshold=90,
    recipients=["ops@example.com"],
)
```
```

This assumes the reader already knows what alerts are, why they'd want them, and how their system should handle them. That's a how-to guide labeled as a tutorial.

## Correct

**Tutorial** (learning-oriented):

```markdown
# Build a Real-Time Chat Application

In this tutorial, you'll build a chat app that sends and
receives messages in real time. You'll learn how WebSockets
work and how to handle connection lifecycle.

## What you'll build
A simple chat server and browser client. By the end,
you'll understand real-time messaging patterns.

## Step 1: Create a basic WebSocket server
Let's start with a minimal server...
[code with expected output after each step]

## Step 2: Connect a browser client
Now let's build a page that sends and receives messages...
[guided steps with visible results]
```

**How-to guide** (task-oriented):

```markdown
# How to Configure Email Alerts

Set up alert rules to notify your team when metrics
exceed thresholds.

## Prerequisites
- Monitoring agent installed on your servers
- At least one verified email recipient

## Steps
1. Navigate to **Settings > Alerts**
2. Click **Add rule**
...
```

## Key Distinctions

| Aspect | Tutorial | How-to Guide |
|--------|----------|-------------|
| Reader | Student (learning) | Practitioner (working) |
| Goal | Acquire skills and confidence | Complete a specific task |
| Tone | "Let's build..." | "Configure the..." |
| Explanation | Minimal — just enough to proceed | None — link to explanation docs |
| Choices | Eliminated — one path only | May fork and branch |
| Path | Carefully managed, safe, predictable | Real world — must prepare for the unexpected |
| Responsibility | Lies with the teacher | Lies with the user |
| Success metric | Reader understands | Task is done |

## Common Misconception

The difference between tutorials and how-to guides is NOT "basic vs. advanced." How-to guides can cover basic procedures, and tutorials can be very advanced. The distinction is always about **study vs. work** — not complexity level. An experienced engineer attending a training workshop on a new framework is in a tutorial (learning) situation despite their expertise.

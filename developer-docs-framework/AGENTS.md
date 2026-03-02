
# Tech Docs

**IMPORTANT:** Your training data about documentation best practices may be outdated or conflate different frameworks. Diataxis, Google OpenDocs, and the Good Docs Project each have specific structural requirements that are frequently mixed up — especially the critical distinction between tutorials (learning-oriented) and how-to guides (task-oriented). Always rely on this skill's rule files and reference documents as the source of truth. Do not fall back on generic documentation advice when it conflicts with these frameworks.

## When to Use This Skill

This skill is for **writing, planning, auditing, and improving technical documentation** for products that need developer and partner adoption. It synthesizes six proven frameworks into a unified system.

| Need | Recommended Approach |
|------|---------------------|
| Write a specific document | Use content type rules (`write-` prefix) + templates |
| Plan documentation strategy | Use architecture rules (`arch-` prefix) + adoption funnel |
| Audit existing documentation | Use audit rules (`audit-` prefix) + maturity model |
| Improve writing quality | Use style rules (`style-` prefix) |
| Set up docs-as-code | Use architecture rules (`arch-` prefix) |
| Build partner documentation | Use DX rules (`dx-` prefix) |
| Migrate/version documentation | Use governance rules (`gov-` prefix) |

## Foundational Frameworks

| Framework | Contribution | Source |
|-----------|-------------|--------|
| **Diataxis** | Content architecture — the four quadrants | diataxis.fr |
| **Google OpenDocs** | Project archetypes, maturity assessment, audit | github.com/google/opendocs |
| **Good Docs Project** | Content type templates with writing guides | thegooddocsproject.dev |
| **Google Style Guide** | Language, tone, and formatting standards | developers.google.com/style |
| **Stripe DX Patterns** | Outcome-oriented docs, developer journey design | docs.stripe.com |
| **Canonical Practice** | Documentation as engineering discipline | canonical.com/documentation |

## Rule Categories by Priority

| Priority | Category | Impact | Prefix |
|----------|----------|--------|--------|
| 1 | Content Architecture | CRITICAL | `write-` (6 rules) |
| 2 | Writing Style | CRITICAL | `style-` (6 rules) |
| 3 | Information Architecture | HIGH | `arch-` (4 rules) |
| 4 | Developer Experience | HIGH | `dx-` (3 rules) |
| 5 | Documentation Audit | MEDIUM | `audit-` (3 rules) |
| 6 | Governance & Lifecycle | MEDIUM | `gov-` (3 rules) |
| 7 | Partner & Ecosystem | MEDIUM | `partner-` (2 rules) |

## Quick Reference

### 1. Content Architecture (CRITICAL)

- `write-one-purpose-per-doc` — Never mix content types; tutorials teach, how-to guides solve, reference describes, explanation contextualizes
- `write-tutorial-not-howto` — Tutorials are learning-oriented (student); how-to guides are task-oriented (practitioner). Most common conflation in docs
- `write-reference-describe-only` — Reference docs describe machinery neutrally; never instruct, explain, or opine
- `write-explanation-no-steps` — Explanation provides "why" and context; never include step-by-step procedures
- `write-outcomes-not-features` — Document what users achieve ("move data to your warehouse"), not what exists ("the Pipeline object")
- `write-show-dont-tell` — Every concept needs a concrete example; abstract descriptions become concrete through code and diagrams

### 2. Writing Style (CRITICAL)

- `style-active-voice-second-person` — Use active voice and address the reader as "you"; present tense for descriptions
- `style-code-examples-must-work` — Every code example must be copy-pasteable and runnable; test examples in CI
- `style-consistent-terminology` — One term per concept everywhere; never alternate between synonyms for the same thing
- `style-global-readability` — No idioms, cultural references, or humor that doesn't translate; spell out acronyms on first use
- `style-minimize-admonitions` — Max 2-3 callouts per page; if everything is a warning, nothing is
- `style-tone-matches-type` — Tutorials are encouraging; how-to guides are direct; reference is neutral; explanation is conversational

### 3. Information Architecture (HIGH)

- `arch-organize-by-type-not-team` — Structure docs by content type (guides, reference, tutorials), not by internal team or component
- `arch-two-level-max` — Limit navigation hierarchy to two levels of nesting; deeper structures lose readers
- `arch-adoption-funnel` — Prioritize docs that unblock the current adoption bottleneck: Discover → Evaluate → Start → Build → Operate → Upgrade
- `arch-cross-link-strategy` — Every doc links to prerequisites, related content, and next steps; no dead ends

### 4. Developer Experience (HIGH)

- `dx-time-to-hello-world` — Optimize quickstart for speed; experienced devs should reach a working example in under 5 minutes
- `dx-audience-matrix` — Map audiences (new devs, building devs, evaluators, partners, operators, decision makers) to content types
- `dx-interactive-examples` — Provide runnable sandboxes, multi-language code tabs, and copy-pasteable examples wherever possible

### 5. Documentation Audit (MEDIUM)

- `audit-inventory-first` — Before improving docs, inventory every page: URL, title, content type, owner, last updated, accuracy
- `audit-classify-and-gap` — Classify each page into its Diataxis quadrant; identify gaps, overlaps, and misclassifications
- `audit-maturity-model` — Assess against four maturity levels: Seeds → Foundation → Integration → Excellence

### 6. Governance & Lifecycle (MEDIUM)

- `gov-docs-are-done` — A feature is not shipped until its documentation is written, reviewed, and published
- `gov-version-strategy` — Version API/SDK docs per major version; don't version conceptual docs unless concepts change
- `gov-freshness-cadence` — API reference: matches current release; how-to guides: quarterly review; runbooks: review after every incident

### 7. Partner & Ecosystem (MEDIUM)

- `partner-both-sides` — Integration guides document both sides of the interaction, not just your API
- `partner-production-readiness` — Every integration guide includes a production readiness checklist and support escalation paths

## The Documentation Compass

Every document serves one of four fundamental purposes (Diataxis quadrants):

```
                    PRACTICAL
                       |
         Tutorials     |     How-to Guides
        (learning)     |     (task-oriented)
                       |
   ACQUISITION --------+-------- APPLICATION
                       |
        Explanation    |     Reference
       (understanding) |     (information)
                       |
                   THEORETICAL
```

**Quick classification — ask two questions:**

1. **Studying or working?** Studying → left (tutorials, explanation). Working → right (how-to, reference).
2. **Practical steps or theoretical knowledge?** Practical → top (tutorials, how-to). Theoretical → bottom (explanation, reference).

## Enterprise Content Types

| Content Type | Quadrant | When to Use |
|-------------|----------|-------------|
| **Tutorial** | Learning | New users need guided first experience |
| **Quickstart** | Learning + Task | Experienced devs need fast path to "hello world" |
| **How-to Guide** | Task | Users need to accomplish specific goals |
| **Integration Guide** | Task | Partners need to connect their systems |
| **Migration Guide** | Task | Users need to upgrade between versions |
| **Troubleshooting** | Task | Users need to diagnose and fix problems |
| **API Reference** | Information | Developers need exact specifications |
| **SDK Reference** | Information | Developers need language-specific details |
| **Configuration Reference** | Information | Operators need parameter details |
| **Changelog** | Information | Users need to track what changed |
| **Explanation** | Understanding | Users need to understand "why" |
| **Architecture Guide** | Understanding | Engineers need system design context |
| **Glossary** | Information | Everyone needs consistent terminology |
| **Runbook** | Task | Operators need incident response procedures |

## Audience Matrix

| Audience | Primary Need | Key Content Types |
|----------|-------------|-------------------|
| **New developers** | Get started quickly | Quickstart, Tutorial |
| **Building developers** | Complete tasks efficiently | How-to guides, API reference |
| **Evaluating developers** | Decide whether to adopt | Explanation, Architecture |
| **Partner integrators** | Connect their systems | Integration guide, SDK reference |
| **Internal engineers** | Operate and maintain | Runbook, Architecture, Config reference |
| **Decision makers** | Understand capabilities | Explanation, Architecture overview |

## Adoption Funnel

Prioritize content types that unblock the current bottleneck:

```
Discover  → "What is this?"           → Explanation, README
Evaluate  → "Should I use this?"      → Architecture, Comparison
Start     → "How do I begin?"         → Quickstart, Tutorial
Build     → "How do I do X?"          → How-to guides, API reference
Operate   → "How do I keep it going?" → Runbook, Troubleshooting, Config ref
Upgrade   → "How do I move forward?"  → Migration guide, Changelog
```

## Documentation Project Archetypes

When planning documentation work (not single documents), use Google OpenDocs archetypes:

| Project Type | When to Use |
|-------------|-------------|
| **The Manual** | Writing new user/developer/admin guides from scratch |
| **The Edit** | Improving existing docs for accuracy, style, or goals |
| **The Audit** | Reviewing existing docs to assess condition and gaps |
| **The Migration** | Changing docs infrastructure (platform, format, hosting) |
| **The Factory** | Setting up automation, CI/CD, and tooling for docs |
| **The Translation** | Internationalizing and localizing documentation |
| **The Rules** | Creating contributor guidelines and style standards |
| **The Study** | Investigating user needs and documentation usage patterns |

## Quality Standards

Every document should pass two quality checks:

**Functional quality** (measurable): Accurate, Complete, Consistent, Current

**Deep quality** (experiential): Flows naturally, Anticipates needs, Respects reader's time, Feels trustworthy

## How to Use

Read individual rule files for detailed explanations and examples:

```
rules/write-one-purpose-per-doc.md
rules/style-active-voice-second-person.md
rules/arch-adoption-funnel.md
```

Each rule file contains:

- Brief explanation of why it matters
- Incorrect example with explanation
- Correct example with explanation
- Additional context and decision tables

## Writing Style System

This skill supports **pluggable writing styles**. The default is Diataxis style — per-quadrant tone that matches each content type's purpose. Override with a specific organization's conventions when needed.

**Default**: Diataxis style (loaded automatically). Each quadrant has its own voice, person, and tone.

| Style | Best For | Key Difference from Default |
|-------|----------|----------------------------|
| **Diataxis** (default) | Any project | Per-quadrant tone: "we" in tutorials, impersonal in reference, opinionated in explanation |
| **Google** | Open source, Google ecosystem | Always "you", uniform conversational tone, strict word list, accessibility-first |
| **Microsoft** | Enterprise B2B, internal platforms | Warm brand voice everywhere, bias-free communication, UI text conventions |
| **Stripe** | API-first products, DX-focused | Outcome-first framing, three-column layout, interactive code, docs as product |
| **Canonical** | Infrastructure, open source platforms | Pure Diataxis + engineering discipline, four pillars framework, starter packs |
| **Minimal** | Startups, MVPs, internal tools | README-first, auto-generate what you can, ship without perfection |

To apply a style override, read `references/styles/[style].md` and follow its divergences from the default.

## References

| Priority | Reference | When to read |
|----------|-----------|-------------|
| 1 | `references/content-types.md` | Writing any specific content type — purpose, structure, principles, anti-patterns for all 14 types |
| 2 | `references/templates.md` | Starting a new document — ready-to-use skeletons for tutorials, how-to, API ref, migration, runbook, etc. |
| 3 | `references/style-guide.md` | Making writing decisions — formatting, code examples, accessibility, multi-audience patterns |
| 4 | `references/anti-patterns.md` | Reviewing documentation — consolidated checklist of documentation smells and common mistakes |
| 5 | `references/enterprise-patterns.md` | Planning docs strategy — IA, docs-as-code, versioning, governance, maturity model, metrics, partner docs |
| 6 | `references/styles/diataxis.md` | Default style — per-quadrant voice, person, tone, phrasing patterns for all four Diataxis types |
| 7 | `references/styles/google.md` | Google style override — uniform "you", sentence case, word list, accessibility priority |
| 8 | `references/styles/microsoft.md` | Microsoft style override — warm brand voice, bias-free communication, UI conventions |
| 9 | `references/styles/stripe.md` | Stripe style override — outcome-first, interactive code, docs-as-product culture |
| 10 | `references/styles/canonical.md` | Canonical style override — pure Diataxis + engineering discipline, four pillars |
| 11 | `references/styles/minimal.md` | Minimal style override — README-first, MVP docs, ship fast |

## Ecosystem

This skill works well alongside complementary skills for related workflows:

| Companion Skill | When It Helps |
|----------------|---------------|
| **API design skills** (OpenAPI, Zod) | Generating accurate API reference docs from schemas |
| **Testing skills** (Jest, Vitest) | Writing testable code examples that stay correct |
| **Frontend design skills** | Building interactive documentation sites and sandboxes |
| **Code review skills** | Reviewing documentation PRs for quality and completeness |
| **Git workflow skills** | Managing docs-as-code workflows and PR-based reviews |

## Full Compiled Document

For the complete guide with all rules expanded: `AGENTS.md`



---

# Rules: Content Architecture


# write-explanation-no-steps

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Explanation documentation provides the "why" — design decisions, architectural context, trade-offs, and conceptual foundations. When step-by-step procedures creep in, the document loses its reflective purpose. Readers of explanation are thinking, not doing. They're away from the keyboard, building mental models. Procedures break that flow.

## Incorrect

```markdown
# Understanding Rate Limiting

Rate limiting protects our API from abuse. Here's how to
configure it:

1. Set your rate limit in the dashboard
2. Add the X-RateLimit-Remaining header check to your code
3. Implement exponential backoff

When you hit a rate limit, you'll get a 429 response. The
algorithm uses a token bucket approach where...
```

This starts as explanation, shifts to a how-to guide, then returns to explanation.

## Correct

```markdown
# Understanding Rate Limiting

## Why rate limiting exists

Rate limiting protects API stability by preventing any single
client from consuming disproportionate resources. Without it,
a misconfigured integration could degrade service for all users.

## How the token bucket works

Our rate limiter uses a token bucket algorithm. Each API key
receives a bucket with a fixed capacity. Each request consumes
one token. Tokens regenerate at a fixed rate...

## Why token bucket over alternatives

We considered fixed windows (simpler but causes thundering
herd at window boundaries) and sliding windows (smoother but
more memory per client). Token buckets balance fairness with
implementation simplicity.

**Related**: [How to handle rate limits](/guides/rate-limiting) |
[Rate limit API reference](/reference/rate-limits)
```

## Principle

Explanation discusses, contextualizes, and illuminates. It never says "do this." If you find yourself writing numbered steps, you're writing a how-to guide — move those steps to a separate document and link to it.


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


# write-outcomes-not-features

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

The best developer documentation converts significantly better because it documents what developers want to **achieve**, not what API objects exist. Feature-centric docs describe your product. Outcome-centric docs describe the developer's success. The difference determines whether developers adopt your product or abandon it at the docs stage.

## Incorrect

Feature-centric documentation:

```markdown
# Pipeline API

The Pipeline object represents a data processing pipeline.
It contains fields for source, destination, transforms, and status.

## Create a Pipeline
POST /v1/pipelines

## Update a Pipeline
PATCH /v1/pipelines/:id

## Run a Pipeline
POST /v1/pipelines/:id/run
```

This describes what exists. The developer must figure out how these pieces solve their problem.

## Correct

Outcome-centric documentation:

```markdown
# Move Data from PostgreSQL to Your Data Warehouse

Set up a data sync in three steps:
define your source, configure transforms, and start the pipeline.

## 1. Connect your source database

```python
pipeline = dataflow.Pipeline.create(
    source="postgresql://prod-db/analytics",
    destination="bigquery://my-project.dataset",
)
# Pipeline is ready to configure transforms
```

## 2. Define transforms
...

## 3. Start the sync
...
```

The developer sees their goal ("move data to warehouse") and follows a path to achieve it.

## Principle

Name documents after what the developer achieves, not what the API provides. "Move data to your warehouse" not "Pipeline API." "Send email notifications" not "Notifications endpoint." Reference docs can be feature-centric (they describe machinery). How-to guides and tutorials must be outcome-centric.


# write-reference-describe-only

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Reference documentation is the map of your product. Maps don't tell you where to go — they describe what exists. When reference docs include instructions ("To use this, first do X"), explanations ("This works because of Y"), or opinions ("We recommend Z"), they become harder to scan and less trustworthy. Users consult reference while coding; they need facts instantly, not narratives.

## Incorrect

```markdown
# POST /v1/users

You should use this endpoint to create a new user. First,
make sure you've set up your API key (see our getting started
guide). We recommend using the batch endpoint for importing
multiple users because it's more efficient.

To create a user, you'll need to specify an email and role.
Here's how:

```python
user = admin.User.create(email="ada@example.com", role="viewer")
```

The role field uses RBAC because it provides fine-grained access control.
```

This mixes instruction ("first, make sure"), opinion ("we recommend"), how-to ("here's how"), and explanation ("because it provides").

## Correct

```markdown
# POST /v1/users

Creates a new user in the specified organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `email` | string | yes | Valid email address. Must be unique within the organization. |
| `role` | string | yes | One of `owner`, `admin`, `editor`, `viewer`. |
| `org_id` | string | yes | Organization identifier. |

## Example request

```python
admin.User.create(email="ada@example.com", role="editor", org_id="org_42")
```

## Example response

```json
{
  "id": "usr_5678",
  "email": "ada@example.com",
  "role": "editor",
  "status": "invited"
}
```

## Errors

| Code | Description |
|------|-------------|
| `email_taken` | A user with this email already exists in the organization. |
| `invalid_role` | Role must be one of: owner, admin, editor, viewer. |
```

## Principle

Reference docs use **neutral description**. State what the machinery does. Don't instruct, explain, or opine. Link to how-to guides and explanation docs for those purposes.


# write-show-dont-tell

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Abstract descriptions remain abstract until grounded in concrete examples. Developers learn by seeing working code, real responses, and actual behavior — not by reading paragraphs about how something "can be used." Every claim, every concept, every feature needs a concrete illustration.

## Incorrect

```markdown
# Event Streams

Event streams allow you to consume real-time data from
your application. They can be configured to deliver events
to any consumer. The payload contains event details in JSON
format. You should handle backpressure to avoid data loss.
```

Four sentences of telling. No showing. The developer has no idea what an event looks like, how to consume it, or what code to write.

## Correct

```markdown
# Event Streams

Subscribe to a stream and process events as they arrive:

```json
{
  "id": "evt_1234",
  "type": "order.shipped",
  "timestamp": "2025-06-15T14:30:00Z",
  "data": {
    "order_id": "ord_5678",
    "tracking_number": "1Z999AA10123456784",
    "carrier": "ups"
  }
}
```

Connect and consume events:

```python
from eventbus import Consumer

consumer = Consumer(topic="orders", group="shipping-service")
for event in consumer.stream():
    print(f"Order {event.data['order_id']} shipped")
    event.ack()
```
```

Real payload. Real code. The developer understands immediately.

## Principle

For every concept you describe, ask: "Can I show this with code, a response, a diagram, or a screenshot?" If yes, show it. The showing often replaces the telling entirely.


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
| Choices | Eliminated — one path only | May offer alternatives |
| Success metric | Reader understands | Task is done |



---

# Rules: Writing Style


# style-active-voice-second-person

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Active voice is clearer, shorter, and more direct. Second person ("you") makes documentation feel like guidance rather than a textbook. Present tense for descriptions keeps language grounded. These three conventions — active voice, second person, present tense — are the foundation of readable technical writing, endorsed by both Google and Microsoft style guides.

## Incorrect

```markdown
The request will be processed by the server. It is recommended
that the user should set a timeout value. Once the configuration
has been completed, the service can be started by running the
start command.
```

Passive voice, third person, future tense. Wordy and impersonal.

## Correct

```markdown
The server processes the request. Set a timeout value to avoid
hanging connections. After you configure the service, start it
with `service start`.
```

Active voice, second person, present tense. Half the words, twice the clarity.

## Tone by Content Type

| Content Type | Voice Example |
|-------------|--------------|
| Tutorial | "Let's create our first endpoint" |
| How-to guide | "Configure the storage bucket" |
| Reference | "Returns a list of user objects" |
| Explanation | "The system uses eventual consistency because..." |
| Troubleshooting | "If you see this error, check your API key" |

## Exception

Use passive voice when the actor is unknown or irrelevant: "The log file is created automatically when the server starts."


# style-code-examples-must-work

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

A broken code example destroys trust faster than any other documentation failure. Developers copy-paste from docs and expect it to work. When it doesn't, they question everything else in the documentation. Stripe, Twilio, and AWS all test their code examples in CI — this is the standard for developer-facing documentation.

## Incorrect

```python
# Incomplete — missing imports and initialization
user = User.create(name="Ada", email="ada@example.com")
```

```javascript
// Undefined variable and missing setup
const result = await db.users.insert({
  data: userData, // Where does 'userData' come from?
})
```

## Correct

```python
from myapp.db import DatabaseClient

db = DatabaseClient(url="postgresql://localhost/mydb")  # TODO: Replace with your connection string

user = db.users.create(
    name="Ada Lovelace",
    email="ada@example.com",
    role="engineer",
)
print(user.id)  # "usr_1234..."
```

Complete context: import, initialization, operation, and output.

## Checklist

- [ ] Includes all necessary imports
- [ ] Shows initialization/setup
- [ ] Uses realistic values (`user@example.com`, not `foo`)
- [ ] Specifies language for syntax highlighting
- [ ] Shows expected output where helpful
- [ ] Marks values the reader must replace with `# TODO:` comments
- [ ] Tested and verified to work against the current API version


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


# style-global-readability

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Enterprise products serve a global audience. Idioms, cultural references, and region-specific assumptions exclude non-native English speakers — often the majority of your developer community. Simple, direct language translates better, both literally (for localization) and cognitively (for non-native readers).

## Incorrect

```markdown
Out of the box, the SDK handles authentication. This is a
slam dunk for teams that want to hit the ground running.
If you drop the ball on error handling, you'll be in hot water.
```

Three idioms that don't translate and add no precision.

## Correct

```markdown
The SDK handles authentication by default. This simplifies
setup for teams that want to start quickly. If you skip error
handling, your integration will fail silently.
```

Same meaning, globally clear.

## Guidelines

- No idioms or colloquialisms ("out of the box," "low-hanging fruit," "boilerplate")
- No sports or cultural metaphors ("slam dunk," "home run," "cricket analogy")
- Spell out acronyms on first use: "Transport Layer Security (TLS)"
- Use standard date formats: "March 15, 2025" or ISO 8601 (`2025-03-15`)
- Avoid humor — it rarely translates and can seem dismissive
- Keep sentences under 25 words
- Use inclusive language: "allowlist/blocklist" not "whitelist/blacklist"


# style-minimize-admonitions

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Callout boxes (Note, Warning, Important, Caution) are designed to draw attention to critical information. When overused, they create visual noise and readers learn to ignore them — including the ones that actually matter. If everything is a warning, nothing is.

## Incorrect

```markdown
> **Note**: You need an API key to continue.

> **Important**: The API key must have write permissions.

> **Warning**: Don't share your API key publicly.

> **Caution**: Rate limits apply to all API calls.

> **Note**: See the API reference for all endpoints.
```

Five callouts in a row. The reader's eye skips all of them.

## Correct

```markdown
You need an API key with write permissions to continue.
See [API Keys](/reference/api-keys) for setup instructions.

> **Warning**: Never expose your API key in client-side code
> or public repositories. Use environment variables instead.

Rate limits apply to all API calls. See [rate limits](/reference/rate-limits).
```

One callout for the genuinely critical security concern. Everything else flows as regular text.

## Guidelines

- Maximum 2-3 admonitions per page
- Use **Warning** only for data loss or security risks
- Use **Note** only for genuinely surprising or non-obvious information
- If the information is expected or routine, write it as regular text
- If a page needs many warnings, the product has a UX problem, not a docs problem


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



---

# Rules: Information Architecture


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


# arch-organize-by-type-not-team

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Users think in terms of what they need to do (learn, accomplish, look up), not which internal team built the feature. Organizing docs by team or product component creates navigation that mirrors your org chart — meaningful to employees, meaningless to developers. Content-type organization maps to how developers actually use documentation.

## Incorrect

```
docs/
├── platform-team/
│   ├── authentication.md
│   ├── rate-limiting.md
│   └── api-gateway.md
├── compute-team/
│   ├── containers.md
│   ├── scaling.md
│   └── deployments.md
└── storage-team/
    ├── buckets.md
    └── cdn.md
```

A developer deploying a containerized app with CDN needs to navigate three team silos.

## Correct

```
docs/
├── tutorials/
│   ├── deploy-first-app.md
│   └── container-basics.md
├── guides/
│   ├── authentication.md
│   ├── deploy-containers.md
│   ├── configure-autoscaling.md
│   └── set-up-cdn.md
├── reference/
│   ├── compute-api.md
│   ├── storage-api.md
│   └── networking-api.md
└── concepts/
    ├── deployment-lifecycle.md
    └── rate-limiting.md
```

Organized by what developers need to do, not who built it internally.

## Principle

The internal org chart changes. Documentation structure should be stable and user-centric. If a team reorganization would require restructuring your docs, your IA is coupled to the wrong thing.


# arch-two-level-max

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Beyond two levels of nesting, users lose their position in the documentation hierarchy. Deep navigation structures create a maze where readers can't find their way back or forward. Research on information architecture consistently shows that broad, shallow structures outperform narrow, deep ones for findability.

## Incorrect

```
docs/
└── guides/
    └── messaging/
        └── channels/
            └── notifications/
                └── templates/
                    └── configure-sms-template.md   ← 5 levels deep
```

Users clicking through 5 levels of folders will abandon the search.

## Correct

```
docs/
├── guides/
│   ├── send-sms.md
│   ├── set-up-push-notifications.md
│   ├── configure-message-templates.md    ← 2 levels
│   └── handle-delivery-failures.md
└── reference/
    ├── messages-api.md
    └── channels-api.md
```

Two levels: category → document. If a category grows too large, split it into parallel categories rather than adding depth.

## When You Need More Structure

If you genuinely have hundreds of documents, use **faceted navigation** (filtering by topic, content type, language) rather than deeper hierarchy. Search also becomes critical at scale — invest in good search rather than deeper folder structures.



---

# Rules: Developer Experience


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


# dx-interactive-examples

**Priority**: HIGH
**Category**: Developer Experience

## Why It Matters

Interactive examples — runnable sandboxes, multi-language code tabs, "try it" buttons — let developers validate understanding immediately without leaving the docs. Stripe's three-column layout with hoverable code is the gold standard. Even without custom tooling, tabbed multi-language examples and copy buttons significantly improve the developer experience.

## Incorrect

```markdown
Here's how to upload a file in Python:

```python
storage.upload("my-bucket", file="report.csv")
```

For Node.js, see our [Node.js guide](/guides/node).
For Go, see our [Go guide](/guides/go).
```

Forces language-switching developers to navigate away.

## Correct

Tabbed code blocks showing all languages inline:

````markdown
# Upload a File

{% tabs %}
{% tab title="Python" %}
```python
from cloudstore import Client

client = Client(api_key="cs_test_...")
result = client.upload(
    bucket="my-bucket",
    file="report.csv",
)
```
{% endtab %}
{% tab title="Node.js" %}
```javascript
const { CloudStore } = require("cloudstore");

const client = new CloudStore("cs_test_...");
const result = await client.upload({
  bucket: "my-bucket",
  file: "report.csv",
});
```
{% endtab %}
{% tab title="Go" %}
```go
client := cloudstore.NewClient("cs_test_...")

result, err := client.Upload(ctx, &cloudstore.UploadParams{
    Bucket: "my-bucket",
    File:   "report.csv",
})
```
{% endtab %}
{% endtabs %}
````

All languages visible on one page. The developer stays in context.

## Levels of Interactivity

| Level | Implementation | Effort |
|-------|---------------|--------|
| Copy button | Static code blocks with clipboard | Low |
| Language tabs | Tabbed code blocks per language | Low |
| "Try it" API explorer | Interactive request builder | Medium |
| Embedded sandbox | Runnable code in the browser | High |
| Live preview | Real-time output as code changes | High |

Start with copy buttons and language tabs. These provide the most DX improvement for the least effort.


# dx-time-to-hello-world

**Priority**: HIGH
**Category**: Developer Experience

## Why It Matters

Time to first API call (or first working example) is the single most important DX metric. Every minute a developer spends before seeing a working result increases the probability they'll abandon your product. Stripe, Twilio, and Firebase all optimize for "hello world in under 5 minutes." If your quickstart takes longer, developers are evaluating alternatives.

## Incorrect

```markdown
# Getting Started

## Step 1: Understand the Architecture
Our platform uses a serverless architecture with...
[500 words of explanation]

## Step 2: Set Up Your Development Environment
Install the CLI, configure IAM roles, set up VPC...
[complex multi-tool setup]

## Step 3: Configure Authentication
Create a service account and generate credentials...
[15 steps of configuration]

## Step 4: Make Your First Request
[finally, 20 minutes later]
```

## Correct

```markdown
# Quickstart

## Install

```bash
pip install sendwave
```

## Send your first message

```python
import sendwave

client = sendwave.Client("sw_test_demo")
message = client.sms.send(
    to="+1234567890",
    body="Hello from SendWave!",
)
print(message.sid)  # "msg_abc123..."
```

Run it:
```bash
python send.py
```

You should see a message ID printed. You've sent your first
SMS.

## Next steps
- [Tutorial: Build a notification service](/tutorials/notifications)
- [API reference](/reference)
```

Three steps. Under 5 minutes. Working result.

## Principle

Strip the quickstart to the absolute minimum: install, configure one credential, make one meaningful call, see one meaningful result. Everything else (architecture, advanced config, edge cases) lives in other documents.



---

# Rules: Documentation Audit


# audit-classify-and-gap

**Priority**: MEDIUM
**Category**: Documentation Audit

## Why It Matters

After inventorying your docs, classify each page into its Diataxis quadrant and then map gaps. Most documentation sets are heavy on reference (easy to generate) and light on tutorials and how-to guides (hard to write, high adoption impact). Classification reveals the imbalance; gap analysis tells you what's missing.

## Process

### Step 1: Classify

For each inventoried page, determine:
- **Is it the right content type?** Many pages mix types
- **Is it in the right location?** A tutorial in the reference section won't be found
- **Does the title signal its type?** "Authentication" is ambiguous; "How to set up authentication" is clear

### Step 2: Map Gaps

Using the 14 enterprise content types, check:

| Content Type | Covered? | Coverage Quality |
|-------------|----------|-----------------|
| Quickstart | Yes/No | Complete / Partial / Outdated |
| Tutorials | Yes/No | ... |
| How-to guides | Yes/No | ... |
| API reference | Yes/No | ... |
| ... | ... | ... |

### Step 3: Cross-Reference with Adoption Funnel

For each funnel stage (Discover → Evaluate → Start → Build → Operate → Upgrade), check whether the required content types exist and are adequate.

## Common Findings

- 70% of content is reference, 5% is tutorials
- Many "tutorials" are actually how-to guides
- Explanation content scattered across how-to guides instead of centralized
- Migration guides missing for previous major versions
- No troubleshooting guides despite high support ticket volume


# audit-inventory-first

**Priority**: MEDIUM
**Category**: Documentation Audit

## Why It Matters

You can't improve what you haven't inventoried. Before restructuring, rewriting, or adding documentation, catalog everything that exists. This prevents duplicating existing content, reveals forgotten docs that may be outdated, and gives you a baseline to measure improvement against. Google OpenDocs audit methodology starts here.

## Process

Create a spreadsheet with one row per documentation page:

| Column | What to Record |
|--------|---------------|
| URL / path | Where the page lives |
| Title | Current page title |
| Content type | Tutorial, how-to, reference, explanation, or unknown |
| Owner | Team or person responsible |
| Last updated | Date of most recent edit |
| Accuracy | Current / possibly stale / likely outdated |
| Traffic | Page views (if analytics available) |
| Notes | Observations (e.g., "mixes tutorial and reference") |

## What People Get Wrong

- **Skipping the inventory** — jumping straight to "let's rewrite everything" without understanding what exists
- **Inventorying only official docs** — missing README files, wiki pages, blog posts, support articles, and internal docs that developers actually read
- **Not recording ownership** — unowned docs are the first to become stale

## When to Do This

- Before any documentation restructuring project
- When inheriting documentation from another team or project
- When support tickets suggest developers can't find information
- Annually, as a documentation health check


# audit-maturity-model

**Priority**: MEDIUM
**Category**: Documentation Audit

## Why It Matters

The maturity model provides a roadmap — not a judgment. It helps teams understand where they are and what the next achievable level looks like. Adapted from Google OpenDocs Content Maturity Checklist with enterprise extensions.

## The Four Levels

### Level 1: Seeds

Minimum viable documentation. The product is findable and installable.

- [ ] README with project description and purpose
- [ ] Installation/setup instructions
- [ ] At least one usage example
- [ ] License information

### Level 2: Foundation

Core use cases documented, structurally organized.

- [ ] Quickstart guide (under 10 minutes)
- [ ] API reference (complete for core endpoints)
- [ ] At least 3 how-to guides for common tasks
- [ ] Error documentation with resolution steps
- [ ] Consistent formatting and style
- [ ] Working code examples in primary language

### Level 3: Integration

Documentation integrated into the development process.

- [ ] Docs-as-code workflow (Git, CI/CD, PR review)
- [ ] Documentation is part of the definition of done
- [ ] Tutorials for major use cases
- [ ] Multi-language code examples
- [ ] Versioned documentation
- [ ] Changelog maintained with every release
- [ ] Analytics tracking documentation usage
- [ ] Automated link checking and example testing

### Level 4: Excellence

Documentation is a strategic asset driving adoption.

- [ ] Interactive examples and sandboxes
- [ ] Comprehensive explanation/conceptual docs
- [ ] Partner documentation program
- [ ] Migration guides for every major version
- [ ] Troubleshooting guides informed by support data
- [ ] Localization for key markets
- [ ] User research informing documentation priorities
- [ ] Community contributions accepted and reviewed
- [ ] Documentation quality metrics tracked and improved

## How to Use

1. Assess current level honestly — partial completion of a level means you're still at the previous level
2. Focus on completing the current level before advancing
3. Use the checklist items as sprint tasks
4. Reassess quarterly



---

# Rules: Governance & Lifecycle


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


# gov-freshness-cadence

**Priority**: MEDIUM
**Category**: Governance & Lifecycle

## Why It Matters

Stale documentation is worse than no documentation — it actively misleads. Different content types have different staleness tolerances. API reference that's one version behind causes integration failures. Explanation docs can remain valid for years. Setting explicit review cadences prevents the worst-case scenario: a critical doc silently becoming outdated.

## Freshness Standards

| Content Type | Maximum Staleness | Review Trigger |
|-------------|-------------------|---------------|
| API reference | Must match current release | Every release |
| SDK reference | Must match current release | Every release |
| Changelog | Updated with every release | Every release |
| Quickstart | Verified quarterly | Quarterly |
| Tutorials | Tested quarterly | Quarterly |
| How-to guides | Reviewed quarterly | Quarterly |
| Configuration reference | Updated with every release | Every release |
| Runbooks | Reviewed after every incident | After incident |
| Troubleshooting | Reviewed with support data monthly | Monthly |
| Migration guides | Verified at release time | At release |
| Explanation | Reviewed semi-annually | Semi-annually |
| Architecture guide | Reviewed semi-annually | Semi-annually |
| Glossary | Reviewed annually | Annually |

## Automation

- **Link checking**: Automated, run daily or weekly
- **Code example testing**: Automated in CI, run with every release
- **Last-updated timestamps**: Visible on every page
- **Staleness alerts**: Automated notification when a page exceeds its review cadence
- **Analytics cross-reference**: Flag high-traffic pages that haven't been updated recently

## Principle

Dead docs are worse than no docs. They misinform, slow teams down, and erode trust in the entire documentation system. A small set of fresh, accurate docs is better than a large set in various states of decay.


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



---

# Rules: Partner & Ecosystem


# partner-both-sides

**Priority**: MEDIUM
**Category**: Partner & Ecosystem

## Why It Matters

Integration guides that only document your API leave partners guessing about what happens on their side. A partner integrating with your platform needs to know what request you expect, what response you return, AND what their system should do with that response. Documenting only your side forces partners to reverse-engineer the full integration.

## Incorrect

```markdown
# Device Telemetry Integration

## Endpoint
POST /v1/telemetry/subscribe

## Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| callback_url | string | Your endpoint URL |
| device_types | array | Device types to subscribe to |
```

Only your side documented. The partner doesn't know: What does the telemetry payload look like? What should their endpoint return? How should they verify authenticity? What happens on timeout?

## Correct

```markdown
# Device Telemetry Integration

## 1. Register your endpoint (your side → our API)

```bash
curl -X POST https://api.example.com/v1/telemetry/subscribe \
  -d callback_url="https://partner.com/telemetry" \
  -d device_types[]="sensor.temperature"
```

## 2. Receive telemetry (our system → your endpoint)

We send a POST request to your endpoint:

```json
{
  "id": "evt_1234",
  "type": "sensor.temperature.reading",
  "data": { "device_id": "dev_5678", "value": 23.4, "unit": "celsius" }
}
```

**Your endpoint must:**
- Return HTTP 200 within 30 seconds
- Verify the `X-Signature` header (see [signature verification](/guides/signatures))
- Process idempotently (we may retry)

## 3. Handle failures (retry behavior)

If your endpoint returns non-200 or times out:
- We retry 3 times with exponential backoff (1s, 10s, 100s)
- After 3 failures, the subscription is paused
- You receive an email notification
```

Both sides documented. The partner can build a complete integration from one document.

## Principle

For every request you document, document the expected response. For every callback you send, document what the partner's system should do with it. Include architecture diagrams showing the full interaction flow.


# partner-production-readiness

**Priority**: MEDIUM
**Category**: Partner & Ecosystem

## Why It Matters

Partners building against your API in a sandbox can get surprisingly far before realizing they're missing production requirements — rate limits, authentication hardening, error handling, monitoring. A production readiness checklist at the end of every integration guide prevents failed launches and reduces partner support burden.

## Every Integration Guide Should End With

```markdown
## Production Readiness Checklist

### Security
- [ ] API keys stored in environment variables, not code
- [ ] Webhook signatures verified on every request
- [ ] HTTPS enforced for all endpoints
- [ ] API key permissions scoped to minimum required

### Reliability
- [ ] Retry logic with exponential backoff implemented
- [ ] Idempotency keys used for create/update operations
- [ ] Timeout handling configured (recommended: 30s)
- [ ] Circuit breaker for downstream API calls

### Monitoring
- [ ] Error rates tracked per endpoint
- [ ] Webhook delivery success rate monitored
- [ ] API response times logged
- [ ] Alerts configured for failure thresholds

### Compliance
- [ ] Data handling complies with relevant regulations
- [ ] PII is encrypted at rest and in transit
- [ ] Audit logging enabled for sensitive operations

### Support
- [ ] Production API key obtained (not test key)
- [ ] Support contact established: support@example.com
- [ ] Escalation path documented for P1 incidents
- [ ] SLA reviewed and understood
```

## Principle

Sandbox success does not equal production readiness. Bridge the gap with an explicit checklist. Partners will thank you — and your support team will handle fewer production incidents.



---

# Writing Style Guides


# Diataxis Style (Default)

The default writing style for this skill. Diataxis provides per-quadrant style guidance — each content type has its own voice, person, tense, and phrasing conventions. This creates documentation where the writing style reinforces the content's purpose.

The key Diataxis insight: **style follows function.** A tutorial's encouraging tone builds learner confidence. A reference doc's austere precision enables fast lookup. Forcing one uniform style across all content types fights the reader's mental state.

## Universal Principles

These apply across all quadrants:

- **Concrete over abstract.** Specific examples, real values, observable outputs
- **Minimal surprise.** Consistent structure within each content type
- **Respect boundaries.** Never mix instruction into reference, explanation into tutorials, or teaching into how-to guides
- **Link, don't embed.** When another quadrant's content is needed, link to it rather than inlining it

## Per-Quadrant Style

### Tutorials — Learning-Oriented

**Voice**: First-person plural ("we"). Creates solidarity between tutor and learner.
**Tense**: Imperative mood with sequential markers.
**Tone**: Encouraging, patient, collaborative.

| Pattern | Example |
|---------|---------|
| Opening | "In this tutorial, we will build a..." |
| Sequencing | "First, do x. Now, do y." |
| Setting expectations | "The output should look something like..." |
| Prompting observation | "Notice that the response includes..." |
| Minimal explanation | "We use HTTPS because it's more secure." |
| Celebrating progress | "You have built a working payment integration." |

**What to avoid:**
- Extended explanation (link to explanation docs)
- Options or alternatives ("you could also use...") — pick one path
- Abstract generalization — stay concrete and specific
- "In this tutorial you will learn..." — describe what they'll *build*, not what they'll *learn*

**The teacher's contract:** You bear responsibility for the learner's success. If they follow your steps and fail, the tutorial is broken, not the learner.

### How-to Guides — Task-Oriented

**Voice**: Second person ("you") with conditional imperatives.
**Tense**: Imperative mood.
**Tone**: Direct, efficient, respectful of the reader's competence.

| Pattern | Example |
|---------|---------|
| Opening | "This guide shows you how to..." |
| Conditional steps | "If you need X, do Y. To achieve W, do Z." |
| Assumed competence | No re-explaining fundamentals |
| Linking reference | "Refer to the [config reference] for all options." |
| Goal framing | "How to handle failed payments" not "PaymentError class" |

**What to avoid:**
- Teaching or explaining concepts (link to tutorials/explanation)
- Describing tool mechanics the reader already knows
- Listing every parameter (that's reference)
- Being so procedural it can't adapt to real-world variation

**Key insight:** How-to guides address a human need ("I need to handle errors"), not a tool function ("here's the error API"). Frame everything around what the user wants to achieve.

### Reference — Information-Oriented

**Voice**: Third person, passive where natural. Neutral and impersonal.
**Tense**: Present tense, declarative.
**Tone**: Austere, precise, factual. No personality.

| Pattern | Example |
|---------|---------|
| Descriptions | "Returns a list of Payment objects." |
| Constraints | "Must be a valid ISO 8601 datetime." |
| Defaults | "Defaults to `usd` if not specified." |
| Warnings | "Must not exceed 5000 characters." |
| Listing | Commands, options, flags, errors, limits |

**What to avoid:**
- Instruction ("To use this, first do...") — that's a how-to guide
- Explanation ("This works because...") — that's explanation
- Opinion ("We recommend...") — that's editorial
- Narrative flow — reference is for scanning, not reading

**Key insight:** Reference mirrors the structure of the machinery it describes. If the API has `/users`, `/orders`, `/payments`, the reference follows the same grouping. The reader navigates the docs and the product simultaneously.

### Explanation — Understanding-Oriented

**Voice**: First person singular ("I") or plural ("we") is acceptable. Conversational.
**Tense**: Mixed — present for current state, past for history, conditional for alternatives.
**Tone**: Thoughtful, exploratory, opinionated. Like a knowledgeable colleague over coffee.

| Pattern | Example |
|---------|---------|
| Contextualizing | "The reason we chose eventual consistency is..." |
| Alternatives | "We considered X, but it would have meant..." |
| Connections | "This is similar to how DNS resolution works." |
| Trade-offs | "This favors throughput over immediate consistency." |
| Admitting complexity | "There's no perfect solution here — each approach trades..." |

**What to avoid:**
- Step-by-step procedures (that's a how-to guide)
- Complete parameter listings (that's reference)
- Staying strictly neutral — explanation should have perspective
- Being so abstract that no one benefits

**Key insight:** Explanation is the only quadrant where opinion and perspective are not just allowed but encouraged. "We chose X because..." and "The downside of this approach is..." are exactly what explanation should contain.

## How Diataxis Style Differs from Generic Style Guides

| Convention | Google/Microsoft | Diataxis |
|-----------|-----------------|----------|
| Person | Always "you" (2nd person) | Varies by quadrant: "we" in tutorials, "you" in how-to, impersonal in reference |
| Opinion | Avoid personal opinions | Encouraged in explanation quadrant |
| Explanation in guides | Include context | Ruthlessly minimize; link instead |
| Tone consistency | Uniform across all docs | Deliberately varies per content type |
| Choices/alternatives | Present options | Eliminate in tutorials; allow in how-to |
| Teaching | Teach as you go | Only in tutorials; never in how-to/reference |


# Google Style Override

Divergences from the Diataxis default when following the [Google Developer Documentation Style Guide](https://developers.google.com/style). Apply this overlay when your organization uses Google's conventions or when writing for Google-adjacent ecosystems (Android, Firebase, Cloud, open-source projects using Google standards).

## Where Google Agrees with Diataxis Default

- Active voice preferred
- Present tense for descriptions
- Concrete examples over abstract descriptions
- Code examples must be complete and runnable
- Consistent terminology throughout
- Oxford/serial comma

These are already in the default. No override needed.

## Where Google Diverges

### Person: Always Second Person

**Diataxis default:** First-person plural ("we") in tutorials.
**Google override:** Always use "you" — even in tutorials.

```markdown
# Diataxis default (tutorial)
Let's create our first endpoint. We'll start by...

# Google override (tutorial)
Create your first endpoint. You start by...
```

**When to prefer Google:** When your docs serve a global audience where "we" might feel presumptuous, or when you want a uniform voice across all content types.

### Headings: Sentence Case

**Google rule:** Sentence case for all headings. Only capitalize the first word and proper nouns.

```markdown
# Good: Configure the database connection
# Bad: Configure the Database Connection
```

### Tone: Uniform Conversational

**Diataxis default:** Tone varies by quadrant (austere in reference, warm in tutorials).
**Google override:** Conversational and friendly across all content types, including reference.

```markdown
# Diataxis reference style
Returns a `Payment` object. Accepts `amount` (integer, required).

# Google reference style
This method returns a `Payment` object. You must provide
an `amount` value as an integer.
```

### Opinion: Avoid

**Diataxis default:** Opinion encouraged in explanation docs.
**Google override:** Avoid personal opinions everywhere. Use "we recommend" sparingly and only for well-established best practices.

```markdown
# Diataxis explanation style
We chose OAuth 2.0 because API keys are fundamentally less secure
for delegated access. The trade-off is complexity.

# Google override
OAuth 2.0 provides delegated authorization without sharing
credentials. For applications that require delegated access,
use OAuth 2.0 instead of API keys.
```

### Word List

Google maintains a specific [word list](https://developers.google.com/style/word-list) with preferred/avoided terms:

| Avoid | Prefer |
|-------|--------|
| "please" | Omit — just give the instruction |
| "simple" / "easy" | Omit — subjective and potentially alienating |
| "click here" | Use descriptive link text |
| "above" / "below" | "preceding" / "following" |
| "e.g." / "i.e." | "for example" / "that is" |
| "via" | "through" or "using" |
| "leverage" | "use" |
| "utilize" | "use" |

### Accessibility Priority

Google places accessibility at a higher priority than Diataxis:
- All images must have meaningful alt text
- Don't rely on color alone to convey information
- Use proper heading hierarchy (no skipping levels)
- Write descriptive link text (never "click here")
- Provide text alternatives for all non-text content

### Code Formatting

- Use backticks for inline code: `method_name`
- Use bold for UI elements: **Settings > General**
- Use code blocks with language identifiers for all code examples
- Don't use code font for emphasis or for product names

## When to Choose Google Style

- Open-source projects in the Google ecosystem
- Teams that want a single uniform tone across all content types
- Documentation that prioritizes accessibility compliance
- API documentation where Google's API-specific conventions (endpoint format, parameter tables) are useful
- When following a strict word list is important for consistency


# Microsoft Style Override

Divergences from the Diataxis default when following the [Microsoft Writing Style Guide](https://learn.microsoft.com/en-us/style-guide/welcome/). Apply this overlay when writing enterprise B2B documentation, internal platform docs, or when your organization follows Microsoft conventions.

## Where Microsoft Agrees with Diataxis Default

- Active voice preferred
- Second person ("you") for instructions
- Present tense for descriptions
- Sentence case for headings
- Oxford/serial comma
- Accessibility-first approach

## Where Microsoft Diverges

### Voice: Warm, Relaxed Brand Voice

**Diataxis default:** Tone varies by quadrant (austere in reference).
**Microsoft override:** Consistently warm and conversational across all content, including reference. Three brand voice principles: crisp and clear, warm and relaxed, ready to help.

```markdown
# Diataxis reference style
Returns a `User` object. Accepts `id` (string, required).

# Microsoft override
Use this method to get information about a user. Pass
the user's ID, and you'll get back a `User` object with
their profile details.
```

### Tutorials: Second Person, Not First-Person Plural

**Diataxis default:** "Let's build..." (first-person plural).
**Microsoft override:** "You'll build..." (second person).

```markdown
# Diataxis default (tutorial)
In this tutorial, we will create a web app that...

# Microsoft override (tutorial)
In this tutorial, you create a web app that...
```

### Bias-Free Communication

Microsoft has an extensive bias-free communication section that goes beyond Diataxis:

- Avoid gendered pronouns — use "they" or rephrase
- Don't use terms that reference age, disability, ethnicity, or gender
- Use "select" instead of "click" (device-neutral)
- Use "developer" not "coder" or "programmer"
- Accessibility is a core requirement, not an add-on

### UI Text Conventions

Microsoft provides specific formatting for UI interactions:

| Element | Format | Example |
|---------|--------|---------|
| Menu paths | Bold with > | **File > Save As** |
| Button names | Bold | Select **Create** |
| UI labels | Bold | In the **Name** field |
| Keyboard shortcuts | Plus sign | Ctrl+S |
| User input | Italic or code | Enter *your-name* |

### Error Messages

Microsoft has specific guidance for error message documentation:

- Lead with what went wrong
- Tell the user what to do to fix it
- Use plain language, not error codes, as primary heading
- Include the error code for searchability

```markdown
# Good
## Can't connect to the database
Error code: DB_CONNECTION_TIMEOUT

Your app can't reach the database server. Check that...

# Bad
## Error DB_CONNECTION_TIMEOUT
A database connection timeout occurred.
```

### Developer Content Conventions

Microsoft defines two foundations for developer docs:
1. **Reference documentation** — encyclopedia of all programming elements
2. **Code examples** — show how to use those elements

Specific conventions:
- Always show complete, compilable code examples
- Include `using`/`import` statements
- Show output as comments in the code
- Use meaningful variable names, never `foo`/`bar`

## When to Choose Microsoft Style

- Enterprise B2B products
- Internal platform documentation
- Windows, Azure, or .NET ecosystem documentation
- Organizations that value warm, inclusive tone uniformly
- Documentation that needs extensive accessibility compliance
- Products with significant UI documentation needs


# Stripe Style Override

Divergences from the Diataxis default when following Stripe's developer documentation patterns. Apply this overlay when building API-first products where developer adoption is the primary business metric, or when you want the gold standard of DX-focused documentation.

## Where Stripe Agrees with Diataxis Default

- Content types are clearly separated
- Reference docs are precise and comprehensive
- Code examples are complete and runnable
- One concept per page

## Where Stripe Diverges

### Outcome-First Framing (Everywhere)

**Diataxis default:** Tutorials are learning-oriented, reference is descriptive.
**Stripe override:** Everything is outcome-oriented. Even reference pages are organized around what the developer achieves, not what objects exist.

```markdown
# Diataxis reference organization
/reference/payment-intents
/reference/charges
/reference/customers

# Stripe-style organization
/docs/payments/accept-a-payment      → uses PaymentIntents
/docs/payments/save-and-reuse        → uses Customers + PaymentMethods
/docs/payments/handle-failed         → uses Charges, Events
```

The API reference exists separately, but the primary navigation is outcome-based.

### Three-Column Layout

Stripe's signature design pattern:
- **Left column**: Persistent navigation tree
- **Center column**: Written guidance and explanations
- **Right column**: Live, syntax-highlighted code examples

Code and documentation are viewed side-by-side, never requiring the developer to scroll between prose and code. When you hover over a concept in the center, the corresponding code highlights in the right column.

### Interactive Code

**Diataxis default:** Static code blocks with expected output.
**Stripe override:** Code examples are interactive — copy-paste buttons, language selectors, and in some cases, executable directly from the documentation.

```markdown
# Diataxis default
```python
payment = stripe.PaymentIntent.create(amount=2000, currency="usd")
```

# Stripe style — tabbed, copyable, with response preview
[Python | Ruby | Node | Go | Java | PHP | .NET]

```python
import stripe
stripe.api_key = "sk_test_..."

intent = stripe.PaymentIntent.create(
    amount=2000,
    currency="usd",
)
```

→ Response:
```json
{
  "id": "pi_1234",
  "status": "requires_payment_method"
}
```
```

### Documentation as Product Culture

**Diataxis default:** Documentation is a practice.
**Stripe override:** Documentation is a product with its own engineering investment.

Key cultural practices:
- **Career ladders include documentation** at every engineering level
- **Performance reviews** assess documentation contributions
- **A feature isn't done** until docs are written, reviewed, and published
- **Writing classes** offered to all engineers during onboarding
- **Office hours** with technical writers for documentation help
- **Custom tooling** (Markdoc) built specifically for docs authoring

### Personalization

Stripe docs adapt to the reader:
- Detect the developer's likely language and show relevant examples first
- Dashboard context carries into documentation (test vs. live mode indicators)
- Code examples use the developer's actual test API keys when logged in

### Error Documentation

Every error includes:
1. The exact error code
2. Why it happens (one sentence)
3. How to fix it (specific steps)
4. Link to relevant guide

```markdown
## 402 — card_declined

The card was declined. The most common causes are
insufficient funds or a card that doesn't support
the transaction type.

**Fix**: Ask the customer to use a different card,
or retry with [3D Secure authentication](/guides/3d-secure).
```

## When to Choose Stripe Style

- API-first products where developer adoption drives revenue
- Products with multiple language SDKs
- Teams with engineering investment in documentation tooling
- Products where time-to-first-API-call is a business KPI
- Organizations willing to treat documentation as a product


# Canonical Style Override

Divergences from the Diataxis default when following [Canonical's documentation practice](https://canonical.com/documentation). Apply this overlay when building infrastructure documentation, open-source platform docs (Ubuntu, cloud-native), or when you want documentation treated as a rigorous engineering discipline.

## Where Canonical Agrees with Diataxis Default

Canonical is the primary adopter and promoter of Diataxis — their approach is the closest to pure Diataxis of any organization. Most Diataxis defaults ARE Canonical's conventions.

Agreement on:
- Four content types with strict separation
- Per-quadrant tone variation
- First-person plural in tutorials
- Austere reference style
- Cross-linking between quadrants

## Where Canonical Extends Diataxis

### Documentation as Engineering Practice

**Diataxis default:** Documentation is a practice.
**Canonical extension:** Documentation is an **engineering practice** — not an engineering task. This distinction means:

- Engineers, product managers, and technical authors all share responsibility
- Documentation work is reviewed with the same rigor as code
- The organization applies scientific methodology to documentation: "critical, exploratory, collaborative and iterative"
- Documentation quality is a team-level metric, not a writer-level metric

### Four Pillars Framework

Canonical extends Diataxis with an organizational framework:

| Pillar | Purpose |
|--------|---------|
| **Direction** | Standards and quality metrics aligned with user needs |
| **Care** | Culture that treats documentation as a living concern |
| **Execution** | Workflows that improve output consistency and efficiency |
| **Equipment** | Tools that serve the documentation work |

### Starter Packs

Canonical provides starter packs for new documentation projects — pre-configured templates and tooling that enforce Diataxis structure from day one:

- Pre-built navigation matching the four quadrants
- Template files for each content type
- CI checks for content type purity
- Style linting configured for Canonical conventions

### Rigorous Discipline

**Diataxis default:** Explains what to do and why.
**Canonical extension:** Enforces it through process.

- Documentation changes go through the same PR review as code
- Technical authors review for Diataxis compliance (correct quadrant, no mixing)
- CI/CD pipeline includes documentation builds, link checks, and style validation
- Regular audits against Diataxis structure

### Plain Language + Technical Precision

Canonical favors a style that is:
- Technically precise without being verbose
- Plain language without being oversimplified
- Structured for scanning (short paragraphs, clear headings)
- Consistent in formatting (RST or Markdown with strict conventions)

```markdown
# Canonical style (tutorial)
In this tutorial, we will set up a basic Juju controller
on a local LXD cloud. At the end, you will have a working
controller ready to deploy applications.

## Prerequisites
- Ubuntu 22.04 LTS or later
- At least 8 GB RAM

## Create the controller
First, let's bootstrap a controller:

```bash
juju bootstrap localhost my-controller
```

You should see output like:
```
Creating Juju controller "my-controller" on localhost/localhost
```
```

### Open-Source Documentation Community

Canonical actively hires technical authors and embeds them in engineering teams. Documentation is a career path, not a side task. This influences the style:

- Professional technical writing standards
- Consistent voice across large documentation sets
- Terminology governance through glossaries and style linting
- Multi-product documentation architecture (Ubuntu, Juju, MAAS, LXD each with Diataxis structure)

## When to Choose Canonical Style

- Infrastructure and platform documentation (cloud, DevOps, Linux)
- Open-source projects that want Diataxis in its purest form
- Organizations ready to invest in documentation as an engineering discipline
- Teams with dedicated technical authors
- Large documentation sets across multiple products needing consistency
- When documentation quality is a strategic differentiator


# Minimal Style Override

Divergences from the Diataxis default when documentation speed and lean coverage matter more than comprehensive depth. Apply this overlay for early-stage startups, internal tools, MVPs, hackathon projects, or any product where developer time is the constraint and "good enough docs now" beats "perfect docs never."

## Where Minimal Agrees with Diataxis Default

- Content types should still be separated (even if you only have 2-3 types)
- Code examples must work
- Audience awareness matters

## Where Minimal Diverges

### Scope: Minimum Viable Documentation

**Diataxis default:** 14 content types with full coverage.
**Minimal override:** Start with 3 documents. Add more only when support burden justifies it.

```
Priority 1 (ship with these):
  README.md         → What it is + quickstart (combined)
  API reference     → Generated from code/OpenAPI spec

Priority 2 (add when users ask):
  Top 3 how-to guides  → Most common support questions
  Changelog            → Start maintaining from v1.0

Priority 3 (add when adoption matters):
  Tutorial             → First guided learning experience
  Troubleshooting      → Top 5 support tickets as docs

Priority 4 (add at scale):
  Everything else
```

### README-First

**Diataxis default:** Separate quickstart document.
**Minimal override:** The README IS the quickstart. Combine "what is this" + "get started" in one file.

```markdown
# MyProduct

One sentence: what it does and who it's for.

## Install

```bash
npm install myproduct
```

## Quick Example

```javascript
import { Client } from "myproduct";
const client = new Client("your-key");
const result = await client.doThing({ param: "value" });
console.log(result);
```

## API Reference

See [docs/api.md](docs/api.md)

## License

MIT
```

### Auto-Generate What You Can

**Diataxis default:** Auto-generated docs are a starting point, not the end.
**Minimal override:** Auto-generated docs are fine for now. Enhance later.

- OpenAPI spec → API reference (tools: Redocly, Stoplight, Swagger UI)
- JSDoc/TSDoc → SDK reference
- Code comments → Configuration reference
- Git log → Changelog (tools: conventional-changelog)

### Style: Telegraphic

**Diataxis default:** Full sentences, proper grammar, conversational tone.
**Minimal override:** Bullet points, sentence fragments, and code blocks are fine. Correctness over polish.

```markdown
# Diataxis default
To configure the database connection, set the `DATABASE_URL`
environment variable to a valid PostgreSQL connection string.
The format should follow the standard URI syntax.

# Minimal override
Set `DATABASE_URL`:
```bash
DATABASE_URL=postgres://user:pass@host:5432/dbname
```
```

### Ship Without Perfection

Principles:
- Working code example > polished prose
- Incomplete but accurate > comprehensive but stale
- In the README > in a separate docs site nobody visits
- Answering the top 3 questions > covering every edge case

### When to Graduate

Move to a fuller style when:
- Support tickets repeatedly ask the same questions → write how-to guides
- New developers take more than 30 minutes to onboard → write a tutorial
- Partners need to integrate → write integration guides
- You have more than 2 major versions → write migration guides

## When to Choose Minimal Style

- Pre-product-market-fit startups
- Internal tools with small user bases
- Hackathon projects and prototypes
- Developer tools where the code is the documentation
- Open-source libraries with a single maintainer
- Any situation where "no docs" is the realistic alternative



---

# Anti-Patterns Reference


# Documentation Anti-Patterns

A consolidated checklist of documentation smells — common mistakes that reduce documentation quality, adoption, and trust. Use this as a review checklist before publishing.

## Table of Contents

1. [Structural Anti-Patterns](#structural-anti-patterns)
2. [Content Anti-Patterns](#content-anti-patterns)
3. [Style Anti-Patterns](#style-anti-patterns)
4. [Developer Experience Anti-Patterns](#developer-experience-anti-patterns)
5. [Governance Anti-Patterns](#governance-anti-patterns)
6. [Partner Documentation Anti-Patterns](#partner-documentation-anti-patterns)

---

## Structural Anti-Patterns

### The Kitchen Sink Page
A single page that mixes tutorial steps, API reference tables, conceptual explanations, and troubleshooting tips. Serves no audience well because every reader must scan past irrelevant content. **Fix**: Split into one document per Diataxis purpose and cross-link between them.

### The Org Chart Mirror
Documentation organized by internal team structure (`/platform-team/`, `/compute-team/`) instead of user need. When teams reorganize, the docs restructure breaks. **Fix**: Organize by content type (tutorials, guides, reference, concepts).

### The Rabbit Hole
Navigation deeper than two levels (`docs/guides/messaging/channels/templates/configure.md`). Users lose orientation after two clicks. **Fix**: Keep to two levels (category → document). Use faceted search for large doc sets.

### The Dead End
Documents with no prerequisites, no next steps, and no related links. Readers finish and don't know where to go. **Fix**: Every document gets prerequisites at the top, next steps at the bottom, and inline links to related content.

### The Feature Mirror
Documentation structure that mirrors the API surface (`/payments/`, `/users/`, `/reports/`) instead of user goals. **Fix**: Organize how-to guides and tutorials by outcome ("Accept a payment", "Export monthly reports"), not by endpoint.

---

## Content Anti-Patterns

### The Lecture Tutorial
A tutorial that spends more time explaining concepts than guiding actions. Multiple paragraphs of theory between steps. **Fix**: Ruthlessly minimize explanation in tutorials. Link to explanation docs for depth. Every step should produce a visible result.

### The Disguised How-To
A document labeled "tutorial" that assumes prior knowledge and jumps straight to configuration steps without teaching. **Fix**: If the reader needs existing knowledge, it's a how-to guide. Relabel and restructure accordingly.

### The Opinionated Reference
Reference documentation that includes recommendations, instructions, or explanations inline with parameter tables. "We recommend using X because..." **Fix**: Reference docs describe what exists. Move opinions to explanation docs, instructions to how-to guides.

### The Explanation With Steps
An explanation document that drifts into step-by-step instructions. Starts with "Understanding X" but ends with "Now do this." **Fix**: Keep explanation reflective and conceptual. Link to how-to guides for actionable steps.

### The Feature Announcement
Documentation written from the product team's perspective ("We've added a new X feature!") instead of the developer's perspective ("You can now do X"). **Fix**: Frame everything around what the developer achieves, not what you built.

### The Abstract Description
Content that describes what something "can do" without showing it. Four paragraphs about webhooks without a single payload example. **Fix**: For every concept, show code, a response, a diagram, or a screenshot. Showing often replaces telling entirely.

### The Choices Buffet
Tutorials or quickstarts that offer multiple paths ("You can use Python, Node.js, Go, or Java. If you're using Docker, see..."). **Fix**: In tutorials, eliminate choices — pick one path. In how-to guides, offer alternatives only when the reader's context genuinely varies.

---

## Style Anti-Patterns

### The Passive Maze
Heavy use of passive voice: "The request is processed by the server." "The configuration file should be edited." **Fix**: Use active voice and address the reader directly: "The server processes the request." "Edit the configuration file."

### The Thesaurus Trap
Using different words for the same concept: "workspace" in one paragraph, "project" in the next, "environment" later. **Fix**: Pick one term per concept. Define it in the glossary. Use it consistently everywhere.

### The Idiom Minefield
Prose full of idioms, slang, and culturally specific metaphors: "out of the box," "hit the ground running," "slam dunk." **Fix**: Use plain language. Replace idioms with direct statements. Documentation is read by a global audience.

### The Admonition Avalanche
Pages cluttered with warning boxes, note blocks, and tip callouts every few paragraphs. The important warnings drown in noise. **Fix**: Limit to 1-2 admonitions per page. Reserve warnings for genuine risks (data loss, security). Integrate minor notes into prose.

### The Mismatched Tone
Tutorial written in reference style ("The `authenticate()` method accepts a `credentials` parameter of type `AuthCredentials`"). Or reference written in tutorial style ("Let's learn about the token endpoint!"). **Fix**: Match tone to Diataxis quadrant — encouraging for tutorials, direct for how-to, neutral for reference, conversational for explanation.

### The Broken Example
Code examples that are missing imports, use undefined variables, reference deprecated APIs, or simply don't compile. **Fix**: Every code example must include imports, initialization, the operation, and expected output. Test examples in CI.

---

## Developer Experience Anti-Patterns

### The 20-Minute Quickstart
A "quickstart" that requires installing Docker, PostgreSQL, Redis, configuring three environment files, and generating SSH keys before making the first API call. **Fix**: Strip to absolute minimum — install, one credential, one call, one result. Target under 5 minutes.

### The Monolingual Docs
Code examples in only one language, with "see our X guide" links for other languages. **Fix**: Use tabbed code blocks showing all supported languages inline. Developers shouldn't navigate away to switch languages.

### The Invisible Audience
Documentation written for a single "developer" persona when the product serves new developers, experienced builders, partner integrators, and operators. **Fix**: Map audiences explicitly. Create separate entry points per audience with content matched to their mental state and goals.

### The Theory-First Onboarding
Getting started pages that begin with architecture diagrams, design philosophy, and system requirements before showing any working code. **Fix**: Show the simplest working example first. Architecture and philosophy belong in explanation docs, linked from the quickstart's "next steps."

---

## Governance Anti-Patterns

### The Orphan Docs
Documentation with no clear owner. Pages go stale because nobody is responsible for reviewing them. **Fix**: Assign an owner to every page. Review on a defined cadence (quarterly for tutorials, every release for reference).

### The Ship-Without-Docs
Features released without accompanying documentation. "We'll write docs later" becomes "we never wrote docs." **Fix**: Make documentation a definition-of-done requirement. No feature ships without its docs PR approved.

### The Stale Quickstart
A quickstart that worked 6 months ago but now fails because dependencies changed, APIs were updated, or default configurations shifted. **Fix**: Test quickstarts and tutorials in CI. Review them quarterly at minimum.

### The Version Amnesia
Documentation that doesn't specify which version it applies to. Users on v2 follow v3 instructions and get confused. **Fix**: Version reference docs and API docs. Show version selectors. Mark deprecated content clearly.

### The Vague Changelog
Release notes that say "Various improvements" or "Bug fixes." **Fix**: Be specific: "Fixed null pointer exception in auth middleware when session token is expired." Link every change to its documentation.

---

## Partner Documentation Anti-Patterns

### The One-Sided Integration
Integration guides that only document your API, leaving partners to guess what happens on their side — what payload to expect, what to return, how to verify signatures. **Fix**: For every request you document, document the expected response. Show both sides of the interaction.

### The Sandbox Surprise
Partners who build a working sandbox integration only to discover production requirements they never knew about — rate limits, signature verification, idempotency. **Fix**: End every integration guide with a production readiness checklist covering security, reliability, monitoring, and compliance.

### The Internal Jargon Guide
Integration docs that use your internal terminology without definition. Partners don't know what your "workflow engine" or "event bus" means. **Fix**: Define terms on first use. Link to a glossary. Write from the partner's perspective, not yours.

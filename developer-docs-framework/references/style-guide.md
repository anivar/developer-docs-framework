# Documentation Style Guide

Writing standards for enterprise technical documentation. Synthesized from Google Developer Documentation Style Guide, Microsoft Writing Style Guide, and patterns from best-in-class developer documentation (Stripe, Twilio, AWS).

## Table of Contents

1. [Voice and Tone](#voice-and-tone)
2. [Language Conventions](#language-conventions)
3. [Formatting Standards](#formatting-standards)
4. [Code Examples](#code-examples)
5. [API Documentation Style](#api-documentation-style)
6. [Visual Content](#visual-content)
7. [Accessibility](#accessibility)
8. [Multi-Audience Writing](#multi-audience-writing)

---

## Voice and Tone

### Core Principles

**Conversational but precise.** Write like a knowledgeable colleague explaining something clearly — not like a textbook, not like marketing copy.

**Confident without arrogance.** State facts directly. "This method returns a list" not "This method should return a list" or "This method will typically return a list."

**Respectful of the reader's time.** Every sentence should earn its place. If you can say it in fewer words without losing clarity, do so.

### Second Person

Address the reader as "you." This makes documentation feel direct and actionable.

- Good: "You can configure the timeout by setting `TIMEOUT_MS`"
- Avoid: "One can configure the timeout" or "The user configures the timeout"

### Active Voice

Use active voice. It's clearer, shorter, and more direct.

- Good: "The server processes the request"
- Avoid: "The request is processed by the server"

Exception: Use passive voice when the actor is unknown or irrelevant: "The log file is created automatically."

### Present Tense

Use present tense for descriptions. Use future tense only when describing something that literally happens later in a sequence.

- Good: "This method returns a JSON object"
- Avoid: "This method will return a JSON object"

### Tone by Content Type

| Content Type | Tone |
|-------------|------|
| Tutorial | Encouraging, patient, collaborative ("Let's build...") |
| How-to guide | Direct, efficient, action-oriented ("Configure the...") |
| Reference | Precise, neutral, factual ("Returns a string of...") |
| Explanation | Thoughtful, conversational, exploratory ("The reason for...") |
| Troubleshooting | Calm, empathetic, solution-focused ("If you see this error...") |
| Migration guide | Clear, reassuring, step-by-step ("This change requires...") |

---

## Language Conventions

### Clarity

**Use simple words.** "Use" not "utilize." "Start" not "initiate." "End" not "terminate." Technical precision matters for technical terms; plain language matters for everything else.

**Write short sentences.** If a sentence has more than 25 words, consider splitting it. If it has a semicolon and two dependent clauses, it definitely needs splitting.

**One idea per paragraph.** Each paragraph should make one point. If you're covering two related but distinct ideas, use two paragraphs.

### Terminology

**Be consistent.** Pick one term for each concept and use it everywhere. If you call it a "workspace" in the UI, call it a "workspace" in the docs. Never switch between "workspace," "project," and "environment" for the same thing.

**Define terms on first use.** When introducing a product-specific term, define it immediately or link to the glossary.

**Use industry-standard terms.** Don't invent new names for established concepts. Call a webhook a "webhook," not a "notification callback" or "event relay."

### Inclusive Language

- Use gender-neutral pronouns ("they/them") or rephrase to avoid pronouns
- Avoid ableist language ("crippled," "blind to," "lame")
- Use "allowlist/blocklist" instead of "whitelist/blacklist"
- Use "primary/replica" instead of "master/slave"
- Avoid violent metaphors ("kill the process" → "stop the process")

### Global Readability

- Avoid idioms and colloquialisms ("out of the box," "low-hanging fruit")
- Don't assume cultural context (holidays, sports metaphors, regional references)
- Spell out acronyms on first use: "Transport Layer Security (TLS)"
- Use standard date formats: "March 15, 2025" or ISO 8601 (`2025-03-15`)
- Use metric units with imperial in parentheses if needed

---

## Formatting Standards

### Headings

- Use sentence case: "Configure the database connection"
- Keep headings descriptive and specific
- Don't skip heading levels (H2 → H4)
- Make headings scannable — a reader should understand the page structure from headings alone

### Lists

**Use numbered lists for sequences.** Steps the reader must follow in order.

**Use bulleted lists for non-sequential items.** Options, features, requirements.

**Start each item with a capital letter.** End with a period if items are complete sentences.

**Keep list items parallel.** If the first item starts with a verb, all items should start with a verb.

### Tables

Use tables for structured data that has consistent attributes across items (parameters, configuration options, error codes). Don't use tables for narrative content.

### Links

- Use descriptive link text: "See the [authentication guide](/docs/auth)" not "Click [here](/docs/auth)"
- Link to specific sections when possible, not just pages
- Verify links work (broken links destroy trust)
- Prefer relative links within your documentation

### Admonitions

Use callouts sparingly and with purpose:

- **Note**: Additional context that's helpful but not critical
- **Important**: Information that affects correct usage
- **Warning**: Information that prevents errors or data loss
- **Caution**: Information that prevents security issues

Don't use more than 2-3 admonitions per page. If everything is a warning, nothing is.

### File Paths and Commands

- Use code formatting for file paths: `config/database.yml`
- Use code formatting for commands: `npm install`
- Use code formatting for parameter names, values, and variable names
- Use bold for UI elements: **Settings > General > API Keys**

---

## Code Examples

### Principles

**Every example must work.** Copy-pasteable, runnable code. Test your examples. Broken code examples are worse than no examples.

**Show the minimum viable example.** Strip everything that isn't essential to understanding the concept. Add comments only where behavior isn't obvious from the code.

**Use realistic values.** `user@example.com` and `sk_test_abc123` not `foo` and `bar`. Realistic examples help readers map to their own code.

**Show complete context.** Include imports, initialization, and error handling when they're necessary for the code to work. Don't show a method call without showing how the client was initialized.

### Multi-Language Support

When supporting multiple languages, follow these patterns:

- Show the most common language first (usually the one matching your primary audience)
- Use language-specific idioms — Python code should look Pythonic, Go code should look like Go
- Keep examples functionally equivalent across languages
- Use tabbed code blocks so readers can switch languages
- Don't force every language into the same structure

### Code Block Format

Always specify the language for syntax highlighting:

````
```python
import stripe

stripe.api_key = "sk_test_..."
payment = stripe.PaymentIntent.create(
    amount=2000,
    currency="usd",
)
```
````

### What to Include in Code Examples

| Content Type | What to Show |
|-------------|-------------|
| Quickstart | Complete, runnable "hello world" |
| How-to guide | Focused snippet for the specific task |
| API reference | Request + response for each endpoint |
| Tutorial | Building blocks that accumulate through steps |
| Migration guide | Before/after pairs showing the change |

### Comments in Code

- Comment the "why," not the "what"
- Don't comment obvious code: `# Initialize the client` above `client = Client()`
- Do comment non-obvious behavior: `# Retry with exponential backoff (max 3 attempts)`
- Use TODO comments for parts the reader should customize: `# TODO: Replace with your API key`

---

## API Documentation Style

### Endpoint Descriptions

- Start with a verb: "Creates a new payment intent" not "This endpoint is used to create..."
- Be specific about what happens: "Creates a new payment intent and returns it with status `requires_payment_method`"
- Document side effects: "Also sends a `payment_intent.created` webhook event"

### Parameter Descriptions

- State what the parameter does, not just what it is
- Good: "The amount to charge, in the smallest currency unit (e.g., cents for USD)"
- Bad: "The amount"
- Include valid ranges, formats, and constraints
- Document defaults: "Defaults to `usd` if not specified"
- Mark required vs optional clearly

### Response Descriptions

- Document every field in the response object
- Include example responses (both success and error)
- Document the content type and status codes
- Show paginated responses if applicable

### Error Documentation

- Include every possible error code
- Show the error response format
- Explain what caused the error and how to fix it
- Good: "401 Unauthorized — The API key is missing or invalid. Verify your key at dashboard.example.com/api-keys"

---

## Visual Content

### Diagrams

- Use diagrams for system architecture, data flow, and process sequences
- Keep diagrams simple — if it needs more than 10 boxes, break it into multiple diagrams
- Include text descriptions alongside diagrams for accessibility
- Use consistent visual language (colors, shapes, arrows) across all diagrams
- Prefer text-based diagram formats (Mermaid, PlantUML) for version control

### Screenshots

- Use screenshots sparingly — they become stale quickly
- Annotate screenshots with numbered callouts
- Include alt text
- Capture at consistent resolution and dimensions
- Consider whether a text description would age better

---

## Accessibility

- Write meaningful alt text for all images
- Don't rely on color alone to convey meaning ("the red button" → "the Delete button")
- Use proper heading hierarchy for screen readers
- Provide text alternatives for video and audio content
- Ensure code examples are readable by screen readers (use proper code blocks, not images of code)
- Test documentation with keyboard-only navigation
- Use sufficient color contrast in diagrams and UI screenshots

---

## Multi-Audience Writing

### When You Have Multiple Audiences

Don't write one document that tries to serve everyone. Instead:

1. **Identify the primary audience** for each document
2. **Create separate paths** for different audiences when needs diverge significantly
3. **Use progressive disclosure** — start with what everyone needs, then go deeper
4. **Label audience clearly** — "For administrators:" or "If you're integrating as a partner:"

### Audience-Specific Adjustments

| Audience | Adjust For |
|----------|-----------|
| New developers | More context, fewer assumptions, guided paths |
| Experienced developers | Less hand-holding, more code, faster pace |
| Partner integrators | Both-side perspective, security emphasis, production readiness |
| Operators/SREs | Command-line focus, monitoring, incident response |
| Decision makers | Business value, architecture overview, comparison |

### What NOT to Do

- Don't use conditional sections within a single document for different audiences (this creates cognitive overhead)
- Don't write down to experienced developers ("As you probably know...")
- Don't assume expertise from new developers ("Simply configure the...")
- Don't mix developer docs with marketing content

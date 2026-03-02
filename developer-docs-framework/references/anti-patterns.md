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

# Content Types Reference

Detailed guidance for writing each enterprise documentation content type. Each section covers purpose, audience, structure, writing principles, and common anti-patterns.

## Table of Contents

1. [Tutorial](#tutorial)
2. [Quickstart](#quickstart)
3. [How-to Guide](#how-to-guide)
4. [Integration Guide](#integration-guide)
5. [Migration Guide](#migration-guide)
6. [Troubleshooting Guide](#troubleshooting-guide)
7. [API Reference](#api-reference)
8. [SDK Reference](#sdk-reference)
9. [Configuration Reference](#configuration-reference)
10. [Changelog and Release Notes](#changelog-and-release-notes)
11. [Explanation](#explanation)
12. [Architecture Guide](#architecture-guide)
13. [Glossary](#glossary)
14. [Runbook](#runbook)

---

## Tutorial

**Quadrant**: Learning-oriented (Acquisition + Action)
**Reader's mindset**: "I'm new to this and want to learn by doing"
**Answers the question**: "Can you teach me to...?"

### Purpose

A tutorial takes learners through a series of steps to complete a meaningful project. The goal is not task completion — it's skill acquisition. The learner should finish the tutorial having discovered what Diataxis calls "the feeling of doing" — a joined-up sense of purpose, action, thinking, and result that the accomplished practitioner experiences. Your challenge is to create a cradle for this feeling.

Tutorials are genuinely hard to write well, and they consume remarkable effort to maintain. Changes often cascade through the entire learning journey. This is normal — accept it and invest accordingly.

### Writing Principles

**Don't try to teach — provide a learning experience.** The first rule of teaching: don't try to teach by telling and explaining. Your job is to provide activities that produce results and let learning happen through doing. If you catch yourself writing a paragraph of theory, stop and convert it into a step the reader performs. Resist the anti-pedagogical temptations: abstraction, generalisation, explanation, choices, and information.

**Show the destination first.** Tell learners what they'll build before they start. "By the end of this tutorial, you'll have a working integration that receives events and logs them." This gives them motivation and a mental map. Describe what they'll *build*, not what they'll *learn* — "In this tutorial you will learn..." is a poor pattern.

**Deliver visible results early.** Each step should produce something the learner can see — a running server, a response in the terminal, a rendered component. Long stretches without feedback erode confidence.

**Point out what the learner should notice.** Learners are typically too focused on what they're doing to notice signs in their environment. Close the loops of learning by pointing things out in passing: "Notice that the response includes a `status` field — that will become important when we add error handling." Observation is an active skill the tutorial teaches.

**Encourage repetition.** Design steps so they can be re-run. Learners return to and repeat exercises that give them success, for the pleasure of getting the expected result. Repetition is sometimes the only teacher.

**Maintain narrative expectations.** After each step, tell the learner what they should see. "You should see a JSON response like this:" followed by the exact output. When reality matches expectation, confidence builds.

**Ruthlessly minimize explanation.** A tutorial is not the place for theory. Keep explanations to one sentence maximum: "We're using HTTPS because it's more secure." Link to explanation docs for readers who want depth.

**Eliminate choices.** Don't offer alternatives or options. Pick one path and guide the reader through it completely. "Use PostgreSQL" not "You can use PostgreSQL, MySQL, or SQLite."

**Aspire to perfect reliability.** Test your tutorial on a clean environment. Every step must work exactly as described. A single broken step destroys learner confidence, and confidence is the entire point.

### Structure

1. Title: "Build a [concrete thing] with [product]"
2. Introduction: What you'll build, prerequisites, time estimate
3. Setup: Environment preparation (minimal, specific)
4. Steps: Numbered, sequential, each producing visible results
5. Conclusion: What was built, what was learned, where to go next

### Language

- Use first-person plural: "Let's create our first endpoint" (affirms the teacher-student relationship)
- Be direct: "Create a file called `app.py`"
- Affirm progress: "You've now built a working API"
- Point out observations: "Notice that...", "Let's check..."

### Anti-patterns

- Explaining concepts instead of guiding actions (abstraction, generalisation)
- Offering choices between approaches
- Assuming knowledge not covered in prerequisites
- Steps that don't produce visible output
- Mixing reference material into the flow
- Saying "In this tutorial you will learn..." (describe what they'll build, not learn)
- Irreversible steps that prevent repetition

---

## Quickstart

**Quadrant**: Learning + Task (hybrid)
**Reader's mindset**: "I'm experienced and want the fastest path to a working example"

### Purpose

A quickstart gets experienced developers from zero to "hello world" in minutes. Unlike a tutorial, it doesn't teach — it demonstrates. The reader already knows how to code; they just need to see your product work.

### Writing Principles

**Optimize for speed.** Strip everything down to the minimum steps needed to see the product work. A quickstart that takes longer than 10 minutes is too long.

**Assume competence.** Don't explain what an API key is or how to install Node.js. Link to prerequisites and move on.

**Show the payoff immediately.** The reader should see a meaningful result (not just "installation successful") within the first few steps.

**Use real, runnable code.** Every code block should be copy-pasteable and work without modification (except for credentials).

### Structure

1. Title: "Quickstart" or "Get started in 5 minutes"
2. Prerequisites: One-line items with links
3. Install: Package manager commands
4. Configure: Minimum viable configuration
5. Run: The simplest meaningful operation
6. Next steps: Links to tutorials and how-to guides

### Anti-patterns

- Including explanation of architecture or design decisions
- Requiring complex setup before showing any result
- Offering multiple paths ("if you're using X, do this; if Y, do that")
- Skipping the "verify it works" step

---

## How-to Guide

**Quadrant**: Task-oriented (Application + Action)
**Reader's mindset**: "I need to accomplish something specific right now"
**Answers the question**: "How do I...?"

### Purpose

A how-to guide helps a competent user accomplish a real-world goal. The reader already understands the product basics — they need practical directions for a specific task.

How-to guides are not merely procedural. Real-world problems don't always offer themselves up to linear solutions. The sequences of action sometimes need to fork and overlap, with multiple entry and exit points. A how-to guide addresses how the user *thinks* as well as what the user *does*.

### Writing Principles

**Address a real human need, not a feature.** "How to handle delivery failures" not "How to use the `DeliveryError` class." Frame guides around what the user wants to achieve, not what the API exposes. Beware of "fake guidance" that merely narrates the UI: "To deploy, click the Deploy button" is not real guidance — it's obvious. Real guidance addresses the thinking and judgement involved.

**Assume competence.** The reader has completed the tutorial or quickstart. Don't re-explain fundamentals.

**Stay focused on the task.** Eliminate teaching, theory, and tangential information. If context is needed, link to it.

**Design for flow.** At its best, a how-to guide appears to *anticipate* the user — like a helper who has the tool you were about to reach for, ready to place it in your hand. Ground your sequences in the user's thinking patterns. Consider: How long do you require the user to hold thoughts open before they can be resolved in action? Badly-judged pace or disrupted rhythm damages flow.

**Be adaptable.** Real-world situations vary. Where possible, explain the principle behind a step so readers can adapt to their specific context, rather than giving only rigid instructions. Unlike tutorials, how-to guides may need to fork and branch.

**Name it clearly.** "How to implement signature verification" tells the reader exactly whether this guide solves their problem.

### Structure

1. Title: "How to [accomplish specific goal]"
2. Introduction: One sentence describing what this achieves and when you'd need it
3. Prerequisites: What must be in place before starting
4. Steps: Goal-oriented, with code examples (may fork or branch when the problem demands it)
5. Verification: How to confirm the task is complete
6. Related guides: Links to related how-to guides

### Language

- Use conditional imperatives: "If you need to handle retries, add..."
- Be action-oriented: "Configure the storage bucket"
- Address the reader directly: "You can verify this by..."

### Anti-patterns

- Teaching concepts (that belongs in tutorials)
- Including comprehensive parameter lists (that belongs in reference)
- Explaining why the product works this way (that belongs in explanation)
- Narrating the UI without adding real guidance ("Click Deploy to deploy")
- Describing multiple approaches without recommending one

---

## Integration Guide

**Quadrant**: Task-oriented (specialized for partner ecosystems)
**Reader's mindset**: "I need to connect my system with yours"

### Purpose

Integration guides help external developers (partners, third-party developers) connect their systems with your platform. They combine how-to structure with partner-specific context.

### Writing Principles

**Document the integration, not just your API.** The reader needs to understand what happens on both sides — your system and theirs.

**Include architecture context.** A brief system interaction diagram helps partners understand data flow before they start building.

**Provide end-to-end examples.** Show complete request/response cycles, including error scenarios and edge cases partners will actually encounter.

**Address security explicitly.** Partners need clear guidance on authentication, authorization, data handling, and compliance requirements.

### Structure

1. Title: "Integrate [product] with [partner system/use case]"
2. Overview: What the integration accomplishes, architecture diagram
3. Prerequisites: Accounts, credentials, environments needed
4. Authentication: How to authenticate requests
5. Core integration steps: Sequential, with both sides shown
6. Error handling: Common errors and how to handle them
7. Testing: How to verify the integration works
8. Going to production: Checklist for production readiness
9. Support: Where to get help

### Anti-patterns

- Only documenting your side of the interaction
- Skipping error handling and edge cases
- Assuming the partner knows your internal terminology
- Missing production readiness guidance

---

## Migration Guide

**Quadrant**: Task-oriented (version transitions)
**Reader's mindset**: "I need to upgrade without breaking my system"

### Purpose

Migration guides help users upgrade between breaking versions safely. They're critical for trust — if upgrades are painful, adoption of new versions stalls.

### Writing Principles

**Lead with what changed and why.** Before any steps, explain what's different and the reasoning. This helps users assess impact and plan their migration.

**Organize by breaking change, not by file.** Group migration steps by the change that requires them, not by which file needs editing.

**Provide before/after code.** Show the old pattern and the new pattern side by side. This is the most valuable content in any migration guide.

**Offer automated migration where possible.** Codemods, migration scripts, or CLI tools dramatically reduce migration friction. Document them prominently.

**Be honest about effort.** Estimate migration complexity and time. "This migration typically takes 1-2 hours for a medium-sized application."

### Structure

1. Title: "Migrate from v[X] to v[Y]"
2. Overview: Key changes, estimated effort, compatibility notes
3. Prerequisites: Required environment, backup recommendations
4. Automated migration: Codemods or scripts (if available)
5. Breaking changes: Each change with before/after code
6. Deprecations: What's deprecated (still works but will be removed)
7. New features: What's available now (optional adoption)
8. Verification: How to confirm migration succeeded
9. Rollback: How to revert if something goes wrong

### Anti-patterns

- Burying breaking changes in a long narrative
- Missing before/after code comparisons
- Not providing rollback guidance
- Combining multiple version jumps (guide per major version)

---

## Troubleshooting Guide

**Quadrant**: Task-oriented (problem resolution)
**Reader's mindset**: "Something is broken and I need to fix it now"

### Purpose

Troubleshooting guides help users diagnose and resolve problems. The reader is likely frustrated — get them to a solution as fast as possible.

### Writing Principles

**Organize by symptom, not by cause.** Users know what they see ("Connection refused"), not what's wrong ("TLS certificate expired"). Lead with observable symptoms.

**Provide diagnostic steps.** Before jumping to solutions, help users confirm which specific problem they have.

**Give the fix, then explain.** Put the solution first, then explain why it works. Frustrated users need the answer immediately.

**Cover common causes in order of likelihood.** Start with the most common cause and work toward the obscure ones.

### Structure

1. Title: "Troubleshooting [area/feature]"
2. Symptom-based sections, each containing:
   - Symptom: What the user observes (error message, behavior)
   - Diagnosis: How to confirm this specific problem
   - Solution: Steps to resolve it
   - Explanation: Why this happens (brief, linked to explanation docs)

### Anti-patterns

- Organizing by internal component instead of user-visible symptom
- Long explanations before the fix
- Missing exact error messages (users search for these)
- Not covering the most common problems

---

## API Reference

**Quadrant**: Information-oriented (Application + Cognition)
**Reader's mindset**: "I need exact specifications to write code against"
**Answers the question**: "What is...?"

### Purpose

API reference is the technical specification of your API. It describes every endpoint, parameter, response, and error with precision. One hardly *reads* reference material; one *consults* it. It should be **austere** — deliberately stripped down, wholly authoritative. There should be no doubt or ambiguity in reference.

### Writing Principles

**Describe, don't instruct.** Reference is descriptive, not prescriptive. State what each endpoint does, not how to use it in a workflow (that's a how-to guide).

**Mirror the API's structure.** Organize reference docs to match the API's resource structure. If the API has `/users`, `/orders`, `/payments`, the docs should follow the same grouping.

**Be exhaustive.** Every parameter, every response field, every error code, every header. Completeness is the primary virtue of reference documentation.

**Provide examples for every endpoint.** Show a request and its response. This is not instruction — it's illustration of the interface.

**Use consistent formatting.** Every endpoint description should follow the same pattern: description, authentication, parameters, request example, response example, error codes.

### Structure (per endpoint)

1. Endpoint: Method + path (`POST /v1/payments`)
2. Description: One sentence about what it does
3. Authentication: Required auth method
4. Parameters: Table with name, type, required/optional, description
5. Request body: Schema with example
6. Response: Schema with example for success and error cases
7. Error codes: Table of possible errors with descriptions

### Language

- Use present tense: "Returns a list of payments"
- Be precise: "String, max 255 characters" not "text field"
- Use directive language for constraints: "Must be a valid ISO 8601 datetime"

### Anti-patterns

- Mixing how-to content with reference (keep them separate, link between them)
- Incomplete parameter descriptions
- Missing error documentation
- Auto-generated docs without human review (auto-generation is a starting point, not the end)
- Inconsistent formatting across endpoints

---

## SDK Reference

**Quadrant**: Information-oriented (language-specific)
**Reader's mindset**: "I need the exact method signature and behavior for my language"

### Purpose

SDK reference documents language-specific libraries that wrap your API. It should feel native to each language's conventions and ecosystem.

### Writing Principles

**Follow language conventions.** Python docs should use Python idioms. Java docs should follow Javadoc patterns. Don't force a single format across all languages.

**Document types precisely.** Include parameter types, return types, exceptions/errors thrown, and nullability.

**Show idiomatic usage.** Code examples should follow the language's best practices, not just work.

**Keep in sync with API reference.** SDK reference and API reference should describe the same behavior; they just describe it at different abstraction levels.

### Structure (per class/module)

1. Class/module overview
2. Constructor/initialization
3. Methods: Each with signature, parameters, return value, exceptions, example
4. Types/models: Data classes with field descriptions
5. Constants/enums: With descriptions

### Anti-patterns

- Non-idiomatic code examples
- Inconsistency with the API reference
- Missing error/exception documentation
- Treating all languages identically

---

## Configuration Reference

**Quadrant**: Information-oriented (operational)
**Reader's mindset**: "I need to know what this setting does and what values are valid"

### Purpose

Configuration reference documents every configurable parameter — environment variables, config files, CLI flags, feature toggles.

### Structure (per parameter)

1. Name: The exact parameter name
2. Description: What it controls
3. Type: Data type and constraints
4. Default: The default value
5. Required: Whether it must be set
6. Example: A practical value
7. Notes: Interactions with other parameters, caveats

---

## Changelog and Release Notes

**Quadrant**: Information-oriented (temporal)
**Reader's mindset**: "What changed in this release?"

### Purpose

Changelogs track technical changes for developers. Release notes communicate changes for broader audiences including product stakeholders.

### Writing Principles

**Follow a consistent format.** Use categories: Added, Changed, Deprecated, Removed, Fixed, Security.

**Link to relevant docs.** Every change should link to the documentation for that feature.

**Be specific.** "Fixed null pointer exception in payment processing when currency is undefined" not "Bug fixes."

**Include migration notes.** If a change requires user action, say so explicitly and link to the migration guide.

### Structure

- Version number and date
- Summary (one sentence, biggest change)
- Categories: Added, Changed, Deprecated, Removed, Fixed, Security
- Each item: One sentence + link to docs/PR

### Anti-patterns

- Vague descriptions ("Various improvements")
- Missing version numbers or dates
- Mixing internal refactoring with user-facing changes without distinction
- Not linking to migration guides for breaking changes

---

## Explanation

**Quadrant**: Understanding-oriented (Acquisition + Cognition)
**Reader's mindset**: "I want to understand why things work this way"
**Answers the question**: "Why...?"

### Purpose

Explanation provides the "why" behind design decisions, architectural choices, and conceptual foundations. Without explanation, a practitioner's knowledge is loose, fragmented, and fragile — and their exercise of the craft is *anxious*. Explanation is the web that holds everything together.

Explanation is often not explicitly recognized in documentation. Instead, it tends to be scattered in small parcels within other sections. Centralizing it gives it the space it deserves.

### Writing Principles

**Start with a "why" question.** Use a real or imagined *why* question as a prompt to scope the document: "Why does the system use eventual consistency?" This prevents the open-endedness that can make explanation hard to write.

**Take a higher, wider view.** Step back from specific operations and discuss the bigger picture — design philosophy, trade-offs, historical context.

**Make connections.** Link ideas together, even beyond your product. "This approach is similar to how DNS resolution works" helps readers build mental models. Unfold the internal secrets of the machinery.

**Admit alternatives and trade-offs.** Explanation should discuss what was considered and rejected, not just what was chosen. "We chose eventual consistency because strong consistency would add 200ms latency to every write."

**Offer judgements and opinions.** Unlike reference (which is austere and neutral), explanation is the place for considered opinions: "X is better than Y because..." This is one of the key Diataxis distinctions.

**Keep boundaries clear.** Don't slip into how-to instructions or reference-style parameter lists. Link to those documents instead.

**Write for reflection, not action.** Explanation is best read away from the keyboard — imagine reading it in the bath, or discussing it with a colleague over coffee. The reader is thinking, not coding.

### Structure

1. Title: "Understanding [concept]" or "How [system] works" or "About [topic]"
2. Overview: Why this topic matters
3. Key concepts: Core ideas explained with analogies and examples
4. Design decisions: What was chosen and why
5. Trade-offs: What was gained and given up
6. Further reading: Links to related explanation docs and external resources

### Anti-patterns

- Scattering explanation across how-to guides (centralize it)
- Including step-by-step instructions
- Being so abstract that no one benefits
- Undervaluing explanation because it's "not actionable"
- Not recognizing explanation as a distinct content type at all

---

## Architecture Guide

**Quadrant**: Understanding-oriented (system-level)
**Reader's mindset**: "I need to understand the system design to make good decisions"

### Purpose

Architecture guides document system design, component relationships, data flow, and design rationale. They help engineers (internal and partner) understand how the system works at a structural level.

### Structure

1. System overview and diagram
2. Component descriptions and responsibilities
3. Data flow and communication patterns
4. Design decisions and trade-offs (consider ADR format)
5. Scalability and reliability considerations
6. Security architecture
7. Glossary of system-specific terms

---

## Glossary

**Quadrant**: Information-oriented (terminology)
**Reader's mindset**: "What does this term mean in your system?"

### Purpose

A glossary ensures everyone — developers, partners, internal teams — uses the same terms with the same meanings.

### Writing Principles

- Define terms as they apply to your product specifically
- Use plain language in definitions
- Cross-reference related terms
- Include terms that differ from common usage ("In our system, a 'workspace' refers to...")

---

## Runbook

**Quadrant**: Task-oriented (operational)
**Reader's mindset**: "I'm on call and need to respond to this incident"

### Purpose

Runbooks document operational procedures for maintaining, monitoring, and troubleshooting production systems. They're used under time pressure during incidents.

### Writing Principles

**Optimize for speed under stress.** The reader is in an incident. Use short sentences, numbered steps, and clear decision points.

**Include decision trees.** "If the error is X, go to section 3. If the error is Y, go to section 4."

**Provide exact commands.** No pseudocode, no "something like." Give the exact command to run.

**Document escalation paths.** Who to contact, when to escalate, what information to provide.

### Structure

1. Title: "[Service/System] Runbook"
2. Overview: What this runbook covers
3. Access: How to get access to relevant systems
4. Monitoring: Where to see metrics and alerts
5. Common scenarios: Each with symptoms, diagnosis, resolution
6. Escalation: When and how to escalate
7. Post-incident: Checklist for after resolution

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
| Sequencing | "First, do x. Now, do y." (no room for ambiguity) |
| Setting expectations | "The output should look something like..." |
| Prompting observation | "Notice that...", "Let's check...", "Remember that..." |
| Minimal explanation | "We must always do x before y because..." (link to more) |
| Celebrating progress | "You have built a working notification service." |

**What to avoid:**
- The five anti-pedagogical temptations: **abstraction, generalisation, explanation, choices, information**
- "In this tutorial you will learn..." — describe what they'll *build*, not what they'll *learn*
- Irreversible steps that prevent the learner from repeating the exercise

**The teacher's contract:** You are required to be present, but condemned to be absent. You bear responsibility for the learner's success. If they follow your steps and fail, the tutorial is broken, not the learner. Design for "the feeling of doing" — the joined-up sense of purpose, action, thinking, and result.

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
| Goal framing | "How to handle delivery failures" not "DeliveryError class" |

**What to avoid:**
- Teaching or explaining concepts (link to tutorials/explanation)
- "Fake guidance" that narrates the UI ("Click Deploy to deploy")
- Listing every parameter (that's reference)
- Being so procedural it can't adapt to real-world variation
- Disrupting flow with tangential information

**Key insight:** How-to guides address a human need ("I need to handle errors"), not a tool function ("here's the error API"). They include thinking and judgement — not just procedural steps. At its best, a how-to guide anticipates the user like a helper who has the tool you were about to reach for.

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
| Contextualizing | "The reason for x is because historically, y..." |
| Offering judgements | "W is better than z, because..." |
| Alternatives | "Some users prefer w (because z). This can be a good approach, but..." |
| Connections | "An x in system y is analogous to a w in system z. However..." |
| Unfolding secrets | "An x interacts with a y as follows:..." |
| Trade-offs | "This favors throughput over immediate consistency." |

**What to avoid:**
- Step-by-step procedures (that's a how-to guide)
- Complete parameter listings (that's reference)
- Staying strictly neutral — explanation should have perspective
- Being so abstract that no one benefits

**Key insight:** Without explanation, practitioners' knowledge is loose, fragmented, and their practice is *anxious*. Explanation is the web that holds everything together. It is the only quadrant where opinion and perspective are not just allowed but encouraged. Scope each explanation with a "why" question. If you can imagine reading it in the bath or discussing it over coffee, it's probably explanation.

## How Diataxis Style Differs from Generic Style Guides

| Convention | Google/Microsoft | Diataxis |
|-----------|-----------------|----------|
| Person | Always "you" (2nd person) | Varies by quadrant: "we" in tutorials, "you" in how-to, impersonal in reference |
| Opinion | Avoid personal opinions | Encouraged in explanation quadrant |
| Explanation in guides | Include context | Ruthlessly minimize; link instead |
| Tone consistency | Uniform across all docs | Deliberately varies per content type |
| Choices/alternatives | Present options | Eliminate in tutorials; allow in how-to |
| Teaching | Teach as you go | Only in tutorials; never in how-to/reference |

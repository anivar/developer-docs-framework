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

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

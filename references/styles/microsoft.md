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

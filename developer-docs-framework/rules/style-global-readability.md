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

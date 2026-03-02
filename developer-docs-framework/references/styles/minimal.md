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

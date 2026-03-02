# diataxis-docs-framework

Enterprise technical documentation framework — 27 rules, 11 references, 6 pluggable style guides. Content architecture, writing standards, information architecture, DX strategy, documentation audit, anti-patterns checklist.

## What This Does

A comprehensive framework for writing, planning, auditing, and improving technical documentation for products that need developer and partner adoption. Synthesizes six proven frameworks:

- **Diataxis** — Content architecture (tutorials, how-to guides, reference, explanation)
- **Google OpenDocs** — Project archetypes, maturity assessment, audit methodology
- **Good Docs Project** — Content type templates with writing guides
- **Google Style Guide** — Language, tone, and formatting standards
- **Stripe DX Patterns** — Outcome-oriented docs, developer journey design
- **Canonical Practice** — Documentation as engineering discipline

## Key Features

- **27 rules** across 7 categories: content architecture, writing style, information architecture, DX, audit, governance, partner ecosystem
- **14 content types** with detailed writing guidance: tutorial, quickstart, how-to, integration guide, migration guide, troubleshooting, API reference, SDK reference, config reference, changelog, explanation, architecture guide, glossary, runbook
- **6 pluggable style guides**: Diataxis (default), Google, Microsoft, Stripe, Canonical, Minimal
- **Anti-patterns checklist** — consolidated documentation smells for review
- **Ready-to-use templates** for every content type
- **Documentation maturity model** (Seeds → Foundation → Integration → Excellence)
- **Adoption funnel** for prioritizing documentation work

## Structure

```
diataxis-docs-framework/
├── SKILL.md                        — Quick reference, rule summaries, decision trees
├── AGENTS.md                       — Complete compiled guide with all rules expanded
├── references/
│   ├── content-types.md            — 14 content types: purpose, structure, principles
│   ├── templates.md                — Copy-paste skeletons for every content type
│   ├── style-guide.md              — Formatting, code examples, accessibility
│   ├── anti-patterns.md            — Documentation smells and review checklist
│   ├── enterprise-patterns.md      — IA, docs-as-code, versioning, governance, metrics
│   └── styles/
│       ├── diataxis.md             — Default: per-quadrant voice and tone
│       ├── google.md               — Google Developer Docs conventions
│       ├── microsoft.md            — Microsoft Writing Style Guide conventions
│       ├── stripe.md               — Stripe DX-first documentation patterns
│       ├── canonical.md            — Canonical engineering discipline approach
│       └── minimal.md              — MVP docs for startups and internal tools
└── rules/                          — 27 individual rule files
    ├── write-*.md                  — Content architecture (6 rules, CRITICAL)
    ├── style-*.md                  — Writing style (6 rules, CRITICAL)
    ├── arch-*.md                   — Information architecture (4 rules, HIGH)
    ├── dx-*.md                     — Developer experience (3 rules, HIGH)
    ├── audit-*.md                  — Documentation audit (3 rules, MEDIUM)
    ├── gov-*.md                    — Governance & lifecycle (3 rules, MEDIUM)
    └── partner-*.md                — Partner & ecosystem (2 rules, MEDIUM)
```

## Frameworks & Sources

| Framework | What It Provides | Link |
|-----------|-----------------|------|
| Diataxis | Content architecture — the four quadrants | [diataxis.fr](https://diataxis.fr/) |
| Google OpenDocs | Project archetypes, maturity, audit | [github.com/google/opendocs](https://github.com/google/opendocs) |
| Good Docs Project | Templates and writing guides | [thegooddocsproject.dev](https://www.thegooddocsproject.dev/) |
| Google Style Guide | Language and formatting standards | [developers.google.com/style](https://developers.google.com/style) |
| Stripe Docs | DX-first documentation patterns | [docs.stripe.com](https://docs.stripe.com/) |
| Canonical | Documentation as engineering practice | [canonical.com/documentation](https://canonical.com/documentation) |

## Attribution

This framework synthesizes and builds upon six established documentation methodologies. The original frameworks, their authors, and licenses:

| Framework | Author / Maintainer | License | Link |
|-----------|-------------------|---------|------|
| **Diataxis** | Daniele Procida | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | [diataxis.fr](https://diataxis.fr/) |
| **Google OpenDocs** | Google LLC | [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) | [github.com/google/opendocs](https://github.com/google/opendocs) |
| **Good Docs Project** | The Good Docs Project contributors | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [thegooddocsproject.dev](https://www.thegooddocsproject.dev/) |
| **Google Developer Documentation Style Guide** | Google LLC | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [developers.google.com/style](https://developers.google.com/style) |
| **Stripe Documentation Patterns** | Stripe, Inc. | Patterns observed from public documentation | [docs.stripe.com](https://docs.stripe.com/) |
| **Canonical Documentation Practice** | Canonical Ltd. | Public methodology | [canonical.com/documentation](https://canonical.com/documentation) |

The rules, examples, anti-patterns, and templates in this framework are original work that applies and extends the principles from these sources. No content is copied verbatim from the source frameworks.

## Author

**Anivar Aravind** — [anivar.net](https://anivar.net)

## License

MIT — see [LICENSE](LICENSE) for details.

Note: While this framework itself is MIT-licensed, the underlying methodologies have their own licenses (listed above). If you redistribute portions that closely follow a specific framework's structure, respect that framework's license terms.

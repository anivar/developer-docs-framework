# Canonical Style Override

Divergences from the Diataxis default when following [Canonical's documentation practice](https://canonical.com/documentation). Apply this overlay when building infrastructure documentation, open-source platform docs (Ubuntu, cloud-native), or when you want documentation treated as a rigorous engineering discipline.

## Where Canonical Agrees with Diataxis Default

Canonical is the primary adopter and promoter of Diataxis — their approach is the closest to pure Diataxis of any organization. Most Diataxis defaults ARE Canonical's conventions.

Agreement on:
- Four content types with strict separation
- Per-quadrant tone variation
- First-person plural in tutorials
- Austere reference style
- Cross-linking between quadrants

## Where Canonical Extends Diataxis

### Documentation as Engineering Practice

**Diataxis default:** Documentation is a practice.
**Canonical extension:** Documentation is an **engineering practice** — not an engineering task. This distinction means:

- Engineers, product managers, and technical authors all share responsibility
- Documentation work is reviewed with the same rigor as code
- The organization applies scientific methodology to documentation: "critical, exploratory, collaborative and iterative"
- Documentation quality is a team-level metric, not a writer-level metric

### Four Pillars Framework

Canonical extends Diataxis with an organizational framework:

| Pillar | Purpose |
|--------|---------|
| **Direction** | Standards and quality metrics aligned with user needs |
| **Care** | Culture that treats documentation as a living concern |
| **Execution** | Workflows that improve output consistency and efficiency |
| **Equipment** | Tools that serve the documentation work |

### Starter Packs

Canonical provides starter packs for new documentation projects — pre-configured templates and tooling that enforce Diataxis structure from day one:

- Pre-built navigation matching the four quadrants
- Template files for each content type
- CI checks for content type purity
- Style linting configured for Canonical conventions

### Rigorous Discipline

**Diataxis default:** Explains what to do and why.
**Canonical extension:** Enforces it through process.

- Documentation changes go through the same PR review as code
- Technical authors review for Diataxis compliance (correct quadrant, no mixing)
- CI/CD pipeline includes documentation builds, link checks, and style validation
- Regular audits against Diataxis structure

### Plain Language + Technical Precision

Canonical favors a style that is:
- Technically precise without being verbose
- Plain language without being oversimplified
- Structured for scanning (short paragraphs, clear headings)
- Consistent in formatting (RST or Markdown with strict conventions)

```markdown
# Canonical style (tutorial)
In this tutorial, we will set up a basic Juju controller
on a local LXD cloud. At the end, you will have a working
controller ready to deploy applications.

## Prerequisites
- Ubuntu 22.04 LTS or later
- At least 8 GB RAM

## Create the controller
First, let's bootstrap a controller:

```bash
juju bootstrap localhost my-controller
```

You should see output like:
```
Creating Juju controller "my-controller" on localhost/localhost
```
```

### Open-Source Documentation Community

Canonical actively hires technical authors and embeds them in engineering teams. Documentation is a career path, not a side task. This influences the style:

- Professional technical writing standards
- Consistent voice across large documentation sets
- Terminology governance through glossaries and style linting
- Multi-product documentation architecture (Ubuntu, Juju, MAAS, LXD each with Diataxis structure)

## When to Choose Canonical Style

- Infrastructure and platform documentation (cloud, DevOps, Linux)
- Open-source projects that want Diataxis in its purest form
- Organizations ready to invest in documentation as an engineering discipline
- Teams with dedicated technical authors
- Large documentation sets across multiple products needing consistency
- When documentation quality is a strategic differentiator

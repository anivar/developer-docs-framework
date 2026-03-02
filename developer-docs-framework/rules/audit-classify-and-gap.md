# audit-classify-and-gap

**Priority**: MEDIUM
**Category**: Documentation Audit

## Why It Matters

After inventorying your docs, classify each page into its Diataxis quadrant and then map gaps. Most documentation sets are heavy on reference (easy to generate) and light on tutorials and how-to guides (hard to write, high adoption impact). Classification reveals the imbalance; gap analysis tells you what's missing.

## Process

### Step 1: Classify

For each inventoried page, determine:
- **Is it the right content type?** Many pages mix types
- **Is it in the right location?** A tutorial in the reference section won't be found
- **Does the title signal its type?** "Authentication" is ambiguous; "How to set up authentication" is clear

### Step 2: Map Gaps

Using the 14 enterprise content types, check:

| Content Type | Covered? | Coverage Quality |
|-------------|----------|-----------------|
| Quickstart | Yes/No | Complete / Partial / Outdated |
| Tutorials | Yes/No | ... |
| How-to guides | Yes/No | ... |
| API reference | Yes/No | ... |
| ... | ... | ... |

### Step 3: Cross-Reference with Adoption Funnel

For each funnel stage (Discover → Evaluate → Start → Build → Operate → Upgrade), check whether the required content types exist and are adequate.

## Common Findings

- 70% of content is reference, 5% is tutorials
- Many "tutorials" are actually how-to guides
- Explanation content scattered across how-to guides instead of centralized
- Migration guides missing for previous major versions
- No troubleshooting guides despite high support ticket volume

# gov-freshness-cadence

**Priority**: MEDIUM
**Category**: Governance & Lifecycle

## Why It Matters

Stale documentation is worse than no documentation — it actively misleads. Different content types have different staleness tolerances. API reference that's one version behind causes integration failures. Explanation docs can remain valid for years. Setting explicit review cadences prevents the worst-case scenario: a critical doc silently becoming outdated.

## Freshness Standards

| Content Type | Maximum Staleness | Review Trigger |
|-------------|-------------------|---------------|
| API reference | Must match current release | Every release |
| SDK reference | Must match current release | Every release |
| Changelog | Updated with every release | Every release |
| Quickstart | Verified quarterly | Quarterly |
| Tutorials | Tested quarterly | Quarterly |
| How-to guides | Reviewed quarterly | Quarterly |
| Configuration reference | Updated with every release | Every release |
| Runbooks | Reviewed after every incident | After incident |
| Troubleshooting | Reviewed with support data monthly | Monthly |
| Migration guides | Verified at release time | At release |
| Explanation | Reviewed semi-annually | Semi-annually |
| Architecture guide | Reviewed semi-annually | Semi-annually |
| Glossary | Reviewed annually | Annually |

## Automation

- **Link checking**: Automated, run daily or weekly
- **Code example testing**: Automated in CI, run with every release
- **Last-updated timestamps**: Visible on every page
- **Staleness alerts**: Automated notification when a page exceeds its review cadence
- **Analytics cross-reference**: Flag high-traffic pages that haven't been updated recently

## Principle

Dead docs are worse than no docs. They misinform, slow teams down, and erode trust in the entire documentation system. A small set of fresh, accurate docs is better than a large set in various states of decay.

# arch-organize-by-type-not-team

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Users think in terms of what they need to do (learn, accomplish, look up), not which internal team built the feature. Organizing docs by team or product component creates navigation that mirrors your org chart — meaningful to employees, meaningless to developers. Content-type organization maps to how developers actually use documentation.

## Incorrect

```
docs/
├── platform-team/
│   ├── authentication.md
│   ├── rate-limiting.md
│   └── api-gateway.md
├── compute-team/
│   ├── containers.md
│   ├── scaling.md
│   └── deployments.md
└── storage-team/
    ├── buckets.md
    └── cdn.md
```

A developer deploying a containerized app with CDN needs to navigate three team silos.

## Correct

```
docs/
├── tutorials/
│   ├── deploy-first-app.md
│   └── container-basics.md
├── guides/
│   ├── authentication.md
│   ├── deploy-containers.md
│   ├── configure-autoscaling.md
│   └── set-up-cdn.md
├── reference/
│   ├── compute-api.md
│   ├── storage-api.md
│   └── networking-api.md
└── concepts/
    ├── deployment-lifecycle.md
    └── rate-limiting.md
```

Organized by what developers need to do, not who built it internally.

## Principle

The internal org chart changes. Documentation structure should be stable and user-centric. If a team reorganization would require restructuring your docs, your IA is coupled to the wrong thing.

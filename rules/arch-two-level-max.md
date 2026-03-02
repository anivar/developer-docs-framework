# arch-two-level-max

**Priority**: HIGH
**Category**: Information Architecture

## Why It Matters

Beyond two levels of nesting, users lose their position in the documentation hierarchy. Deep navigation structures create a maze where readers can't find their way back or forward. Research on information architecture consistently shows that broad, shallow structures outperform narrow, deep ones for findability.

## Incorrect

```
docs/
└── guides/
    └── messaging/
        └── channels/
            └── notifications/
                └── templates/
                    └── configure-sms-template.md   ← 5 levels deep
```

Users clicking through 5 levels of folders will abandon the search.

## Correct

```
docs/
├── guides/
│   ├── send-sms.md
│   ├── set-up-push-notifications.md
│   ├── configure-message-templates.md    ← 2 levels
│   └── handle-delivery-failures.md
└── reference/
    ├── messages-api.md
    └── channels-api.md
```

Two levels: category → document. If a category grows too large, split it into parallel categories rather than adding depth.

## When You Need More Structure

If you genuinely have hundreds of documents, use **faceted navigation** (filtering by topic, content type, language) rather than deeper hierarchy. Search also becomes critical at scale — invest in good search rather than deeper folder structures.

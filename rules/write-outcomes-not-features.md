# write-outcomes-not-features

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

The best developer documentation converts significantly better because it documents what developers want to **achieve**, not what API objects exist. Feature-centric docs describe your product. Outcome-centric docs describe the developer's success. The difference determines whether developers adopt your product or abandon it at the docs stage.

## Incorrect

Feature-centric documentation:

```markdown
# Pipeline API

The Pipeline object represents a data processing pipeline.
It contains fields for source, destination, transforms, and status.

## Create a Pipeline
POST /v1/pipelines

## Update a Pipeline
PATCH /v1/pipelines/:id

## Run a Pipeline
POST /v1/pipelines/:id/run
```

This describes what exists. The developer must figure out how these pieces solve their problem.

## Correct

Outcome-centric documentation:

```markdown
# Move Data from PostgreSQL to Your Data Warehouse

Set up a data sync in three steps:
define your source, configure transforms, and start the pipeline.

## 1. Connect your source database

```python
pipeline = dataflow.Pipeline.create(
    source="postgresql://prod-db/analytics",
    destination="bigquery://my-project.dataset",
)
# Pipeline is ready to configure transforms
```

## 2. Define transforms
...

## 3. Start the sync
...
```

The developer sees their goal ("move data to warehouse") and follows a path to achieve it.

## Principle

Name documents after what the developer achieves, not what the API provides. "Move data to your warehouse" not "Pipeline API." "Send email notifications" not "Notifications endpoint." Reference docs can be feature-centric (they describe machinery). How-to guides and tutorials must be outcome-centric.

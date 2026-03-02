# write-reference-describe-only

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Reference documentation is the map of your product. Maps don't tell you where to go — they describe what exists. When reference docs include instructions ("To use this, first do X"), explanations ("This works because of Y"), or opinions ("We recommend Z"), they become harder to scan and less trustworthy. Users consult reference while coding; they need facts instantly, not narratives.

## Incorrect

```markdown
# POST /v1/users

You should use this endpoint to create a new user. First,
make sure you've set up your API key (see our getting started
guide). We recommend using the batch endpoint for importing
multiple users because it's more efficient.

To create a user, you'll need to specify an email and role.
Here's how:

```python
user = admin.User.create(email="ada@example.com", role="viewer")
```

The role field uses RBAC because it provides fine-grained access control.
```

This mixes instruction ("first, make sure"), opinion ("we recommend"), how-to ("here's how"), and explanation ("because it provides").

## Correct

```markdown
# POST /v1/users

Creates a new user in the specified organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `email` | string | yes | Valid email address. Must be unique within the organization. |
| `role` | string | yes | One of `owner`, `admin`, `editor`, `viewer`. |
| `org_id` | string | yes | Organization identifier. |

## Example request

```python
admin.User.create(email="ada@example.com", role="editor", org_id="org_42")
```

## Example response

```json
{
  "id": "usr_5678",
  "email": "ada@example.com",
  "role": "editor",
  "status": "invited"
}
```

## Errors

| Code | Description |
|------|-------------|
| `email_taken` | A user with this email already exists in the organization. |
| `invalid_role` | Role must be one of: owner, admin, editor, viewer. |
```

## Principle

Reference docs use **neutral description**. State what the machinery does. Don't instruct, explain, or opine. Link to how-to guides and explanation docs for those purposes.

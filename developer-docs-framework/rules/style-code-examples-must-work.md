# style-code-examples-must-work

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

A broken code example destroys trust faster than any other documentation failure. Developers copy-paste from docs and expect it to work. When it doesn't, they question everything else in the documentation. Stripe, Twilio, and AWS all test their code examples in CI — this is the standard for developer-facing documentation.

## Incorrect

```python
# Incomplete — missing imports and initialization
user = User.create(name="Ada", email="ada@example.com")
```

```javascript
// Undefined variable and missing setup
const result = await db.users.insert({
  data: userData, // Where does 'userData' come from?
})
```

## Correct

```python
from myapp.db import DatabaseClient

db = DatabaseClient(url="postgresql://localhost/mydb")  # TODO: Replace with your connection string

user = db.users.create(
    name="Ada Lovelace",
    email="ada@example.com",
    role="engineer",
)
print(user.id)  # "usr_1234..."
```

Complete context: import, initialization, operation, and output.

## Checklist

- [ ] Includes all necessary imports
- [ ] Shows initialization/setup
- [ ] Uses realistic values (`user@example.com`, not `foo`)
- [ ] Specifies language for syntax highlighting
- [ ] Shows expected output where helpful
- [ ] Marks values the reader must replace with `# TODO:` comments
- [ ] Tested and verified to work against the current API version

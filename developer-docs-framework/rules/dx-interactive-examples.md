# dx-interactive-examples

**Priority**: HIGH
**Category**: Developer Experience

## Why It Matters

Interactive examples — runnable sandboxes, multi-language code tabs, "try it" buttons — let developers validate understanding immediately without leaving the docs. Stripe's three-column layout with hoverable code is the gold standard. Even without custom tooling, tabbed multi-language examples and copy buttons significantly improve the developer experience.

## Incorrect

```markdown
Here's how to upload a file in Python:

```python
storage.upload("my-bucket", file="report.csv")
```

For Node.js, see our [Node.js guide](/guides/node).
For Go, see our [Go guide](/guides/go).
```

Forces language-switching developers to navigate away.

## Correct

Tabbed code blocks showing all languages inline:

````markdown
# Upload a File

{% tabs %}
{% tab title="Python" %}
```python
from cloudstore import Client

client = Client(api_key="cs_test_...")
result = client.upload(
    bucket="my-bucket",
    file="report.csv",
)
```
{% endtab %}
{% tab title="Node.js" %}
```javascript
const { CloudStore } = require("cloudstore");

const client = new CloudStore("cs_test_...");
const result = await client.upload({
  bucket: "my-bucket",
  file: "report.csv",
});
```
{% endtab %}
{% tab title="Go" %}
```go
client := cloudstore.NewClient("cs_test_...")

result, err := client.Upload(ctx, &cloudstore.UploadParams{
    Bucket: "my-bucket",
    File:   "report.csv",
})
```
{% endtab %}
{% endtabs %}
````

All languages visible on one page. The developer stays in context.

## Levels of Interactivity

| Level | Implementation | Effort |
|-------|---------------|--------|
| Copy button | Static code blocks with clipboard | Low |
| Language tabs | Tabbed code blocks per language | Low |
| "Try it" API explorer | Interactive request builder | Medium |
| Embedded sandbox | Runnable code in the browser | High |
| Live preview | Real-time output as code changes | High |

Start with copy buttons and language tabs. These provide the most DX improvement for the least effort.

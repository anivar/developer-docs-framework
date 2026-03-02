# Stripe Style Override

Divergences from the Diataxis default when following Stripe's developer documentation patterns. Apply this overlay when building API-first products where developer adoption is the primary business metric, or when you want the gold standard of DX-focused documentation.

## Where Stripe Agrees with Diataxis Default

- Content types are clearly separated
- Reference docs are precise and comprehensive
- Code examples are complete and runnable
- One concept per page

## Where Stripe Diverges

### Outcome-First Framing (Everywhere)

**Diataxis default:** Tutorials are learning-oriented, reference is descriptive.
**Stripe override:** Everything is outcome-oriented. Even reference pages are organized around what the developer achieves, not what objects exist.

```markdown
# Diataxis reference organization
/reference/payment-intents
/reference/charges
/reference/customers

# Stripe-style organization
/docs/payments/accept-a-payment      → uses PaymentIntents
/docs/payments/save-and-reuse        → uses Customers + PaymentMethods
/docs/payments/handle-failed         → uses Charges, Events
```

The API reference exists separately, but the primary navigation is outcome-based.

### Three-Column Layout

Stripe's signature design pattern:
- **Left column**: Persistent navigation tree
- **Center column**: Written guidance and explanations
- **Right column**: Live, syntax-highlighted code examples

Code and documentation are viewed side-by-side, never requiring the developer to scroll between prose and code. When you hover over a concept in the center, the corresponding code highlights in the right column.

### Interactive Code

**Diataxis default:** Static code blocks with expected output.
**Stripe override:** Code examples are interactive — copy-paste buttons, language selectors, and in some cases, executable directly from the documentation.

```markdown
# Diataxis default
```python
payment = stripe.PaymentIntent.create(amount=2000, currency="usd")
```

# Stripe style — tabbed, copyable, with response preview
[Python | Ruby | Node | Go | Java | PHP | .NET]

```python
import stripe
stripe.api_key = "sk_test_..."

intent = stripe.PaymentIntent.create(
    amount=2000,
    currency="usd",
)
```

→ Response:
```json
{
  "id": "pi_1234",
  "status": "requires_payment_method"
}
```
```

### Documentation as Product Culture

**Diataxis default:** Documentation is a practice.
**Stripe override:** Documentation is a product with its own engineering investment.

Key cultural practices:
- **Career ladders include documentation** at every engineering level
- **Performance reviews** assess documentation contributions
- **A feature isn't done** until docs are written, reviewed, and published
- **Writing classes** offered to all engineers during onboarding
- **Office hours** with technical writers for documentation help
- **Custom tooling** (Markdoc) built specifically for docs authoring

### Personalization

Stripe docs adapt to the reader:
- Detect the developer's likely language and show relevant examples first
- Dashboard context carries into documentation (test vs. live mode indicators)
- Code examples use the developer's actual test API keys when logged in

### Error Documentation

Every error includes:
1. The exact error code
2. Why it happens (one sentence)
3. How to fix it (specific steps)
4. Link to relevant guide

```markdown
## 402 — card_declined

The card was declined. The most common causes are
insufficient funds or a card that doesn't support
the transaction type.

**Fix**: Ask the customer to use a different card,
or retry with [3D Secure authentication](/guides/3d-secure).
```

## When to Choose Stripe Style

- API-first products where developer adoption drives revenue
- Products with multiple language SDKs
- Teams with engineering investment in documentation tooling
- Products where time-to-first-API-call is a business KPI
- Organizations willing to treat documentation as a product

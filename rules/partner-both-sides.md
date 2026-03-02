# partner-both-sides

**Priority**: MEDIUM
**Category**: Partner & Ecosystem

## Why It Matters

Integration guides that only document your API leave partners guessing about what happens on their side. A partner integrating with your platform needs to know what request you expect, what response you return, AND what their system should do with that response. Documenting only your side forces partners to reverse-engineer the full integration.

## Incorrect

```markdown
# Device Telemetry Integration

## Endpoint
POST /v1/telemetry/subscribe

## Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| callback_url | string | Your endpoint URL |
| device_types | array | Device types to subscribe to |
```

Only your side documented. The partner doesn't know: What does the telemetry payload look like? What should their endpoint return? How should they verify authenticity? What happens on timeout?

## Correct

```markdown
# Device Telemetry Integration

## 1. Register your endpoint (your side → our API)

```bash
curl -X POST https://api.example.com/v1/telemetry/subscribe \
  -d callback_url="https://partner.com/telemetry" \
  -d device_types[]="sensor.temperature"
```

## 2. Receive telemetry (our system → your endpoint)

We send a POST request to your endpoint:

```json
{
  "id": "evt_1234",
  "type": "sensor.temperature.reading",
  "data": { "device_id": "dev_5678", "value": 23.4, "unit": "celsius" }
}
```

**Your endpoint must:**
- Return HTTP 200 within 30 seconds
- Verify the `X-Signature` header (see [signature verification](/guides/signatures))
- Process idempotently (we may retry)

## 3. Handle failures (retry behavior)

If your endpoint returns non-200 or times out:
- We retry 3 times with exponential backoff (1s, 10s, 100s)
- After 3 failures, the subscription is paused
- You receive an email notification
```

Both sides documented. The partner can build a complete integration from one document.

## Principle

For every request you document, document the expected response. For every callback you send, document what the partner's system should do with it. Include architecture diagrams showing the full interaction flow.

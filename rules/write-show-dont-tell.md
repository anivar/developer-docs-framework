# write-show-dont-tell

**Priority**: CRITICAL
**Category**: Content Architecture

## Why It Matters

Abstract descriptions remain abstract until grounded in concrete examples. Developers learn by seeing working code, real responses, and actual behavior — not by reading paragraphs about how something "can be used." Every claim, every concept, every feature needs a concrete illustration.

## Incorrect

```markdown
# Event Streams

Event streams allow you to consume real-time data from
your application. They can be configured to deliver events
to any consumer. The payload contains event details in JSON
format. You should handle backpressure to avoid data loss.
```

Four sentences of telling. No showing. The developer has no idea what an event looks like, how to consume it, or what code to write.

## Correct

```markdown
# Event Streams

Subscribe to a stream and process events as they arrive:

```json
{
  "id": "evt_1234",
  "type": "order.shipped",
  "timestamp": "2025-06-15T14:30:00Z",
  "data": {
    "order_id": "ord_5678",
    "tracking_number": "1Z999AA10123456784",
    "carrier": "ups"
  }
}
```

Connect and consume events:

```python
from eventbus import Consumer

consumer = Consumer(topic="orders", group="shipping-service")
for event in consumer.stream():
    print(f"Order {event.data['order_id']} shipped")
    event.ack()
```
```

Real payload. Real code. The developer understands immediately.

## Principle

For every concept you describe, ask: "Can I show this with code, a response, a diagram, or a screenshot?" If yes, show it. The showing often replaces the telling entirely.

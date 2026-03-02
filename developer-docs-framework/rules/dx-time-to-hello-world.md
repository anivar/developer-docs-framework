# dx-time-to-hello-world

**Priority**: HIGH
**Category**: Developer Experience

## Why It Matters

Time to first API call (or first working example) is the single most important DX metric. Every minute a developer spends before seeing a working result increases the probability they'll abandon your product. Stripe, Twilio, and Firebase all optimize for "hello world in under 5 minutes." If your quickstart takes longer, developers are evaluating alternatives.

## Incorrect

```markdown
# Getting Started

## Step 1: Understand the Architecture
Our platform uses a serverless architecture with...
[500 words of explanation]

## Step 2: Set Up Your Development Environment
Install the CLI, configure IAM roles, set up VPC...
[complex multi-tool setup]

## Step 3: Configure Authentication
Create a service account and generate credentials...
[15 steps of configuration]

## Step 4: Make Your First Request
[finally, 20 minutes later]
```

## Correct

```markdown
# Quickstart

## Install

```bash
pip install sendwave
```

## Send your first message

```python
import sendwave

client = sendwave.Client("sw_test_demo")
message = client.sms.send(
    to="+1234567890",
    body="Hello from SendWave!",
)
print(message.sid)  # "msg_abc123..."
```

Run it:
```bash
python send.py
```

You should see a message ID printed. You've sent your first
SMS.

## Next steps
- [Tutorial: Build a notification service](/tutorials/notifications)
- [API reference](/reference)
```

Three steps. Under 5 minutes. Working result.

## Principle

Strip the quickstart to the absolute minimum: install, configure one credential, make one meaningful call, see one meaningful result. Everything else (architecture, advanced config, edge cases) lives in other documents.

# style-active-voice-second-person

**Priority**: CRITICAL
**Category**: Writing Style

## Why It Matters

Active voice is clearer, shorter, and more direct. Second person ("you") makes documentation feel like guidance rather than a textbook. Present tense for descriptions keeps language grounded. These three conventions — active voice, second person, present tense — are the foundation of readable technical writing, endorsed by both Google and Microsoft style guides.

## Incorrect

```markdown
The request will be processed by the server. It is recommended
that the user should set a timeout value. Once the configuration
has been completed, the service can be started by running the
start command.
```

Passive voice, third person, future tense. Wordy and impersonal.

## Correct

```markdown
The server processes the request. Set a timeout value to avoid
hanging connections. After you configure the service, start it
with `service start`.
```

Active voice, second person, present tense. Half the words, twice the clarity.

## Tone by Content Type

| Content Type | Voice Example |
|-------------|--------------|
| Tutorial | "Let's create our first endpoint" |
| How-to guide | "Configure the storage bucket" |
| Reference | "Returns a list of user objects" |
| Explanation | "The system uses eventual consistency because..." |
| Troubleshooting | "If you see this error, check your API key" |

## Exception

Use passive voice when the actor is unknown or irrelevant: "The log file is created automatically when the server starts."

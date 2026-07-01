# Playbook: Customer Support

How to handle support requests, bug reports, and user complaints with empathy and speed.

## Rules

- Respond to every support request within 24 hours.
- Never be defensive. Acknowledge, empathize, resolve.
- If it's a bug, log it in docs/intelligence/bugs.md immediately.
- If it's a feature request, log it in docs/intelligence/feature_requests.md.
- Every conversation is an opportunity to learn.

## Response SLAs

| Priority | Response Time | Resolution Time |
|----------|---------------|------------------|
| Critical (data loss, outage) | 1 hour | 4 hours |
| High (feature broken) | 4 hours | 24 hours |
| Medium (minor issue) | 24 hours | 72 hours |
| Low (question/feedback) | 48 hours | N/A |

## Response Templates

### Acknowledge a Bug
```
Hi [Name],

Thank you for reporting this. You're right, this isn't working as expected and I'm sorry for the frustration.

I've logged this as a priority bug and will update you as soon as it's resolved.

In the meantime, [workaround if applicable].

[Name]
```

### Feature Not Available
```
Hi [Name],

Great idea! This isn't something we support yet, but I've added it to our feature request list.

I'll personally follow up when we ship it.

[Name]
```

### Closing a Ticket
```
Hi [Name],

[Summary of what was resolved].

Let me know if there's anything else I can help with.

[Name]
```

## After Each Support Interaction

- Log in docs/intelligence/conversations.md if insight-worthy
- Log bug in docs/intelligence/bugs.md if applicable
- Log feature request in docs/intelligence/feature_requests.md if applicable

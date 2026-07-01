# Playbook: Bug Triage

How to identify, prioritize, and resolve bugs efficiently.

## Bug Severity Levels

| Level | Definition | Response Time |
|-------|------------|---------------|
| P0 - Critical | Product down or data loss | Immediate |
| P1 - High | Core feature broken for many users | < 4 hours |
| P2 - Medium | Feature broken for some users | < 24 hours |
| P3 - Low | Minor issue or cosmetic | Next sprint |

## Triage Process

1. **Receive** - Bug reported via support, GitHub issue, or internal discovery
2. **Reproduce** - Confirm the bug is real and reproducible
3. **Classify** - Assign severity (P0-P3)
4. **Log** - Add to docs/intelligence/bugs.md with all details
5. **Assign** - Assign to engineer or add to backlog
6. **Communicate** - If user-reported, acknowledge within SLA
7. **Resolve** - Fix and test
8. **Close** - Update status in bugs.md, notify user if applicable

## Bug Report Fields

When logging in docs/intelligence/bugs.md:

```
---
Date: YYYY-MM-DD
Reporter: [user or internal]
Severity: P0 | P1 | P2 | P3
Title: [short description]
Steps to Reproduce: [numbered steps]
Expected: [what should happen]
Actual: [what actually happens]
Environment: [browser, OS, device]
Status: OPEN | IN PROGRESS | RESOLVED | WONTFIX
Assignee: [engineer]
Notes: [any context]
---
```

## Post-Resolution

- Update status in docs/intelligence/bugs.md
- Notify user if they reported it
- Log in CHANGELOG.md if user-facing fix
- Consider if systemic issue warrants a post-mortem

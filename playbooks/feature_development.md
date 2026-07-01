# Playbook: Feature Development

How to take a feature from idea to shipped.

## Lifecycle

```
Idea -> Feature Request -> Scoped -> Designed -> Built -> Tested -> Shipped -> Logged
```

## Step 1: Feature Request

- Log in docs/intelligence/feature_requests.md
- Include: source, user quote if available, frequency of request, potential impact
- Tag as REQUESTED

## Step 2: Prioritization

Score each feature against:
- **Impact**: How many users benefit?
- **Effort**: How much engineering time?
- **Alignment**: Does it fit our mission?
- **Urgency**: Is there a time constraint?

Use impact/effort matrix. Only move HIGH impact, LOW/MEDIUM effort features to sprint.

## Step 3: Scoping

Before any design or code:
- Write a 1-paragraph description of the feature
- Define: what's in scope and what's explicitly OUT of scope
- Identify dependencies
- Estimate effort (hours)
- Get CEO sign-off if > 8 hours

## Step 4: Design (if needed)

- Wireframe or describe the UX in plain language
- Get feedback from 1-2 users before building if possible
- Keep it simple. Ship the smallest version that delivers value.

## Step 5: Build

- Create a branch
- Build with test coverage
- Open PR with description referencing the feature request
- Self-review before requesting review

## Step 6: Test

- Test on staging
- Run through the happy path and edge cases
- Get at least one other person to test

## Step 7: Ship

- Merge PR
- Update CHANGELOG.md
- Notify users who requested the feature if possible
- Update feature status in docs/intelligence/feature_requests.md to SHIPPED

## Step 8: Log

- Add to execution/completed.md
- Update CURRENT_METRICS.md if it affects a key metric
- Consider announcing on social (see playbooks/twitter.md)

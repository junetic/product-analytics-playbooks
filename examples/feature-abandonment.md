# Feature Abandonment

## Problem

A feature gets started but not completed, or used once and never again. Adoption metrics look low but it's unclear whether the feature is confusing, not valuable, or simply not discovered by the right users.

## Event Trigger

```
feature_started
```

Fired when a user enters the feature flow. Abandonment is identified when `feature_completed` does not follow within a defined session or time window.

For repeat-use features, a secondary signal is useful:

```
feature_used (count = 1, no subsequent use in 7–14 days)
```

## Workflow Overview

The pattern: `feature_started` fires without `feature_completed` → PostHog workflow sends interview link → user shares feedback → responses are summarized.

1. Configure both events in PostHog (`feature_started`, `feature_completed`)
2. Set up a workflow that triggers when a user fires `feature_started` but not `feature_completed` within a defined window
3. Send the interview link while the experience is still fresh — same session or within a few hours
4. Look for patterns across responses; a small number of conversations can quickly reveal the true cause

Low adoption can mean many things. A user who tried the feature and got stuck is a different problem than a user who tried it, understood it, and decided it wasn't useful. Interviews distinguish between the two.

## Example Insight

Common findings from feature abandonment interviews:

- Users didn't understand what the feature was supposed to do before starting
- A prerequisite step wasn't obvious (e.g., needing data that wasn't yet in the product)
- The feature solved a problem users had, but in a way that didn't match their mental model
- Users completed the feature but didn't realize it — missing confirmation or feedback

One useful framing: ask users to walk through what they were trying to accomplish, not what they did in the product. This often reveals whether the underlying job is being addressed at all.

## Interview Template

Keep it to 2–3 minutes. Focus on intent and where things broke down.

```
- What were you attempting to accomplish?
- Which part felt confusing or difficult?
- What improvements would make it more useful?
- Did you accomplish what you were trying to do? If not, how did you handle it?
```

## Message Template

```
Subject: Quick question about [feature name]

Hi [Name],

I noticed you tried [feature name] but didn't finish — I'm curious what happened.

It would really help us to hear about your experience. It only takes 2–3 minutes.

[AI interview link or reply to schedule]

[Your name]
```

## Full Guide

[Understand feature abandonment using PostHog workflows](https://www.usercall.co/post/understand-feature-abandonment-using-posthog-workflows)

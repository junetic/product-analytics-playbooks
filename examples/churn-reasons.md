# Churn Spike

## Problem

Cancellations increase above baseline. Exit surveys give you categories but not causes. You need to understand what actually drove the decision — not just which bucket users selected.

## Event Trigger

```
subscription_cancelled
```

Fired when a user cancels or downgrades. Can also be applied to free-tier churn using an inactivity signal (e.g., no activity for 14+ days before account deletion).

## Workflow Overview

The pattern: `subscription_cancelled` event fires → PostHog workflow sends interview link automatically → user shares feedback → responses are summarized.

1. Configure the trigger event in PostHog (fires when cancellation is confirmed)
2. Set up a workflow to send a message with an interview link immediately on cancellation
3. Keep the interview to 2–3 minutes — users who just cancelled are unlikely to invest more time
4. Review patterns across responses to separate genuine root causes from surface-level reasons

Exit surveys tell you what users clicked. Interviews tell you what was actually happening in the weeks before they decided to leave. Timing matters: reaching users at the moment of cancellation produces specific answers ("I needed X feature and you didn't have it") rather than vague ones collected weeks later.

## Example Insight

Common patterns that emerge across churn interviews:

- A competitor offered a specific capability the user needed
- A workflow changed internally and the product no longer fit
- The user never reached the value they expected — a slow-burn onboarding failure
- Pricing felt misaligned with what they were actually getting

The same cancellation reason (e.g., "too expensive") often masks different root causes. Price objections frequently reflect a perceived value gap rather than a budget constraint.

## Interview Template

Keep it to 2–3 minutes. Focus on the decision and what was behind it.

```
- What made you decide to cancel today?
- What problem were you hoping the product would solve?
- What could have made you stay?
- Did you find an alternative? What does it do differently?
```

## Message Template

```
Subject: Before you go — can I ask one thing?

Hi [Name],

I saw you cancelled [product] — completely fine. I just want to understand what happened so we can get better.

Would you be open to sharing why? It takes 2–3 minutes and I'm not going to try to win you back — I just want to hear what didn't work.

[AI interview link or reply to schedule]

[Your name]
```

## Full Guide

[Capture churn reasons using PostHog workflows](https://www.usercall.co/post/capture-churn-reasons-using-posthog-workflows)

# Activation Drop

## Problem

The percentage of new users reaching your activation milestone is declining. This could reflect a change in signup quality, a product regression, a UX issue, or a mismatch between what users expect and what the product delivers.

## Event Trigger

```
activation_milestone_not_reached
```

Fired (or derived) when a user completes signup but does not reach your defined activation event within a set window — typically 3–7 days depending on your product's time-to-value.

Common activation events:

- `first_core_action_completed`
- `project_created`
- `integration_connected`
- `report_generated`

## Workflow Overview

The pattern: user reaches signup but not activation milestone within the defined window → PostHog workflow sends interview link → user shares feedback → responses are summarized.

1. Define or confirm your activation milestone — the event that reliably predicts retention
2. Configure PostHog to detect users who fire the signup event but not the activation event within your window
3. Set up a workflow to send an interview link at the end of that window (e.g., day 3 or day 7 after signup)
4. Interview users who signed up with intent but didn't activate — not users who clearly signed up by mistake

A drop in activation rate is sometimes a leading indicator of a change in the signup population (e.g., a new paid channel attracting a different audience) rather than a product problem. Interviews help distinguish between these.

See also: [How to investigate product analytics anomalies](https://www.usercall.co/post/investigate-product-analytics-anomalies)

## Example Insight

Common findings from activation interviews:

- Users understood the product's purpose but couldn't connect it to their immediate problem
- A required setup step was blocked by something outside the product (e.g., needing IT approval, needing a teammate to be involved)
- The product's value was only apparent after a threshold of data or usage that users didn't reach
- Users activated on the metric but didn't experience the value — the activation definition was wrong

The last point is worth examining before starting interviews: if activation rates drop but retention among "activated" users also drops, the milestone may need revisiting.

## Interview Template

```
- What made you sign up for [product]?
- What did you expect to be able to do in the first week?
- Walk me through what you actually did after signing up.
- Was there a point where you ran out of steam or decided to pause?
- Are you still trying to solve the original problem? How?
```

## Message Template

```
Subject: How did your first week with [product] go?

Hi [Name],

You signed up for [product] last week — I wanted to check in and hear how it went.

Did you get a chance to try it out? If you hit any friction early on, I'd love to hear about it. It only takes 2–3 minutes.

[AI interview link or reply to schedule]

[Your name]
```

## Full Guide

[How to investigate product analytics anomalies](https://www.usercall.co/post/investigate-product-analytics-anomalies)

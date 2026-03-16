# Onboarding Drop-off

## Problem

Users sign up but don't complete onboarding. Your analytics shows where they stop, but not why — whether it's confusion, missing context, a missing feature, or the wrong audience.

## Event Trigger

```
onboarding_abandoned
```

Fired when a user starts onboarding but does not reach the completion event within a defined window (e.g., 24–48 hours).

## Workflow Overview

The pattern: `onboarding_abandoned` event fires → PostHog workflow sends interview link automatically → user shares feedback → responses are summarized.

1. Configure the trigger event in PostHog
2. Set up a workflow that sends a message with an interview link when the event fires
3. Collect responses across multiple users (5–10 is usually enough to see patterns)
4. Review summaries to identify recurring friction points

The goal is not to recover these users — it's to understand the pattern across enough of them to make an informed change. Immediate triggering matters: users contacted while the experience is fresh give specific answers ("The setup step for X confused me") rather than vague ones ("Something didn't work").

## Example Insight

Teams commonly find one of a few root causes:

- Users couldn't complete a required setup step (e.g., connecting an integration, inviting a teammate)
- The value wasn't clear before they were asked to do work
- The onboarding assumed context the user didn't have

A single conversation rarely reveals the full picture. After five to ten interviews, patterns tend to emerge.

## Interview Template

Keep it to 2–3 minutes. Aim for specific recall, not general reflection.

```
- What were you trying to accomplish during onboarding?
- Which setup step felt most confusing?
- What almost caused you to stop using the product?
- Did you end up finding another solution, or is this still unsolved?
```

## Message Template

```
Subject: Quick question about your signup

Hi [Name],

You signed up for [product] recently but didn't finish getting set up — totally fine, just curious what happened.

If you have a few minutes, I'd love to hear about it. No pitch, just trying to understand where things got confusing.

[AI interview link or reply to schedule]

[Your name]
```

## Full Guide

[Investigate onboarding drop-off using PostHog workflows](https://www.usercall.co/post/investigate-onboarding-drop-off-using-posthog-workflows)

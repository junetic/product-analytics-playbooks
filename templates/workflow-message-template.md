# Workflow Message Templates

Message templates for reaching users after product events. These are designed to be sent automatically (or semi-automatically) as part of a workflow triggered by an analytics event.

Adapt the tone and content to your product and audience. The goal is a short, human message — not a support ticket or a marketing email.

---

## Onboarding Drop-off

**Trigger:** `onboarding_abandoned` — user started onboarding but did not complete it within 24–48 hours.

```
Subject: Quick question about your signup

Hi [Name],

You signed up for [product] recently but didn't finish getting set up — totally fine, just curious what happened.

If you have a few minutes, I'd love to hear about it. No pitch, just trying to understand where things got confusing.

[AI interview link or reply to schedule]

[Your name]
```

---

## Churn / Cancellation

**Trigger:** `subscription_cancelled` — user cancelled their subscription.

```
Subject: Before you go — can I ask one thing?

Hi [Name],

I saw you cancelled [product] — completely fine. I just want to understand what happened so we can get better.

Would you be open to sharing why? It takes 2–3 minutes and I'm not going to try to win you back — I just want to hear what didn't work.

[AI interview link or reply to schedule]

[Your name]
```

---

## Feature Abandonment

**Trigger:** `feature_started` without subsequent `feature_completed` within a session or time window.

```
Subject: Quick question about [feature name]

Hi [Name],

I noticed you tried [feature name] but didn't finish — I'm curious what happened.

It would really help us to hear about your experience. It only takes 2–3 minutes.

[AI interview link or reply to schedule]

[Your name]
```

---

## Activation Drop

**Trigger:** User did not reach activation milestone within 3–7 days of signup.

```
Subject: How did your first week with [product] go?

Hi [Name],

You signed up for [product] last week — I wanted to check in and hear how it went.

Did you get a chance to try it out? If you hit any friction early on, I'd love to hear about it. It only takes 2–3 minutes.

[AI interview link or reply to schedule]

[Your name]
```

---

## Tips

- Send within 24–48 hours of the trigger event — while the experience is still fresh
- Keep the message short; anything longer than 5–6 lines reduces response rates
- Make the ask specific (an AI interview link, a reply) rather than open-ended
- Avoid language that sounds automated — "I noticed" works better than "Our system detected"
- A direct reply option works well alongside the AI interview link for users who prefer async text

# Product Analytics Playbooks

Analytics shows what happened. These playbooks help you figure out why.

When your metrics shift — drop-off increases, churn spikes, a feature goes unused — the next step is usually qualitative. Talking to the right users at the right moment surfaces context that dashboards can't show.

This repository contains playbooks for investigating common product analytics signals such as onboarding drop-off, churn spikes, feature abandonment, and activation decline — using tools like PostHog workflows and short user interviews.

---

## How it works

```
PostHog event fires
  → workflow triggers a message to the user
    → user completes a short AI interview (2–3 min)
      → AI summarizes insights across responses
```

Each playbook maps a specific analytics signal to a trigger event, a workflow, and a set of interview questions.

---

## Playbooks

| Scenario | Playbook |
|---|---|
| Users dropping off during onboarding | [onboarding-dropoff.md](examples/onboarding-dropoff.md) |
| Churn spike with unclear cause | [churn-reasons.md](examples/churn-reasons.md) |
| Feature with low adoption or abandonment | [feature-abandonment.md](examples/feature-abandonment.md) |
| Activation rate declining | [activation-drop.md](examples/activation-drop.md) |

---

## Example insight

Onboarding completion dropped from 62% to 38% over three weeks. Funnel analysis showed the drop was concentrated at the integration setup step, but gave no indication of why.

Five interviews later: users were trying to connect a required integration but hitting a permissions error they didn't know how to resolve. It wasn't a motivation problem — it was a blocked setup step.

Fixing the error message and adding a fallback option brought completion back to 55%.

---

## Templates

Reusable assets for building your own workflows:

- [Interview question templates](templates/interview-questions.md)
- [Workflow message templates](templates/workflow-message-template.md)

---

## Full Guides

Step-by-step walkthroughs with PostHog setup instructions:

- [Investigate onboarding drop-off](https://www.usercall.co/post/investigate-onboarding-drop-off-using-posthog-workflows)
- [Capture churn reasons](https://www.usercall.co/post/capture-churn-reasons-using-posthog-workflows)
- [Understand feature abandonment](https://www.usercall.co/post/understand-feature-abandonment-using-posthog-workflows)
- [PostHog workflows for understanding user behavior](https://www.usercall.co/post/posthog-workflows-understand-user-behavior)
- [How to investigate product analytics anomalies](https://www.usercall.co/post/investigate-product-analytics-anomalies)

---

## Try this workflow

1. Pick a product event (`onboarding_abandoned`, `subscription_cancelled`, `feature_started`)
2. Send a short interview request immediately when it fires
3. Collect 5–10 responses
4. Look for patterns

That's it. Most teams find a clear signal within the first few conversations.

If you want to implement this approach, you can create an interview and trigger it from product events.

https://usercall.co/research-triggers

---

## Contributing

If you have a playbook for a different analytics scenario, open a pull request. Keep it minimal and focused on the investigation workflow.

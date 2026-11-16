# Experimentation Plan (Module 5)

## Get your documents ready
- **From M3, your hypothesis sentence:** Based on qualitative evidence that consumers don’t understand what an affordable, sustainable rate looks like or how to combine several claims in one plan, and on quantitative evidence that variable-income consumers (41.6% agreement, 22.5% missed payments) and consumers with 2+ open claims (37.7% / 27.6% agreement vs. 52.1% for one claim) underperform, I believe that helping consumers with multiple open claims and variable income find an affordable rate they can keep, across all their claims, will increase the instalment agreement rate by +10 pp in this segment. I will protect the missed payment rate (no more than +2 pp vs. the segment’s own baseline or control group) and SSR (no decline vs. baseline), and will make a go/no-go decision after 8 weeks of enrolment plus 2 payment cycles per cohort (about 3-4 months), provided enough plans per group are observed.
- **From M3, your primary success metric & guardrail metric:** agreement rate
guardrail: missed payment rate and SSR
- **From M4, the feature you scoped in your PRD this is what you're testing:** Plain explainer for why income is asked and how it is used so that users don't drop journey before registering an instalment plan

## Define your experiment parameters
- **Feature under test pull from your M4 PRD:** Plain explainer for why income is asked and how it is used so that users don't drop journey before registering an instalment plan
- **Persona pull your M2 persona:** Consumers with multiple open claims and variable income, who cannot pay a claim in one go
- **Expected outcome the behaviour change you expect, from your M3 hypothesis:** Reduce dropout rate when creating a new instalment plan due to uncertainty related to the income question
- **Primary success metric the one number that defines success, from M3:** agreement rate
- **Baseline rate today's rate of your primary metric, from your M3 data:** 41.6
- **Guardrail metric & boundary what must not break, and how far it can move before you investigate:** Don't increase missed payment rate or reduce SSR
- **Minimum Detectable Effect (MDE) the smallest improvement worth shipping, your floor:** +6 pt
- **Sample size per arm use the calculator in the builder, baseline + MDE:** 1077
- **Traffic split & test duration 50/50 standard · cover ≥ 2 weekly cycles:** 50/50 covering 2 weeks
- **Significance threshold p < 0.05 is standard, explain any deviation:** p < 0.05

## Define your control and variant
- **Control (A) the current experience, reference your M2 moment of misery and M3 funnel/workflow data:** _(not filled in)_
- **Variant (B) your single change, copy the relevant screens & functional requirements from your M4 PRD:** _(not filled in)_
- **Isolation check, what has NOT changed? list everything identical between arms (app version, eligibility rules, notifications, onboarding). If something changed inadvertently, your test is compromised.:** _(not filled in)_

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** _(not filled in)_
- **Your shipping criteria (filled in):** _(not filled in)_
- **Hardest parameter to define, and did it change your hypothesis? quick debrief:** _(not filled in)_

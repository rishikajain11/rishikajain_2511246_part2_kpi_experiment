# Recommendation Memo – Part 2 KPI Experiment

## Executive Summary

The new onboarding and activation campaign improved the North Star metric, **paid conversion rate**, from **3.19%** in Control to **7.04%** in Treatment. The one-tailed two-proportion z-test produced a p-value of **0.000549**, which means the conversion lift is statistically significant at the 5% level.

However, the treatment also increased the **support ticket rate** from **14.78%** to **24.79%** and introduced a small refund rate of **0.42%**. Revenue per converted user also declined from **$1630.10** to **$770.41**.

## Final Recommendation

**Launch only for selected segments through a staged rollout. Do not launch to all users yet.**

The treatment has strong conversion evidence, but the guardrail risks are too clear to ignore. A full launch would be premature because the campaign may create additional support burden and lower-quality revenue.

## Business Problem

Leadership needs to decide whether the new onboarding and activation campaign should be launched to all users, kept limited to selected users, improved further, or stopped.

This decision impacts:

- New users entering the onboarding flow.
- Marketing and product teams responsible for activation.
- Customer support teams handling onboarding confusion.
- Revenue teams focused on paid conversion and revenue quality.

The primary metric that should improve is **paid conversion rate**. The risks that must be monitored are refund rate, support ticket rate, engagement quality, days to convert, and segment-level declines.

## North Star Metric

The selected North Star metric is:

**Paid conversion rate = paid converted users / total users**

This is the main success metric because the company is subscription-based and the campaign is designed to convert users into paying customers. Landing page visits, trial starts, onboarding completion, and engagement are important, but they are supporting metrics because they only matter if they eventually improve paid conversion and business growth.

Optimizing paid conversion blindly could be dangerous if the campaign attracts low-quality users, increases refunds, increases support burden, or reduces revenue per converted user.

## KPI Tree Explanation

The KPI tree breaks the North Star metric into the following drivers:

1. Landing page reach and message fit.
2. Trial activation.
3. Onboarding completion.
4. Revenue quality.

Each driver is supported by sub-drivers such as landing page visit rate, trial start rate, onboarding completion rate, time to convert, engagement score, ARPU, revenue per converted user, and refund risk.

Guardrail metrics include refund rate, support ticket rate, days to convert, engagement score, and segment-level decline.

## Experiment Result Summary

| Metric | Control | Treatment | Difference |
|---|---:|---:|---:|
| Landing page visit rate | 63.62% | 72.39% | 8.77% |
| Trial start rate | 25.07% | 29.01% | 3.94% |
| Onboarding completion rate | 15.65% | 21.13% | 5.47% |
| Paid conversion rate | 3.19% | 7.04% | 3.85% |
| Average revenue per user | $51.97 | $54.25 | $2.28 |

## Hypothesis Test Interpretation

The hypothesis test supports the conclusion that Treatment improved paid conversion. Since the p-value of **0.000549** is below **0.05**, the improvement is statistically meaningful.

This means the campaign is likely better than the existing onboarding experience at converting users to paid subscriptions.

## Guardrail Analysis

| Guardrail | Control | Treatment | Risk |
|---|---:|---:|---|
| Refund rate | 0.00% | 0.42% | Small refund risk appeared in Treatment |
| Support ticket rate | 14.78% | 24.79% | High operational risk |
| Average days to convert | 8.86 | 6.40 | Positive; Treatment converts faster |
| Engagement score | 57.03 | 62.94 | Positive; Treatment users are more engaged |
| Revenue per converted user | $1630.10 | $770.41 | Revenue quality risk |

The biggest issue is support burden. A campaign that improves conversion but creates many more support tickets can still hurt customer experience and internal operations.

## Segment-Level Insight

Segment analysis shows that the treatment performs especially well directionally for:

- **Free plan users**, where conversion lift and ARPU lift are strong.
- **Referral traffic**, where conversion lift and ARPU lift are also strong.
- **Mobile users**, where paid conversion improves clearly.

These segment results should be treated as directional because the main hypothesis test was performed at the overall experiment level, not separately for every segment.

## Risks and Limitations

- Segment-level results may have smaller sample sizes and should not be overinterpreted.
- Revenue outliers were retained because they represent real revenue behavior, but they can influence ARPU.
- Support ticket increase may indicate onboarding confusion.
- Refunds appeared in Treatment, although the absolute refund rate is small.
- The experiment measures 30-day outcomes only and may not fully capture long-term retention or lifetime value.

## Next Steps

1. Roll out the treatment first to selected segments such as Free plan users and Referral traffic.
2. Add clearer onboarding help, FAQs, tooltips, and support deflection before expanding.
3. Monitor support tickets, refunds, and revenue per converted user daily during rollout.
4. Run a follow-up test focused on revenue quality and support burden.
5. Move to full launch only if guardrails remain stable.

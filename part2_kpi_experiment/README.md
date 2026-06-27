# Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

## Business Context

This project analyzes an onboarding and activation campaign for a subscription-based digital product company. Users were split into two experiment groups:

- **Control:** Existing onboarding experience.
- **Treatment:** New campaign experience.

Leadership needs to decide whether the Treatment should be launched to all users, rejected, continued for testing, or launched only to selected segments.

## Business Problem Statement

The business decision is whether the new onboarding and activation campaign should be rolled out beyond the experiment.

This decision impacts new users, product teams, marketing teams, customer support teams, and revenue teams. The main metric that should improve is paid conversion rate. However, the business must also monitor risks such as refunds, support tickets, slower conversion, lower engagement, weak revenue quality, and segment-level decline.

The evidence required before making a recommendation includes:

- Control vs Treatment performance on the North Star metric.
- Statistical test result for the primary metric.
- Guardrail metric analysis.
- Segment-level analysis.
- Clear business interpretation of risks and limitations.

## Dataset Description

The dataset is stored in:

`data/campaign_experiment_data.xlsx`

The dataset contains user-level experiment data including:

- User ID
- Signup date
- Experiment group
- Region
- Device type
- Traffic source
- Plan type
- Landing page visit flag
- Trial start flag
- Onboarding completion flag
- Paid conversion flag
- 30-day revenue
- Support tickets
- Refund requests
- Days to convert
- Engagement score

## North Star Metric Selected

The selected North Star metric is:

**Paid conversion rate**

Formula:

`paid converted users / total users`

This metric was selected because the business is subscription-based and the campaign is intended to convert users into paying customers.

Other metrics such as landing page visit rate, trial start rate, onboarding completion rate, engagement score, and revenue are supporting metrics. They help explain why conversion changes, but they do not replace the main business outcome.

## KPI Tree Summary

The KPI tree is saved as:

`outputs/kpi_tree.png`

It breaks paid conversion rate into the following primary KPI drivers:

1. Landing page reach and message fit.
2. Trial activation.
3. Onboarding completion.
4. Revenue quality.

Guardrail metrics include:

- Refund rate.
- Support ticket rate.
- Days to convert.
- Engagement score.
- Segment-level decline.

## Experiment Analysis Approach

The analysis was performed in:

`analysis/experiment_analysis.xlsx`

The following checks were completed:

| Check | Result |
|---|---:|
| Raw records | 1408 |
| Records after exact duplicate removal | 1400 |
| Exact duplicate rows removed | 8 |
| Duplicate user IDs in raw data | 8 |
| Conflicting duplicate user IDs after cleaning | 0 |
| Invalid binary values | 0 |
| Revenue outliers among converted users | 4 |
| Missing device type values | 18 |
| Missing traffic source values | 24 |
| Missing engagement score values | 14 |

Exact duplicate records were removed before analysis. Missing device type and traffic source values were filled as `Unknown` for segmentation. Revenue outliers were flagged and retained because they may represent genuine high-value users. Missing engagement scores were excluded from engagement average calculations rather than imputed.

## Experiment Summary

The experiment summary is stored in:

`outputs/experiment_summary.xlsx`

| Metric | Control | Treatment |
|---|---:|---:|
| User count | 690 | 710 |
| Landing page visit rate | 63.62% | 72.39% |
| Trial start rate | 25.07% | 29.01% |
| Onboarding completion rate | 15.65% | 21.13% |
| Paid conversion rate | 3.19% | 7.04% |
| Average revenue per user | $51.97 | $54.25 |
| Average revenue per converted user | $1630.10 | $770.41 |
| Refund rate | 0.00% | 0.42% |
| Support ticket rate | 14.78% | 24.79% |
| Average engagement score | 57.03 | 62.94 |
| Average days to convert | 8.86 | 6.40 |

## Hypothesis Test Summary

The hypothesis test is documented in:

`analysis/hypothesis_test_notes.md`

A one-tailed two-proportion z-test was used to test whether Treatment improved paid conversion rate.

| Test Output | Value |
|---|---:|
| Control conversion rate | 3.19% |
| Treatment conversion rate | 7.04% |
| Absolute lift | 3.85% |
| Z-statistic | 3.2640 |
| P-value | 0.000549 |

Since the p-value is below 0.05, the null hypothesis is rejected. The Treatment group shows statistically significant improvement in paid conversion rate.

## Guardrail Metrics Considered

The following guardrail metrics were reviewed:

- Refund rate.
- Support ticket rate.
- Average days to convert.
- Average engagement score.
- Revenue per converted user.
- Segment-level performance decline.

The major guardrail issue is support ticket rate, which increased from **14.78%** to **24.79%**.

## Final Recommendation

**Launch only for selected segments through a staged rollout. Do not launch to all users yet.**

The Treatment clearly improves paid conversion, but the support ticket increase and revenue quality concerns make a full launch risky. A staged launch allows the business to capture the conversion upside while monitoring and reducing operational risks.

## Assumptions and Limitations

- Exact duplicate rows were removed before analysis.
- Missing device type and traffic source values were filled as `Unknown`.
- Revenue outliers were retained and flagged.
- Engagement averages exclude missing engagement values.
- Days to convert was calculated only for converted users.
- Segment-level findings are directional and should be validated with further testing.

## Screenshots Included

The following screenshots are included:

- `screenshots/summary_metrics.png`
- `screenshots/hypothesis_test_output.png`
- `screenshots/kpi_tree_preview.png`

## Repository Structure

```text
part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
├── outputs/
│   ├── kpi_tree.png
│   ├── experiment_summary.xlsx
│   └── recommendation_memo.md
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
└── README.md
```

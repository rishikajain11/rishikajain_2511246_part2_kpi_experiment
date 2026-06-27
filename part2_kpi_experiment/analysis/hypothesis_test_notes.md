# Hypothesis Test Notes – Part 2 KPI Experiment

## Metric Being Tested

The primary metric tested is **paid conversion rate**, calculated as:

`users converted to paid / total users`

This metric is the North Star metric for the experiment because the business decision is whether the new onboarding and activation campaign should be launched to more users. A campaign that does not improve paid conversion does not justify rollout, even if it improves softer engagement metrics.

## Hypotheses

### Null Hypothesis

The treatment group does not improve paid conversion compared with the control group.

`H0: p_treatment <= p_control`

### Alternative Hypothesis

The treatment group improves paid conversion compared with the control group.

`H1: p_treatment > p_control`

## Test Type

A **one-tailed two-proportion z-test** was used.

This is one-tailed because the business question is specifically whether the treatment improves conversion, not merely whether the two groups are different in either direction.

## Significance Level

The significance level used was:

`alpha = 0.05`

## Test Inputs

| Input | Value |
|---|---:|
| Control users | 690 |
| Control paid conversions | 22 |
| Control paid conversion rate | 3.1884% |
| Treatment users | 710 |
| Treatment paid conversions | 50 |
| Treatment paid conversion rate | 7.0423% |
| Observed absolute lift | 3.8538% |
| Observed relative lift | 120.87% |

## Test Output

| Output | Value |
|---|---:|
| Pooled conversion rate | 5.1429% |
| Standard error | 0.011807 |
| Z-statistic | 3.2640 |
| P-value | 0.000549 |
| 95% confidence interval for absolute lift | 1.56% to 6.15% |

## Decision Rule

Reject the null hypothesis if:

`p-value < 0.05`

## Statistical Decision

The p-value is **0.000549**, which is below 0.05.

Therefore, the null hypothesis is rejected. The experiment provides statistical evidence that the treatment improved paid conversion rate.

## Business Interpretation

The treatment increased paid conversion from **3.19%** to **7.04%**, an absolute lift of **3.85%**.

However, this result alone is not enough to justify a full launch. Guardrail metrics must also be considered because the treatment increased support ticket rate and introduced refund requests. The correct business interpretation is that the treatment improves conversion, but the rollout should be controlled rather than launched blindly to all users.

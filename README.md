# Correlation & Causality: Confounders, Colliders and the Limits of Controls

## Objective

I examined why correlation alone cannot establish causation and how the choice of control variables can either remove or create bias.

## Methodology

- Simulated causal, confounded and selected datasets with similar correlations
- Represented confounders, colliders and mediators as directed graphs
- Compared regressions with and without appropriate controls
- Simulated M-bias caused by controlling for a pre-treatment collider
- Wrote `coef_on_d()` to estimate the treatment coefficient with different control sets
- Compared LaLonde’s randomized job-training estimate with a CPS comparison group
- Measured how much of the observational gap was closed by covariate adjustment

## Key Findings

The three simulated datasets had correlations of **0.654, 0.664 and 0.632**, even though their true causal effects were **2.0, 0.0 and 0.0**.

Controlling for a confounder recovered the correct effect, but controlling for a collider produced an estimate of **−0.592** when the truth was zero. In the M-bias simulation, controlling for a pre-treatment collider produced an estimate of **−0.191**. Adding one of the hidden causes reduced the estimate to **0.006**, close to the truth.

The randomized LaLonde experiment estimated an effect of **$1,794**. Using the CPS comparison group produced a naive estimate of **−$8,498**. Covariate adjustment moved the estimate to **$699**, closing **89%** of the gap without fully recovering the experimental result.

The lab showed that controls should be chosen according to a causal structure, not simply because they were measured before treatment.

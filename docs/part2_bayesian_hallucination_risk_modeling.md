# Supporting Study: Text-Only Risk Calibration

**Status:** Supporting protocol scaffold; not the next thesis-core study

This page preserves a useful text-only calibration exercise from the earlier
Part II plan. It may be used to test feature interfaces, noisy-label models,
proper scoring, and selective prediction at small scale. It must not delay the
first thesis study on controlled image--text conflict.

## Supporting Question

Can raw text-output uncertainty and evidence signals be converted into a
calibrated probability of a frozen, claim-level error?

The central distinction is that a raw uncertainty signal is not a calibrated
outcome risk.

## Candidate Model

For a frozen binary outcome \(H_i\) and observed features \(z_i\):

    H_i ~ Bernoulli(r_i)
    logit(r_i) = alpha + z_i^T w

Candidate features include token likelihood, semantic variation across sampled
answers, retrieval support, verifier evidence, claim count, and contradiction
scores. Their dependence and label noise must not be ignored.

## Evaluation

- binary NLL and Brier score;
- calibration intercept, slope, and reliability curves;
- AUROC and AUPRC with prevalence;
- risk--coverage and fixed-coverage risk;
- repeated or paired uncertainty intervals;
- sensitivity to label and verifier noise.

## Boundary

This exercise cannot establish:

- source-specific cross-modal uncertainty;
- medical validity;
- that Bayesian calibration is superior to matched alternatives;
- decision value without an explicit action and cost.

Any implementation requires its own bounded protocol. The active thesis order
is defined in the [roadmap](roadmap.md), and thesis risk evaluation is governed
by the [evaluation protocol](thesis/evaluation_protocol.md).

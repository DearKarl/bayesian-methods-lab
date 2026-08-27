# Evaluation Protocol

**Status:** Protocol scaffold; primary estimand awaits task and supervisor gates

## Evaluation Principle

Point performance, uncertainty quality, probabilistic calibration, robustness,
and decision utility are different outcomes. Improvement in one does not imply
improvement in the others.

## Evaluation Sequence

1. Validate the measurement construct.
2. Test incremental prediction of a frozen task-relevant error.
3. Assess calibration in-domain and under pre-specified shifts.
4. Evaluate selective decisions under fixed coverage, review budget, or cost.
5. Consider clinician-in-the-loop evaluation only after computational evidence
   passes the earlier gates.

## Candidate Risk Model

For a pre-specified binary failure outcome \(H_i\), a transparent starting
model is

```math
H_i \sim \operatorname{Bernoulli}(r_i),
```

```math
\operatorname{logit}(r_i)
= \alpha
+ \beta_v U_{v,i}
+ \beta_t U_{t,i}
+ \beta_c C_{vt,i}
+ \beta_e U_{\mathrm{epi},i}
+ \beta_o U_{\mathrm{out},i}
+ b_{\mathrm{model}[i]}
+ b_{\mathrm{site}[i]}
+ b_{\mathrm{subgroup}[i]}.
```

This is a candidate analysis object, not a commitment to Bayesian logistic
regression. The contribution of conflict is assessed by held-out prediction
and calibrated decision value, not only by an in-sample coefficient.

## Required Comparisons

- task score or deterministic similarity alone;
- model-reported or sequence confidence;
- image-only and text-only uncertainty;
- output semantic uncertainty where applicable;
- a matched deterministic failure predictor;
- probabilistic embeddings;
- ensemble or approximate-epistemic baselines;
- post-hoc calibration and, where appropriate, conformal or risk-controlling
  selection.

Comparisons should share backbone, data, preprocessing, prompts, and output
format where feasible. Any mismatch is a limitation, not a harmless detail.

## Metric Families

| Property | Required evidence |
| --- | --- |
| Task performance | Task-appropriate accuracy or loss with uncertainty intervals |
| Probabilistic quality | NLL or another proper score; Brier score for binary risk |
| Calibration | Intercept, slope, reliability curves, and subgroup calibration; ECE only as secondary evidence |
| Ranking | AUROC and AUPRC with class prevalence reported |
| Selective prediction | Risk--coverage curve, area under the curve, risk at fixed coverage, and coverage at fixed risk |
| Decision value | Expected utility or regret under frozen action costs and review budgets |
| Robustness | Paired changes across pre-specified shifts and subgroups |

## Statistical Design

- split by patient or the highest leakage-relevant entity;
- keep development, calibration, and final evaluation roles distinct;
- use repeated seeds or splits for stochastic comparisons;
- use paired bootstrap intervals or an appropriate hierarchical analysis;
- pre-specify the primary outcome and smallest effect of interest;
- report effect sizes and intervals, not only significance tests;
- correct or organize multiplicity for confirmatory secondary outcomes;
- run sensitivity analyses for labels, priors, calibration sets, and thresholds;
- publish negative and subgroup results.

## Decision Evaluation

Candidate actions are

```text
answer | clarify | retrieve | verify | regenerate | abstain | human_review
```

A simple decision rule is

```math
d_i^* = \arg\min_{d\in\mathcal A}
\mathbb E[L(d,H_i)\mid\text{available evidence}].
```

Action costs and information available at decision time must be frozen before
threshold optimization. Policies should be compared at equal answer coverage,
equal review budget, or under the same loss table. A human-review action must
not assume perfect, immediate, or cost-free review.

## Promotion Gates

- **To calibration:** measurement construct passes its protocol.
- **To decision study:** held-out risk adds non-negligible information and has
  acceptable calibration for the tested population.
- **To clinician study:** computational findings replicate; the interface,
  human-factors outcomes, governance, and ethics plan are approved.
- **To clinical claim:** requires separate evidence beyond retrospective model
  evaluation.

If a generic deterministic predictor subsumes the conflict component, report
that result and narrow the research claim. Do not expand the endpoint or choose a
favourable subgroup after the confirmatory analysis.

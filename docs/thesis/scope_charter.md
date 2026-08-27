# PhD Scope Charter

**Status:** Canonical research boundary

**Decision:** DR-0001

**Last reviewed:** 2026-08-27

## Primary Outcome

The programme aims to develop and validate a decomposition of cross-modal
semantic uncertainty that supports calibrated and decision-relevant risk
estimation. The core scientific claim must concern measurable information
added by cross-modal conflict after accounting for ambiguity within each
modality and other uncertainty sources.

The programme does not assume that probabilistic embeddings, Bayesian
inference, or any particular divergence will succeed. Those are candidate
methods to be compared under matched conditions.

## Canonical Research Object

For image input \(x_v\), text input \(x_t\), model parameters \(\theta\), and
task outcome \(y\), the initial decomposition is

```math
U_v = U(x_v), \qquad
U_t = U(x_t), \qquad
C_{vt} = C(x_v,x_t), \qquad
U_{\mathrm{epi}} = U(\theta\mid\mathcal D), \qquad
U_{\mathrm{out}} = U(\hat y).
```

- \(U_v\): ambiguity or information loss attributable to the image;
- \(U_t\): ambiguity or information loss attributable to the text;
- \(C_{vt}\): conditional incompatibility between the two modalities;
- \(U_{\mathrm{epi}}\): uncertainty associated with model knowledge or
  parameters;
- \(U_{\mathrm{out}}\): uncertainty expressed across output meanings.

These are desired operational distinctions, not quantities already known to
be identifiable.

## Domain Position

Medical image--text systems are the primary validation domain because
overconfident errors and inappropriate reliance can be consequential. The
first computational task should be smaller and more controlled than autonomous
diagnosis or open-ended clinical deployment.

The mathematical method remains domain-general until the supervisors approve
the medical task, dataset, access conditions, and clinical evaluation plan.

## In Scope

- paired image--text representation and prediction;
- controlled ambiguity, contradiction, missing-modality, corruption, and
  distribution-shift interventions;
- probabilistic embeddings and matched deterministic baselines;
- ensembles, Bayesian last layers, Laplace approximations, and other defensible
  epistemic-uncertainty baselines;
- output semantic uncertainty as a comparison rather than a substitute for
  input conflict;
- calibration, proper scoring, overconfident error, risk--coverage, and
  decision utility;
- patient-separated retrospective evaluation when approved data are used;
- clarification, verification, abstention, and human review as downstream
  actions.

## Out of Scope Without a New Decision Record

- autonomous clinical diagnosis, treatment, or deployment;
- claims of clinical benefit from retrospective benchmarks;
- collection of new patient data;
- a thesis whose main contribution is generic RAG, generic hallucination
  detection, or multi-agent orchestration;
- treating agent agreement as independent evidence without testing shared
  error sources;
- selecting a method merely because it is labelled Bayesian;
- large-model training before the measurement and data protocols are frozen.

## Outcome Hierarchy

| Gate | Primary outcome | Promotion requirement |
| --- | --- | --- |
| Measurement | Construct validity of \(C_{vt}\) under controlled interventions | Conflict responds to compatibility manipulations and is not explained by \(U_v\) or \(U_t\) alone |
| Incremental validity | Held-out change in a pre-specified proper score after adding \(C_{vt}\) | Paired effect estimate with uncertainty and robustness checks |
| Calibration | Risk calibration under in-domain and shifted conditions | NLL/Brier plus calibration intercept, slope, curves, and subgroup evidence |
| Decision value | Selective risk or utility at fixed coverage/review budget | Improvement over pre-specified confidence and uncertainty baselines |

The exact primary metric and smallest effect of interest must be frozen in the
evaluation protocol before confirmatory experiments.

## Evidence Required for a Thesis Claim

- frozen task, prediction unit, outcome label, and intervention taxonomy;
- dataset version, provenance, exclusions, leakage controls, and split logic;
- matched backbones, data, prompts, and output formats where comparisons allow;
- repeated seeds or splits and paired uncertainty intervals;
- proper scoring and calibration, not accuracy alone;
- null, negative, and subgroup results;
- code revision, environment, model and data versions, and saved artifacts;
- a statement of what the experiment cannot establish.

## Authority and Irreversible Boundaries

Supervisor confirmation is required before fixing the clinical task, claiming
access to restricted data, initiating clinician studies, or changing the
approved research area. Ethics, information-governance, licensing, compute,
and clinical-collaboration requirements are gates, not implementation details.

No personal correspondence, visa material, patient data, access credentials,
or identifiable information belongs in this repository.

## Stop Conditions

Pause or revise the route if:

- the intervention does not isolate its intended uncertainty source;
- a proposed conflict score is dominated by trivial modality or scale effects;
- the score adds no meaningful held-out information beyond matched baselines;
- calibration fails materially under the pre-specified shifts;
- data access or governance assumptions are not satisfied;
- a downstream decision study would require unsupported clinical claims.

A null result narrows the claim; it does not justify changing endpoints or
expanding scope after seeing the data.

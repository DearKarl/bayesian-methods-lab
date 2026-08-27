# Research Roadmap

**Status:** Canonical execution order
**Scope authority:** [research scope charter](research/scope_charter.md)

This roadmap is organized by evidence gates rather than by method names. A
later study does not begin merely because an earlier implementation is
complete; it begins only when the required scientific evidence exists.

## Gate 0: Freeze the Research Contract

**Outcome:** A supervisor-ready protocol with no unresolved ambiguity about
what is being measured.

Required decisions:

1. first task and prediction unit;
2. primary medical domain and dataset candidate;
3. operational definitions of image ambiguity, text ambiguity, cross-modal
   conflict, epistemic uncertainty, and output uncertainty;
4. controlled intervention design and negative controls;
5. primary estimand, smallest effect of interest, and matched baselines;
6. data access, governance, compute, and clinical-expertise constraints.

**Promotion evidence:** Approved scope, measurement protocol, evaluation
protocol, and dataset decision record.

**Stop condition:** Do not implement core models while the task or
measurement object remains unfrozen.

## Study 1: Controlled Conflict Identifiability

**Primary question:** Can cross-modal conflict be distinguished from ambiguity
within either modality?

Planned work:

1. construct held-fixed matched and contradictory pairs;
2. add separate ambiguity, missingness, corruption, and shift conditions;
3. run deterministic compatibility and unimodal uncertainty baselines;
4. evaluate candidate conflict measurements with paired contrasts and negative
   controls;
5. audit failure cases and intervention artifacts.

**Promotion evidence:** The candidate conflict measurement responds to
compatibility manipulations, is not driven by trivial quality or scale effects,
and is not fully explained by unimodal uncertainty.

**Stop condition:** If the construct is not identifiable, revise or abandon the
measurement before risk modelling.

## Study 2: Probabilistic Representation and Decomposition

**Primary question:** Which representation estimates the intended components
most reliably under matched conditions?

Planned comparisons:

- deterministic point embeddings;
- a matched deterministic failure predictor;
- probabilistic image--text embeddings;
- ensembles or parameter-efficient ensembles;
- Bayesian last-layer or Laplace-style approximations;
- output semantic uncertainty where generation is required.

**Promotion evidence:** Reproducible construct validity under the frozen
protocol, including stability across seeds, normalization choices, and a
pre-specified shift.

**Stop condition:** Distributional representation alone is not a promotion
criterion. Stop if variance or distance has no defensible source
interpretation.

## Study 3: Calibration and Incremental Validity

**Primary question:** Does the identified conflict component improve held-out
prediction and calibration of a task-relevant error?

Planned work:

1. freeze the error outcome and annotation protocol;
2. compare risk models with and without the conflict component;
3. report NLL, Brier score, calibration intercept and slope, reliability
   curves, AUROC, AUPRC, and risk--coverage;
4. use patient-level partitions, repeated seeds, and paired uncertainty
   intervals;
5. test subgroup and shift calibration.

**Promotion evidence:** Non-negligible held-out incremental value relative to
pre-specified baselines, with adequate calibration for the tested population.

**Stop condition:** If generic confidence or a matched deterministic predictor
subsumes conflict, report the null result and narrow the research claim.

## Study 4: Selective and Human-Review Decisions

**Primary question:** Does calibrated decomposed risk improve action selection
at a fixed coverage, review budget, or cost?

Planned actions:

```text
answer | clarify | retrieve | verify | regenerate | abstain | human_review
```

**Promotion evidence:** Lower selective risk or higher expected utility under
the same pre-specified constraints than confidence-only and output-uncertainty
policies.

**Stop condition:** Do not proceed to human evaluation if the computational
signal is unstable, poorly calibrated, or dependent on information unavailable
at decision time.

## Later Clinical Interpretation Gate

A clinician-in-the-loop study is a separate governed project. It should measure
review decisions, time, accuracy, appropriate reliance, and inappropriate
reliance. It must not be described as prospective clinical benefit or
deployment evidence.

## Supporting Evidence, Not Sequential Prerequisites

### Completed foundation

- Part I Boston Housing Bayesian regression benchmark;
- probabilistic scoring and posterior prediction;
- MCMC diagnostics and repeated-split comparisons.

This evidence establishes methodological discipline but is not medical or
multimodal evidence.

### Reproduction layer

- Part 0 Route 1 LM-Polygraph mechanism-level pilot: completed;
- remaining text, calibration, RAG, multimodal, and agentic routes: protocol
  scaffolds unless their pages state otherwise.

Text-only hallucination modelling may be used as a small calibration exercise.
It is not the next research stage and must not delay Study 1.

## Current Repository Stop Point

The documentation transition is authorized. New core research code, data access,
model training, and experiment execution are not authorized until Gate 0 is
closed through supervisor decisions and a bounded implementation brief.

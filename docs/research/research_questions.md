# Research Questions and Falsifiable Hypotheses

**Status:** Canonical hypothesis set; exact estimands remain protocol gates

## RQ1: Identifiability

Can modality-specific ambiguity and conditional cross-modal conflict be
separately identified under controlled interventions?

**H1.** A valid conflict measurement changes when semantic compatibility is
manipulated while one modality is held fixed, and the change is not fully
explained by either unimodal uncertainty measurement.

**Falsifier.** The apparent signal is equally sensitive to unimodal corruption,
latent dimension, embedding norm, or irrelevant modality differences.

## RQ2: Incremental Validity

Does cross-modal conflict improve prediction of a pre-specified meaningful
error beyond standard confidence, unimodal uncertainty, output semantic
uncertainty, and a matched deterministic failure predictor?

**H2.** Adding the conflict component improves a frozen held-out proper score
by more than the smallest effect of interest and improves risk ranking under
paired uncertainty analysis.

**Falsifier.** The effect disappears under matched controls, patient-level
splits, repeated seeds, or an appropriate deterministic baseline.

## RQ3: Robustness and Calibration

Does the decomposition remain probabilistically meaningful across model,
pathology, prevalence, modality degradation, and distribution shifts?

**H3.** A decomposed and recalibrated risk model retains better calibration or
degrades less than an undifferentiated confidence baseline under pre-specified
shifts.

**Falsifier.** Improvements occur only in the development distribution or in
aggregate while clinically relevant subgroups become materially worse.

## RQ4: Selective Decision Value

Can calibrated risk reduce consequential overconfident errors at a fixed
answer coverage or human-review budget?

**H4.** A policy using decomposed risk achieves lower selective risk or higher
expected utility than policies based on model confidence and output uncertainty
alone.

**Falsifier.** Any apparent benefit depends on post-hoc threshold choice,
unrealistic action costs, or access to information unavailable at decision
time.

## Claim Ladder

The permitted claim grows only with the evidence:

1. **Association:** the measurement correlates with an outcome.
2. **Construct validity:** controlled interventions support the intended
   interpretation.
3. **Incremental validity:** the measurement adds held-out information beyond
   pre-specified baselines.
4. **Calibration:** estimated risks have probabilistic meaning in the tested
   populations.
5. **Decision value:** a pre-specified policy improves a decision outcome.
6. **Clinical value:** requires a separate, appropriately governed clinical
   evaluation and cannot be inferred from the earlier steps.

No study may skip a rung by changing terminology. In particular,
distributional embeddings do not establish uncertainty decomposition, and a
better AUROC does not establish calibration or clinical usefulness.

## Supporting Questions

The following questions are useful but are not independent programme axes:

- Which probabilistic representation is computationally tractable and stable?
- Which uncertainty components can be estimated without full model retraining?
- How sensitive are conclusions to distance, covariance parameterization, and
  calibration method?
- When is clarification, retrieval, verification, another model, or human
  review worth its cost?
- Which failure modes remain after a policy rejects high-risk cases?

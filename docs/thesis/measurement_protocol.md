# Measurement Protocol

**Status:** Protocol design; no thesis-core measurement has been validated

## Objective

The first thesis study will test whether cross-modal conflict can be measured
as a distinct construct rather than as a mixture of unimodal ambiguity,
information loss, representation scale, model uncertainty, and output
variation.

The protocol must be frozen before thesis-core implementation begins.

## Decisions Required Before Implementation

- task and prediction unit;
- dataset, version, access route, and permitted use;
- patient or entity split unit;
- frozen backbone and model-size boundary;
- propositions or labels whose compatibility can be manipulated;
- operational definitions of image ambiguity, text ambiguity, and conflict;
- primary conflict estimand and smallest effect of interest;
- deterministic and uncertainty-aware baselines;
- compute budget and stopping rule.

## Controlled Intervention Design

The minimum design should contain paired or factorial conditions that vary one
intended source while holding others as stable as possible.

| Condition | Intended manipulation | Required negative control |
| --- | --- | --- |
| Matched clear pair | Neither ambiguity nor conflict | Equivalent pair construction without semantic change |
| Image ambiguity | Degrade or make visual evidence multiply interpretable | Text and compatibility remain fixed |
| Text ambiguity | Make wording underspecified or multiply interpretable | Image and compatibility remain fixed |
| Cross-modal conflict | Change a task-relevant proposition in one modality | Perceptual and linguistic quality remain matched |
| Missing modality | Remove one evidence source | Distinguish absence from contradiction |
| Corruption | Reduce signal quality without introducing a contrary proposition | Compare with ambiguity and missingness |
| Distribution shift | Change a pre-specified population or acquisition factor | Preserve the outcome definition |

An intervention that simultaneously changes clarity, label prevalence, text
length, image quality, and semantic compatibility cannot identify conflict
without additional controls.

## Candidate Representations

At minimum, compare:

1. deterministic point embeddings and similarity;
2. a matched learned deterministic failure predictor;
3. probabilistic image--text embeddings with explicit covariance or scale;
4. an ensemble or parameter-efficient ensemble;
5. a defensible approximate-epistemic method such as a Bayesian last layer or
   Laplace approximation;
6. output semantic uncertainty when generation is part of the task.

The same frozen backbone, data partitions, preprocessing, and task outputs
should be used wherever technically possible.

## Candidate Conflict Quantities

For modality-specific distributions \(q_v\) and \(q_t\), candidates include:

- normalized symmetric KL divergence;
- Wasserstein--Bures distance;
- energy or contrastive disagreement;
- evidential conflict;
- a learned conditional compatibility likelihood ratio.

Raw latent distance is not the preferred scientific object because legitimate
modality-specific content can produce separation. The target is conflict
relative to the distribution of compatible pairs under the frozen task.

Covariance parameterization, regularization, positive-definiteness, latent
dimension, scale, and normalization must be documented. A scalar divergence
must not be combined with a covariance matrix without a dimensionally valid
definition.

## Construct-Validity Tests

- held-fixed paired contrasts for each intervention;
- monotonic response to pre-specified conflict severity;
- negative controls for modality quality, length, norm, and latent dimension;
- conditional models that include \(U_v\) and \(U_t\) before assessing
  \(C_{vt}\);
- recovery of known intervention labels without using those labels to define
  the evaluated score;
- replication across seeds and at least one meaningful shift;
- inspection of failure cases where compatible pairs receive high conflict or
  contradictions receive low conflict.

## Measurement Promotion Gate

A candidate may advance to outcome-risk modelling only if:

1. its direction and estimand were pre-specified;
2. it responds to compatibility interventions more than to matched negative
   controls;
3. the response is not fully explained by unimodal ambiguity measurements;
4. the result is stable across paired repetitions and normalization choices;
5. uncertainty intervals and null results are reported;
6. the implementation and artifacts are reproducible.

Failure at this gate stops promotion. It does not authorize selecting a new
metric after inspecting the confirmatory outcomes.

## Required Artifacts

- frozen protocol and decision record;
- dataset card and intervention manifest;
- configuration and environment lock;
- pair-level intervention metadata without restricted raw data;
- raw measurement outputs where governance permits;
- paired summaries and uncertainty intervals;
- failure-case audit;
- explicit deviations from the protocol.

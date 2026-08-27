# Bayesian Methods Lab

## Decomposable Cross-Modal Semantic Uncertainty for Reliable Decisions

This repository is the working record for a research programme on
cross-modal semantic uncertainty. The central problem is to determine whether
uncertainty caused by genuine disagreement between image and text can be
distinguished from ambiguity within either modality, uncertainty about model
parameters, and uncertainty expressed in a generated output.

The intended contribution is not a new confidence score in isolation. It is a
validated decomposition that can be connected to calibrated error risk and to
decisions such as answering, requesting clarification, retrieving more
evidence, abstaining, or requesting human review.

Medical image--text systems are the primary validation domain. The methods
remain general until the task, dataset, and clinical scope are confirmed with
the supervisors. Nothing in this repository is a clinical decision system or
evidence of clinical benefit.

```text
controlled image--text interventions
        -> identifiable uncertainty components
        -> calibrated outcome risk
        -> selective and human-review decisions
```

## Canonical Research Questions

1. Can within-image ambiguity, within-text ambiguity, cross-modal conflict,
   epistemic uncertainty, and output uncertainty be operationally separated?
2. Does an explicit conflict component add held-out predictive information
   beyond unimodal uncertainty, model confidence, and output semantic
   uncertainty?
3. Does the decomposition remain calibrated under clinically relevant shifts?
4. Can calibrated risk reduce consequential overconfident errors at a fixed
   answer coverage or human-review budget?

The hypotheses, null interpretations, and claim boundaries are maintained in
the [canonical research questions](docs/research/research_questions.md).

## Research Workstreams

| Workstream | Purpose | Current status |
| --- | --- | --- |
| [Study 1: Conflict identifiability](docs/research/measurement_protocol.md) | Test whether controlled interventions isolate cross-modal conflict from unimodal ambiguity | Protocol design; no result |
| [Study 2: Uncertainty decomposition](docs/research/measurement_protocol.md) | Compare deterministic, probabilistic-embedding, ensemble, and approximate-Bayesian representations | Planned |
| [Study 3: Calibration and incremental value](docs/research/evaluation_protocol.md) | Test whether conflict improves proper scores, calibration, and risk ranking on held-out data | Planned |
| [Study 4: Selective decisions](docs/research/evaluation_protocol.md) | Compare answer, clarify, verify, abstain, and human-review policies under explicit costs | Planned |

The studies are gates, not a promise that one proposed method will succeed.
Study 2 cannot be promoted because it uses distributions over embeddings;
promotion depends on measurement validity and matched comparisons. Study 4
does not begin until the risk signal is sufficiently stable and calibrated.

## Canonical Documents

- [Scope charter](docs/research/scope_charter.md)
- [Problem and outcome taxonomy](docs/research/problem_taxonomy.md)
- [Research questions and hypotheses](docs/research/research_questions.md)
- [Literature matrix](docs/research/literature_matrix.md)
- [Measurement protocol](docs/research/measurement_protocol.md)
- [Evaluation protocol](docs/research/evaluation_protocol.md)
- [Data governance](docs/research/data_governance.md)
- [Decision log](docs/research/decision_log.md)
- [Roadmap and promotion gates](docs/roadmap.md)

These documents are authoritative for future work. Older Part II--IV
pages are retained only as supporting design history and point back to the
canonical protocols.

## Preserved Evidence

### Bayesian predictive foundation

The existing Boston Housing benchmark is preserved as a completed
methodological foundation under [Part I](docs/part1_bayesian_regression_foundations.md).
It demonstrates posterior prediction, diagnostics, proper scoring, and repeated
comparison. It is not medical evidence. Across the saved repeated splits, the
custom Gibbs model does not show a stable RMSE advantage over the baselines.

The implementation remains under `src/bayeslinreg/`; saved tables remain in
`reports/tables/`, and saved figures remain in `reports/figures/`.

### Reproduction and evidence map

[Part 0](part0_reproductions/README.md) records literature reproductions and
supporting pilots. Its completed Route 1 pilot runs three official
LM-Polygraph estimators on a small prompt stress test. It is a mechanism-level
pilot, not a core result and not a full benchmark reproduction.

Routes on text uncertainty, Bayesian risk, calibration, retrieval, multimodal
risk, and agentic systems remain supporting evidence. They enter the core
programme only when they test a pre-specified cross-modal hypothesis.

## Evidence Status Vocabulary

Every research claim should use one of these labels:

- **literature lead**: relevant work that still requires bibliographic audit;
- **protocol**: a pre-specified design with no result;
- **mechanism-level pilot**: a small diagnostic run that does not establish a
  benchmark claim;
- **completed experiment**: a documented run with saved outputs;
- **promoted research evidence**: a completed experiment that passes its
  pre-specified validity, robustness, and reporting gates.

Planned work must never be described as implemented, and a raw uncertainty
score must never be described as a calibrated probability without validation.

## Repository Map

```text
docs/research/               canonical research scope and protocols
part0_reproductions/         supporting literature and reproduction evidence
docs/part1_*.md              preserved Bayesian predictive foundation
experiments/                 existing reproducible benchmark runners
experiments/research_core/   reserved gated research experiment structure
src/bayeslinreg/             preserved Part I package
tests/                       existing package tests
reports/tables/              generated tables
reports/figures/             generated figures
```

Future core research code will be added only after the corresponding protocol
is frozen. It will not be forced into the historically named `bayeslinreg`
package.

## Reproduce Preserved Studies

### Part I

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python experiments/run_boston_benchmark.py
python experiments/run_repeated_split_comparison.py
pytest -q
```

### Part 0, Route 1

Use the isolated environment in the
[route environment record](part0_reproductions/01_uncertainty_signals/ENVIRONMENT.md),
then run:

```bash
python part0_reproductions/01_uncertainty_signals/experiments/run_lm_polygraph_signal_pilot.py
```

Do not regenerate saved outputs merely to update documentation. If an
experiment is rerun, record the exact command, environment, data and model
versions, and every numerical change.

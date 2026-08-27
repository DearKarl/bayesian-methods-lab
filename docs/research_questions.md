# Research Questions

The authoritative research questions, hypotheses, falsifiers, and claim ladder are
maintained in
[research/research_questions.md](research/research_questions.md).

The canonical sequence is:

1. identify cross-modal conflict separately from ambiguity within image and
   text;
2. compare deterministic, probabilistic, ensemble, and approximate-Bayesian
   representations under matched conditions;
3. test incremental validity and calibration of the identified component;
4. evaluate selective and human-review decisions under explicit constraints.

## Preserved Foundation Question

Part I asks what posterior prediction adds beyond point estimation in a
controlled regression benchmark. Its answer is methodological: posterior
samples, predictive distributions, intervals, diagnostics, and proper scoring
provide objects that RMSE alone does not. The saved repeated-split results do
not establish general RMSE superiority for the Gibbs model.

## Supporting Evidence Questions

Part 0 asks which published uncertainty methods can be reproduced, which
quantities they measure, and whether their outputs are calibrated risks or raw
signals. Text-only hallucination, retrieval, and agentic questions remain
supporting routes unless a protocol connects them to a canonical cross-modal
hypothesis.

See the [scope charter](research/scope_charter.md), [problem
taxonomy](research/problem_taxonomy.md), and [roadmap](roadmap.md) before adding a
new research question or implementation.

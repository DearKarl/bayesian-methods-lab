# Decision Log

This file records scope-changing decisions. Evidence and reasoning should be
linked rather than copied into each entry.

## DR-0001: Canonical Research Direction

- **Date:** 2026-08-27
- **Status:** Approved by the researcher
- **Decision:** The research programme will study decomposable cross-modal semantic
  uncertainty for reliable decisions. Medical image--text systems are the
  primary validation domain, while the method remains theoretically general
  until the supervisors formally narrow the scope.
- **First scientific gate:** Controlled identifiability of cross-modal conflict
  relative to within-modality ambiguity.
- **Downstream gates:** Incremental validity, calibration under shift, and
  selective decision value.
- **Rejected ordering:** A long text-only hallucination programme before the
  multimodal core programme.
- **Boundary:** Existing Bayesian regression and LM uncertainty evidence is
  preserved but is not promoted as medical or core evidence.

## DR-0002: Repository Transition Boundary

- **Date:** 2026-08-27
- **Status:** Approved for implementation
- **Decision:** Replace the active research narrative and roadmap with the
  canonical research structure.
- **Preserve:** `src/bayeslinreg/`, the Gibbs sampler, tests, experiment runners,
  saved tables, saved figures, and numeric results.
- **Do not authorize:** New model implementation, experiment reruns, dataset
  download, external deployment, or clinical claims.
- **Promotion evidence:** Consistent canonical documents, valid internal links,
  passing repository tests, and a reviewed diff with no evidence artifacts
  changed.

## Open Supervisor Gates

The following are deliberately undecided:

- first medical task and prediction unit;
- primary dataset and approved access route;
- acceptable controlled or synthetic contradiction procedures;
- available compute and model-size boundary;
- access to clinical expertise and annotation support;
- timing and governance of any clinician-in-the-loop study;
- smallest effect of interest and final confirmatory primary metric.

These items must not be silently resolved by implementation convenience.

## DR-0003: Guarded Automatic GitHub Synchronization

- **Date:** 2026-08-27
- **Status:** Approved by the researcher
- **Decision:** After an authorized repository change passes its required
  checks, automatically stage the bounded files, create a descriptive commit,
  and push the current branch to its configured GitHub upstream unless the
  researcher explicitly opts out.
- **Hard boundaries:** No force-push, history rewrite, branch-protection bypass,
  suspected secret or restricted-data commit, or inclusion of unrelated user
  changes.
- **Stop conditions:** Failed checks, merge conflicts, missing or unexpected
  upstream, remote divergence, suspected sensitive content, or an inseparable
  dirty worktree.

## DR-0004: Research-Repository Identity

- **Date:** 2026-08-27
- **Status:** Approved by the researcher
- **Decision:** Present the project as a general research repository without
  degree-programme identity labels in current files, paths, headings, status
  labels, or roadmap language.
- **Preserve:** The canonical scope, hypotheses, evidence gates, experiments,
  code, saved results, and medical image--text validation direction.
- **Path convention:** Canonical documents live under `docs/research/`, and
  gated core experiments live under `experiments/research_core/`.

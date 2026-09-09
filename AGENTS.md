# Agent Guidelines

This repository is the working record for a research programme on
**decomposable cross-modal semantic uncertainty for reliable decisions**.
Medical image--text systems are the primary validation domain. The canonical
scope, terminology, hypotheses, and evidence gates are under `docs/research/`.

## Scope Rules

- Treat controlled identification of cross-modal conflict relative to image
  ambiguity and text ambiguity as the first core study.
- Treat probabilistic embeddings, Bayesian inference, ensembles, semantic
  entropy, and conformal methods as candidates to compare, not predetermined
  winners.
- Do not use *cross-modal conflict*, *hallucination*, *calibration failure*, and
  *overconfident error* as synonyms.
- Keep text-only hallucination, RAG, generic agentic, and multi-agent studies as
  supporting work unless a bounded brief connects them directly to a canonical
  research hypothesis.
- Do not begin core implementation until the task, dataset, intervention
  taxonomy, primary outcome, baselines, promotion criteria, and stopping rules
  are frozen.
- Do not claim clinical value, autonomous diagnostic capability, or deployment
  readiness from retrospective benchmark evidence.

## Preserved Evidence Rules

- Treat the Boston Housing benchmark as **Part I: Bayesian Predictive
  Foundations** and never as medical evidence.
- Preserve the existing benchmark, generated result tables, figures, and
  numeric results unless a task explicitly asks to rerun or revise them.
- Do not claim that Bayesian methods improve RMSE over OLS unless repeated-split
  or otherwise statistically meaningful evidence supports it.
- Keep the custom Gibbs sampler and the Python package name `bayeslinreg` unless
  a task explicitly authorizes a change.
- Treat the completed LM-Polygraph prompt study as a mechanism-level pilot, not
  a full benchmark reproduction or core result.
- Keep generated tables in `reports/tables/` and generated figures in
  `reports/figures/`.

## Development Rules

- Use documentation-first, PR-sized changes and preserve working reproduction
  instructions in `README.md`.
- Future core research code should receive a package name only after its
  protocol and interface are frozen; do not force it into `bayeslinreg`.
- Run `pytest -q` before publishing changes.
- Do not regenerate benchmark outputs merely for documentation changes.
- If outputs are regenerated, report the exact command, environment, and every
  numerical change.
- Keep all claims aligned with saved artifacts and label planned, pilot,
  completed, and promoted evidence explicitly.

## GitHub Synchronization Rule

- After an authorized repository change is complete and its required checks
  pass, stage the bounded change set, create a descriptive commit, and push the
  current branch to its configured GitHub upstream automatically unless the
  user explicitly opts out.
- Before pushing, verify the remote, branch, upstream, staged files, and that
  the remote branch has not diverged from the expected base.
- Never force-push, rewrite published history, bypass branch protection, commit
  suspected credentials or restricted data, or include unrelated user changes.
- Stop and report instead of syncing when checks fail, merge conflicts exist,
  the upstream is missing or unexpected, the remote has diverged, or the
  bounded change set cannot be separated safely.

## Research Standards

- Separate task performance, uncertainty quality, calibration, robustness, and
  decision utility.
- Pre-specify the prediction unit, estimand, smallest effect of interest,
  baselines, shifts, and stop conditions before confirmatory experiments.
- Use patient-level or the highest leakage-relevant split for medical data.
- Prefer proper scores, calibration diagnostics, paired uncertainty intervals,
  repeated evaluation, subgroup results, and falsifiable language.
- Treat raw uncertainty scores, verifier outputs, labels, and agent agreement as
  potentially noisy or correlated evidence.
- Record negative results and narrow the claim when a deterministic or simpler
  baseline subsumes the proposed conflict component.

## Governance Rules

- Do not commit restricted medical data, credentials, identifiers, personal
  correspondence, visa material, or protected information.
- Dataset access, synthetic clinical conflict, clinician studies, and changes
  to the approved research area require their respective governance or
  supervisor gates.
- Stop before destructive, external, costly, irreversible, or scope-expanding
  actions unless they are explicitly authorized in a bounded brief.

## Role routing contract (legacy mapping)

- See [CODEX_ROLE_HARNESS.md](./CODEX_ROLE_HARNESS.md) for the shared four-role
  routing contract and display titles.
- Legacy role references map to role keys:
  - Strategic adviser → `advisor` (Advisor (GPT-6 Astra / Ultra))
  - Intake/state/dispatch coordinator → `adjutant` (Adjutant (GPT-6 Astra / Medium))
  - Technical design lead → `engineer` (Engineer (GPT-6 Astra / XHigh))
  - Implementation executor → `executor` (Executor (GPT-5.3 Codex-Spark / XHigh))

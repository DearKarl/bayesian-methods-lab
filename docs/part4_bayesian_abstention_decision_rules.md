# Study 4 Design Record: Selective and Human-Review Decisions

**Status:** Downstream protocol scaffold; blocked on measurement and calibration
gates

This study asks how a validated and calibrated risk estimate should change an
action. It does not begin with a threshold chosen from the test results.

## Candidate Actions

    answer | clarify | retrieve | verify | regenerate | abstain | human_review

For action \(d\), failure state \(H\), and loss \(L\), a candidate decision rule
minimizes posterior expected loss over the available actions.

A conservative rule may use a calibrated upper risk bound, but it must be
compared with posterior-mean, confidence-only, output-uncertainty, and simple
coverage-based baselines.

## Required Outcomes

- selective risk and answer coverage;
- area under the risk--coverage curve;
- risk at fixed coverage and coverage at fixed risk;
- expected utility or regret under a frozen loss table;
- clarification, verification, abstention, and review rates;
- subgroup and shift results;
- sensitivity to imperfect, delayed, or costly human review.

## Promotion Boundary

This study is authorized only after:

1. the source-specific measurement passes construct-validity checks;
2. the outcome risk adds held-out information beyond matched baselines;
3. calibration is adequate for the tested population;
4. actions, information availability, costs, and review budget are frozen.

Improved retrospective selective risk is not evidence of clinical benefit. A
clinician-in-the-loop study requires separate ethics, governance, interface,
and human-factors protocols.

See the canonical [evaluation protocol](research/evaluation_protocol.md) and
[roadmap](roadmap.md).

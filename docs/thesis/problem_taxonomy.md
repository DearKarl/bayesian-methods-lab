# Problem and Outcome Taxonomy

**Status:** Canonical terminology protocol

The programme separates statistical objects that are often compressed into a
single word such as *uncertainty* or *hallucination*. Each experiment must name
the object it manipulates, measures, predicts, or uses for a decision.

## Input and Representation Objects

| Term | Operational meaning | Not sufficient evidence of |
| --- | --- | --- |
| Image ambiguity | More than one clinically or semantically plausible interpretation of the visual evidence | Cross-modal conflict or epistemic uncertainty |
| Text ambiguity | More than one plausible interpretation of the textual evidence | Cross-modal conflict or model ignorance |
| Information loss | Evidence is missing, corrupted, occluded, truncated, or otherwise unavailable | Genuine contradiction |
| Cross-modal conflict | Image and text provide conditionally incompatible evidence about a task-relevant proposition | Output hallucination by itself |
| Modality gap | A systematic difference between representation spaces or model behaviour across modalities | Semantic contradiction in an individual pair |
| Epistemic uncertainty | Uncertainty attributable to limited knowledge about the model or parameters | Input ambiguity when estimated only by a data-dependent variance head |
| Output semantic uncertainty | Variation in meaning across plausible generated outputs | The source of that variation |

## Outcome Objects

| Term | Operational meaning |
| --- | --- |
| Task error | The output is wrong under the frozen task definition |
| Unsupported claim | A generated claim is not supported by the available evidence |
| Contradictory claim | A generated claim conflicts with the available evidence |
| Hallucination | A specific unsupported, contradictory, or fabricated output under a stated annotation protocol |
| Calibration failure | Predicted probabilities do not match observed frequencies under the evaluation design |
| Overconfident error | An incorrect output receives confidence above a pre-specified threshold |
| Selective risk | Residual error among cases on which the system chooses to answer |

Cross-modal conflict is an input relationship. Hallucination is an output
failure. Either may occur without the other. The thesis must not use the terms
as synonyms.

## Decision Objects

Candidate actions are

```text
answer | clarify | retrieve | verify | regenerate | abstain | human_review
```

An action is justified by expected loss or a pre-specified risk-control rule,
not by the magnitude of a raw uncertainty score alone. Review budget, delay,
false reassurance, unnecessary escalation, and missed harmful errors should be
represented explicitly when the study reaches the decision stage.

## Required Labels in Research Records

Every result should state:

1. the prediction unit: pair, patient, question, claim, report, or trajectory;
2. the manipulated condition: ambiguity, conflict, information loss, shift, or
   another pre-specified factor;
3. the measured signal and its units or normalization;
4. the outcome label and annotation source;
5. the decision, if any, made from the signal;
6. whether the evidence is a pilot, completed experiment, or promoted thesis
   result.

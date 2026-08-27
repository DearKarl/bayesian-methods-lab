# Supporting Design Record: Multimodal Failure Risk

**Status:** Earlier design scaffold; superseded as the thesis entry point

The previous Part III plan compressed perceptual failure, cross-modal conflict,
and output hallucination into a single multimodal risk stage. The canonical PhD
programme now separates those objects.

    input ambiguity and conflict
        -> validated uncertainty components
        -> task-relevant output or claim error
        -> calibrated risk
        -> action

## Typed Outcomes

Typed multimodal failures remain useful outcomes:

- unsupported object or attribute;
- incorrect relation or count;
- OCR or document-reading failure;
- reasoning failure;
- omitted evidence;
- claim contradicting the image, text, or their joint semantics.

They are outcome labels, not interchangeable uncertainty sources.

## Permitted Use of This Scaffold

This page may inform a later hierarchical outcome model across models, datasets,
sites, or error types. Such a model becomes thesis work only after the
[measurement protocol](thesis/measurement_protocol.md) has identified the
input-side constructs and the [evaluation protocol](thesis/evaluation_protocol.md)
has frozen the outcome and comparison.

## Minimum Comparisons

- deterministic task confidence;
- image-only and text-only uncertainty;
- generic multimodal failure prediction;
- identified conflict measurement;
- output semantic uncertainty where generation is used;
- matched calibrated and uncalibrated risk models.

## Boundary

Starting from a generic multimodal hallucination benchmark is not sufficient to
establish ambiguity-versus-conflict decomposition. Benchmark labels, visual
grounding signals, and model-based judges may be noisy. Results must remain
dataset- and task-bounded.

The canonical first study is
[controlled conflict identifiability](thesis/measurement_protocol.md), not this
historical Part III sequence.

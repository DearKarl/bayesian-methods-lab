# Data Governance and Dataset Protocol

**Status:** Governance scaffold; no core dataset is approved by this file

## Current Position

Medical image--text data are the intended primary validation domain. MIMIC-CXR
is a direct candidate for paired radiographs and reports, while linked clinical
context may require additional resources. Candidate status does not imply
access, approval, suitability, or permission to redistribute data.

No patient-level or restricted medical data may be committed to this
repository.

## Dataset Decision Record

Before download, preprocessing, or model training, freeze:

- canonical dataset name, version, release date, and access date;
- licence, data-use agreement, credentialing, and local storage boundary;
- task, prediction unit, inclusion and exclusion criteria;
- cohort construction and temporal alignment;
- patient-level split and duplicate controls;
- report, label, and prompt leakage checks;
- missingness and selection-bias analysis;
- subgroup definitions and minimum reporting thresholds;
- annotation provenance, reliability, and adjudication;
- retention, deletion, and artifact-sharing rules.

## Split and Leakage Rules

- Patients must not cross training, calibration, development, and final test
  partitions.
- Multiple studies, images, reports, or paraphrases from the same underlying
  event must be treated as linked observations.
- Generated counterfactuals must inherit the split of their source record.
- Label extraction methods must be fitted without final-test information.
- Thresholds and calibration parameters must not be selected on the final test
  set.
- Model pretraining overlap and benchmark contamination should be documented
  where they can be assessed.

## Controlled Conflict Governance

Synthetic or edited contradictions require:

- a taxonomy of which proposition is changed;
- preservation of clinically plausible language and visual quality;
- a record of whether the example is naturally observed, rule-generated,
  model-generated, or manually edited;
- separation of contradiction from ambiguity and corruption;
- expert review when clinical validity is claimed;
- an analysis of artifacts that make synthetic conditions trivially
  detectable.

Synthetic conflict is a measurement instrument, not evidence of real-world
prevalence.

## Repository Artifacts

Permitted artifacts may include:

- code, configurations, environment records, and hashes;
- aggregate tables and figures that satisfy the data-use agreement;
- non-identifying derived metadata where explicitly permitted;
- synthetic examples whose provenance and licence allow redistribution.

Do not commit credentials, access tokens, raw restricted records, identifying
metadata, personal correspondence, or screenshots containing protected data.

## Clinical and Human Evaluation Gate

Any clinician-in-the-loop study requires a separate protocol defining:

- research question and human-factors outcomes;
- participant population and recruitment;
- consent, ethics, compensation, and data handling;
- interface, randomization, and comparator;
- review accuracy, time, reliance, and inappropriate-reliance measures;
- adverse-event and stopping procedures.

User preference alone is not evidence that uncertainty displays improve
decisions. Retrospective benchmark performance is not prospective clinical
benefit.

## Stop Conditions

Stop before data access or experimentation if permissions are unclear, the
split cannot prevent leakage, the proposed task is not supported by the data,
or clinically meaningful labels cannot be defended. Use a non-clinical or
fully approved pilot only when its role and transfer limitations are explicit.

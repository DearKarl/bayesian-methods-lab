# Literature Matrix

**Status:** Seed evidence map; verify versions, licences, code revisions, and
study details before formal citation or reproduction

The matrix asks what each work establishes, what it does not establish, and
which thesis comparison it motivates. Inclusion is not an endorsement of a
method or a claim of reproducibility.

## Verified Primary-Source Starting Points

| Area | Primary source | Relevance | Boundary for this thesis |
| --- | --- | --- | --- |
| Output semantic uncertainty | [Farquhar et al., semantic entropy, Nature 2024](https://www.nature.com/articles/s41586-024-07421-0) | Measures variation at the level of answer meaning | Does not by itself isolate input-level image--text conflict |
| Evaluation incentives | [Kalai et al., Nature 2026](https://www.nature.com/articles/s41586-026-10549-w) | Motivates explicit error costs and abstention-aware evaluation | Does not supply a cross-modal uncertainty decomposition |
| Text uncertainty benchmark | [LM-Polygraph, TACL 2025](https://aclanthology.org/2025.tacl-1.11/) | Provides text-UQ estimators and calibration baselines | Text-output evidence is supporting, not the thesis core |
| Probabilistic image--text embeddings | [PCME, CVPR 2021](https://openaccess.thecvf.com/content/CVPR2021/html/Chun_Probabilistic_Embeddings_for_Cross-Modal_Retrieval_CVPR_2021_paper.html) | Establishes a probabilistic cross-modal representation baseline | Representation spread is not automatically an identified uncertainty source |
| Improved probabilistic embeddings | [PCME++, ICLR 2024](https://proceedings.iclr.cc/paper_files/paper/2024/hash/ad9d6ab10446114cf5482d5e1f971a84-Abstract-Conference.html) | Provides an updated probabilistic image--text comparison | Retrieval performance does not establish calibrated failure risk |
| Frozen-VLM probabilistic adapter | [ProbVLM, ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/html/Upadhyay_ProbVLM_Probabilistic_Adapter_for_Frozen_Vison-Language_Models_ICCV_2023_paper.html) | Motivates tractable distributional adapters | Must be compared with matched deterministic and other uncertainty baselines |
| Cross-modal inconsistency | [van Sprang et al., CVPR 2026](https://openaccess.thecvf.com/content/CVPR2026/html/van_Sprang_Same_Content_Different_Answers_Cross-Modal_Inconsistency_in_MLLMs_CVPR_2026_paper.html) | Provides controlled evidence that semantically equivalent presentations can yield inconsistent MLLM answers | Behavioural inconsistency is not the same object as ambiguity-versus-conflict decomposition |
| Conflict resolution | [Tian et al., CrossCheck-Bench, AAAI 2026](https://ojs.aaai.org/index.php/AAAI/article/view/39788) | Tests contradiction detection and compositional conflict resolution | Benchmark performance does not identify the source or calibration of uncertainty |
| Generic VLM failure prediction | [ViLU, ICCV 2025](https://openaccess.thecvf.com/content/ICCV2025/html/Lafon_ViLU_Learning_Vision-Language_Uncertainties_for_Failure_Prediction_ICCV_2025_paper.html) | Supplies a learned deterministic failure-prediction baseline | The conflict component must add value beyond this class of predictor |
| Bayesian VLM approximation | [BayesVLM](https://openreview.net/forum?id=XLiUcvHfzS) | Supplies a candidate Bayesian last-layer or Laplace-style baseline | Bayesian naming does not guarantee calibration or source identifiability |
| Distribution-free selection | [Conformal prediction for zero-shot models, CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Silva-Rodriguez_Conformal_Prediction_for_Zero-Shot_Models_CVPR_2025_paper.html) | Provides a complementary path to prediction sets or risk control | Guarantees depend on assumptions such as exchangeability and the chosen calibration population |

## Medical Data and Error Resources

| Resource | Candidate role | Decision still required |
| --- | --- | --- |
| [MIMIC-CXR v2.1.0](https://physionet.org/content/mimic-cxr/2.1.0/) | Paired chest radiographs and reports | Access, cohort, task, labels, leakage controls, and governance |
| [MIMIC-IV](https://physionet.org/content/mimiciv/3.1/) | Additional linked clinical context | Whether linkage is scientifically necessary and temporally valid |
| [ReXErr](https://physionet.org/content/rexerr-v1/1.0.0/) | Radiology-report error examples | Compatibility with the chosen prediction unit and annotation protocol |

These are candidates, not approved datasets. Versioned access and a frozen
dataset protocol are required before use.

## Defensible Gap

The thesis gap is not uncertainty in vision--language models generally, nor the
use of Gaussian embeddings by itself. The testable gap is:

> Does an explicitly identified measure of image--text conflict add calibrated,
> decision-relevant information beyond image-only ambiguity, text-only
> ambiguity, model uncertainty, output semantic uncertainty, and generic
> failure prediction under controlled conflict and shift?

This gap can yield a useful null result. If a matched deterministic predictor
or output uncertainty fully subsumes the proposed conflict component, the
thesis claim should narrow accordingly.

## Bibliographic Audit Fields

Before a study is promoted from literature lead to reproduction candidate,
record:

- canonical title, authors, venue, year, DOI or stable URL;
- peer-review and publication status;
- official code location, licence, commit, and release tag;
- dataset and checkpoint versions;
- compute and dependency requirements;
- exact claim selected for reproduction;
- permitted comparison and known deviations.

Emerging medical multimodal resources mentioned in discussion should remain
literature leads until their review status, licence, annotation validity, and
reproducibility have been audited.

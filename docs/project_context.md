# Project Context

## Identity

- Project: Radar / ISAR Classification Pipeline
- Owner: Sadik Enes Erisen
- Maturity: Planned Portfolio MVP
- Intended stack: Python, NumPy, pandas, OpenCV or scikit-image, scikit-learn, optional PyTorch, Matplotlib, pytest, GitHub Actions
- Repository visibility: Public

## Purpose

Create a reproducible radar/ISAR signal- and image-processing portfolio project that validates inputs, documents preprocessing, establishes transparent baselines, evaluates classification and calibration, and makes data and uncertainty limitations explicit.

The first MVP should be usable with a synthetic fallback dataset so software quality can be demonstrated without relying on restricted, proprietary, or unavailable radar data.

## Planned system boundaries

```text
Authorised dataset or synthetic fallback
                |
                v
Validation + sample identity + split manifest
                |
                v
Reproducible preprocessing
                |
          +-----+-----+
          |           |
  Classical baseline  Optional neural baseline
          |           |
          +-----+-----+
                |
     Evaluation, calibration, uncertainty, reports
```

## Milestone order

### M0 — Dataset and experiment specification

- choose an authorised dataset or define the synthetic fallback;
- record licence, citation, redistribution, sample identity, classes, groups, and split unit;
- define preprocessing, metrics, calibration, seeds, and acceptance criteria.

### M1 — Data foundation

- typed dataset adapter;
- schema and range validation;
- stable class mapping;
- sample IDs and split manifest;
- deterministic synthetic fallback;
- duplicate and leakage checks.

### M2 — Transparent baseline

- documented preprocessing;
- simple feature or image representation;
- classical baseline such as logistic regression, SVM, or random forest selected by evidence;
- reproducible metrics and confusion matrix.

### M3 — Evaluation and uncertainty

- per-class and macro metrics;
- calibration curve and calibration error;
- confidence and error analysis;
- repeated seeds or cross-validation where methodologically appropriate;
- reproducible reports and saved configuration.

### M4 — Optional neural baseline

- PyTorch model only after M1–M3 are stable;
- training/validation checkpoint selection without test leakage;
- saved model card, seed, environment, and comparison against the classical baseline.

## Core invariants

1. Dataset use is authorised and documented.
2. Sample identity and the independent split unit remain explicit.
3. Duplicates, augmentations, correlated sessions, and derived samples cannot cross splits unnoticed.
4. Test data is not used for fitting, tuning, calibration, or checkpoint selection.
5. Synthetic and real-data results remain separate.
6. Class mapping and preprocessing are deterministic and versioned.
7. Reported metrics identify dataset, split, seed, configuration, and variability.
8. Uncertainty scores are not presented as guaranteed correctness.

## Non-goals for the first MVP

- operational target identification;
- defence, surveillance, targeting, or safety-critical deployment;
- claims of field radar performance;
- restricted or proprietary data redistribution;
- large neural architectures before a trustworthy baseline;
- real-time embedded inference;
- cloud MLOps infrastructure;
- claiming uncertainty estimates are fully calibrated outside tested data.

## Definition of done for the first MVP

- [ ] Dataset card, licence, citation, sample identity, and split unit are documented.
- [ ] Synthetic fallback can run the complete software pipeline.
- [ ] Split manifest and leakage checks are reproducible.
- [ ] Preprocessing is deterministic and fitted only on allowed data.
- [ ] A classical baseline produces reproducible per-class and macro metrics.
- [ ] Confusion matrix, calibration, error analysis, and limitations are reported.
- [ ] Tests cover validation, splits, preprocessing, metrics, and configuration replay.
- [ ] CI passes on the documented environment.
- [ ] No unsupported operational or real-world claim is present.
- [ ] Enes can explain the data, representation, baseline, leakage controls, metrics, and uncertainty limitations.

# Radar / ISAR Classification Pipeline

This repository defines a future radar and inverse synthetic-aperture radar classification study. It is currently a specification: no dataset adapter, preprocessing pipeline, trained classifier or measured result has been implemented.

The planned work focuses on reproducible signal/image-processing experiments rather than a single headline accuracy number.

## Research question

How do transparent classical features and an optional neural baseline compare when radar or ISAR representations are processed through the same leakage-safe dataset and evaluation pipeline?

## First executable release

The first milestone should deliver:

- a documented dataset interface and licence/provenance record;
- a deterministic synthetic fallback dataset for tests and examples;
- validation of image shape, labels, metadata and finite values;
- normalization, cropping and denoising with visible before/after artifacts;
- subject- or acquisition-aware train/validation/test splits where metadata permits;
- one classical feature baseline;
- confusion matrix, per-class precision/recall/F1 and calibration output;
- repeatable configuration, tests and CI.

A neural model belongs after the data contract and classical baseline are stable.

## Planned data flow

```text
radar / ISAR source + provenance
              |
              v
       validation and split
              |
              v
     preprocessing pipeline
              |
       +------+------+
       |             |
classical features   optional neural input
       |             |
       +------+------+
              |
              v
 evaluation, calibration and error review
```

## Intended technology

| Purpose | Planned tools |
| --- | --- |
| Data and numerics | Python, NumPy, pandas |
| Image processing | OpenCV or scikit-image |
| Classical baseline | scikit-learn |
| Optional neural baseline | PyTorch |
| Reporting | Matplotlib, JSON and CSV artifacts |
| Quality checks | pytest, Ruff and GitHub Actions |

The final choices will be recorded when the first dataset is selected. Listing a library here does not mean it is already used.

## Milestones

1. Select a legally usable dataset and freeze the metadata contract.
2. Build the adapter, validation layer and synthetic CI fixtures.
3. Implement preprocessing with deterministic artifact checks.
4. Establish a classical baseline and leakage-safe evaluation.
5. Add calibration, uncertainty and difficult-example analysis.
6. Add an optional neural baseline only when it answers a clear comparison question.
7. Publish a reproducible experiment and a limitations section tied to the selected data.

## Important scope distinction

ISAR image classification is not the same task as automotive radar point-cloud processing or camera–LiDAR–radar fusion. Automotive multimodal sensor work is developed separately in [Autonomous Sensor Fusion Lab](https://github.com/seneserisen/autonomous-sensor-fusion-lab).

## Current status

Specification and milestone planning only. [Issue #1](https://github.com/seneserisen/radar-isar-classification-pipeline/issues/1) defines the dataset-adapter and classical-baseline milestone.

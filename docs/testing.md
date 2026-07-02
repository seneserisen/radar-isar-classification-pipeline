# Testing and Verification

## Current state

The repository is currently specification-first. No executable Python package, dataset adapter, model, test suite, or CI baseline is documented yet.

Until those files exist:

- do not report installation, preprocessing, training, evaluation, coverage, or GPU checks as passed;
- documentation review is not model verification;
- first implementation work must add exact reproducible commands and CI.

## Proposed commands after the Python scaffold

The first scaffold should support commands equivalent to:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
ruff check .
ruff format --check .
pytest
```

Exact Python versions, dependencies, configuration, and platform limitations must be recorded when implemented.

## Required data tests

- schema, dtype, shape, label, and range validation;
- stable sample IDs and class mapping;
- missing, corrupt, empty, and unsupported inputs;
- complex-valued representation handling where applicable;
- deterministic synthetic fallback generation;
- duplicate and near-duplicate detection;
- split-manifest reproducibility;
- no group, object, session, source file, temporal neighbour, or augmented derivative crosses splits when prohibited;
- dataset licence and citation metadata present.

## Required preprocessing tests

- deterministic output for fixed configuration;
- expected shape, dtype, finite values, and dynamic range;
- normalisation fitted only on training data;
- denoising, cropping, resizing, and augmentation boundaries;
- no label-dependent preprocessing leakage;
- transform configuration saved and replayable;
- synthetic analytical patterns with independently predictable output where practical.

## Required model and evaluation tests

- baseline can overfit a tiny controlled dataset as a pipeline sanity check without using that result as performance evidence;
- metric functions match hand-calculated confusion matrices;
- class ordering remains stable;
- per-class, macro, and weighted metrics are labelled correctly;
- test set is not used for tuning, calibration fitting, early stopping, or checkpoint selection;
- model and preprocessing serialization reproduce predictions;
- repeated run with identical seed and environment reproduces results within documented tolerance;
- multiple seeds or cross-validation results are reported when required;
- calibration metrics and curves use a methodologically valid split;
- uncertainty and confidence outputs handle invalid or out-of-distribution examples without guaranteed claims.

## Experiment record

Every reported run should record:

- code commit;
- dataset version and licence;
- split manifest hash or identifier;
- Python and dependency versions;
- hardware where performance is reported;
- preprocessing configuration;
- model and hyperparameters;
- random seeds;
- training and selection procedure;
- final metrics and artifacts;
- known limitations.

## CI acceptance for initial implementation

- clean package installation;
- Ruff and tests pass;
- synthetic fallback completes end to end;
- split-integrity tests pass;
- classical baseline produces deterministic artifacts;
- metric reference tests pass;
- no real dataset is required for public CI unless licence permits it;
- optional neural tests remain small and deterministic or are separated from core CI.

## Baseline status

All executable checks are currently **Not implemented**, not passed.

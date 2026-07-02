# Project Status

- Last updated: 2 July 2026
- Maturity: Planned Portfolio MVP
- Default branch: `main`

## Current repository state

The repository currently contains a project concept and high-level architecture. It does not yet contain a documented dataset adapter, authorised dataset card, synthetic fallback generator, preprocessing package, classifier, test suite, experiment configuration, or CI implementation.

## Implemented

- high-level goals;
- planned architecture;
- intended technology and evidence;
- specification-first governance and verification requirements on the `chore/ai-project-governance` branch.

## Not yet implemented

- dataset licence and data card;
- sample identity and split manifest;
- synthetic fallback dataset;
- validation and preprocessing pipeline;
- classical baseline;
- optional neural baseline;
- evaluation, calibration, and uncertainty reports;
- package, tests, experiment runner, and CI.

## Highest-priority next tasks

1. Select an authorised dataset or formally define the synthetic fallback and its limitations.
2. Define the independent split unit and leakage risks before loading data.
3. Create the dataset card, licence record, class mapping, sample-ID schema, and split-manifest format.
4. Build a minimal deterministic Python package with validation and synthetic fallback tests.
5. Implement one transparent classical baseline and hand-verified metric functions before PyTorch.

## Primary risks

- using a dataset without clear licence, citation, or redistribution rights;
- splitting correlated images rather than independent objects or acquisition sessions;
- duplicate, augmented, or temporally adjacent samples leaking across splits;
- fitting normalisation or calibration on held-out data;
- selecting models or checkpoints using the final test set;
- reporting only the best seed;
- claiming operational radar, defence, or real-world performance from a synthetic or small dataset;
- introducing a neural model before the data and evaluation foundation is trustworthy.

## Verification status

| Area | Status |
|---|---|
| Dataset authorisation | Not selected or documented |
| Synthetic fallback | Not implemented |
| Split manifest | Not implemented |
| Preprocessing | Not implemented |
| Classical baseline | Not implemented |
| Neural baseline | Not implemented |
| Metrics and calibration | Not implemented |
| Tests and CI | Not implemented |
| External or operational validation | Not performed |

## Status language

Until code and experiments exist, describe features as **planned**. Until authorised real data and valid held-out evaluation exist, do not report real-data classification performance. Synthetic results must remain visibly synthetic.

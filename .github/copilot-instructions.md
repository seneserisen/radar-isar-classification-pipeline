# Radar / ISAR Classification Pipeline — Copilot Instructions

- Treat the repository as planned and specification-first, not as an implemented or validated classifier.
- Read `AGENTS.md`, `docs/project_context.md`, `docs/testing.md`, and `docs/project_status.md` before substantial work.
- Verify dataset licence, access, citation, redistribution, and split unit before using data.
- Preserve sample IDs and explicit split manifests.
- Prevent duplicate, near-duplicate, augmented, session-correlated, or temporally adjacent samples from crossing splits.
- Fit preprocessing, feature selection, calibration, and tuning only on permitted data.
- Keep synthetic fallback data and real-data results separate.
- Establish transparent classical baselines before optional neural models.
- Report class counts, per-class metrics, macro metrics, confusion matrices, calibration, uncertainty limitations, seeds, and run variability.
- Do not use the final test set for model or checkpoint selection.
- Do not invent datasets, citations, model weights, accuracy, training runs, or operational radar claims.
- Add deterministic tests for validation, preprocessing, split integrity, metrics, serialization, and configuration replay.
- Report planned, implemented, trained, evaluated, and externally validated status separately.

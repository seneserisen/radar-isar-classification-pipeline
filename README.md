# Radar / ISAR Classification Pipeline

A planned reproducible signal- and image-processing project for preprocessing radar or ISAR representations, training transparent baselines, and evaluating classification performance and uncertainty.

## Project goals

- Provide a documented dataset adapter with a synthetic fallback dataset
- Implement normalisation, denoising, cropping, and augmentation steps
- Establish classical and neural-network classification baselines
- Report confusion matrices, per-class metrics, calibration, and uncertainty
- Prevent data leakage with explicit train, validation, and test splits
- Package tests and repeatable experiment configurations

## Planned architecture

```text
Radar / ISAR data
        |
        v
Validation and preprocessing
        |
        v
Feature or image representation
      /   \
Classical  Neural baseline
      \   /
Evaluation, calibration, and reports
```

## Planned technology

- Python
- NumPy and pandas
- OpenCV or scikit-image
- scikit-learn
- PyTorch for the optional neural baseline
- Matplotlib
- pytest and GitHub Actions

## Intended evidence

The finished repository will demonstrate reproducible experimentation, signal/image preprocessing, model evaluation, uncertainty awareness, software testing, and clear technical communication.

## Status

Project specification and milestone planning are in progress. Implementation will begin after the industrial, embedded, and ROS 2 portfolio projects have stable foundations.

## Author

Sadik Enes Erisen — M.Sc. Autonomy Technologies, FAU Erlangen-Nürnberg; B.Sc. Electrical and Electronics Engineering.

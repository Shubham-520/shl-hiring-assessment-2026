# SHL Hiring Assessment 2026

## Overview

This repository contains my solution for the SHL Hiring Assessment 2026 Kaggle challenge.

The task is a speech-based Grammar Scoring Engine, where the goal is to predict a grammar score from audio recordings.

## Approach

The solution uses handcrafted audio features extracted from the speech recordings using Librosa.

### Feature Engineering

The final model uses enhanced acoustic features including:

- RMS energy statistics
- Zero-crossing rate
- Spectral centroid
- Spectral bandwidth
- Spectral rolloff
- Spectral contrast
- MFCC features
- Pitch statistics

Additional fluency-related features were also evaluated, including:

- Active speech ratio
- Silence ratio
- Energy variation
- Spectral flatness
- Spectral flux

The enhanced acoustic feature model performed best on the Kaggle public leaderboard.

## Model

The final selected model is an ExtraTrees Regressor with:

- 400 trees
- `max_features=0.8`
- `min_samples_leaf=2`
- `random_state=42`

## Results

| Model | Kaggle Public RMSE |
|---|---:|
| Baseline acoustic features | 0.7560 |
| Enhanced acoustic features | **0.7265** |
| Acoustic + fluency features | 0.7424 |

The final submission uses the enhanced acoustic feature model with a public RMSE of **0.7265**.

## Reproducibility

The solution was developed in a Kaggle Notebook using Python, Librosa, NumPy, Pandas and Scikit-learn.

The competition dataset is private and is therefore not included in this repository.

## Files

- `README.md` — Project documentation
- `notebook.ipynb` — Solution notebook
- `requirements.txt` — Python dependencies
- `submission_enhanced.csv` — Final Kaggle submission

## Note

The audio dataset is not included because it is provided through the private Kaggle competition environment.

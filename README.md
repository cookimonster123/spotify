# Predicting Song Popularity with Spotify Data

## Overview
This project investigates whether a song’s popularity can be predicted using Spotify audio features and artist-level metadata. The focus is on building a regression model, establishing strong baselines, and evaluating generalization performance using proper train, validation, and test splits.

---

## Data
Two datasets were used:
- **Tracks dataset**: audio features (e.g. danceability, energy, valence) and track popularity
- **Artists dataset**: artist-level popularity scores

Tracks with multiple artists were handled by exploding artist IDs and aggregating artist popularity back to the track level.

---

## Preprocessing & Feature Engineering
- Removed rows with missing values
- Dropped non-predictive identifier and text columns
- Parsed multi-artist tracks
- Added a new feature: **median artist popularity per track**
- Ensured one row per track with numeric features only

---

## Modeling Approach
- **Baseline**: predict mean popularity from the training set
- **Model**: Linear Regression
- **Split**: 70% train, 15% validation, 15% test
- Feature scaling applied for coefficient interpretability

---

## Evaluation
Models were evaluated using:
- R² (coefficient of determination)
- RMSE (root mean squared error)

Results:
- Baseline R² ≈ 0
- Linear regression achieved **R² ≈ 0.45 on the test set**
- RMSE ≈ 13.5 popularity points

Adding artist popularity significantly improved performance over audio features alone.

---

## Key Findings
- Artist popularity is a strong predictor of track popularity
- Danceability and energy show positive associations with popularity
- Audio features alone are insufficient to fully explain popularity

---

## Limitations & Future Work
- Popularity depends on factors not captured in the dataset (marketing, exposure)
- Nonlinear models (e.g. tree-based methods) may improve performance
- Additional features such as genre could provide further gains

---

## Tech Stack
Python, pandas, NumPy, scikit-learn
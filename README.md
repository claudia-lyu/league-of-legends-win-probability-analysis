# League of Legends Win Probability Prediction

Predicting match outcomes from early-game signals using logistic regression, cross-validation, and bootstrap uncertainty.

## About
We analyze ~9,000 ranked League of Legends matches to quantify how early metrics (kills, deaths, gold/experience diff) shape the probability of winning.  
Originally implemented in R; this repository includes a Python re-implementation for reproducibility and alignment with my current toolset.

## Tech Stack
- **Language:** Python 3.10+
- **Libraries:** pandas, numpy, scikit-learn, statsmodels, matplotlib
- **Data Source:** [Kaggle – League of Legends Diamond Ranked Games (10 min)](https://www.kaggle.com/datasets/bobbyscience/league-of-legends-diamond-ranked-games-10-min)

## Methods
- Data cleaning + feature engineering for early-game KPIs:
  - `blueGoldDiff`, `blueExperienceDiff`, `blueKills`, `blueDeaths` (and optional interactions)
- **Logistic regression** with 5-fold cross-validation (accuracy, ROC-AUC)
- **Bootstrap (1,000 resamples)** to quantify uncertainty in coefficients and model performance

## Key Findings
- Positive predictors of winning: **kills**, **gold diff**, **experience diff**
- Negative predictor: **deaths**
- Model reached **~0.72 accuracy (± CI)** with good calibration—useful for early strategic decisions.

## Repository Structure

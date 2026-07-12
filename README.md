# FIFA-World-Cup-2026-Prediction-Model 🏆

A machine learning project that predicts **Win / Draw / Loss** outcomes for FIFA World Cup matches. The models were trained on 96 years of FIFA World Cup history (1930–2022) and evaluated using the ongoing 2026 FIFA World Cup.

This project demonstrates an end-to-end machine learning pipeline, including data collection, preprocessing, feature engineering, model comparison, evaluation, and tournament simulation.

---

## Project Overview

This project combines historical FIFA World Cup data with real 2026 tournament data to predict football match outcomes using machine learning.

The main objectives were:

- Build a leakage-safe machine learning pipeline
- Compare multiple classification algorithms
- Predict match outcomes (Win / Draw / Loss)
- Simulate the remaining tournament to estimate each team's probability of winning the World Cup

---

## Features

- Combined historical FIFA World Cup matches (1930–2022) with real 2026 tournament data
- Integrated datasets collected from multiple public sources
- Cleaned, standardized, and validated data before training
- Engineered leakage-safe features including:
  - Recent team form
  - Head-to-head record
  - FIFA ranking difference
  - Host advantage
  - Knockout stage indicator
- Used `.shift()` to ensure rolling and expanding statistics never use future information
- Trained and compared four machine learning models:
  - Decision Tree
  - Random Forest
  - Logistic Regression (with standardized features)
  - XGBoost
- Used chronological train/test splitting suitable for time-series sports data
- Extended the model into a tournament bracket simulation to estimate each team's probability of winning the tournament

---

## Results (as of the 2026 Semifinals)

### Best Model

🏆 **XGBoost** achieved the best performance based on **Weighted F1-score**.

### Key Results

- FIFA ranking difference was consistently the most predictive feature.
- Correctly predicted the winners of the final three quarterfinal matches before kickoff:

  - ✅ Spain
  - ✅ England
  - ✅ Argentina

### Predicted 2026 World Cup Champion Probabilities

| Team | Probability |
|------|------------:|
| 🇫🇷 France | **59.3%** |
| 🇦🇷 Argentina | **23.1%** |
| 🇪🇸 Spain | **12.5%** |
| 🏴 England | **5%** |

---

## Machine Learning Models

The project trained and compared four supervised learning models:

| Model | Description |
|------|-------------|
| Decision Tree | Simple and interpretable baseline model |
| Random Forest | Ensemble of decision trees for improved robustness |
| Logistic Regression | Linear baseline model using standardized features |
| XGBoost | Gradient-boosted tree model with strong performance on tabular data |

---

## Dataset Sources

The dataset was created by combining information from multiple public sources.

Data used includes:

- FIFA World Cup historical match results (1930–2022)
- FIFA World Cup 2026 match data
- FIFA ranking history
- Team and tournament information
- EA Sports FC player ratings

Since no single dataset contained all required features, multiple CSV files were collected, cleaned, merged, and validated before being used for machine learning.

---
## Contributors

This project was developed collaboratively by:

- **Homaira Mohammadi**
- **Wolanga Jalalzai**

---

## Disclaimer

This project was built for educational and research purposes and mostly build for fun to explore how machine learning works in real world.


The predictions are probabilistic estimates and should **not** be interpreted as guarantees or used as betting advice.
---

## Project Showcase 📸

You can view screenshots, results, and project updates shared on LinkedIn by the contributors:

- **Homaira Mohammadi**: https://www.linkedin.com/in/homairamohammadi/
- **Wolanga Jalalzai**: https://www.linkedin.com/in/wolanga-jalalzai-24a1a1217?utm_source=share_via&utm_content=profile&utm_medium=member_ios
- 
The LinkedIn posts showcase the model predictions, tournament simulation results, and highlights from the development process.
-----

## Running the Project

### 1. Clone the repository

```bash
git clone <https://github.com/homaira-mohammadi/FIFA-World-Cup-2026-Prediction-Model.git>

---


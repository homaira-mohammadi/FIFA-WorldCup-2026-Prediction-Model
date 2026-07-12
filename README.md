# FIFA-WorldCup-2026-Prediction-Model
Here is only the **README.md** content (without extra explanation):

````markdown
# FIFA World Cup 2026 Match Outcome Predictor 🏆

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
| 🇫🇷 France | **59%** |
| 🇦🇷 Argentina | **23%** |
| 🇪🇸 Spain | **13%** |
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

## Project Structure

```
02_worldcup_2026_final_model.ipynb   # Main notebook

data/
├── raw/
│   ├── historical/                  # FIFA World Cup matches (1930–2022)
│   ├── 2026_data/
│   │   ├── fifa_overall/            # 2026 tournament data
│   │   └── updated/                 # Additional 2026 results for validation
│   └── enrichment/                  # FIFA rankings and player rating data
```

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

## Running the Project

### 1. Clone the repository

```bash
git clone <repository-url>
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib scikit-learn xgboost
```

### 3. Run the notebook

Open:

```
02_worldcup_2026_final_model.ipynb
```

and run all cells.

---

## Known Limitations

- The dataset contains approximately **1,000 FIFA World Cup matches**, which is relatively small for machine learning.
- Predicting draws remains challenging because pre-match statistics cannot capture all match-specific events, tactics, injuries, or randomness.
- Data was collected from multiple public sources rather than a single standardized dataset, requiring additional cleaning and validation.
- Some datasets had different formats and naming conventions, which required preprocessing before integration.
- The `home_team` and `away_team` labels represent data-entry order rather than true home advantage, except for host nations.
- EA Sports FC squad ratings were not used as training features because equivalent historical data is unavailable for older tournaments.

---

## Future Improvements

- Hyperparameter tuning using Grid Search or Randomized Search
- Dixon-Coles Poisson model for score prediction
- Add player-level and squad-quality features
- Build a deployable web application or prediction API
- Expand the dataset with qualifiers and international competitions

---

## Contributors

This project was developed collaboratively by:

- **Homaira Mohammadi**
- **Wolanga Jalalzai**

---

## Disclaimer

This project was built for educational and research purposes.

The predictions are machine learning estimates and should not be considered guarantees or used as betting advice.
````

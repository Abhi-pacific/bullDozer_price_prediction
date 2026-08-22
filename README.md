# 🚜 Bulldozer Price Prediction

Predicting sale prices of heavy equipment (bulldozers) at auction using **Random Forest regression** on 400,000+ records.

## 📋 Problem Statement

Auction houses and equipment buyers need accurate price predictions to:
- Set appropriate bid limits
- Value equipment for resale
- Understand market trends for different equipment categories

## 📊 Dataset

- **Source:** Blue Book for Bulldozers (Kaggle)
- **Records:** 400,000+ auction transactions
- **Features:** Equipment type, make, model, product group, size, year made, sale date, mechanism, state, seller rating, and more
- **Target:** Sale price (continuous)

## 🔧 Approach

### Feature Engineering
- Extracted **10+ datetime features** from sale dates (year, month, day of week, seasonality)
- Converted **50+ categorical fields** into numerical features using label encoding and one-hot encoding
- Created derived features from existing attributes
- Handled missing values with appropriate strategies per feature type

### Modeling
- **Algorithm:** Random Forest Regressor
- **Hyperparameter Tuning:** RandomizedSearchCV with cross-validation
- **Key hyperparameters tuned:** n_estimators, max_depth, min_samples_split, min_samples_leaf

### Evaluation
- **Metric:** RMSLE (Root Mean Squared Log Error)
- RMSLE is preferred for price prediction as it penalizes relative errors rather than absolute ones

## 📈 Key Results

- **Top predictive features:**
  - `YearMade` — equipment age is the strongest price signal
  - `ProductSize` — size category significantly affects value
  - Additional contributors: equipment type, mechanism, seller factors

- Improved RMSLE through systematic feature engineering + hyperparameter tuning

## 📁 Project Structure

```
bullDozer_price_prediction/
├── bullDozer_price_prediction_code.ipynb   # Full end-to-end notebook
└── README.md                                 # This file
```

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Core language |
| Pandas | Data loading, manipulation, feature engineering |
| NumPy | Numerical operations |
| Scikit-learn | Random Forest, RandomizedSearchCV, preprocessing, metrics |
| Matplotlib | Visualization of results and feature importance |

## 🚀 How to Run

```bash
# Clone
git clone https://github.com/Abhi-pacific/bullDozer_price_prediction.git
cd bullDozer_price_prediction

# Install dependencies
pip install pandas numpy scikit-learn matplotlib jupyter

# Run the notebook
jupyter notebook bullDozer_price_prediction_code.ipynb
```

## 💡 Key Insights

1. Equipment age (`YearMade`) is the single strongest predictor of auction price
2. Product size and category create distinct price tiers
3. Seasonal patterns in auction timing affect final prices
4. Proper feature encoding of 50+ categorical variables significantly improves model performance

## 👨‍💻 Author

**Abhishek Chauhan** — Data Analyst @ Netimpact Solutions  
[LinkedIn](https://linkedin.com/in/abhishek-chauhan-28c) | [Email](mailto:Chauhan.a.abhishek@icloud.com)

---

*Part of my machine learning portfolio. Check out my other projects on [GitHub](https://github.com/Abhi-pacific).*

# 🏡 House Prices Prediction (California Housing Dataset)

This project focuses on predicting **median house values** using the California Housing dataset.  
It demonstrates a full end-to-end **Machine Learning pipeline**, including data exploration, preprocessing, model training, hyperparameter tuning, and evaluation.

---

## 📌 Project Steps

### 1. Exploratory Data Analysis (EDA)
- Checked for missing values → none found.
- Analyzed feature distributions and identified skewness in several variables.
- Detected outliers in `MedInc`, `AveRooms`, `AveBedrms`, `Population`, and `AveOccup`.
- Explored correlations:
  - `MedInc` (median income) showed the **strongest positive correlation** with house values.
  - Most other features had weak or noisy relationships.
- Visualizations:
  - Boxplots for outlier detection.
  - Scatterplots for correlation inspection.
  - Distribution plots for skewness.

### 2. Preprocessing
- Applied **log-transformations** to skewed features (`Population`, `AveOccup`, `AveRooms`, `AveBedrms`).
- Standardized features with **StandardScaler**.
- Train-test split for robust evaluation.

### 3. Linear Models
- Implemented **Polynomial Regression with Ridge Regularization**.
- Used **GridSearchCV** to find best polynomial degree and regularization strength.
- Best result: **degree=3, alpha=1** → R² ≈ **0.73** on test data.

### 4. Non-linear Models
- **Random Forest**:
  - Served as a baseline non-linear model.
  - Provided initial feature importance ranking.
- **XGBoost**:
  - Applied **RandomizedSearchCV** for hyperparameter tuning.
  - Achieved best performance:
    - **Test R² = 0.857**
    - **Train R² = 0.94**
    - **RMSE = 0.453**
  - Outperformed both linear models and Random Forest.

---

## 📊 Results Summary

| Model                      | Test R² | Notes |
|----------------------------|---------|-------|
| Polynomial Ridge Regression | 0.73    | Best linear model (degree=3, alpha=1) |
| Random Forest               | ~0.80   | Strong baseline, provided feature importances |
| XGBoost                     | **0.857** | Best overall, after hyperparameter tuning |

---

## 🚀 Key Takeaways
- **Median Income** is the most important predictor of housing prices.
- Handling **skewness and outliers** improved model stability.
- **XGBoost significantly outperformed** both linear and Random Forest models.
- Feature importance analysis provides insights into housing market drivers.

---

## 🛠️ Tech Stack
- **Python**
- **Pandas, NumPy, Matplotlib, Seaborn** → EDA & visualization
- **Scikit-learn** → preprocessing, linear models, Grid/RandomizedSearchCV
- **XGBoost** → gradient boosting model
- **Google Colab** → development environment

---

## 📂 Repository Structure


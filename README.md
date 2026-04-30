# Capstone Assignment 20.1: Initial Report and Exploratory Data Analysis (EDA)

## Diamond Price Analysis & Prediction

**Author:** Arun Elumalai  
**Program:** UC Berkeley Professional Certificate in Machine Learning & Artificial Intelligence  
**Assignment:** Capstone 20.1 — Initial Report and Exploratory Data Analysis

---

## Executive Summary

This project analyzes diamond pricing to understand the key physical and quality factors that
determine diamond market value. Using the Diamonds dataset (53,940 records, 9 features), we
perform a comprehensive Exploratory Data Analysis (EDA) to uncover distribution patterns,
feature correlations, and the influence of grading characteristics on price.

Our analysis reveals that **carat weight** is the dominant predictor of price (r = 0.92), while
the **4Cs grading attributes** (Cut, Color, Clarity) also significantly influence value —
sometimes counter-intuitively when carat weight is not controlled for. A baseline **Linear
Regression** model on log-transformed data achieves an R² of ~0.92, establishing a strong
foundation for advanced modeling in subsequent capstone stages.

---

## Rationale

The global diamond market is valued at over $80 billion annually, with pricing driven by a
complex interaction of physical attributes and quality grades assessed by gemological experts.
Accurately predicting diamond prices has significant value for:

- **Consumers**: Making informed purchasing decisions and negotiating fair prices.
- **Retailers & Dealers**: Setting competitive prices and managing inventory valuation.
- **Insurance Companies**: Providing accurate replacement value estimates.
- **Investment Platforms**: Evaluating diamonds as alternative assets.

Traditional diamond pricing relies on expert appraisers who introduce subjectivity and
inconsistency. A data-driven model could provide transparent, reproducible price estimates
that democratize access to fair market valuations.

---

## Research Question

> **"What physical and quality characteristics of a diamond most strongly determine its market
> price, and can we build a machine learning model to accurately predict diamond prices from
> these attributes?"**

More specifically:

1. Which features (carat, cut, color, clarity, dimensions) most strongly correlate with price?
2. How do ordinal quality grades (Cut, Color, Clarity) influence price independently of carat?
3. Are there non-linear relationships between physical dimensions and price?
4. What baseline model performance can we achieve with Linear Regression?

---

## Data Sources

| Source | Description | Size |
|--------|-------------|------|
| [Diamonds Dataset (Seaborn / ggplot2)](https://ggplot2.tidyverse.org/reference/diamonds.html) | Classic gemological dataset containing prices and quality attributes of ~54K round-cut diamonds | 53,940 rows × 10 columns |

### Feature Descriptions

| Feature | Type | Description |
|---------|------|-------------|
| `carat` | Float | Weight of the diamond (0.2 – 5.01 ct) |
| `cut` | Ordinal | Quality of the cut: Fair → Good → Very Good → Premium → Ideal |
| `color` | Ordinal | Diamond color grade: D (colorless/best) → J (noticeable color/worst) |
| `clarity` | Ordinal | Diamond clarity: I1 (inclusions/worst) → IF (internally flawless/best) |
| `depth` | Float | Total depth percentage = z / mean(x, y) |
| `table` | Float | Width of top of diamond relative to widest point (%) |
| `x` | Float | Length in mm |
| `y` | Float | Width in mm |
| `z` | Float | Depth in mm |
| `price` | Int | **Target**: Price in USD ($326 – $18,823) |

---

## Methodology

1. **Data Cleaning**: Identified and removed records with physically impossible zero dimensions
   and extreme outliers in `y` and `z` (58 rows removed, 0.1% of dataset).

2. **Exploratory Data Analysis (EDA)**:
   - Univariate distributions for all numeric features
   - Log-transformation of the right-skewed price target
   - Bivariate scatter plots with trend lines and Pearson correlations
   - Full correlation heatmap with ordinal-encoded categorical features
   - Categorical feature distribution counts for Cut, Color, and Clarity
   - Price distribution boxplots by each quality grade
   - Simpson's Paradox analysis: carat weight as a confounding variable
   - IQR-based outlier analysis for all numeric features

3. **Feature Engineering**: Ordinal encoding of Cut, Color, and Clarity using natural
   gemological ordering.

4. **Baseline Model**: Linear Regression with log-transformed price target, StandardScaler
   normalization, and 80/20 train/test split.

---

## Results

### Key Findings

1. **Carat is the dominant predictor** (r = 0.92). Physical dimensions (x, y, z) are
   near-perfectly correlated with carat and are largely redundant.

2. **Simpson's Paradox in quality grades**: Lower color and clarity grades appear to command
   higher raw prices because these grades are disproportionately assigned to *larger* diamonds.
   Controlling for carat reveals the expected quality premium.

3. **Depth and Table are weakly correlated with price** (r ≈ −0.01 and −0.19 respectively),
   suggesting these proportional measurements have minimal standalone predictive power.

4. **Log transformation yields a near-normal price distribution** (skewness reduced from 1.62
   to 0.38), which is preferred for linear modeling.

5. **Ideal cut is the most common grade** (39.9% of diamonds), while Fair cut is the rarest
   (3.0%).

### Baseline Model Performance

| Metric | Value |
|--------|-------|
| R² (log-price) | ~0.92 |
| RMSE | ~$1,100 |
| MAE | ~$740 |

The baseline Linear Regression explains ~92% of variance in log-transformed diamond prices,
establishing a strong benchmark for advanced models.

---

## Next Steps

1. **Non-Linear Models**: Implement Random Forest and Gradient Boosting (XGBoost/LightGBM)
   to capture non-linear interactions, especially between carat and quality grades.
2. **Feature Engineering**: Create `volume = x * y * z`, polynomial carat terms, and
   carat × clarity interaction features.
3. **k-Fold Cross-Validation**: Use 5-fold CV for robust performance estimates.
4. **Hyperparameter Tuning**: Apply GridSearchCV for tree-based models.
5. **SHAP Analysis**: Apply SHAP values to explain individual predictions.
6. **Market Segmentation**: Cluster diamonds by carat/quality profile to identify distinct
   market segments.
7. **Price Recommendation Tool**: Build an interactive Streamlit app for real-time price
   estimation.

---

## Outline of Project

- [**capstone_EDA.ipynb**](capstone_EDA.ipynb) — Full EDA and baseline modeling notebook
- [**figures/**](figures/) — All generated visualization figures
- [**README.md**](README.md) — Project summary and findings

---

## References

- Wickham, H. (2016). *ggplot2: Elegant Graphics for Data Analysis.* Springer.
  (Source of the Diamonds dataset)
- GIA (Gemological Institute of America). *The 4Cs of Diamond Quality.*
  https://www.gia.edu/gia-about/4Cs
- Pedregosa et al. *Scikit-learn: Machine Learning in Python.* JMLR 12, pp. 2825-2830, 2011.

---

*Capstone Assignment 20.1 | UC Berkeley Professional Certificate in ML & AI*


# Multiple Linear Regression – Multi-Channel Marketing Analysis

## Project Overview

This project analyzes a multi-channel marketing dataset to determine how **TV**, **Radio**, **Social Media**, and **Influencer** spend jointly affect **Sales**. Using Python and `statsmodels`, a Multiple Linear Regression model is built, checked for multicollinearity, refined, validated against core regression assumptions, and interpreted to produce a data-driven marketing budget recommendation.

## Dataset Description

The dataset (`marketing_sales_data.csv`) contains 572 records with the following columns:

| Column | Type | Description |
|---|---|---|
| `TV` | Categorical | Spend tier: Low / Medium / High |
| `Radio` | Numeric | Radio advertising spend |
| `Social Media` | Numeric | Social media advertising spend |
| `Influencer` | Categorical | Influencer tier: Nano / Micro / Macro / Mega |
| `Sales` | Numeric | Target variable — sales revenue |

No missing values were present in the dataset.

## Analysis Goals

- Detect and address multicollinearity among predictors using a correlation matrix and Variance Inflation Factor (VIF)
- Encode categorical variables (TV, Influencer) as dummy variables
- Build a Multiple Linear Regression model using `statsmodels`
- Evaluate the model using Adjusted R-squared and individual predictor p-values
- Refine the model by removing statistically insignificant predictors
- Validate model assumptions (Linearity, Normality, Homoscedasticity) using diagnostic plots
- Interpret coefficients in business terms, holding other variables constant
- Deliver a prioritized, evidence-based marketing budget recommendation

## Key Findings

- **TV spend category** is the strongest driver of Sales — High TV spend produces the largest predicted Sales relative to the other categories
- **Radio** spend has a smaller but statistically significant positive effect on Sales
- **Social Media** and **Influencer tier** were not statistically significant once TV and Radio were accounted for, and were dropped from the refined model
- No problematic multicollinearity was detected among retained predictors (all VIF values were low)
- **Recommendation:** Prioritize TV advertising at the High spend tier, with Radio as a secondary investment. Deprioritize Social Media and Influencer marketing pending further targeted testing.

## Repository Contents

| File | Description |
|---|---|
| `multiple_regression_analysis.ipynb` | Jupyter Notebook with full analysis — EDA, multicollinearity check, OLS model, diagnostics, and business interpretation |
| `marketing_sales_data.csv` | Dataset used for the analysis |
| `README.md` | Project overview and setup instructions |

## Environment Setup

This project requires Python 3.8+ and the following libraries:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy
```

## How to Run

1. Clone this repository:
   ```bash
   git clone <your-repo-url>
   cd <repo-folder>
   ```
2. Install the required dependencies (see above)
3. Ensure `marketing_sales_data.csv` is in the same directory as the notebook
4. Open `multiple_regression_analysis.ipynb` in Jupyter Notebook, JupyterLab, or VS Code
5. Run all cells in order (Run All)

## Methodology Summary

1. **Data Exploration** – Loaded and inspected the dataset; confirmed no missing values
2. **Encoding** – One-hot encoded `TV` and `Influencer` categorical variables
3. **Multicollinearity Check** – Used a correlation matrix and VIF to confirm predictors were not problematically correlated
4. **Model Building** – Fit a full OLS regression model with all predictors using `statsmodels`
5. **Model Refinement** – Removed statistically insignificant predictors (p ≥ 0.05) to produce a cleaner final model
6. **Model Validation** – Verified assumptions using residual plots, a Q-Q plot, and a scale-location plot
7. **Business Interpretation** – Converted statistical output (Adjusted R², coefficients, p-values) into a marketing budget recommendation

## Author

Happy Oluwafemi Odole

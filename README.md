# Part 3: Regression-Based Business Insights & Model Interpretation
**Student:** Harsh Verma | **ID:** bitsom_ba_25111060 | **Module:** 6

---
## Business Problem
A retail chain is looking to understand which factors influence monthly sales performance across its stores, in order to inform decisions around marketing, inventory, staffing, and pricing.

## Tools Used
Python (numpy, pandas, openpyxl, matplotlib), Excel, Claude AI

## Dataset
- **File:** business_regression_data.xlsx | **Rows:** 320 | **Columns:** 14
- **Dependent variable:** `monthly_sales`
- **Independent variables:** marketing_spend, footfall, avg_discount_pct, inventory_availability_pct, customer_rating, staff_count, competitor_distance_km, holiday_flag
- **Categorical:** region (East, North, South, West), store_type (Airport, High Street, Mall, Residential)

## Regression Approach
1. Simple OLS regression run separately for each numeric predictor (5 models in total)
2. A multiple OLS regression combining the 5 numeric predictors with region and store_type dummy variables

## Dummy Variable Approach
- Reference region: `East` (excluded to avoid multicollinearity)
- Reference store type: `Airport` (excluded)
- Each dummy coefficient represents the difference relative to its reference category, with all other variables held constant

## Model Comparison Summary
| Model | R² |
|-------|-----|
| Simple: marketing_spend | 0.1672 |
| Simple: footfall | 0.7363 |
| Simple: avg_discount_pct | 0.0083 |
| Simple: inventory_availability_pct | 0.0131 |
| Simple: customer_rating | 0.0008 |
| **Final Multiple Model** | **0.8321** |

## Final Model Selected
The multiple OLS model, incorporating all numeric predictors plus region and store_type dummies, was selected as the final model. R² = 0.8321.

## Business Recommendation
- Treat marketing spend and footfall as the primary levers to increase
- Give priority to the regions identified as top performers via dummy coefficients
- Approach discounting strategically, since it erodes margin
- Refer to `outputs/final_recommendation.md` for the complete write-up

## Assumptions & Limitations
- OLS relies on the assumptions of linear relationships and homoscedastic errors
- Correlation does not imply causation — controlled experiments would be needed to establish causal impact
- A sample of 320 rows is moderate in size, so results should be interpreted as directional rather than definitive

## Screenshots
- `screenshots/simple_regression_output.png` — Scatter plots from the simple regression models
- `screenshots/multiple_regression_output.png` — Coefficient table from the multiple regression model
- `screenshots/residuals_preview.png` — Residuals vs. fitted values, along with their distribution
- `screenshots/model_comparison_preview.png` — Comparison of R² values across all models

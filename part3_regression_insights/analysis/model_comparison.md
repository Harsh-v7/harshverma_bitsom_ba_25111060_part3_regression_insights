# Model Comparison — Part 3: Regression Analysis

| Model | Variables | R² | Significant Vars | Business Use |
|-------|-----------|-----|------------------|--------------|
| Model 1: marketing_spend | monthly_sales ~ marketing_spend | 0.1672 | marketing_spend | Low — single predictor |
| Model 2: footfall | monthly_sales ~ footfall | 0.7363 | footfall | Low — single predictor |
| Model 3: avg_discount_pct | monthly_sales ~ avg_discount_pct | 0.0083 | None | Low — single predictor |
| Model 4: inventory_availability_pct | monthly_sales ~ inventory_availability_pct | 0.0131 | inventory_availability_pct | Low — single predictor |
| Model 5: customer_rating | monthly_sales ~ customer_rating | 0.0008 | None | Low — single predictor |
| **Final Model** | All 5 numerics + dummies | **0.8321** | marketing_spend, footfall, region dummies | **High — actionable** |


## Why the Final Multiple Model is Best
- An R² of 0.8321 indicates the model accounts for 83.2% of the variance in monthly_sales — a substantial improvement over any of the single-variable models.
- It brings together both continuous predictors (marketing spend, footfall) and categorical context (region, store_type).
- The dummy variables let leadership compare store performance across regions and store types while controlling for other factors.

## Limitations
- OLS assumes linear relationships, so non-linear effects (such as diminishing returns on marketing spend) go uncaptured.
- There's a possibility of multicollinearity between footfall and marketing_spend.
- The model doesn't account for time trends, meaning seasonality isn't fully reflected.

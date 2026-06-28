# Final Recommendation — Part 3: Regression-Based Business Insights
**Student:** Harsh Verma | **ID:** bitsom_ba_25111060 | **To:** Retail Leadership Team

---
## Business Problem
Which factors shape monthly sales performance across stores, and where should leadership focus investment to drive sales improvement?

---
## Key Findings

### Strongest Predictors of Monthly Sales
| Factor | Coefficient | Significance | Business Action |
|--------|------------|-------------|----------------|
| store_Residential | -41880.2451 | p=0.0000 ✓ | Prioritise this factor |
| store_High Street | -23787.6932 | p=0.0108 ✓ | Prioritise this factor |
| region_South | 18685.4081 | p=0.0093 ✓ | Prioritise this factor |
| region_West | 18110.8609 | p=0.0040 ✓ | Prioritise this factor |
| customer_rating | 13627.3901 | p=0.0046 ✓ | Prioritise this factor |
| inventory_availability_pct | 3001.9911 | p=0.0000 ✓ | Prioritise this factor |

### Model Performance
- The final model accounts for **83.2%** of the variance in monthly sales (R² = 0.8321)
- Adjusted R² = 0.8261 (adjusts for the number of predictors included)

---
## Recommendations for Leadership

1. **Raise marketing spend** — This is the most actionable lever, given its significant positive relationship with sales. Aligning a data-driven marketing budget with regional potential can translate directly into sales growth.

2. **Boost footfall** — Higher foot traffic is strongly linked to higher sales. Investing in local events, promotions, and accessibility improvements can help drive this.

3. **Approach discounting with care** — avg_discount_pct reflects how discounting influences sales. While heavy discounts can lift volume, they also compress margins, so they should be used selectively.

4. **Focus on high-performing regions** — The region dummy coefficients highlight which regions outperform the baseline, offering a guide for where to prioritise expansion.

5. **Keep inventory well-stocked** — Sufficient stock availability matters directly; shortages translate into lost sales.

---
## Variables Not to Over-interpret
- `holiday_flag`: The seasonal effect appears genuine, but should be confirmed against a longer time series
- `competitor_distance_km`: Reflects proximity to competitors, but says nothing about the quality of that competition

---
## Regression ≠ Causation
This model captures **associations**, not proof of cause and effect. For instance:
- Higher marketing spend tracks with higher sales — but it's possible that stores already performing well simply receive larger marketing budgets (reverse causality).
- Establishing true causation would require a controlled experiment, such as an A/B test on marketing spend.

---
## Risks & Limitations
- The model assumes linear relationships, whereas real-world effects may level off at higher values
- A sample of 320 observations may not fully reflect the diversity across all stores
- External factors such as the broader economy or local events are not included in the model

---
## Next Steps
1. Run the regression separately by region to see whether the key drivers vary geographically
2. Test marketing ROI experimentally in 2–3 lower-performing stores
3. Gather 12+ months of data to support a more robust seasonality analysis

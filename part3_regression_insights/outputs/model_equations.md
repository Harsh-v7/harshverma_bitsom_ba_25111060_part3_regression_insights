# Model Equations — Part 3
**Student:** Harsh Verma | **ID:** bitsom_ba_25111060

---
## Simple Regression Equations

**Model 1: marketing_spend**
```
monthly_sales = 560777.35 + 2.1296 × marketing_spend
R² = 0.1672 | P-value = 0.000000
```
*For every ₹1 rise in marketing spend, monthly sales are expected to shift by ₹2.1296.*

**Model 2: footfall**
```
monthly_sales = 446410.58 + 35.6780 × footfall
R² = 0.7363 | P-value = 0.000000
```
*Each extra customer visit corresponds to an additional ₹35.6780 in monthly sales.*

---
## Multiple Regression Equation

```
monthly_sales = 91793.05
  + 1.2004 × marketing_spend
  + 34.0032 × footfall
  - 45708.5494 × avg_discount_pct
  + 3001.9911 × inventory_availability_pct
  + 13627.3901 × customer_rating
  + 6184.5087 × region_North
  + 18685.4081 × region_South
  + 18110.8609 × region_West
  - 23787.6932 × store_High Street
  - 12794.0786 × store_Mall
  - 41880.2451 × store_Residential
```
R² = 0.8321 | Adjusted R² = 0.8261

---
## Dummy Variable Explanation
- **Reference region:** `East` — every region dummy is measured against this baseline
- **Reference store type:** `Airport` — every store_type dummy is measured against this baseline
- For example: a `region_North` coefficient of +50,000 would mean stores in North bring in ₹50,000 more per month than East stores, with all else held equal.

---
## Final Model Selected
**Multiple Regression with 5 numeric predictors + region + store_type dummies**

### Reason
- Delivers the highest R² (0.8321) of any model tested
- Contains statistically significant predictors (marketing_spend, footfall)
- Incorporates business-relevant categorical context (region, store_type)
- Is actionable: leadership has direct levers to pull — increasing marketing_spend or footfall — to drive sales

---
## Coefficient Interpretations (Business Language)

| Variable | Coefficient | Meaning |
|----------|------------|---------|
| marketing_spend | +1.2004 | ✓ Significant — holding other factors constant |
| footfall | +34.0032 | ✓ Significant — holding other factors constant |
| avg_discount_pct | -45708.5494 | Not significant — holding other factors constant |
| inventory_availability_pct | +3001.9911 | ✓ Significant — holding other factors constant |
| customer_rating | +13627.3901 | ✓ Significant — holding other factors constant |
| region_North | +6184.5087 | Not significant — holding other factors constant |
| region_South | +18685.4081 | ✓ Significant — holding other factors constant |
| region_West | +18110.8609 | ✓ Significant — holding other factors constant |
| store_High Street | -23787.6932 | ✓ Significant — holding other factors constant |
| store_Mall | -12794.0786 | Not significant — holding other factors constant |
| store_Residential | -41880.2451 | ✓ Significant — holding other factors constant |

# Taxi Fare Analysis by Company

This project explores how fare structures differ across four major ride-hailing companies—**Uber, Lyft, Via, and Juno**—using New York City trip data.

---

## Objective

To compare how each taxi company charges fares per mile by analyzing the relationship between **trip distance** and **fare amount**.  
The goal is to identify the most cost-efficient company and understand differences in fare variability.

---

## Methods

### Data Preprocessing

- Loaded and cleaned `.parquet` files from **Kaggle**
- Extracted key columns such as:
  - `trip_miles`
  - `base_passenger_fare`, `tolls`, `sales_tax`, `congestion_surcharge`, `airport_fee`, `tips`
- Calculated `total_amount` by summing all fare components (excluding tips)

### Company Mapping

Mapped `hvfhs_license_num` codes to their respective company names:
HV0002 → Juno
HV0003 → Uber
HV0004 → Via
HV0005 → Lyft


### Modeling

- Trained both **Linear Regression** and **Random Forest Regressor** models for each company
- Predicted `total_amount` based on `trip_miles`
- Evaluated models using:
  - **R² score**
  - **RMSE (Root Mean Squared Error)**
- Used Linear Regression to extract interpretable metrics:
  - **Slope** (cost per mile)
  - **Intercept** (base fare)

### Visualization

- **Boxplots**: Compared fare distributions across companies
- **Regression plots**: Visualized trends in fare by distance
- **Actual vs. Predicted** scatter plots: Assessed model performance by company

---

## Key Insights

- **Via** had the lowest cost per mile, followed by **Uber**, **Lyft**, and **Juno**
- However, **Via** and **Uber** showed relatively lower R² scores, suggesting greater variability in fare patterns
- **Via’s trips are concentrated around shorter distances**, which should be considered when interpreting pricing policies

---

## Future Improvements

- Increase the amount of training data
- Analyze fare trends over time (e.g., monthly/yearly)
- Perform statistical comparisons between companies for more robust insights




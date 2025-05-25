# Taxi Fare Analysis: NYC Ride-Hailing Companies

This is a simple analysis of how four major ride-hailing services — Uber, Lyft, Via, and Juno — charge fares in New York City.  
The focus is on understanding how fare relates to trip distance and how consistent each company is in its pricing.

---

## Project Goals

- Compare how fare increases with distance across companies  
- Estimate cost per mile and base fare using linear regression  
- Try a non-linear model (random forest) to see if predictions can be improved  
- Visualize and summarize patterns that stand out

---

## Data

The data comes from public NYC trip records (Kaggle).  
Key variables used in this project:

-  trip_miles : trip distance  
- Fare components:  
   base_passenger_fare ,  tolls ,  sales_tax ,  congestion_surcharge ,  airport_fee   
- Tips were excluded

All fare-related columns (excluding tips) were summed into a single  total_amount  column for modeling.

Companies were identified by  hvfhs_license_num :

 HV0002 - Juno    
 HV0003 - Uber    
 HV0004 - Via     
 HV0005 - Lyft    

---

## Modeling

Two models were tested for each company:

1. **Linear Regression** — just to get a sense of base fare and cost per mile  
2. **Random Forest Regressor** — to see if we can better capture variation

Both models used  trip_miles  to predict  total_amount .

Performance was evaluated using:
- R² (explained variance)
- RMSE (root mean squared error)

---

## Plots and Visuals

- **Boxplots** show fare distribution differences between companies  
- **Regression lines** highlight how fare changes with distance  
- **Actual vs. predicted plots** check model fit

---

## What Stood Out

- **Via** had the lowest cost per mile, followed by Uber, Lyft, and Juno  
- But Via (and also Uber) showed lower R² scores → fares were less predictable  
- Via mostly handled short-distance rides, which might explain some of the variation


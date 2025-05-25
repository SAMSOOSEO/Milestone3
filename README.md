Taxi Fare Analysis by Company
This analysis investigates how fare structures differ across four major ride-hailing companies—Uber, Lyft, Via, and Juno—using trip data from New York City.

Objective
The aim of this project is to examine how each company sets fares relative to trip distance.
Specifically, we compare cost per mile and evaluate how consistently each company applies its fare structure, with the broader goal of identifying the most cost-effective provider.

Methods
Data Preparation
Raw .parquet files were sourced from Kaggle and cleaned for analysis.

Key variables included:

trip_miles

Fare components such as base_passenger_fare, tolls, sales_tax, congestion_surcharge, and airport_fee (excluding tips).

A new column total_amount was computed by summing the relevant fare elements.

Company Identification
The variable hvfhs_license_num was mapped to company names as follows:
HV0002 → Juno
HV0003 → Uber
HV0004 → Via
HV0005 → Lyft

Modeling Approach
Two models were applied for each company:

Linear Regression for interpretability (cost per mile and base fare)

Random Forest Regressor for improved fit

Both models used trip_miles as input to predict total_amount.

Evaluation metrics included:

R² score (explained variance)

RMSE (root mean squared error)

Visualization
Boxplots to compare fare distributions across companies

Regression lines to observe fare trends by distance

Actual vs. Predicted scatter plots to assess model performance

Key Findings
Via offered the lowest average cost per mile, followed by Uber, Lyft, and Juno.

That said, Via and Uber had noticeably lower R² scores, implying more variability in their fare patterns.

It’s worth noting that Via’s trips were mostly short-distance, which may influence the observed pricing trend.

Future Directions
Expand the dataset to include more records for better model generalization

Explore how fares evolve over time (monthly or yearly trends)

Use statistical testing to formally compare fare structures between companies


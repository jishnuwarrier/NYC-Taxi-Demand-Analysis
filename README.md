# NYC Taxi Demand Forecasting

## Project Overview

This project builds a machine learning system to predict hourly taxi demand across NYC's 265 taxi zones using PySpark to process 17 million Yellow Taxi trip records from September through November 2023. The pipeline transforms raw trip data into zone-hour aggregations, engineers 35 features including temporal patterns, weather conditions, and lag variables, then trains three models (Linear Regression, Random Forest, Gradient Boosted Trees) to forecast demand. Random Forest performed best with an R² of 0.947 and average error of just 7.88 trips per zone-hour, showing that taxi demand is primarily driven by recent historical patterns combined with time and location context. The project demonstrates Big Data engineering practices including distributed processing with Spark, proper time-series handling to prevent data leakage, and scalable feature engineering using window functions. One key finding: the model's heavy reliance on recent demand lags (which provide 80% of predictive power) makes it excellent for short-term predictions but limits its usefulness for advance planning. For real operational deployment, you'd want separate medium-term models that exclude recent lags and rely more on weekly patterns and weather forecasts instead.

---

**Tech Stack:** PySpark, MLlib, Pandas, Matplotlib, Seaborn  
**Dataset:** 17M Yellow Taxi trips (Sept-Nov 2023)  
**Best Model:** Random Forest (R² = 0.947, MAE = 7.88 trips)

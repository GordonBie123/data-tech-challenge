# Flight Traffic Analysis & Prediction Model

## Overview
This project analyzes historical flight data from Australian airports (1985-1989) to build a predictive model for passenger traffic and provide strategic recommendations for route optimization.

## Data
- **Source**: `cleaned_flight_data.csv` 
- **Records**: ~10,000 monthly passenger counts
- **Routes**: International flights from Australian cities to foreign destinations
- **Key Metrics**: Passengers In/Out, Total Passengers, Freight, Mail

## Approach

### 1. Data Exploration
- Identified top routes by total passenger volume
- Found Sydney-Auckland as the busiest route (2.96M passengers)
- Discovered clear seasonal patterns and growth trends

### 2. Model Selection
We chose time series models over machine learning because:
- Passenger traffic is temporally dependent (next month depends on previous months)
- Strong seasonal patterns exist (holiday peaks, summer increases)
- Historical trends matter for forecasting

**Models tested:**
- **Exponential Smoothing**: Captures level, trend, and seasonal components
- **SARIMA**: Handles complex autocorrelations and seasonal patterns

### 3. Model Evaluation
- Used 6-month holdout test set for validation
- Selected best model based on Mean Absolute Error (MAE)
- Achieved ~4.5% error rate on major routes

### 4. Predictions
- Generated 12-month forecasts for passenger traffic
- Included 95% confidence intervals
- Exported predictions to CSV for operational use

## Key Findings

**High-Performance Routes:**
1. Sydney-Auckland: 2.96M passengers
2. Sydney-Singapore: 1.44M passengers  
3. Perth-Singapore: 953K passengers

**Model Performance:**
- Error rate: <5% on high-traffic routes
- Successfully captures seasonal patterns
- Reliable for 6-month predictions, acceptable for 12-month

## Recommendations

**Invest in:**
- High-volume hub connections (Singapore, Auckland)
- Underserved markets with growth potential (Perth routes)

**Scale back:**
- Routes with consistently low traffic (<100 passengers/month)
- Redundant routes with strong competition

**Operational Use:**
- Monthly reforecasting for capacity planning
- Dynamic pricing based on demand predictions
- Monitor forecast accuracy to maintain <5% error

## Cleaned Data
https://docs.google.com/spreadsheets/d/1_YqAoDysbQGPME3kYHcxe9MHI4kszHl3gpFby-Vrt7g/edit?usp=sharing

# AI-Assisted Time Series Modeling of Drug Overdose Death Rates

## Overview
This project analyzes historical drug overdose death rate data in the United States using AI-assisted statistical modeling and forecasting techniques. 
The goal was to transform semi-structured XML data into an analysis-ready time series, model trends, evaluate behavior, and forecast future overdose death rates.

The project demonstrates strong data engineering, statistical modeling, and responsible AI usage.

---

## Data Source
Drug overdose death rate data was obtained from:

https://catalog.data.gov/dataset/drug-overdose-death-rates-by-drug-type-sex-age-race-and-hispanic-origin-united-states-3f72f

For modeling consistency, the analysis focused on:
- All Ages
- All Drug Overdose Deaths

---

## Key Skills Demonstrated
- XML data parsing and transformation
- Exploratory data analysis and statistical testing
- Time series modeling using ARIMA
- Volatility modeling using ARCH and GARCH
- Forecasting with confidence intervals
- Validated AI-assisted analytical workflow

---

## Workflow Summary

### Data Preparation
- Parsed XML data using Python
- Cleaned and converted string-based values into numeric time series format
- Structured yearly overdose death rate observations

### Exploratory Analysis
- Created correlation heatmap and performed Pearson correlation testing
- Confirmed statistically significant increasing overdose trend over time
- Conducted stationarity testing using the Augmented Dickey-Fuller test

### Time Series Modeling
- Built ARIMA models to capture trend and temporal dynamics
- Compared ARIMA(1,1,1) and ARIMA(2,1,1)
- Selected ARIMA(2,1,1) based on statistical tests and model fit

### Volatility Modeling
- Detected heteroskedasticity in ARIMA residuals
- Modeled volatility using ARCH and GARCH models
- Selected standard GARCH due to improved AIC and stronger volatility persistence modeling

### Forecasting
- Generated 5-year overdose death rate forecasts using:
  - ARIMA for mean predictions
  - GARCH for time-varying uncertainty (volitality)
  - 
---

## Technologies Used
- Python
- pandas
- NumPy
- Matplotlib
- statsmodels
- arch
- xml.etree.ElementTree

---

## AI Literacy
AI tools were used to assist with coding, workflow development, and documentation. All AI-assisted outputs were independently verified for statistical correctness, data integrity, and modeling validity.

---

## Author
**Olivia Rueschhoff**  
Master of Science in Mathematics  
Bachelor of Science in Mathematics (Data Science & Statistics)  
Minor: Computer Science – Algorithms & Data Structures

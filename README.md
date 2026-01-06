# AirFly Insights: Data Visualization and Analysis of Airline Operations (2015)

**Student:** Geethika Buridi  
**Dataset:** US Airline Flight Delays 2015 (Kaggle) – 5.81 million flights  
**Project Duration:** [Your Semester/Year]

## Project Objective
Analyze large-scale US airline flight data to uncover operational trends, delay patterns, and cancellation reasons using data visualization techniques. The goal is to understand airline and airport-level performance and provide actionable insights for passengers and operators.

## Dataset
- Source: Kaggle US Flight Delays 2015
- Contains 5.81 million domestic flight records with 31 columns

## Milestone-Wise Work & Deliverables

### Milestone 1: Data Foundation and Cleaning (Week 1–2)
**Work Done:**
- Loaded raw data and merged airline/airport mappings for readable names
- Memory optimization: Reduced from ~6 GB to 1.3 GB using int8, category dtypes
- Feature Engineering: Created ROUTE, DEP_HOUR, FLIGHT_DATE, MONTH_NAME, DAY_NAME, IS_DELAYED (>15 min delay)
- Handled cancelled/diverted flights by filling delay/time columns with 0
- Mapped cancellation reason codes to readable labels (e.g., "Bad Weather")
- Created SEASON column for seasonal analysis

**Deliverables:**
- `flights_milestone1_final.pkl` – Cleaned & optimized dataset
- `feature_dictionary.csv` – Description of all features

### Milestone 2: Visual Exploration and Delay Trends (Week 3–4)
**Work Done:**
- Univariate Analysis: Top airlines, routes, flights by day/hour/month, delay distribution
- Bivariate Analysis: Delay % by airline, U-curve (delay by hour), delay vs distance
- Delay Cause Analysis: Total delay minutes by cause, top delay-prone airlines

**Deliverables:**
- 12+ visualizations (bar, line, scatter, histogram)
- Insights on flight volume, delay patterns, and airline performance

### Milestone 3: Route, Cancellation, and Seasonal Insights (Week 5–6)
**Work Done:**
- Cancellation Analysis: Overall rate, by month, season, reason, airline
- Seasonal Trends: Proved winter has 3× higher cancellation rate
- Route & Airport-Level: Top routes, busiest airports, interactive maps (delay & cancellation by airport)

**Deliverables:**
- Interactive Plotly maps (delay & cancellation by airport)
- Heatmaps (cancellation day vs month/season)
- Seasonal validation of delay/cancellation spikes

### Milestone 4: Final Report and Presentation (Week 7–8)
**Work Done:**
- Combined all visualizations into coherent storyline
- Created Streamlit interactive dashboard
- Prepared slide deck and final report

**Deliverables:**
- `airfly_dashboard.py` – Live interactive dashboard
- Presentation slides (PPT)
- This README + full documentation

## Key Insights
- Southwest dominates flight volume; Hawaiian & Alaska most punctual
- Late aircraft (not weather) is #1 delay cause
- U-curve: Early morning least delays, evening maximum
- Winter has 3× higher cancellation rate
- ORD, ATL, DFW cause >50% of total delay minutes

## Actionable Recommendations
- **Passengers:** Book Hawaiian/Alaska + early morning + Saturday + non-winter months
- **Airlines:** Improve aircraft turnaround + winter preparation

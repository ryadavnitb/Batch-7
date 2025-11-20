# AirFly Insights - Airlines Flight Data Analysis

A comprehensive data analysis project examining U.S. domestic flight operations in 2015, focusing on delays, cancellations, and operational patterns to derive actionable business insights.

---

## Project Overview

This project analyzes 5.8 million flight records from 2015, integrating data from airlines, airports, and flight operations to understand:
- Flight delay patterns and root causes
- Cancellation trends and reasons
- Seasonal and temporal variations
- Airline and route performance
- Operational efficiency metrics

---

## Milestone 1: Data Preparation & Exploratory Analysis 

### Completed Tasks

#### 1. Data Integration
- Merged three datasets: airlines.csv, airports.csv, and flights.csv
- Combined 5.8M flight records with airline names and airport information
- Created unified dataset with origin/destination details
- Final shape: 5,819,079 rows × 38 columns

#### 2. Data Cleaning
- Handled missing values in delay columns (filled with 0)
- Processed cancellation data (1 = cancelled, 0 = not cancelled)
- Removed duplicate records
- Standardized data types and formats

#### 3. Feature Engineering
Created 7 new features for enhanced analysis:
- FLIGHT_DATE: Complete date field
- DAY_NAME: Day of week (Monday-Sunday)
- MONTH_NAME: Full month names
- ROUTE: Origin → Destination pairs
- TOTAL_DELAY: Sum of all delay types
- IS_DELAYED: Binary indicator (>15 min)
- DEPARTURE_HOUR: Hour of scheduled departure (0-23)

#### 4. Univariate Analysis
Analyzed individual variables:
- Top Airlines: Identified highest-volume carriers
- Busiest Airports: Top 10 origin and destination hubs
- Temporal Patterns: Monthly and daily flight distributions
- Cancellation Rate: 1.5% industry-standard cancellation rate
- Delay Distribution: Right-skewed with median 15-30 min
- Departure Times: Bimodal peaks at 6-8 AM and 5-7 PM

#### 5. Bivariate Analysis
Explored relationships between variables:
- Airline Performance: Delay rates and average delays by carrier
- Delay Causes: Late aircraft (50%+), weather (15%), airline issues (28%)
- Seasonal Trends: June/December show highest delays
- Weekly Patterns: Thursday/Friday worst, Saturday best
- Hourly Analysis: 5-6 AM best, 6-7 PM worst
- Distance Impact: Mid-range flights (1500-2000 mi) most delayed
- Top Routes: Identified 10 busiest corridors

#### 6. Statistical Validation
- Central Limit Theorem: Verified sample means follow normal distribution
- Enables confident statistical inference despite skewed data
- Supports future hypothesis testing and predictive modeling

---

## Dataset Information

### Files
- airlines.csv: Airline codes and names (14 carriers)
- airports.csv: Airport details with IATA codes (322 airports)
- flights.csv: 5.8M flight records with delays, cancellations, and operations data
- flight_cleaned.csv: Cleaned and enriched dataset (output)

### Key Metrics
| Metric | Value |
|--------|-------|
| Total Flights | 5,819,079 |
| Cancellation Rate | 1.5% (89,884 flights) |
| Cancelled Flights | 89,884 |
| Average Delay | 4.8 minutes |
| Delayed Flights (>15 min) | ~40% |
| Airlines Analyzed | 14 major carriers |
| Airports Covered | 322 U.S. airports |
| Time Period | January - December 2015 |

---

## Key Insights Summary

### Delays
- Best time to fly: 5-6 AM (average 12 min early arrival)
- Worst time to fly: 6-7 PM (average 16 min late)
- Best day: Saturday (lowest delay rate)
- Worst days: Thursday/Friday (delays accumulate through week)
- Best month: September (mild weather, less traffic)
- Worst months: June (thunderstorms) and December (holiday congestion)

### Root Causes
- Late Aircraft Delays: 50%+ (cascading effect from previous flights)
- Weather Delays: 15% (uncontrollable but predictable seasonally)
- Airline Issues: 28% (controllable - maintenance, crew scheduling)
- Air System: 15% (ATC and airport infrastructure)
- Security: <3% (rare but necessary)

### Distance Patterns
- Short flights (<500 mi): Affected by taxi/gate delays
- Mid-range (1500-2000 mi): Highest delays (~9 min avg)
- Long flights (2000+ mi): Better performance (built-in recovery time)

---

## Technologies Used

- Python 3.x
- Libraries:
  - pandas: Data manipulation and analysis
  - numpy: Numerical computing
  - matplotlib: Data visualization
  - seaborn: Statistical graphics
  - scipy: Statistical analysis (CLT verification)

---

## Business Implications

### For Airlines
1. Operational Focus: Improve aircraft turnaround efficiency (biggest delay driver)
2. Scheduling: Add 10-15 min buffer to June/December and 1500-2000 mi flights
3. Maintenance: Schedule during low-traffic months (Feb, Sept)
4. Marketing: Highlight on-time performance if competitive (>75% on-time)

### For Passengers
1. Best booking: Saturday departures, 5-7 AM flights, September travel
2. Connection planning: 60+ min buffer for peak hours/months
3. Critical meetings: Book early morning flights (arrive early on average)

### For Airports
1. Resource allocation: Maximum staffing 6-8 AM and 5-7 PM
2. Gate management: More capacity needed for hub operations
3. Infrastructure: Focus investments on top 10 busiest airports

---

## Next Steps (Milestone 2)

### Planned Activities
1. Advanced Statistical Analysis
   - Hypothesis testing (airline comparisons)
   - ANOVA for multi-group comparisons
   - Correlation analysis

2. Predictive Modeling
   - Flight delay prediction models
   - Cancellation risk assessment
   - Route optimization

3. Deep Dive Analysis
   - Airport-specific performance
   - Airline head-to-head comparisons
   - Weather impact quantification
   - Cost analysis (delay costs, cancellation impact)

4. Interactive Visualizations
   - Dashboard development
   - Geospatial analysis
   - Time-series forecasting

---

## Author

Benadict Infant A

---

## Project Timeline

- Milestone 1: Data Preparation & EDA - Completed
- Milestone 2: Advanced Analysis & Modeling - Upcoming
- Milestone 3: Dashboard & Reporting - Planned

---

## License

This project is created for educational and analytical purposes.

---

## Acknowledgments

- Dataset source: U.S. Department of Transportation (2015 flight data)
- Analysis framework: Pandas, NumPy, Matplotlib, Seaborn
- Inspiration: Real-world aviation operations optimization

---

Last Updated: November 20, 2025

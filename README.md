
# AirFly Insights: US Flight Delay Analysis

## Hypothesis Testing & Statistical Validation

This project includes rigorous hypothesis testing to uncover statistically significant patterns in US flight delays and cancellations. Below are the key hypothesis tests performed, their results, and actionable insights:

### Seasonal & Holiday Flight Patterns

**Test 1: Winter vs Summer Arrival Delays**
- **Null Hypothesis (H₀):** Winter delays = Summer delays (no seasonal effect)
- **Alternative Hypothesis (H₁):** Winter delays ≠ Summer delays
- **Result:**
  - Winter: 1,378,389 flights, Mean delay = 6.46 min
  - Summer: 1,535,151 flights, Mean delay = 6.75 min
  - Difference: -0.29 min
  - p-value: < 0.000001 (rounded as 0.000000)
  - **Conclusion:** Winter has significantly different delays than summer. Airlines should allocate extra buffer time in winter schedules.

**Test 2: Winter vs Summer Cancellation Rates**
- **Null Hypothesis (H₀):** Winter cancellation rate = Summer cancellation rate
- **Alternative Hypothesis (H₁):** Winter cancellation rate > Summer cancellation rate
- **Result:**
  - Winter: 40,562 cancelled out of 1,378,389 (2.94%)
  - Summer: 18,978 cancelled out of 1,535,151 (1.24%)
  - p-value: < 0.000001 (rounded as 0.000000)
  - **Conclusion:** Winter cancellation rate is significantly higher. Passengers should consider travel insurance for winter flights.

**Test 3: Holiday Period vs Regular Day Delays**
- **Null Hypothesis (H₀):** Holiday delays = Regular day delays
- **Alternative Hypothesis (H₁):** Holiday delays > Regular day delays
- **Result:**
  - Holiday periods: 434,962 flights, Mean delay = 7.42 min
  - Regular days: 5,384,117 flights, Mean delay = 4.08 min
  - p-value: < 0.000001 (rounded as 0.000000)
  - **Conclusion:** Holidays have significantly higher delays. Booking earlier flights during holidays is recommended.

**Test 4: Correlation Between Weather Delay and Arrival Delay**
- **Null Hypothesis (H₀):** No correlation between weather delay and arrival delay
- **Alternative Hypothesis (H₁):** Positive correlation exists
- **Result:**
  - Correlation coefficient: 0.2777 (weak positive correlation)
  - Sample size: 2,086,896 flights
  - p-value: < 0.000001 (rounded as 0.000000)
  - **Conclusion:** Weather delay is positively correlated with arrival delay, but other factors also contribute.

#### Key Findings & Business Recommendations
- Winter vs Summer delay difference: 0.3 minutes
- Winter cancellation rate is 2.4x higher than summer
- Holiday periods show elevated delays
- **Recommendations:**
  1. Add schedule padding for winter flights
  2. Recommend travel insurance for December-February travel
  3. Staff extra crew during holiday peak periods


## Project Overview
This project delivers a comprehensive, step-by-step analysis of US domestic flight operations for the year 2015, focusing on delay and cancellation patterns, operational bottlenecks, and statistical validation. The workflow is organized into weekly milestones, each with explicit deliverables and technical rationale. The analysis is performed in Python using pandas, numpy, matplotlib, and seaborn, with all code and outputs documented in a Jupyter notebook.

## Data Sources and Preparation
- **Raw Datasets:**
  - `airlines.csv`: Contains airline IATA codes and full names for mapping carrier identities.
  - `airports.csv`: Includes airport IATA codes, names, cities, and states for both origin and destination mapping.
  - `flights.csv`: The main dataset with 5,819,079 flight records, including scheduled and actual times, delays, cancellations, and cause codes.
- **Data Loading:**
  - All datasets are loaded using pandas, with explicit path handling and memory optimization for large files.
- **Merging:**
  - Flights are merged with airline and airport metadata using IATA codes, resulting in a unified DataFrame with readable names and locations for all flights.
  - Both origin and destination airport details are joined, with suffixes to distinguish columns.
- **Cleaning:**
  - Duplicate rows are identified and removed using sample-based and full-dataset checks.
  - Missing values in delay columns are filled with zeros (interpreted as no delay), and cancellation columns are standardized (binary flags, reason codes).
  - Data types are corrected: dates are parsed, categorical columns are set, and numerics are ensured for analysis.
- **Feature Engineering:**
  - **Date features:** Flight date, day of week, and month name extracted for temporal analysis.
  - **Route:** Concatenation of origin and destination codes to create a unique route identifier.
  - **Delay metrics:**
    - Total delay calculated as the sum of all delay components.
    - Binary delay flag (`IS_DELAYED`) set for flights with arrival delay > 15 minutes.
    - Departure hour extracted from scheduled departure time for hourly analysis.
    - Distance range binned for segmenting flights by length.
  - **Holiday/seasonal flags:** Custom logic to tag flights occurring during major US holidays and winter months for seasonal impact analysis.

## Analysis Milestones and Deliverables

### Milestone 1: Data Foundation (Weeks 1–2)
- **Week 1:**
  - Project setup: Environment configuration, library imports, and display settings for large data.
  - Data loading: Read all three datasets, print summary statistics, and validate schema.
  - Initial merging: Join flights with airline and airport metadata, drop redundant columns, and confirm final shape.
- **Week 2:**
  - Data cleaning: Remove duplicates, fill missing values, and standardize cancellation flags.
  - Outlier detection: Apply IQR method to key numeric columns, print bounds and outlier rates.
  - Feature engineering: Add all derived columns for subsequent analysis.

### Milestone 2: Exploratory and Delay Analysis (Weeks 3–4)
- **Week 3:**
  - Univariate analysis:
    - Top airlines by flight count (bar chart)
    - Top origin and destination airports (horizontal bar charts)
    - Monthly and weekday flight distributions (bar charts)
    - Cancellation rate (pie chart)
    - Delay distribution (histogram, focus on positive delays up to 95th percentile)
    - Departure time distribution (bar chart by hour)
  - Each visual is accompanied by a markdown cell with detailed insights, including interpretation of patterns, outliers, and operational context.
- **Week 4:**
  - Delay analysis:
    - Average arrival delay by airline (bar chart, top 10)
    - Total delay minutes by cause (bar chart)
    - Average delay by month (line chart)
    - Average delay by day of week (bar chart)
    - Cancellation reasons (bar chart)
    - Top 10 busiest routes (horizontal bar chart)
    - Delay rate by airline (bar chart)
    - Average delay by departure hour (line chart)
    - Correlation matrix (heatmap) for all delay and operational variables
    - Distance vs delay (bar chart by distance range)
  - Outlier detection and box plots for key delay metrics, with explicit annotation of quartiles and medians.
  - Correlation analysis includes both positive and negative relationships, with printed lists of strongest pairs.

### Milestone 3: Network, Route, and Seasonal Insights (Weeks 5–6)
- **Week 5:**
  - Route analysis:
    - Top 10 origin-destination pairs by flight count, with printed table of average delays and delay rates.
    - Airport delay bars: Top 15 origin and destination airports by average delay (side-by-side bar charts).
    - Route performance matrix: Heatmap of average delays for top 10 origin and destination airports, with annotation for best/worst routes and explanation of negative values (early arrivals).
- **Week 6:**
  - Monthly cancellation trends:
    - Dual-axis plot of total cancellations (bar) and cancellation rate (line), with printed summary table and identification of peak months.
  - Cancellation types:
    - Pie chart of cancellation reasons (Airline/Carrier, Weather, NAS, Security), with code mapping and percentage breakdown.
    - Stacked bar chart of monthly cancellations by type, showing seasonal shifts in causes.
  - Holiday and winter impact:
    - Multi-panel visualization of average delays, cancellation rates, weather delays, and holiday period comparison.
    - Printed summary of winter vs summer delay and cancellation rates.
  - Central Limit Theorem:
    - Sampling demonstration: Draw 100 samples of 30 flights each, plot population and sampling distributions, overlay theoretical normal curve, and print summary statistics (mean, std, skewness).
    - Explicit validation of CLT for delay averages, with interpretation of statistical power and inference reliability.

## Documentation and Insights
- Every visual is followed by a markdown cell with detailed insights, including:
  - What the chart measures
  - How to interpret axes, colors, and patterns
  - Key findings, anomalies, and operational implications
  - Statistical rationale where relevant (e.g., CLT, correlation)
- All business-oriented language has been removed; insights focus on data-driven analysis and technical interpretation.

## Data Export and Version Control
- The cleaned and feature-enriched dataset is saved as `data/flight_cleaned.csv` for downstream analysis or modeling.
- `.gitignore` excludes all CSV files and the `data/` folder to prevent large data from being committed.
- All code, analysis, and outputs are tracked in `main.ipynb`.

## Repository Structure
- `main.ipynb`: Complete notebook with all code, analysis, and visualizations, organized by milestone and week.
- `remove_emojis.py`: Utility script for text cleaning (if needed).
- Raw data files: `airlines.csv`, `airports.csv`, `flights.csv` (not tracked in git).
- Cleaned data: `data/flight_cleaned.csv` (not tracked in git).
- `.gitignore`: Ensures large data files and outputs are not committed.
- `README.md`: This file, documenting all project phases, methods, and deliverables.

## Technical Choices and Rationale
- **Python & pandas:** Chosen for robust data handling and analysis of large datasets.
- **Jupyter Notebook:** Enables stepwise, documented analysis with code, visuals, and narrative in one place.
- **Matplotlib & Seaborn:** Used for high-quality, customizable visualizations.
- **Feature engineering:** Custom columns allow for granular analysis of time, route, and operational factors.
- **Statistical methods:** IQR for outlier detection, correlation for variable relationships, CLT for inference validation.
- **Version control:** Git used for code and documentation, with data excluded for efficiency and privacy.

## Next Steps and Extensions
- Add predictive modeling (e.g., delay prediction, cancellation risk) using machine learning algorithms.
- Perform deeper statistical tests (e.g., hypothesis testing, regression analysis) on delay/cancellation patterns.
- Enhance visualizations with interactive dashboards (Plotly, Dash, Streamlit).
- Document additional milestones and expand analysis to multi-year or multi-country datasets.
- Collaborate with domain experts for operational recommendations or policy insights.

---

**Current Branch:** Benadict-Infant-A

For full details, see all code and outputs in `main.ipynb`. For questions, collaboration, or further analysis, please refer to this notebook and the project structure above.

![Project Banner](banner.png)
# Delivery-Performance
## Overview
This project analyzes truckload delivery performance data to validate customer claims, identify operational bottlenecks, and provide data-driven recommendations for supply chain optimization. Using Python and advanced data analytics techniques, this analysis examines over 370 delivery records to assess on-time performance, pinpoint problem locations, and diagnose root causes of delivery delays.

Key Business Questions Answered:       
Does the data support the customer's claim of 90% on-time performance?
Which delivery locations are the most problematic?
Are delivery time windows realistic for worst-performing locations?
### Business Problem
A logistics customer believes they mantain:
* 90% on-time delivery performance across their network
* Minimal delays of only "a couple of hours at most" when drivers are late

This analysis validates these claims and identifies areas for operational improvement using historical truckload data.

### 📊 Dataset Description
Data Source
* Files: 
  * sample_data1.csv
  * sample_data2.csv
  * sample_data3.csv
  * sample_data4.csv

* Records: 400 truckload deliveries
* Time Period: May 2020 - April 2021
* Geographic Coverage: Multiple origin and destination locations across the network

 Key Variables
| Variable|Description|
| --------| --------- |
| `LOAD_ID`| Unique identifier for each load |
| `ORIG` | Origin location code |
| `DEST` | Destination location code
| `PKUP_ST_DT/TM` | Proposed pickup window start (date/time)|
| `PKUP_END_DT/TM` | Proposed pickup window end (date/time) |
| `PKUP_ARRIVAL_ACT_DT/TM` | Actual pickup arrival (date/time) code |
| `PKUP_DEPARTURE_ACT_DT/TM` | Actual pickup departure (date/time) |
| `DLVERY_ST_DT/TM` | Proposed delivery window start (date/time) |
| `DLVERY_END_DT/TM` | Proposed delivery window end (date/time) |
| `DLVERY_ARRIVAL_ACT_DT/TM` | Actual delivery arrival (date/time) |
| `DLVERY_DEPARTURE_ACT_DT/TM` | Actual delivery departure (date/time) |
| `MILEAGE` | Total miles for the route |

### Technologies & Tools
Programming Language
Python 3.8+

Libraries Used:
* pandas          # Data manipulation and analysis
* numpy           # Numerical computations
* matplotlib      # Data visualization
* seaborn         # Statistical data visualization
* datetime        # Date and time handling

Development Environment
- Jupyter Notebook - Interactive data analysis and visualization

### 📁  Project Structure

```text
supply-chain-analysis/
│
├── data/
│   └── sample_size.csv              # Raw dataset
│
├── notebooks/
│   └── supply_chain_analysis.ipynb  # Main analysis notebook
│
├── visualizations/
│   ├── on_time_performance.png      # Performance charts
│   ├── problem_locations.png        # Location analysis
│   └── diagnostic_results.png       # Diagnostic test results
│
├── README.md                        # Project documentation
└── requirements.txt                 # Python dependencies
```

### Analysis Methodology

**1. Data Preprocessing**

* Load and inspect raw CSV data
* Convert date/time strings to datetime objects
* Handle missing values and data quality issues
* Create calculated fields for analysis

**2. Performance Metrics Calculation**

(python)
##### Key metrics calculated:
- Delivery delay (hours) = Actual arrival - Window end time
- On-time status = True if delay ≤ 0
- Pickup dwell time = Departure time - Arrival time

**3. Statistical Analysis**

* Descriptive Statistics: Mean, median, standard deviation of delays
* Percentage Analysis: On-time performance rates by location
* Trend Analysis: Performance over time (monthly trends)
* Variability Analysis: Standard deviation of delays by location

**4. Diagnostic Testing**

Simulated optimal delivery scenario:

* Driver arrives at pickup window start
* Dwell time = 90th percentile by origin
* Travel speed = 40 mph constant
* Calculate if windows are achievable

### 📈 Key Findings
#### Question 1: Overall Performance Validation

###### On-Time Performance

* Actual Performance: 75% on-time

* Customer Claim: 90% on-time

* Conclusion: ❌ Claim Not Supported

###### Delay Analysis (for late deliveries)

* Average Delay: 15.3 hours (25.0%)

* Maximum Delay: 8824 hours

* Customer Claim: "Couple of hours at most"

* Conclusion: ❌ Claim Not Supported



#### Question 2: Problem Locations Identified

##### Bottom 5 Destinations by On-Time Performance

Rank | Destination | On-Time % | Total Loads |
| :--- | :--- | :---: | :---: |
|1|    499477|    0.0%|     11|
|2|    906049|    14.3%|   14|
|3| 1288141| 16.7%| 12|
|4|  594983|20.0%| 20|
|5| 971635| 25.0%| 20|


##### Top 5 Most Unpredictable Destinations
Rank |	Destination	| Std Dev (hours)|	Avg Delay|
| :--- | :--- | :---: | :---: |
|1|	1012707	| 1513.75	| 257.21 |
|2|	53363 |	766.84	| 77.90
|3|	1302285 |	525.75 |	[-73.65]
|4|	1284775 |	450.80 |	[-92.27]
|5|	2061913 | 425.49 |	[-80.78]

#### Question 3: Diagnostic Test Results

##### Worst Performing Location: Destination [499477]

Current On-Time Rate: 0.0%

Feasibility with Optimal Execution: 100.0%
Average Time Difference: -2.83 hours

Conclusion: Windows are ✅ Realistic. Most loads could meet the window with optimal execution.

📊 ### Visualizations

**1. On-Time Performance Dashboard**

Performance Dashboard Four-panel visualization showing overall performance, delay distribution, monthly trends, and day-of-week analysis

**2. Problem Location Analysis**

Problem Locations Comparison of worst-performing and most unpredictable delivery destinations

**3. Diagnostic Test Results**

Diagnostic Results Distribution analysis showing window feasibility for the worst-performing location





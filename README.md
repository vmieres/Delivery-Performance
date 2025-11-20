# Delivery-Performance
## Overview
This project analyzes truckload delivery performance data to validate customer claims, identify operational bottlenecks, and provide data-driven recommendations for supply chain optimization. Using Python and advanced data analytics techniques, this analysis examines over 60,000 delivery records to assess on-time performance, pinpoint problem locations, and diagnose root causes of delivery delays.

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

* Records: 60,000 truckload deliveries
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








# iitg-summer-analytics-capstone-project

🚗 Smart Urban Parking: Dynamic Pricing Models using Pathway
This project was developed as part of the Summer Analytics 2025 Capstone and focuses on building dynamic pricing models for urban parking systems using real-time data streams.

📌 Objective
To implement pricing models that respond to occupancy, demand, traffic, and competitive conditions using real-time data, powered by the Pathway framework for streaming data.

✅ Models Implemented
Model 1 – Occupancy-Based Linear Pricing
Adjusts price based on occupancy ratio.

Stateless: pricing resets at each time window.

Used 30-minute tumbling windows.

Implemented successfully using Pathway reducers and UDFs.

Model 2 – Demand-Based Dynamic Pricing
Incorporates additional features:

QueueLength

TrafficConditionNearby

IsSpecialDay

VehicleType

Computes a demand score and adjusts base price proportionally.

Successfully implemented with UDFs and time-based aggregation in Pathway.

⚠️ Model 3 – Competitive Pricing (Not Completed)
Intended to compare prices between nearby lots and adjust accordingly.

Required spatial self-joins and competitor-aware pricing adjustments.

Due to complexity in join mechanics, absence of LotID, and execution timeout issues, I was not able to fully complete Model 3.

The base logic was partially written using haversine() distance and self-joins, but pipeline execution remained unresolved.

📉 Visualization (Bokeh Plotting - Not Working)
Attempted to visualize price vs time using Bokeh and Panel.

Despite using Pathway’s .plot() method and custom Bokeh functions:

Ran into issues like KeyError: 't'

Possible root causes: schema mismatch or streaming rendering issues in Colab.

Therefore, plots could not be generated during this project phase.

🛠 Tools & Frameworks Used
Pathway: core streaming data framework (real-time windowing, joins, UDFs)

NumPy, Pandas: used for intermediate testing, file inspection

Python 3.11 on Google Colab

Attempted Bokeh + Panel for visualization (unsuccessful)

📁 Dataset Fields
Timestamp, Occupancy, Capacity

QueueLength, TrafficConditionNearby

IsSpecialDay, VehicleType

Latitude, Longitude (for Model 3)

📄 File Outputs
model1_prices.csv – output of Model 1

model2_prices.csv – output of Model 2

model3_prices.csv – (partially functional / incomplete)

🙏 Acknowledgements
This work was done under the mentorship of the Summer Analytics 2025 team and was an excellent introduction to real-time data processing using the Pathway ecosystem.

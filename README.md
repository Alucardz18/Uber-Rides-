# :car: Uber Ride Data Analysis 🚙
This project performs exploratory data analysis (EDA) and visualization on a dataset of Uber rides. It includes data cleaning, feature engineering, categorical encoding, and a variety of plots to uncover insights about ride purpose, timing, and distance.

# Tools and Technologies 🛠️

This project was developed using a hybrid approach, leveraging the strengths of both Python for data manipulation and Power BI for final dashboard creation.

| Tool | Purpose | Key Libraries / Components |
| :--- | :--- | :--- |
| **Python 🐍** | Data Cleaning, Feature Engineering, Transformation, and Advanced Visualization. | Pandas, Matplotlib, Seaborn, Scikit-learn (sklearn) |
| **Power BI 📊** | Interactive Data Visualization, Dashboard Design, and Sharing of Final Insights. | Power Query (M Language)|

# Dataset Description 📋
A sample of Uber ride data with the following columns:
| Column Name  | Description                           | Type     | Nulls |
|--------------|----------------------------------------|----------|-------|
| START_DATE   | Ride start timestamp                  | object   | No    |
| END_DATE     | Ride end timestamp                    | object   | Yes   |
| CATEGORY     | Business or personal ride             | object   | Yes   |
| START        | Starting location                     | object   | Yes   |
| STOP         | Destination                           | object   | Yes   |
| MILES        | Distance of the ride in miles         | float64  | No    |
| PURPOSE      | Purpose of the ride (e.g., Meeting)   | object   | Yes   |

# Features Engineered :hammer_and_wrench:
- date and time extracted from START_DATE
- day-night: time-of-day classification (Morning, Afternoon, Evening, Night)
- MONTH: mapped month label from date
- DAYS: mapped weekday name from date

  # 🔑 Key Findings from Uber Rides Data Analysis
1. Trip Purpose and Category
- Primary Demand: The majority of rides were booked for business purposes.  
- Top Purposes: The most common reasons for booking a ride are for Meetings and Meal/Entertainment.  
- Correlation: The encoded Business and Personal ride categories were highly negatively correlated, which confirms that a trip is typically classified as one or the other. Other features showed little to no strong correlation.  

2. Time-Based Trends
- Peak Time of Day: The majority of trips occurred during the Afternoon (10 AM – 5 PM), suggesting peak usage during standard business hours.  
- Seasonal Drop: Ride counts were irregular across the months, but there was a distinct drop in ride frequency during November, December, and January, which the analysis attributed to winter.  

3. Distance and Usage Patterns
- Average Distance: Most cabs were booked for short distances, primarily around 4–5 miles.  
- Distance Range: The majority of all rides fell within the 0–20 miles range.  
- Long Trips: Rides exceeding 20 miles had negligible counts, indicating the service is overwhelmingly used for shorter, local travel.


# Visualization :bar_chart:
1. Categorical Distributions
    * Count of rides by CATEGORY
    * Count of rides by PURPOSE
    * Count by Day vs Night
    * Cross-distribution of PURPOSE vs CATEGORY
      
2. Heatmap of Numeric Features
    - Correlation between MILES and encoded categorical features.

3. Monthly Trends
    - Line plot showing monthly ride frequency and max miles.

4. Day of Week
    - Bar plot: Number of rides per weekday.

5. Distance Insights
    - Boxplot: Ride distances (MILES)
    - Zoomed Boxplot: Miles under 100
    - Histogram: Miles under 40
  
# Data Preprocessing ⚙️
- Missing PURPOSE values replaced with 'Unknown'
- Converted START_DATE and END_DATE to datetime
- Dropped rows with nulls or duplicates

# Encoding 💻
Used OneHotEncoding to convert categorical variables CATEGORY and PURPOSE into numeric features for correlation analysis.

# License 📃
This project is for educational and personal learning purposes.

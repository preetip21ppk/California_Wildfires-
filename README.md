# California Wildfires Analysis and Prediction

## 🌲 Project Overview
Wildfires have become an increasing concern in California, with studies showing that forest soils can take up to 80 years to recover from fire disturbances. Over the past seven years, California has lost more than 4,000 acres of forest land due to wildfires. This project aims to **analyze the trends and impacts of wildfires**, focusing on how **weather conditions** and **human factors** contribute to their occurrence and severity.

The analysis combines historical wildfire data with weather and geographical features to uncover patterns and build predictive insights. The framework is scalable and can be extended to other states prone to wildfires.

---

## 🧾 Problem Statement
To investigate:
- How weather conditions (temperature, precipitation, wind speed) influence wildfire occurrences.
- The extent to which human negligence and environmental factors amplify wildfire risks.

The goal is to provide actionable insights and predictive modeling that support fire management and prevention strategies.

---

## 🗂️ Resources

**Data Sources**
- Kaggle wildfire dataset  
- California government open data  
- Historical weather data (via API)  
- Geographical coordinates  

**Tools & Technologies**
- **Data Analysis:** Python, Pandas, Seaborn  
- **Database:** PostgreSQL (`wildfire_db`)  
- **Visualization:** Tableau, Seaborn  
- **Machine Learning:** Scikit-learn (Logistic Regression)

---

## 📊 Dataset Description
The dataset includes **1,636 records** of wildfire occurrences in California between **2013–2020**.  
Each record contains:
- **Core attributes:** Archive year, Fire name, County, Acres burned  
- **Additional features:** Latitude, Longitude, Structures damaged, Injuries, Weather data  

---

## 🔍 Exploratory Data Analysis (EDA)

### Data Preprocessing Steps
1. **Data Loading:** Imported data using Pandas and retrieved additional weather data through APIs.  
2. **Duplicate Removal:** Consolidated records across sources to ensure accuracy.  
3. **Null Value Handling:** Replaced or dropped missing entries based on column relevance.  
4. **Data Enrichment:** Filled missing weather values via API calls.  
5. **Merging Datasets:** Combined all relevant data frames using `pandas.merge()` for a unified dataset.  
6. **Statistical Summary:** Generated descriptive statistics to understand key data distributions.

---

## 🧮 Database Design
Data was stored in a **PostgreSQL** relational database (`wildfire_db`) using **SQLAlchemy** and **psycopg2** for Python connectivity.  
The schema includes four primary tables representing wildfire incidents, weather data, geographical information, and damage statistics.

---

## 📈 Data Analysis Highlights

### 🔥 Fires vs. Temperature
- Higher wildfire frequency observed from **June to August**, aligning with peak summer temperatures.  

### 🌧 Fires vs. Precipitation
- Most wildfires occurred during **low precipitation months**, emphasizing the impact of dry conditions.  

### 📦 Weather Patterns
- Box plots revealed significant variation in temperature and wind speed, with expected outliers due to California’s extreme weather.

---

## 🤖 Machine Learning Predictive Analysis

### Model Objective
Predict whether a **major fire** could occur based on historical weather data.

**Major Fire Definition:**  
A fire with **maximum temperature ≥ 32°C** and **acres burned > 1000**.

### Model Selection: Logistic Regression
**Reasons:**
- Binary target variable (Major Fire / Not Major Fire)  
- Simplicity, interpretability, and strong performance on small datasets  

### Features and Target
- **Features:** Month of fire, Maximum temperature, Wind speed, Precipitation  
- **Target:** Major Fire (binary)  
- **Encoding:** Label encoding for categorical features  

### Training & Evaluation
- Data split using `train_test_split()` with stratified sampling (random_state=42)  
- **Accuracy:** 71%  
- **Recall (for major fires):** 81%  
- **Confusion Matrix:** Minor false negatives due to skewed weather data  

### Key Insights
- Strong correlation between high temperatures and wildfire likelihood  
- Logistic regression performed well, though performance could improve with more diverse data

---

## 🧠 Model Evaluation

**Advantages:**
- Simple and efficient  
- Works well with smaller datasets  
- Low overfitting risk in low-dimensional data  

**Limitations:**
- Linear decision boundaries  
- Struggles with non-linear patterns  
- Performance limited by dataset size (California-only data)

---

## 📊 Dashboard & Visualization

### Seaborn (Python)
Used for:
- Scatter plots of fires vs. temperature/precipitation  
- Box plots for weather variable analysis  
- Correlation heatmaps

### Tableau
Developed an **interactive dashboard** with:
- **California Wildfire Map:** County-wise fire spread (latitude/longitude-based)
- **Cause of Fire Map:** Distribution of fire causes (human, lightning, unidentified)
- **Monthly Temperature vs. Fire Chart:** Seasonal trends in wildfire frequency
- **Top Counties Donut Chart:** Highest total acres burned by county

---

## 🧩 Summary
This project integrates historical wildfire and weather data to build a **data-driven predictive model** for California wildfires.  
While the model’s accuracy is moderate, the methodology demonstrates how **machine learning and data visualization** can assist decision-makers in proactive wildfire management.

---

## 🚀 Project Execution Plan
1. Load and preprocess data using Python and APIs  
2. Store structured data in PostgreSQL  
3. Perform EDA and visualize relationships  
4. Train Logistic Regression model and evaluate performance  
5. Build interactive Tableau dashboard  

---

## 🧰 Technologies Used
| Category | Tools |
|-----------|--------|
| Language | Python |
| Data Analysis | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Database | PostgreSQL, SQLAlchemy |
| Visualization | Seaborn, Tableau |
| API | OpenWeatherMap (for weather data) |

---

## 💡 Future Scope
- Expand dataset to include other states  
- Integrate satellite imagery and vegetation data  
- Explore non-linear models (e.g., Random Forest, XGBoost) for better predictions  


**⭐ This repository demonstrates how data-driven methods can guide environmental protection and wildfire management through predictive analytics and visualization.**

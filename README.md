# ✈️ Flight Price Prediction & Analysis (Python, ML, Stats)

This project integrates **data science, machine learning, and statistical modeling** to analyze flight ticket pricing and predict fares with high accuracy.  
It explores **seasonality trends, busiest routes, airline strategies, and the main drivers of pricing.**

---

## 🔎 Research Questions & Findings

### 1. Ticket Price Distribution
- **Base Fare** ranges: `8,856 – 85,722 BDT`  
- **Taxes & Fees** range: `200 – 17,513 BDT`  
- **Total Fares** range: `9,603 – 103,801 BDT`  

👉 **Outliers** (e.g., fares over `449,000 BDT`) skew averages upward, leading to overestimated revenue and poor pricing insights.  
👉 After removing extreme outliers, fares fall into realistic ranges → insights become more **reliable**.  

---

### 2. Key Factors Affecting Fares
- **Base Fare** → Correlation with total fare = `0.9985` (strongest driver).  
- **Tax & Surcharge** → Correlation = `0.9827` (heavy impact).  
- **Stopovers** → Higher fares vs. direct flights.  
- **Class** → Premium cabins ≈ **3x economy fares**.  
- **Seasonality** → Peak months & holidays increase fares significantly.  

📌 **Business Actions**:
- Adjust base fare with **demand & seasonality**.  
- Offer **surcharge discounts** in off-peak months.  
- Differentiate pricing between **direct vs. stopover flights**.  
- Segment fares by **class** to maximize revenue.  

---

### 3. Departure Date Effects
- **Day of Departure** → No major effect (`r = -0.0035`).  
- **Month of Departure** → Strong seasonal effect (peak months = higher fares).  

📌 **Action** → Focus on **monthly trends**, ignore daily fluctuations.  

---

### 4. Can Ticket Prices Be Predicted?
✅ **Yes!** — Using ML models trained on:  
- Airline, Route, Class, Stopovers  
- Seasonality (Departure Month/Day)  
- Base Fare & Surcharges  

👉 Enables **dynamic pricing strategies** for airlines.  

---

### 5. Data Types & Treatment
- **Categorical** → Encoded (Airline, Route, Class).  
- **Datetime** → Converted into Day, Month, Season.  
- **Numerical** → Scaled & analyzed with stats + ML.  

---

### 6. Descriptive Statistics (Base Fare Example)
- Mean = `58,899 BDT`  
- Median = `31,616 BDT`  
- Std Dev = `68,841 BDT` (high variability)  
- Min = `1,600 BDT`, Max = `449,222 BDT` (**outlier**)  

---

### 7. Outliers
- **Before** → Max Fare = `558,987 BDT`  
- **After Removal** → Max Fare = `245,098 BDT`  

✅ Outliers handled via **IQR method** + optional **log-transform**.  
📌 Improves **model accuracy** & stability.  

---

### 8. Feature Engineering
- Removed redundant columns → *Source Name, Destination Name*.  
- Added → *Departure_Day, Departure_Month* for demand cycle analysis.  

⚡ This **structured exploration** directly feeds into ML modeling & business recommendations.  

---

## 🛠️ Tools & Technologies Used
- **Programming & Analysis** → Python (`Pandas`, `NumPy`, `Scikit-learn`, `Statsmodels`)  
- **Data Handling** → Cleaning, preprocessing, feature engineering (IQR, log-transform, encoding, scaling)  
- **Machine Learning Models** → Linear Regression, Decision Tree, Random Forest, XGBoost  
- **Statistical Analysis** → Correlation analysis, descriptive stats, outlier detection  
- **Visualization** → `Matplotlib`, `Seaborn` (histograms, scatterplots, heatmaps, boxplots)  
- **Version Control & Collaboration** → Git, GitHub  

---

## 📊 Model Performance

| Model              | MAE        | MSE           | RMSE       | R² Score |
|--------------------|-----------:|--------------:|-----------:|---------:|
| Linear Regression  | 1099.63    | 9.48e+06      | 3079.51    | 0.9982   |
| Decision Tree      | 947.63     | 1.95e+07      | 4420.69    | 0.9963   |
| Random Forest      | 907.54     | 1.05e+07      | 3248.61    | 0.9980   |
| XGBoost            | 1043.89    | 1.04e+07      | 3226.28    | 0.9980   |

✅ All models perform with **very high accuracy (R² > 0.99)**.  
⚡ **Random Forest** & **XGBoost** give the best balance between accuracy & robustness.  

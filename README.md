# ⚡ Smart Grid Load Balancing – Energy Forecasting System

### 🧠 AI-Powered Energy Demand Forecasting for Smarter, Greener Grids

---

## 📘 Overview

This project leverages **machine learning and weather-driven forecasting** to predict **hourly electricity consumption** for smart grids.  
It helps utilities and energy operators **balance load**, **reduce costs**, and **optimize sustainability** by forecasting when energy demand will peak.

Using a **Random Forest Regressor**, the model learns patterns from **historical load data** and **weather variables** (temperature, humidity, wind speed).  
It then predicts **future hourly demand** and provides **actionable recommendations** like when to activate battery storage, shift industrial loads, or trigger demand response programs.

---

## 🎯 Objectives

- Predict **next-hour** or **daily** energy demand with high accuracy.  
- Detect **peak load hours** that could strain the grid.  
- Incorporate **real-time weather data** for more realistic predictions.  
- Provide **AI-generated operational strategies** for smart load management.  

---

## 🧩 Key Features

| Feature | Description |
|----------|-------------|
| **Machine Learning Forecasting** | Random Forest Regression predicts energy usage in MW. |
| **Time-Series Analysis** | Includes lag, rolling, and cyclical time-based features. |
| **Weather Integration** | Uses Meteostat weather data (temperature, humidity, wind speed). |
| **Peak Detection System** | Identifies 90th-percentile demand levels for overload prevention. |
| **Intelligent Recommendations** | Suggests actions like battery use, load shifting, or demand response. |
| **High Accuracy** | Achieved **R² = 0.9912**, with low MAE and RMSE. |
| **Deployment-Ready** | Packaged with trained model, input pipeline, and confidence intervals. |

---

## 🧮 Data & Model

### 📊 Dataset  
Source: [PJME Hourly Energy Consumption – Kaggle](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption/data)

The dataset includes hourly energy consumption data (in MW) for the **PJM East** region of the U.S., spanning several years.

### 🌦️ Weather Data
Fetched from **Meteostat API**, which provides historical hourly weather data (temperature, humidity, wind speed) for the region.

### ⚙️ Features Used
- **Time-based:** hour, day of week, month, weekend flag, holiday season  
- **Lag features:** 1-hour, 24-hour, and 168-hour (weekly) lags  
- **Rolling stats:** 24-hour & 168-hour mean and standard deviation  
- **Weather:** temperature, humidity, wind speed, and 6-hour rolling averages  
- **Cyclical encodings:** sine/cosine transforms for hour and month  

---

## 🧠 Machine Learning Model

| Algorithm | Random Forest Regressor |
|------------|-------------------------|
| Libraries  | Scikit-learn |
| Input Data | Engineered time-series + weather features |
| Target     | Energy demand (MW) |
| Accuracy   | **R² = 0.9912** |
| MAE / RMSE | *Very low (exact values from evaluation cell)* |

---

## 📊 Visual Insights

The notebook includes comprehensive visualizations:
- **Energy demand over time**
- **Hourly and monthly usage patterns**
- **Energy vs. temperature correlation**
- **Actual vs. Predicted forecasts**
- **Feature importance rankings**

These help in understanding energy behavior and validating model performance.

---

## ⚡ Load Balancing Recommendations

After forecasting, the system performs **peak demand analysis** and provides recommendations:

| Condition | Recommended Action |
|------------|--------------------|
| Peak lasts ≥ 4 hours | 🔋 Deploy battery storage & ⚡ Activate demand response |
| Avg. demand > 110% threshold | 🏭 Shift industrial loads to off-peak hours |
| Peaks last ≥ 2 hours | 💡 Trigger time-of-use pricing alerts |

These actions help grid operators maintain **stability**, **reduce costs**, and **ensure energy reliability**.

---

## 🧮 Sample Output

```
🎯 Load Balancing Analysis:
Identified 383 peak demand periods

Peak Period 4:
  Duration: 14 hours
  Average demand: 48008 MW
  Excess over threshold: 7409 MW

🔧 Recommended Actions:
 - Deploy battery storage systems
 - Activate demand response programs
 - Implement time-of-use pricing alerts
 - Consider industrial load shifting
```

```
🔮 Next-Hour Prediction:
Predicted demand: 37,792 MW
Peak hour: No
Confidence interval: 36,593 – 38,991 MW
```

---

## 🧰 Tech Stack

| Category | Tools / Libraries |
|-----------|-------------------|
| Language | Python |
| ML | scikit-learn |
| Data | Pandas, NumPy |
| Visualization | Matplotlib |
| Weather | Meteostat |
| Environment | Jupyter Notebook |
| Model Storage | Pickle |
| Future UI | Streamlit / Flask |

---

## 🧱 Project Structure

```
Smart_Grid_Load_Balancing/
│
├── notebooks/
│   └── Smart_Grid_Load_Balancing_Notebook.ipynb
├── models/
│   └── smart_grid_model.pkl
├── data/
│   └── PJME_hourly.csv
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 🧭 How to Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/<your-username>/Smart_Grid_Load_Balancing.git
   cd Smart_Grid_Load_Balancing
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Open Notebook**
   ```bash
   jupyter notebook notebooks/Smart_Grid_Load_Balancing_Notebook.ipynb
   ```

4. **Run All Cells**
   The notebook will:
   - Train the model  
   - Generate weather-merged data  
   - Predict next-hour demand  
   - Display load balancing insights  

---

## 📦 Deployment (Optional)

To deploy as a web app:
- Use **Streamlit** for an interactive dashboard  
- Or **Flask** for an API-based backend  

Example entry:  
```bash
streamlit run app.py
```

---

## 📈 Performance Metrics

| Metric | Value |
|---------|-------|
| **R² Score** | 0.9912 |
| **MAE** | (insert) |
| **RMSE** | (insert) |
| **MAPE** | (insert) |

---

## 🔮 Future Enhancements
- Integrate live weather feeds from OpenWeather API.  
- Add short-term (24-hour) rolling forecasts.  
- Develop Streamlit dashboard for visualization.  
- Include real-time alert system for grid operators.  

---

## 👨‍💻 Author
**Parv Joshi**  
_Data Science & Smart Energy Systems Enthusiast_  
📍 India  
💼 [GitHub Profile](https://github.com/Parvjoshi)

---

## 🪪 License
This project is licensed under the **MIT License** — feel free to use, modify, and distribute with credit.

---

## ⭐ Acknowledgements
- [Kaggle – PJME Dataset](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)  
- [Meteostat – Weather Data API](https://dev.meteostat.net/)  
- [scikit-learn Documentation](https://scikit-learn.org/stable/)

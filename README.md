# Decentralization of Energy Using Solar Batteries

We can’t solve the climate challenge unless we solve for energy — and decentralization is the key.  
This project explores the integration of **rooftop PV (solar)** and **battery storage** to minimize annual energy bills while enabling grid stability, using **machine learning for forecasting**.

---

## 📌 Problem Statement
For a site with rooftop PV and time-of-use tariffs (energy + demand charges), we optimize battery sizing and dispatch strategy to:
- Use PV locally (minimize curtailment).
- Shave monthly peaks to lower demand charges.
- Optionally earn revenue by providing grid services (reg-up/reg-down).
- Apply ML forecasting for next-day solar generation & load consumption.

---

## 🎯 Objectives
- Reduce annual cost of energy usage.
- Optimize self-consumption of solar energy.
- Explore different dispatch strategies (PV-only, PV+Grid, PV+Grid+Services, Load Shifting).
- Identify best-performing battery size and operational mode.

---

## 🔑 Key Concepts
- **Energy Charge (₹/kWh):** Cost per imported kWh (varies by TOU period).  
- **Demand Charge (₹/kW):** Monthly fee based on the single highest import hour.  
- **Curtailment:** Wasted PV when battery is full.  
- **Degradation Cost:** Battery wear cost (₹/kWh throughput).  
- **Grid Services:** Payments for being available to help balance supply/demand.  
- **Arbitrage:** Charge during cheap TOU, discharge during peak TOU.  
- **Headroom:** Margin before hitting demand peak.

---

## 📊 Exploratory Data Analysis (EDA)
- **Deficit vs Surplus Hours:** 5,531 deficit vs 3,253 surplus.  
- **Solar Peak:** 9H–16H.  
- **Load Peak:** 17H–21H.  
- **Weekdays > Weekends** in load.  
- **Seasonal Trends:** Jan–Jun > 50% solar contribution; Sept–Dec load dominates.  

---

## ⚡ Strategies & Results

<img width="2495" height="1403" alt="image" src="https://github.com/user-attachments/assets/6f353a85-ab6a-4d7b-9dce-39ebf50dd453" />

👉 **Best configuration:** 300 kWh battery with PV + Service + Shift → ~72% of baseline cost.

---

## 🧠 Forecasting with Machine Learning
- Models used: **Linear Regression** & **Random Forest**.  
- Random Forest outperformed:  
  - Load Forecast: R² = 0.84  
  - PV Forecast: R² = 0.977, nMAPE = 2.18%  
- Used **Masked MAPE** to avoid night-time zero distortions.

---

## 📦 Scaling to Microgrids
- Shared batteries across multiple households.  
- Collective ML forecasting for demand and generation.  
- Real-time optimization for community-level benefits.  
- Export surplus energy to the grid for revenue.  

---

## 🛠️ Tech Stack
- **Python** (ML + optimization)  
- **Scikit-learn** (Random Forest, Regression)  
- **Pandas/Numpy** (EDA)  
- **Matplotlib/Seaborn** (Visualization)  

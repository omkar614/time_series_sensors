# Predictive Maintenance for Aircraft Engines  
_Time Series Analysis • Sensor Data • Machine Learning_

## 📌 Project Overview

Unexpected engine failures lead to significant financial loss, downtime, and safety risks.  
This project focuses on **predicting engine degradation and imminent failure** using multivariate time-series sensor data collected over operational cycles.

The objective is to:
- Understand sensor behavior over engine life
- Design interpretable health indicators
- Build baseline predictive models
- Provide early-warning failure signals

This project demonstrates **end-to-end predictive maintenance workflow**, from data quality checks to modeling and evaluation.

---

## 🗂 Dataset Description

Each row represents an engine at a given operational cycle.

**Main dataset columns:**
- `id` – Engine identifier
- `cycle` – Operating cycle number
- `setting1, setting2, setting3` – Operational settings
- `s1` to `s21` – Sensor measurements (temperature, pressure, speed, etc.)

**Derived variables:**
- **RUL (Remaining Useful Life)** – Number of cycles remaining before failure
- **Near Failure Label** – Binary indicator for imminent failure window

The dataset contains multiple engines with **varying lifetimes**, making it suitable for degradation analysis.

---

## 🧠 Project Approach

### 1️⃣ Data Quality & Validation
- Checked for duplicate `(id, cycle)` pairs
- Verified monotonic cycle progression per engine
- Identified and removed low-variance sensors
- Validated engine lifetimes and failure points

### 2️⃣ Exploratory Data Analysis (EDA)
- Analyzed sensor trends across engine life
- Compared sensor behavior between healthy and near-failure states
- Identified sensors with strong degradation signals

### 3️⃣ Health Indicator Engineering
- Rolling statistics (mean, standard deviation)
- Trend / slope features per sensor
- Composite **health score** summarizing degradation
- Feature consistency ensured across train and test data

### 4️⃣ Modeling Approaches

#### 🔹 Linear Regression (RUL Prediction)
- Predicts remaining cycles before failure
- Evaluated using Mean Absolute Error (MAE)

#### 🔹 Logistic Regression (Early-Warning Classification)
- Predicts near-failure risk
- Evaluated using Precision, Recall, ROC-AUC

#### 🔹 ARIMA (Time-Series Baseline)
- Univariate sensor forecasting
- Used for interpretable degradation trend analysis
- Stationarity verified using ADF test

---

## 📊 Model Performance Summary

| Model | Objective | Key Result |
|-----|---------|-----------|
| Linear Regression | RUL Prediction | MAE ≈ **32 cycles** |
| Logistic Regression | Failure Alert | Precision **0.89**, Recall **0.83** |
| ARIMA(1,1,1) | Sensor Forecast | Statistically valid, interpretable trends |

**Key Insight:**  
Prediction accuracy is highest near failure, which is operationally the most critical region.

---

## 📈 Visual Outputs

- True vs Predicted RUL scatter plot
- Failure risk progression over engine cycles
- ROC curve for classification model
- ARIMA sensor forecast illustrating degradation

These plots validate both **model correctness** and **interpretability**.

---

## 🛠 Project Structure


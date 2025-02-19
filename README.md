### **🚀 Time Series Forecasting with Air Passenger Data! ✈️📊**  

## **📌 Problem Statement**  
The goal was to predict the number of passengers traveling each month, helping airlines **anticipate demand trends**. The dataset had two features:  
📅 **Month** – Time period  
👥 **Passengers** – Number of travelers per month  

## **📊 What is Time Series Forecasting?**  
Time series analysis involves analyzing **past data over a fixed time duration** to forecast future trends. It’s different from general **prediction**, as forecasting specifically considers **time as a crucial factor**.  

💡 **Prediction vs. Forecasting:**  
🔹 **Prediction** – Estimates an outcome based on data, without necessarily considering time.  
🔹 **Forecasting** – A special type of prediction that analyzes **time-series patterns** to project future values.  

## **🔍 Key Components of Time Series**  
📈 **Trend** – The overall upward/downward movement over time.  
🔁 **Seasonality** – Repetitive patterns at specific intervals (e.g., more flights during holidays).  
♻️ **Cyclic Behavior** – Irregular fluctuations over long intervals (e.g., aviation trends affected by global events).  

## **📉 Making Time Series Data Stationary**  
To build an effective forecasting model, the data must be **stationary** (i.e., stable over time):  
✔️ Constant **mean**  
✔️ Constant **variance**  
✔️ No dependency on time for **auto-covariance**  

To check stationarity, I used:  
📊 **Rolling Statistics** – Moving averages to visually inspect stability.  
🧪 **Augmented Dickey-Fuller (ADF) Test** – A statistical test where:  
   - **p-value > 0.05** → Time series is **non-stationary**  
   - **p-value < 0.05** → Time series is **stationary**  

## **📌 ARIMA Model: Why It Didn't Work? 🤔**  
I first implemented **ARIMA (AutoRegressive Integrated Moving Average)**, which combines:  
🔹 **AutoRegression (AR)** – Uses past values to predict future values.  
🔹 **Moving Average (MA)** – Models dependencies between observations.  
🔹 **Differencing (I)** – Makes the series stationary.  

Despite tuning the **P, D, Q** hyperparameters, ARIMA struggled to **capture seasonality** in the data, leading to **less accurate forecasts**.  

## **🌟 Switching to SARIMA: A Better Approach!**  
To improve accuracy, I implemented **SARIMA (Seasonal ARIMA)**, which extends ARIMA by accounting for **seasonality** using additional parameters:  
📆 **P, D, Q** – Regular ARIMA components  
❄️ **Seasonal (P, D, Q, m)** – Seasonal lags and differencing  

💡 **Why SARIMA?**  
✅ Captures both **trend & seasonality**  
✅ Better accuracy on **test data**  
✅ Successfully forecasted **passenger traffic for the next 5 years!**  

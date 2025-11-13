# 📊 NVDA LSTM Model — Stock Direction Forecasting using Deep Learning

This project investigates the use of a Long Short-Term Memory (LSTM) network to forecast weekly price direction for NVIDIA (NVDA).
Beyond model development, this project emphasizes **failure analysis, error diagnostics,** and **root-cause investigation.**


## 🔍 Overview
- **Objective:** Predict whether NVDA’s closing price will increase (1) or decrease (0) the following week.  
- **Data Source:** Weekly OHLCV data collected via yfinance, enriched with technical indicators:
  - SMA20, SMA50, SMA200
  - MACD, Signal Line, Histogram
  - RSI  
- **Approach:**
  1. Data preprocessing and feature engineering (MACD, RSI, SMA indicators)
  2. Sequence creation for time-series input (20-week lookback)
  3. Training a stacked LSTM model with dropout regularization
  4. Evaluation using accuracy, ROC-AUC, and confusion matrix


## 🧠 Model Architecture
- Two stacked **LSTM** layers (64 and 32 units)  
- **Dropout (0.2)** to reduce overfitting  
- **Dense (sigmoid)** output for binary classification  
- Optimizer: **Adam**  
- Loss function: **Binary Crossentropy**


## 📈 Results Summary
- The LSTM achieved **~34% test accuracy**, showing the **difficulty of capturing weekly stock direction** using only technical indicators.  
- Results highlight the **non-linear and volatile nature** of financial time-series data.  
- Future work could explore:
  - Incorporating **GRU** or **Transformer** architectures  
  - Adding **sentiment or macroeconomic features**  
  - Using **ensemble or hybrid models** for improved stability  


## 🧰 Tools & Libraries
- Python 🐍  
- TensorFlow / Keras  
- Pandas & NumPy  
- Scikit-learn  
- Matplotlib  
- yfinance  


## 📚 Learning Outcomes
This project demonstrates the **data mining workflow** — from data understanding to model evaluation.  
It provides hands-on insight into:
- The challenges of **machine learning-based financial forecasting**
- The role of **feature engineering and data scaling**
- The importance of **realistic performance evaluation** rather than chasing accuracy.


### ✍️ Author
**Nur Hidayah Binti Abd Rahman**  
Master in Data Science*  


### 📅 Last Updated
October 2025
